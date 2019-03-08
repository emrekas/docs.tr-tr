---
title: Bir basit veri temelli CRUD mikro hizmeti oluşturma
description: Kapsayıcılı .NET uygulamaları için .NET mikro hizmet mimarisi | Basit bir CRUD (Veri odaklı) oluşturulmasını anlamak bir mikro Hizmetler uygulaması bağlamında mikro hizmet.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 01/07/2019
ms.openlocfilehash: 84ff3390912f808e6b5733049d9f0b3889576776
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57677441"
---
# <a name="creating-a-simple-data-driven-crud-microservice"></a>Bir basit veri temelli CRUD mikro hizmeti oluşturma

Bu bölümde anahatları basit bir şekilde gerçekleştirir mikro hizmet oluşturma nasıl okuma, güncelleştirme ve silme (CRUD) işlemleri veri kaynağında.

## <a name="designing-a-simple-crud-microservice"></a>Basit bir CRUD mikro hizmet tasarlama

Bir tasarım açısından bakıldığında, bu tür bir kapsayıcılı mikro hizmet çok kolaydır. Belki de sorunu çözmek için basit veya belki de yalnızca bir kavram kanıtı uygulamasıdır.

![Basit bir CRUD mikro hizmeti bir iç tasarım örüntüsüdür.](./media/image4.png)

**Şekil 6-4**. Basit CRUD mikro Hizmetleri için iç tasarım

Bu tür bir basit veri sürücüsü hizmet Kataloğu mikro hizmetine örnek uygulamadan örneğidir. Bu tür bir hizmet sınıfları veri modeliyle, kendi iş mantığı ve veri erişim kodunu içeren tek bir ASP.NET Core Web API'si projede tüm işlevlerini uygular. Ayrıca, ilgili verileri (başka bir kapsayıcı geliştirme ve test amaçları için) olarak SQL Server çalıştıran bir veritabanında depolar ancak normal herhangi bir SQL Server ana Şekil 6-5'te gösterildiği gibi de olabilir.

![Mantıksal Kataloğu mikro hizmet olabilir veya aynı Docker'da barındırma Katalog veritabanı içerir. Veritabanı aynı Docker ana bilgisayara sahip iyi geliştirme, ancak üretim için değil.](./media/image5.png)

**Şekil 6-5**. Basit veri-driven/CRUD mikro hizmet tasarım

Bu tür bir hizmet geliştirirken, yalnızca gereksinim duyduğunuz [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) ve veri erişimi API'si veya ORM [Entity Framework Core](https://docs.microsoft.com/ef/core/index). Ayrıca üretebilir [Swagger](https://swagger.io/) meta verileri otomatik olarak ile [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) ne hizmetiniz sunar, açıklaması sonraki bölümde açıklandığı gibi sağlamak için.

Tüm bağımlılıklarınızı sahip için bir Docker kapsayıcısı içinde SQL Server geliştirme ortamları için harikadır gibi bir veritabanı sunucusunu çalıştıran ve bulutta veya şirket içi bir veritabanını sağlamak zorunda kalmadan çalıştıran unutmayın. Tümleştirme testleri, bu kullanışlı olur. Genellikle bu yaklaşım sayesinde yüksek kullanılabilirlik elde ederim çünkü ancak üretim ortamları için bir veritabanı sunucusu çalıştıran bir kapsayıcıda, önerilmez. Azure'da bir üretim ortamı için Azure SQL DB veya yüksek kullanılabilirlik ve yüksek ölçeklenebilirlik sağlayabilir herhangi bir veritabanı teknolojisini kullanmanız önerilir. Örneğin, bir NoSQL yaklaşım için CosmosDB seçebilirsiniz.

Son olarak, Dockerfile ve docker-compose.yml meta veri dosyaları düzenleyerek, bu kapsayıcı görüntüsü nasıl oluşturulur yapılandırabileceğiniz — hangi temel görüntü kullanmak yanı tasarım iç ve dış adları ve TCP bağlantı noktaları gibi ayarlar.

## <a name="implementing-a-simple-crud-microservice-with-aspnet-core"></a>ASP.NET Core ile bir basit CRUD mikro hizmet uygulama

.NET Core ve Visual Studio kullanarak basit bir CRUD mikro hizmeti uygulamak için (.NET Core üzerinde bir Linux Docker konakta çalışabilecek şekilde çalışan), basit bir ASP.NET Core Web API projesi oluşturarak gösterildiği Şekil 6-6 olarak başlatın.

![Bir ASP.NET Core Web API projesi oluşturmak için öncelikle bir ASP.NET Core Web uygulaması seçin ve ardından API türü seçin.](./media/image6.png)

**Şekil 6-6**. Visual Studio'da bir ASP.NET Core Web API projesi oluşturma

Projeyi oluşturduktan sonra diğer Web API projesi içinde Entity Framework API veya diğer API'yi kullanarak yaptığınız gibi MVC denetleyicileri uygulayabilirsiniz. Yeni bir Web API projesinde, mikro hizmet üzerinde ASP.NET Core kendisini bakımından, yalnızca bağımlılık, olduğunu görebilirsiniz. Dahili olarak, içindeki *Microsoft.AspNetCore.All* bağımlılık başvurduğu Entity Framework ve diğer birçok .NET Core Nuget paketi Şekil 6-7'de gösterildiği gibi.

![API projesinin tüm gerekli paket başvuruları içeren Microsoft.AspNetCore.App NuGet paketine başvuru içerir. Bu, bazı diğer paketleri de dahil olabilir.](./media/image8.png)

**Şekil 6-7**. Basit bir Web API'sini CRUD mikro Hizmet bağımlılıkları

### <a name="implementing-crud-web-api-services-with-entity-framework-core"></a>Entity Framework Core ile uygulama CRUD Web API Hizmetleri

Entity Framework (EF) Core hafif, Genişletilebilir, ve platformlar arası sürümüne popüler Entity Framework Veri erişim teknolojisi. EF Core, .NET geliştiricilerinin .NET nesneleri kullanarak bir veritabanıyla çalışmasına imkan sağlayan bir nesne ilişkisel eşleyicidir (ORM) ' dir.

Veritabanını SQL Server Linux Docker görüntüsü için bir kapsayıcı içinde çalışmakta olduğundan katalog mikro hizmet EF ve SQL Server sağlayıcısı kullanır. Ancak, veritabanı Windows Şirket içi veya Azure SQL DB gibi herhangi bir SQL Server olarak dağıtılabilir. Değiştirmeniz gereken tek şey, ASP.NET Web API mikro hizmet bağlantı dizesidir.

#### <a name="the-data-model"></a>Veri modeli

EF Core ile veri erişimi, bir model kullanarak gerçekleştirilir. Bir model (etki alanı modeli) varlık sınıfları ve böylece sorgu ve veri kaydetmek, veritabanı ile bir oturumu temsil eden türetilmiş bağlamı (DbContext) oluşur. Bir modeli varolan bir veritabanından üretebilir, el ile kod veritabanınızı eşleştirmek için bir model veya (veritabanı modelinizi zamanla değiştikçe geliştirilebilen kolaylaştırır) ilk kod yaklaşımı kullanarak EF geçişleri modelinizden, bir veritabanı oluşturmak için kullanın. Katalog mikro hizmet için son yaklaşımı kullanıyoruz. Bir basit düz eski CLR nesnesi aşağıdaki kod örneğinde, Catalogıtem varlık sınıfı bir örneğini görebilirsiniz ([POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)) varlık sınıfı.

```csharp
public class CatalogItem
{
    public int Id { get; set; }
    public string Name { get; set; }
    public string Description { get; set; }
    public decimal Price { get; set; }
    public string PictureFileName { get; set; }
    public string PictureUri { get; set; }
    public int CatalogTypeId { get; set; }
    public CatalogType CatalogType { get; set; }
    public int CatalogBrandId { get; set; }
    public CatalogBrand CatalogBrand { get; set; }
    public int AvailableStock { get; set; }
    public int RestockThreshold { get; set; }
    public int MaxStockThreshold { get; set; }

    public bool OnReorder { get; set; }
    public CatalogItem() { }

    // Additional code ...
}
```

Ayrıca veritabanı ile bir oturumu temsil eden DbContext gerekir. Katalog mikro hizmet için CatalogContext sınıfı aşağıdaki örnekte gösterildiği gibi DbContext temel sınıfından türetilir:

```csharp
public class CatalogContext : DbContext
{
    public CatalogContext(DbContextOptions<CatalogContext> options) : base(options)
    {
    }
    public DbSet<CatalogItem> CatalogItems { get; set; }
    public DbSet<CatalogBrand> CatalogBrands { get; set; }
    public DbSet<CatalogType> CatalogTypes { get; set; }

    // Additional code ...

}
```

Ek olabilir `DbContext` uygulamaları. Örneğin, örnek Catalog.API mikro hizmet içinde olduğu ikinci `DbContext` adlı `CatalogContextSeed` nerede otomatik olarak doldurulur örnek verileri ilk kez çalıştığında veritabanına erişmek için. Bu yöntem, tanıtım verileri ve otomatikleştirilmiş test senaryoları için de kullanışlıdır.

İçinde `DbContext`, kullandığınız `OnModelCreating` nesne/veritabanı varlık eşlemelerini ve diğer özelleştirme yöntemi [EF genişletilebilirlik noktaları](https://devblogs.microsoft.com/dotnet/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/).

##### <a name="querying-data-from-web-api-controllers"></a>Web APİ'si denetleyicilerinin verileri Sorgulama

Aşağıdaki örnekte gösterildiği gibi varlık sınıflarının örneklerini genellikle dil tümleşik sorgu (LINQ), kullanarak veritabanından alınır:

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    private readonly CatalogContext _catalogContext;
    private readonly CatalogSettings _settings;
    private readonly ICatalogIntegrationEventService _catalogIntegrationEventService;

    public CatalogController(CatalogContext context,
                             IOptionsSnapshot<CatalogSettings> settings,
                             ICatalogIntegrationEventService catalogIntegrationEventService)
    {
        _catalogContext = context ?? throw new ArgumentNullException(nameof(context));
        _catalogIntegrationEventService = catalogIntegrationEventService ?? throw new ArgumentNullException(nameof(catalogIntegrationEventService));

        _settings = settings.Value;
        ((DbContext)context).ChangeTracker.QueryTrackingBehavior = QueryTrackingBehavior.NoTracking;
    }

    // GET api/v1/[controller]/items[?pageSize=3&pageIndex=10]
    [HttpGet]
    [Route("[action]")]
    [ProducesResponseType(typeof(PaginatedItemsViewModel<CatalogItem>), (int)HttpStatusCode.OK)]
    public async Task<IActionResult> Items([FromQuery]int pageSize = 10,
                                           [FromQuery]int pageIndex = 0)

    {
        var totalItems = await _catalogContext.CatalogItems
            .LongCountAsync();

        var itemsOnPage = await _catalogContext.CatalogItems
            .OrderBy(c => c.Name)
            .Skip(pageSize * pageIndex)
            .Take(pageSize)
            .ToListAsync();

        itemsOnPage = ChangeUriPlaceholder(itemsOnPage);

        var model = new PaginatedItemsViewModel<CatalogItem>(
            pageIndex, pageSize, totalItems, itemsOnPage);

        return Ok(model);
    }
    //...
}
```

##### <a name="saving-data"></a>Verileri kaydetme

Veri oluşturulan, silinen ve örnekleri, varlık sınıfları kullanarak veritabanında değiştirildi. Aşağıdaki örnekte olduğu gibi sabit kodlanmış (Bu örnekte sahte veriler), Web APİ'si denetleyicilerinin için kod ekleyebilirsiniz.

```csharp
var catalogItem = new CatalogItem() {CatalogTypeId=2, CatalogBrandId=2,
                                     Name="Roslyn T-Shirt", Price = 12};
_context.Catalog.Add(catalogItem);
_context.SaveChanges();
```

##### <a name="dependency-injection-in-aspnet-core-and-web-api-controllers"></a>ASP.NET Core ve Web API denetleyicilerinin bağımlılık ekleme

ASP.NET Core, kullanıma hazır bağımlılık ekleme (dı) kullanabilirsiniz. İsterseniz, tercih edilen IOC kapsayıcınızın ASP.NET Core altyapısına takılabilir rağmen bir üçüncü taraf denetimi tersine çevirme (IOC) kapsayıcısı ayarlamak gerekmez. Bu durumda, doğrudan gerekli EF DBContext veya ek depoları aracılığıyla denetleyici Oluşturucu ekleyebilir, anlamına gelir.

Yukarıdaki örnekte `CatalogController` sınıfı, biz ekleme bir nesnenin `CatalogContext` türü diğer nesneler arasında artı `CatalogController()` Oluşturucusu.

Hizmetin IOC kapsayıcısına DbContext sınıfı kaydı Web API projesinde ayarlamak için önemli bir yapılandırmadır. Genellikle, bu nedenle bunu `Startup` çağırarak sınıfı `services.AddDbContext<DbContext>()` yöntem içinde `ConfigureServices()` aşağıdaki örnekte gösterildiği gibi yöntemi:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    // Additional code...

    services.AddDbContext<CatalogContext>(options =>
    {
        options.UseSqlServer(Configuration["ConnectionString"],
        sqlServerOptionsAction: sqlOptions =>
        {
           sqlOptions.
               MigrationsAssembly(
                   typeof(Startup).
                    GetTypeInfo().
                     Assembly.
                      GetName().Name);

           //Configuring Connection Resiliency:
           sqlOptions.
               EnableRetryOnFailure(maxRetryCount: 5,
               maxRetryDelay: TimeSpan.FromSeconds(30),
               errorNumbersToAdd: null);

       });

       // Changing default behavior when client evaluation occurs to throw.
       // Default in EFCore would be to log warning when client evaluation is done.
       options.ConfigureWarnings(warnings => warnings.Throw(
           RelationalEventId.QueryClientEvaluationWarning));
   });

  //...

}
```

### <a name="additional-resources"></a>Ek kaynaklar

- **Verileri sorgulama** \
  [*https://docs.microsoft.com/ef/core/querying/index*](https://docs.microsoft.com/ef/core/querying/index)

- **Verileri kaydetme** \
  [*https://docs.microsoft.com/ef/core/saving/index*](https://docs.microsoft.com/ef/core/saving/index)

## <a name="the-db-connection-string-and-environment-variables-used-by-docker-containers"></a>Docker kapsayıcıları tarafından kullanılan DB bağlantı dizesi ve ortam değişkenleri

ASP.NET Core ayarları kullanın ve ConnectionString özelliğini aşağıdaki örnekte gösterildiği gibi settings.json dosyasına ekleyin:

```json
{
    "ConnectionString": "Server=tcp:127.0.0.1,5433;Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word",
    "ExternalCatalogBaseUrl": "http://localhost:5101",
    "Logging": {
        "IncludeScopes": false,
        "LogLevel": {
            "Default": "Debug",
            "System": "Information",
            "Microsoft": "Information"
        }
    }
}
```

ConnectionString özelliği için ya da başka bir özellik için varsayılan değerleri settings.json dosyasına sahip olabilir. Ancak, bu özellikleri Docker kullanarak docker-compose.override.yml dosyasında belirttiğiniz ortam değişkenlerinin değerlerini tarafından geçersiz kılınır.

Docker bunları işletim sistemi ortam değişkenleri olarak sizin için ayarlamanız, böylece docker-compose.yml ya da docker-compose.override.yml dosyalarından, bu ortam değişkenlerini aşağıdaki docker-compose.override.yml dosya (bağlantının gösterilen şekilde başlatabilirsiniz Bu örnekte, dize ve diğer satır kaydırma, ancak bunu kendi dosyasında kaydırılacak).

```yml
# docker-compose.override.yml

#
catalog.api:
  environment:
    - ConnectionString=Server=sql.data;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word
    # Additional environment variables for this service
  ports:
    - "5101:80"
```

Docker-compose.yml dosyaları çözüm düzeyinde yalnızca yapılandırma dosyalarını proje veya mikro hizmet düzeyinde daha esnek değildir, ancak docker-compose dosyalara kümeden değerlerle bildirilen ortam değişkenlerini geçersiz kılarsanız daha da güvenli Dağıtım Araçları, Azure DevOps Hizmetleri Docker dağıtım görevlerini ister.

Kodunuz aracılığıyla yapılandırmayı kullanarak bu değeri son olarak, alabilirsiniz\["ConnectionString"\]Createservicereplicalisteners() yöntemi bir önceki kod örneğinde gösterildiği gibi.

Ancak, üretim ortamları için bağlantı dizeleri gibi gizli dizileri depolamak nasıl ek yollarını keşfetmek isteyebilirsiniz. Uygulama gizli dizilerini yönetmek için mükemmel bir yoldur kullanarak [Azure anahtar kasası](https://azure.microsoft.com/services/key-vault/).

Azure Key Vault depolamak ve şifreleme anahtarlarını ve gizli dizileri, bulut uygulamaları ve Hizmetleri tarafından kullanılan korunmasına yardımcı olur. API anahtarları, bağlantı dizeleri, parolalar vb. gibi katı denetimi, korumak istediğiniz her şeyi bir gizli dizidir ve sıkı denetim günlüğü, sona erme ayarı, erişimi yönetme kullanım içerir *diğerlerinin yanı sıra*.

Azure Key Vault, uygulama gizli anahtarları kullanım herkesin bunları biliyor olanak gerek kalmadan çok ayrıntılı denetim düzeyini sağlar. Gizli dizileri, geliştirme veya işlemleri kesintiye uğratmadan Gelişmiş güvenlik için bile döndürülebilir.

Uygulamaların, anahtar Kasası'nı kullanabilmeleri kuruluşun Active Directory'de kayıtlı olması gerekir.

Denetleyebilirsiniz *Key Vault kavramlarını belgeleri* daha fazla ayrıntı için.

### <a name="implementing-versioning-in-aspnet-web-apis"></a>ASP.NET Web API, uygulama sürümü oluşturma

İş gereksinimleri değiştikçe yeni kaynak koleksiyonları eklenebilir, kaynaklar arasındaki ilişkiler değişebilir ve kaynaklardaki verilerin yapısını düzeltilir. Yeni gereksinimlerini karşılamak için bir Web API güncelleştiriliyor oldukça basit bir işlemdir ancak bu tür değişikliklerin Web API'sini kullanan istemci uygulamalar üzerinde olacak etkileri göz önünde bulundurmanız gerekir. Tasarlama ve uygulama bir Web API'sini bir geliştirici bu API üzerinde tam denetime sahip olsa da, geliştirici aynı derecede uzaktan çalışan üçüncü taraf kuruluşlar tarafından oluşturulabilir istemci uygulamalar üzerinde daha fazla denetime sahip değil.

Sürüm oluşturma, kullanıma sunduğu kaynaklar ve Özellikler belirtmek bir Web API'si sağlar. Bir istemci uygulaması daha sonra bir özellik ya da kaynağın belirli bir sürümünü istekleri gönderebilirsiniz. Sürüm oluşturma uygulamak için birçok yaklaşım vardır:

- URI sürümü oluşturma

- Sorgu dizesi sürümü oluşturma

- Üst bilgi sürümü oluşturma

Sorgu dizesi ve URI sürümü oluşturma uygulamak en basit olan. Üst bilgi sürümü oluşturma iyi bir yaklaşımdır. Bununla birlikte, üst bilgi sürümü oluşturma gibi açık ve basit olarak URI sürümü oluşturma. URL sürüm oluşturma basit ve en açık olduğundan, URI sürümü oluşturma hizmetine örnek uygulamayı kullanır.

Hizmetine örnek uygulaması, olduğu gibi URI sürümü oluşturma ile Web API değiştirmek veya kaynak şemasını değiştirmek eklediğiniz her sefer bir sürüm numarası için her kaynak için URI. Mevcut bir URI'leri önce uygun kaynakları istenen sürümle eşleşen şemalarına gibi çalışmaya devam etmelidir.

Aşağıdaki kod örneğinde gösterildiği gibi sürüm sürüm urı'sindeki açık hale getirir denetleyicideki Web API'si rota özniteliği kullanılarak ayarlanabilir (Bu durumda v1).

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    // Implementation ...
```

Bu sürüm oluşturma mekanizması basittir ve isteği uygun uç noktaya yönlendiren sunucuya bağlıdır. Ancak, daha karmaşık bir sürüm oluşturma ve REST kullanırken en iyi yöntemi için hiper medya kullanma ve uygulamak [HATEOAS (uygulama durumu altyapısı olarak köprü metni)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#use-hateoas-to-enable-navigation-to-related-resources).

### <a name="additional-resources"></a>Ek kaynaklar

- **Scott Hanselman. ASP.NET Core RESTful Web API'si sürümü oluşturma artık daha kolay** \
  [*https://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx*](https://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx)

- **RESTful web API'si sürümü oluşturma** \
  [*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)

- **Roy Fielding. Sürüm oluşturma, iletilir ve REST** \
  [*https://www.infoq.com/articles/roy-fielding-on-versioning*](https://www.infoq.com/articles/roy-fielding-on-versioning)

## <a name="generating-swagger-description-metadata-from-your-aspnet-core-web-api"></a>Swagger tanım meta verileri, ASP.NET Core Web API'si oluşturma

[Swagger](https://swagger.io/) olduğu bir yaygın olarak kullanılan açık kaynak çerçeve tasarım, derleme, belge yardımcı olan oluşan geniş ekosistem araçları tarafından desteklenen ve RESTful API'leri kullanır. Bu API'leri açıklama meta verileri etki alanı için standart hale gelmektedir. Swagger tanım meta verileri ile mikro hizmet, veri odaklı bir mikro hizmetler veya daha fazla etki alanı odaklı bir mikro hizmetler (aşağıdaki bölümde açıklandığı gibi) Gelişmiş herhangi bir türden içermelidir.

Swagger API tanımı meta veriler bir JSON veya YAML dosyasına Swagger belirtimi kalbidir. Tüm kaynakları ve işlemleri hem İnsan ve machine readable biçimde kolay geliştirme, Keşif ve tümleştirme için gerçekleşen API'niz için RESTful sözleşme belirtimi oluşturur.

Belirtimi, Openapı belirtimi'nın (OAS) temelidir ve RESTful arabirimlerinden tanımlanma biçimini standart hale getirmek için bir açık, şeffaf ve işbirliğine dayalı topluluğuna geliştirilmiştir.

Belirtimi, bir hizmetin nasıl bulunabileceğini ve özelliklerini nasıl anladım yapısını tanımlar. Daha fazla bilgi için bir web Düzenleyicisi ve Swagger belirtimlerinden Spotify, Uber, Slack ve Microsoft gibi şirketler örnekleri dahil olmak üzere Swagger sitesine bakın ([https://swagger.io](https://swagger.io)).

### <a name="why-use-swagger"></a>Swagger neden kullanmalısınız?

Apı'leriniz için Swagger meta verileri oluşturmak için temel neden aşağıda verilmiştir.

**Otomatik olarak kullanmak ve Apı'lerinizi tümleştirmek diğer ürünlere yönelik özelliği**. Ürünleri onlarca ve [ticari Araçları](https://swagger.io/commercial-tools/) ve birçok [kitaplıklar ve çerçeveler](https://swagger.io/open-source-integrations/) Swagger'ı destekler. Microsoft üst düzey ürün ve otomatik olarak aşağıdaki gibi Swagger tabanlı API'ler tüketebileceği araç vardır:

- [AutoRest](https://github.com/Azure/AutoRest). Swagger'ı çağırmak için .NET istemci sınıfları otomatik olarak oluşturabilirsiniz. Bu aracı CLI üzerinden kullanılabilir ve GUI aracılığıyla kolay kullanım için de Visual Studio ile tümleştirilir.

- [Microsoft Flow](https://flow.microsoft.com/en-us/). Otomatik olarak [kullanın ve API'nizi tümleştirme](https://flow.microsoft.com/en-us/blog/integrating-custom-api/) üst düzey bir Microsoft Flow iş akışınıza olmadan programlama becerileri gerekir.

- [Microsoft PowerApps](https://powerapps.microsoft.com/). Otomatik olarak, API'SİNDEN tüketebileceği [PowerApps mobil uygulamalar](https://powerapps.microsoft.com/blog/register-and-use-custom-apis-in-powerapps/) ile oluşturulmuş [PowerApps Studio](https://powerapps.microsoft.com/build-powerapps/), gerekli herhangi bir programlama becerilerine sahip.

- [Azure App Service Logic Apps](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps). Otomatik olarak [kullanın ve API'nizi Azure App Service mantıksal uygulamalarla tümleştirme](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api), gerekli herhangi bir programlama becerilerine sahip.

**API belgelerini otomatik olarak oluşturma yeteneği**. Karmaşık mikro hizmet tabanlı uygulamalar gibi büyük ölçekli RESTful API'leri oluşturduğunuzda, istek ve yanıt yükleri kullanılan farklı veri modellerine sahip çok sayıda uç noktalar ele almanız gerekir. API'NİZİN ve geliştiriciler tarafından benimseme başarısı için uygun belgelere sahip olunması ve Swagger ile aldıkça, sağlam bir API Gezgini sahip anahtardır.

Microsoft Flow, PowerApps ve Logic Apps Azure API'leri ve bunlara nasıl kullanılacağını anlamak için kullandıklarınız swagger'ın meta verilerdir.

Temel işlevsel API Yardım sayfaları biçiminde ASP.NET Core REST API uygulamaları için Swagger meta verileri oluşturmayı otomatikleştirmek için birkaç seçenek vardır *swagger kullanıcı arabirimi*.

En iyi bilinen olabilir [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) şu anda kullanılan [hizmetine](https://github.com/dotnet-architecture/eShopOnContainers) ve bu kılavuzdaki bazı ayrıntılı şu konulara değineceğiz ancak kullanmak için bir seçenek de mevcuttur [NSwag](https://github.com/RSuter/NSwag), Typescript ve C oluşturabileceği\# C yanı sıra API istemciler\# denetleyicileri, Swagger veya Openapı belirtiminden ve kullanarak denetleyicileri içeren .dll tarayarak bile [NSwagStudio](https://github.com/RSuter/NSwag/wiki/NSwagStudio).

### <a name="how-to-automate-api-swagger-metadata-generation-with-the-swashbuckle-nuget-package"></a>Swagger API meta verileri oluşturma Swashbuckle NuGet paketini ile otomatikleştirme

Swagger meta verilerde el ile (bir JSON veya YAML dosyası) oluşturmak zahmetli bir iş olabilir. Ancak, ASP.NET Web API Hizmetleri API bulma kullanarak otomatikleştirebileceğiniz [Swashbuckle NuGet paketini](https://aka.ms/swashbuckledotnetcore) dinamik olarak Swagger API'si meta verileri oluşturmak için.

Swashbuckle, ASP.NET Web API projeleriniz için Swagger meta verileri otomatik olarak oluşturur. Bu, ASP.NET Core Web API projelerini ve geleneksel ASP.NET Web API ve Azure API uygulaması, Azure mobil uygulaması, ASP Azure Service Fabric mikro hizmetler gibi diğer tüm flavor destekler. Ayrıca, düz Web API'si için başvuru uygulaması olarak kapsayıcılarında, dağıtılan destekler.

Swashbuckle birleştirir API Gezgini ve Swagger veya [swagger kullanıcı arabirimi](https://github.com/swagger-api/swagger-ui) zengin bulma ve belgeler için API tüketicilerinize deneyimi sağlamak. Kendi Swagger meta verileri Oluşturucu altyapısına ek olarak, Swashbuckle swagger-Swashbuckle yüklendikten sonra otomatik olarak hizmet verecek yukarı kullanıcı arabirimi, katıştırılmış bir sürümünü de içerir.

Bu, iyi bir bulma geliştiricilerin API'nizi kullanmasına yardımcı olmak için kullanıcı Arabirimi ile API'nizi tamamlayabilir anlamına gelir. Bu otomatik olarak, API'nizi geliştirmeye odaklanabilirsiniz oluşturulmuş olduğu için çok az miktarda kodu ve bakım gerektirir. API Gezgini için sonucu Şekil 6-8 gibi görünüyor.

![Swashbuckle'ı üretilen Swagger kullanıcı Arabirimi API belgelerini içeren tüm eylemleri yayımladı.](./media/image9.png)

**Şekil 6-8**. Swashbuckle API Gezgini Swagger meta verileri temel alarak — hizmetine mikro hizmet Kataloğu

API Gezgini burada en önemli şey değil. Kendisini Swagger meta verilerde açıklayan bir Web API'si aldıktan sonra birçok platformda hedefleyebilen istemci proxy sınıfı kod oluşturucuları dahil olmak üzere Swagger tabanlı araçlardan, API'nizi sorunsuz bir şekilde kullanılabilir. Örneğin, bahsedildiği gibi [AutoRest](https://github.com/Azure/AutoRest) otomatik olarak .NET istemci sınıfları oluşturur. Ancak gibi ek araçlar [swagger codegen](https://github.com/swagger-api/swagger-codegen) kod oluşturma API'si istemci kitaplıkları, sunucu saptamalar ve belgeleri otomatik olarak izin olan de kullanılabilir.

Üst düzey meta-package altında beş iç NuGet paketleri şu anda, Swashbuckle oluşan [Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore) ASP.NET Core uygulamaları için.

Bu NuGet paketleri, Web API projesinde yükledikten sonra aşağıdaki kodu (Basitleştirilmiş) olduğu gibi bir başlangıç sınıfı Swagger yapılandırmanız gerekir:

```csharp
public class Startup
{
    public IConfigurationRoot Configuration { get; }
    // Other startup code...

    public void ConfigureServices(IServiceCollection services)
    {
        // Other ConfigureServices() code...

        // Add framework services.
        services.AddSwaggerGen(options =>
        {
            options.DescribeAllEnumsAsStrings();
            options.SwaggerDoc("v1", new Swashbuckle.AspNetCore.Swagger.Info
            {
                Title = "eShopOnContainers - Catalog HTTP API",
                Version = "v1",
                Description = "The Catalog Microservice HTTP API. This is a Data-Driven/CRUD microservice sample",
                TermsOfService = "Terms Of Service"
            });
        });

        // Other ConfigureServices() code...
    }

    public void Configure(IApplicationBuilder app,
        IHostingEnvironment env,
        ILoggerFactory loggerFactory)
    {
        // Other Configure() code...
        // ...
        app.UseSwagger()
            .UseSwaggerUI(c =>
            {
                c.SwaggerEndpoint("/swagger/v1/swagger.json", "My API V1");
            });
    }
}
```

Bunu yaptıktan sonra uygulamanızı başlatın ve bu gibi URL'leri kullanarak aşağıdaki Swagger JSON ve UI uç göz atın:

```url
  http://<your-root-url>/swagger/v1/swagger.json

  http://<your-root-url>/swagger/
```

Daha önce oluşturulan kullanıcı arabirimini gibi bir URL için Swashbuckle tarafından oluşturulan gördüğünüz `http://<your-root-url>/swagger`. Şekil 6-9'da herhangi bir API yöntemini nasıl test görebilirsiniz.

![Swagger kullanıcı Arabirimi API ayrıntılı bir yanıt örneği gösterilmektedir ve geliştirici bulma için harika olan gerçek API yürütmek için kullanılabilir.](./media/image10.png)

**Şekil 6-9**. Swashbuckle UI testi katalog/öğeleri API yöntemi

Şekil 6-10 hizmetine mikro hizmet oluşturulan Swagger JSON meta verileri gösterir (olan araçlar altında kullanın) olduğunda, isteği `http://<your-root-url>/swagger/v1/swagger.json` kullanarak [Postman](https://www.getpostman.com/).

![Swagger JSON meta verileri gösteren örnek Postman UI](./media/image11.png)

**Şekil 6-10**. Swagger JSON meta verileri

Bu basit bir işlemdir. Ve daha fazla işlevsellik API'nize eklediğinizde otomatik olarak oluşturulduğundan, Swagger meta verileri büyüyecektir.

### <a name="additional-resources"></a>Ek kaynaklar

- **Swagger kullanan ASP.NET Web API Yardım sayfaları** \
  [*https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger*](https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger)

- **Swashbuckle'ı ve ASP.NET Core ile çalışmaya başlama** \
  [*https://docs.microsoft.com/aspnet/core/tutorials/getting-started-with-swashbuckle?tabs=visual-studio*](https://docs.microsoft.com/aspnet/core/tutorials/getting-started-with-swashbuckle?tabs=visual-studio)

- **NSwag ve ASP.NET Core ile çalışmaya başlama** \
  [*https://docs.microsoft.com/aspnet/core/tutorials/getting-started-with-nswag?tabs=visual-studio*](https://docs.microsoft.com/aspnet/core/tutorials/getting-started-with-nswag?tabs=visual-studio)

> [!div class="step-by-step"]
> [Önceki](microservice-application-design.md)
> [İleri](multi-container-applications-docker-compose.md)
