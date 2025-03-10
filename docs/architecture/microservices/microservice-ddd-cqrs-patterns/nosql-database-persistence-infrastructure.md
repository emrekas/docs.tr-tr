---
title: NoSQL veritabanlarını bir kalıcılık altyapısı olarak kullanma
description: Kapsayıcılı .NET uygulamaları için .NET mikro hizmetleri mimarisi | Genel olarak NoSql veritabanlarının kullanımını ve özellikle de Azure Cosmos DB, persistance uygulama seçeneği olarak anlayın.
ms.date: 10/08/2018
ms.openlocfilehash: 7a8573f8f668a5b75f50acde57a2f4c42ce4d189
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2019
ms.locfileid: "70374033"
---
# <a name="use-nosql-databases-as-a-persistence-infrastructure"></a>Kalıcı altyapı olarak NoSQL veritabanlarını kullanma

Altyapı veri katmanınız için NoSQL veritabanlarını kullandığınızda, genellikle Entity Framework Core gibi bir ORM kullanmayın. Bunun yerine, Azure Cosmos DB, MongoDB, Cassandra, Rayvendb, Couşdb veya Azure depolama tabloları gibi NoSQL altyapısı tarafından sunulan API 'YI kullanırsınız.

Ancak, bir NoSQL veritabanı kullandığınızda, özellikle de Azure Cosmos DB, Couşdb veya Avendb gibi bir belge yönelimli bir veritabanı kullandığınızda, EF Core bu modeli DDD toplamalarda tasarlama şekliniz, Toplam kökleri, alt varlık sınıfları ve değer nesnesi sınıfları. Ancak, sonunda veritabanı seçimi tasarımınızda etkileyecektir.

Belge yönelimli bir veritabanı kullandığınızda, bir toplamı JSON veya başka bir biçimde sıralanmış tek bir belge olarak uygulayın. Ancak, veritabanının kullanımı bir görünüm etki alanı modeli kod noktasından saydamdır. Bir NoSQL veritabanı kullanırken, hala varlık sınıfları ve toplama kök sınıfları kullanıyorsunuz, ancak Kalıcılık ilişkisel olmadığından EF Core kullanmaktan daha fazla esneklik elde edersiniz.

Fark, bu modeli nasıl kalıcı hale getiribir modeldir. Etki alanı modelinizi POCO varlık sınıflarına göre uyguladıysanız, altyapı kalıcılığına göre bağımsız olarak, ilişkisel ve NoSQL arasında bile farklı bir kalıcılık altyapısına geçebilirsiniz gibi görünebilir. Bununla birlikte, hedefiniz olmaması gerekir. Farklı veritabanı teknolojilerinde her zaman kısıtlamalar ve denge bulunur, bu nedenle ilişkisel veya NoSQL veritabanları için aynı modele sahip olmayacaksınız. İşlem ve Kalıcılık işlemleri çok farklı olacağı için kalıcılık modellerinin değiştirilmesi önemsiz bir görev değildir.

Örneğin, belge odaklı bir veritabanında, bir toplama kökünün birden çok alt koleksiyon özelliği olması normaldir. Bir ilişkisel veritabanında, bir UNıON ALL SQL ifadesini bir UNıON 'den geri alacağınız için, birden çok alt koleksiyon özelliklerini sorgulama özelliği kolayca iyileştirilmez. İlişkisel veritabanları veya NoSQL veritabanları için aynı etki alanı modeline sahip olmak basit değildir ve bunu yapmayı denememelisiniz. Gerçekten de, verilerin belirli bir veritabanında nasıl kullanılacağına ilişkin bir anlama sahip olacak şekilde modelinizin tasarımını yapmanız gerekir.

NoSQL veritabanları kullanmanın bir avantajı, varlıkların daha fazla normalleştirilmiştir, bu nedenle tablo eşlemesi ayarlayamazsınız. Etki alanı modeliniz, ilişkisel bir veritabanı kullanmaktan daha esnek olabilir.

Etki alanı modelinizi toplamalara göre tasarladığınızda, NoSQL ve belge odaklı veritabanlarına geçiş, bir ilişkisel veritabanı kullanmaktan daha da kolay olabilir, çünkü tasarladığınız toplamalar belge odaklı veritabanında seri hale getirilmiş belgelere benzerdir. Daha sonra bu toplama için ihtiyaç duyduğunuz tüm bilgileri bu "Batı" ekleyebilirsiniz.

Örneğin, aşağıdaki JSON kodu, belge yönelimli bir veritabanı kullanılırken bir sıra toplamanın örnek uygulamasıdır. EShopOnContainers örneğinde uyguladığımız sıra toplamasına benzerdir, ancak altında EF Core kullanmadan.

```json
{
    "id": "2017001",
    "orderDate": "2/25/2017",
    "buyerId": "1234567",
    "address": [
        {
        "street": "100 One Microsoft Way",
        "city": "Redmond",
        "state": "WA",
        "zip": "98052",
        "country": "U.S."
        }
    ],
    "orderItems": [
        {"id": 20170011, "productId": "123456", "productName": ".NET T-Shirt",
        "unitPrice": 25, "units": 2, "discount": 0},
        {"id": 20170012, "productId": "123457", "productName": ".NET Mug",
        "unitPrice": 15, "units": 1, "discount": 0}
    ]
}
```

## <a name="introduction-to-azure-cosmos-db-and-the-native-cosmos-db-api"></a>Azure Cosmos DB ve yerel Cosmos DB API 'sine giriş

[Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/introduction) , Microsoft 'un görev açısından kritik uygulamalar için genel olarak dağıtılmış veritabanı hizmetidir. Azure Cosmos DB, [ön anahtar genel dağıtımı](https://docs.microsoft.com/azure/cosmos-db/distribute-data-globally), [Esnek işleme ve depolama için esnek ölçeklendirme](https://docs.microsoft.com/azure/cosmos-db/partition-data) , 99. yüzdebirlik, [beş adet iyi tanımlanmış tutarlılık düzeyi](https://docs.microsoft.com/azure/cosmos-db/consistency-levels)ve garantili yüksek gecikme süreleriyle birlikte, tek basamaklı milisaniyelik gecikme süresi sağlar kullanılabilirlik, hepsi [sektörde önde gelen SLA 'lar](https://azure.microsoft.com/support/legal/sla/cosmos-db/)tarafından desteklenir. Azure Cosmos DB, şema ve dizin yönetimiyle ilgilenmenize gerek kalmadan [otomatik olarak verilerin dizinini oluşturur](https://www.vldb.org/pvldb/vol8/p1668-shukla.pdf). Çok modelli olan bu hizmet belge, anahtar-değer, grafik ve sütunlu veri modellerini destekler.

![Azure Cosmos DB, dört API protokolleriyle erişilebilen, küresel olarak dağıtılmış garantili düşük gecikme süreli bir veritabanıdır. ](./media/image19.1.png)

**Şekil 7-19**. Azure Cosmos DB küresel dağıtım

Azure Cosmos DB API tarafından kullanılacak toplamı\# uygulamak için bir C modeli kullandığınızda, toplama, EF Core kullanılan c\# poco sınıflarına benzer olabilir. Bu fark, aşağıdaki kodda olduğu gibi uygulama ve altyapı katmanlarından kullanmanın bir yoludur:

```csharp
// C# EXAMPLE OF AN ORDER AGGREGATE BEING PERSISTED WITH AZURE COSMOS DB API
// *** Domain Model Code ***
// Aggregate: Create an Order object with its child entities and/or value objects.
// Then, use AggregateRoot’s methods to add the nested objects so invariants and
// logic is consistent across the nested properties (value objects and entities).

Order orderAggregate = new Order
{
    Id = "2017001",
    OrderDate = new DateTime(2005, 7, 1),
    BuyerId = "1234567",
    PurchaseOrderNumber = "PO18009186470"
}

Address address = new Address
{
    Street = "100 One Microsoft Way",
    City = "Redmond",
    State = "WA",
    Zip = "98052",
    Country = "U.S."
}

orderAggregate.UpdateAddress(address);

OrderItem orderItem1 = new OrderItem
{
    Id = 20170011,
    ProductId = "123456",
    ProductName = ".NET T-Shirt",
    UnitPrice = 25,
    Units = 2,
    Discount = 0;
};

//Using methods with domain logic within the entity. No anemic-domain model
orderAggregate.AddOrderItem(orderItem1);
// *** End of Domain Model Code ***

// *** Infrastructure Code using Cosmos DB Client API ***
Uri collectionUri = UriFactory.CreateDocumentCollectionUri(databaseName,
    collectionName);

await client.CreateDocumentAsync(collectionUri, orderAggregate);

// As your app evolves, let's say your object has a new schema. You can insert
// OrderV2 objects without any changes to the database tier.
Order2 newOrder = GetOrderV2Sample("IdForSalesOrder2");
await client.CreateDocumentAsync(collectionUri, newOrder);
```

Altyapı EF olduğunda, etki alanı modelinize çalışırken kullandığınız şekilde, etki alanı modeli katmanınızda kullanma biçimine benzer bir şekilde bakabilirsiniz. Toplama içindeki tutarlılığı, ınvaryantları ve doğrulamaları sağlamak için yine de aynı toplama kök yöntemini kullanırsınız.

Ancak, modelinizi NoSQL veritabanına kalıcı hale getirebilmeniz durumunda kod ve API değişikliği EF Core kodla veya ilişkisel veritabanlarıyla ilgili diğer herhangi bir kodla karşılaştırıldığında önemli ölçüde değişir.

## <a name="implement-net-code-targeting-mongodb-and-azure-cosmos-db"></a>MongoDB hedefleme ve Azure Cosmos DB .NET kodu uygulama

### <a name="use-azure-cosmos-db-from-net-containers"></a>.NET kapsayıcılarından Azure Cosmos DB kullanma

Kapsayıcılarda çalışan .NET kodundan, diğer tüm .NET uygulamaları gibi Azure Cosmos DB veritabanlarına erişebilirsiniz. Örneğin, eShopOnContainers içindeki locations. API ve Marketing. API mikro hizmetleri, Azure Cosmos DB veritabanlarını tüketebilecekleri şekilde uygulanır.

Ancak, bir Docker geliştirme ortamı görünümündeki Azure Cosmos DB bir sınırlama vardır. Bir şirket içi [Azure Cosmos DB öykünücü](https://docs.microsoft.com/azure/cosmos-db/local-emulator) , bir bilgisayar gibi bir yerel geliştirme makinesinde (PC gibi) çalıştırılabilse de, en geç 2017 Itibariyle yalnızca Windows 'u destekler. 

Ayrıca, Linux kapsayıcılarıyla değil, yalnızca Windows kapsayıcılarında bu öykünücüyü çalıştırma olasılığı da vardır. Uygulamanız Linux kapsayıcıları olarak dağıtılmışsa geliştirme ortamı için bir ilk Handicap olan bu, şu anda Linux ve Windows kapsayıcılarını Docker for Windows aynı anda dağıtamazsınız. Dağıtılmakta olan tüm kapsayıcıların Linux veya Windows için olması gerekir.

Geliştirme/test çözümüne yönelik ideal ve daha basit dağıtım, geliştirme ve test ortamlarınızın her zaman tutarlı olması için veritabanı sistemlerinizi özel kapsayıcılarınızla birlikte kapsayıcı olarak dağıtabilmelidir.

### <a name="use-mongodb-api-for-local-devtest-linuxwindows-containers-plus-azure-cosmos-db"></a>Yerel geliştirme ve test için MongoDB API 'SI kullanma ve Linux/Windows kapsayıcıları Plus Azure Cosmos DB

Cosmos DB veritabanları, .NET için MongoDB API 'nin yanı sıra yerel MongoDB kablo protokolünü de destekler. Bu, var olan sürücüler kullanılarak MongoDB için yazılmış uygulamanız artık Cosmos DB ile iletişim kurabilir ve Şekil 7-20 ' de gösterildiği gibi MongoDB veritabanları yerine Cosmos DB veritabanlarını kullanabilir.

![Cosmos DB .NET ve MongoDB kablo protokolü için MongoDB API 'sini destekler, MongoDb 'den Cosmos DB 'e kolayca geçiş yapabilirsiniz.](./media/image19.2.png)

**Şekil 7-20**. Azure Cosmos DB erişmek için MongoDB API 'sini ve protokolünü kullanma

[MongoDB Docker görüntüsü](https://hub.docker.com/r/_/mongo/) , Docker Linux kapsayıcılarını ve Docker Windows kapsayıcılarını destekleyen çok katmanlı bir görüntü olduğundan, Linux kapsayıcılarıyla Docker ortamlarında kavram kanıtı açısından çok kullanışlı bir yaklaşımdır.

Aşağıdaki görüntüde gösterildiği gibi, MongoDB API 'sini kullanarak, eShopOnContainers yerel geliştirme ortamı için MongoDB Linux ve Windows kapsayıcılarını destekler, ancak Azure Cosmos DB daha [sonra yalnızca Azure Cosmos DB işaret etmek için MongoDB bağlantı dizesi](https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account).

![EShopOnContainers 'daki location mikro hizmeti MongoDB kullanılarak uygulanır, ancak bağlantı dizesi değiştirilerek yalnızca Cosmos DB ' a geçiş yapılabilir.](./media/image20-bis.png)

**Şekil 7-21**. geliştirme için MongoDB kapsayıcılarını kullanan eShopOnContainers-env veya Azure Cosmos DB for Production

Üretim Azure Cosmos DB, Azure 'un bulutta PaaS ve ölçeklenebilir bir hizmet olarak çalışıyor olabilir.

Özel .NET Core kapsayıcılarınız yerel bir geliştirme Docker ana bilgisayarında (bir Windows 10 makinesinde Docker for Windows kullanan) veya Azure AKS veya Azure Service Fabric 'de Kubernetes gibi bir üretim ortamına dağıtılabilir. Bu ikinci ortamda, üretimde verileri işlemek için bulutta Azure Cosmos DB kullandığınızdan bu yana MongoDB kapsayıcısını değil yalnızca .NET Core özel kapsayıcılarını dağıtırsınız.

MongoDB API 'sini kullanmanın net bir avantajı, çözümünüzün her iki veritabanı altyapıda, MongoDB veya Azure Cosmos DB çalışmasına, böylece farklı ortamlara geçişlerin kolay olması gerekir. Ancak bazı durumlarda, belirli bir veritabanı altyapısının yetilerinden tam olarak yararlanabilmek için yerel bir API (yerel Cosmos DB API) kullanılması çok önemlidir.

Yalnızca MongoDB ile bulutta Cosmos DB karşılaştırması arasında daha fazla karşılaştırma için [Bu sayfada Azure Cosmos DB kullanmanın avantajları](https://docs.microsoft.com/azure/cosmos-db/mongodb-introduction)bölümüne bakın. 

### <a name="analyze-your-approach-for-production-applications-mongodb-api-vs-cosmos-db-api"></a>Üretim uygulamaları için yaklaşımınızı çözümleyin: MongoDB API 'SI ile Cosmos DB API 'SI

EShopOnContainers 'da, MongoDB API 'sini kullandık. önceliklerimiz, Azure Cosmos DB ile de çalışan bir NoSQL veritabanı kullanarak tutarlı bir geliştirme/test ortamına sahip olacak.

Ancak, Azure 'da üretim uygulamaları için Azure Cosmos DB erişmek üzere MongoDB API 'sini kullanmayı planlıyorsanız, yerel veritabanını kullanmaya kıyasla Azure Cosmos DB veritabanlarına erişmek için MongoDB API 'sini kullanırken yetenekler ve performans farklılıklarını çözümlemeniz gerekir Azure Cosmos DB API 'SI. Benzer bir şekilde, MongoDB API 'sini kullanabilir ve aynı anda iki NoSQL veritabanı altyapısını destekleme avantajına sahip olursunuz.

Ayrıca MongoDB kümelerini, [MongoDB Azure hizmeti](https://www.mongodb.com/scale/mongodb-azure-service)ile Azure bulutu 'nda bulunan üretim veritabanı olarak da kullanabilirsiniz. Ancak Microsoft tarafından sağlanmış bir PaaS hizmeti değildir. Bu durumda, Azure yalnızca bu çözümün MongoDB 'den geldiğini barındırıyor.

Temel olarak bu yalnızca, Azure Cosmos DB karşı MongoDB API 'sini her zaman bir Linux kapsayıcıları için kullanışlı bir seçenek olduğu için, her zaman bir karşı kullanacağınızı belirten bir vazgeçme belgesi. Karar, üretim uygulamanız için yapmanız gereken belirli ihtiyaçları ve Testleri temel almalıdır.

### <a name="the-code-use-mongodb-api-in-net-core-applications"></a>Kod: .NET Core uygulamalarında MongoDB API 'sini kullanma

.NET için MongoDB API 'SI, aşağıdaki şekilde gösterilen konumlar. API projesinde olduğu gibi, projelerinize eklemeniz gereken NuGet paketlerini temel alır.

![MongoDB NuGet paketlerindeki bağımlılıkları gösteren Çözüm Gezgini görünümü.](./media/image21-bis.png)

**Şekil 7-22**. .NET Core projesinde MongoDB API NuGet paketleri başvuruları

Aşağıdaki bölümlerde kodu araştıralım.

#### <a name="a-model-used-by-mongodb-api"></a>MongoDB API tarafından kullanılan bir model

İlk olarak, uygulamanızın bellek alanındaki veritabanından gelen verileri tutacak bir model tanımlamanız gerekir. EShopOnContainers konumundaki konumlar için kullanılan modele bir örnek aşağıda verilmiştir.

```csharp
using MongoDB.Bson;
using MongoDB.Bson.Serialization.Attributes;
using MongoDB.Driver.GeoJsonObjectModel;
using System.Collections.Generic;

public class Locations
{
    [BsonId]
    [BsonRepresentation(BsonType.ObjectId)]
    public string Id { get; set; }
    public int LocationId { get; set; }
    public string Code { get; set; }
    [BsonRepresentation(BsonType.ObjectId)]
    public string Parent_Id { get; set; }
    public string Description { get; set; }
    public double Latitude { get; set; }
    public double Longitude { get; set; }
    public GeoJsonPoint<GeoJson2DGeographicCoordinates> Location 
                                                             { get; private set; }
    public GeoJsonPolygon<GeoJson2DGeographicCoordinates> Polygon 
                                                             { get; private set; }
    public void SetLocation(double lon, double lat) => SetPosition(lon, lat);
    public void SetArea(List<GeoJson2DGeographicCoordinates> coordinatesList) 
                                                    => SetPolygon(coordinatesList);

    private void SetPosition(double lon, double lat)
    {
        Latitude = lat;
        Longitude = lon;
        Location = new GeoJsonPoint<GeoJson2DGeographicCoordinates>(
            new GeoJson2DGeographicCoordinates(lon, lat));
    }

    private void SetPolygon(List<GeoJson2DGeographicCoordinates> coordinatesList)
    {
        Polygon = new GeoJsonPolygon<GeoJson2DGeographicCoordinates>(
                  new GeoJsonPolygonCoordinates<GeoJson2DGeographicCoordinates>(
                  new GeoJsonLinearRingCoordinates<GeoJson2DGeographicCoordinates>(
                                                                 coordinatesList)));
    }
}
```

MongoDB NuGet paketlerinden birkaç öznitelik ve tür olduğunu görebilirsiniz.

NoSQL veritabanları genellikle ilişkisel olmayan hiyerarşik verilerle çalışmaya yönelik oldukça uygundur. Bu örnekte, özellikle gibi `GeoJson2DGeographicCoordinates`coğrafi konumlar Için oluşturulan MongoDB türlerini kullanıyoruz.

#### <a name="retrieve-the-database-and-the-collection"></a>Veritabanını ve koleksiyonu alma

EShopOnContainers 'da, aşağıdaki kodda olduğu gibi veritabanını ve MongoCollections 'ı almak için kodu uyguladığımız özel bir veritabanı bağlamı oluşturduk.

```csharp
public class LocationsContext
{
    private readonly IMongoDatabase _database = null;

    public LocationsContext(IOptions<LocationSettings> settings)
    {
        var client = new MongoClient(settings.Value.ConnectionString);
        if (client != null)
            _database = client.GetDatabase(settings.Value.Database);
    }

    public IMongoCollection<Locations> Locations
    {
        get
        {
            return _database.GetCollection<Locations>("Locations");
        }
    }       
}
```

#### <a name="retrieve-the-data"></a>Verileri alma

Web C# API denetleyicileri veya özel depolar uygulama gibi kodda, MongoDB API 'si ile sorgulama yaparken aşağıdakine benzer bir kod yazabilirsiniz. `_context` Nesnenin önceki`LocationsContext` sınıfın bir örneği olduğunu unutmayın.

```csharp
public async Task<Locations> GetAsync(int locationId)
{
    var filter = Builders<Locations>.Filter.Eq("LocationId", locationId);
    return await _context.Locations
                            .Find(filter)
                            .FirstOrDefaultAsync();
}
```

#### <a name="use-an-env-var-in-the-docker-composeoverrideyml-file-for-the-mongodb-connection-string"></a>MongoDB bağlantı dizesi için Docker-Compose. override. yıml dosyasında bir env-var kullanın

Mongoclient nesnesi oluştururken doğru veritabanına işaret eden bir `ConnectionString` parametre olan temel bir parametreye ihtiyacı vardır. EShopOnContainers söz konusu olduğunda, bağlantı dizesi bir yerel MongoDB Docker kapsayıcısına veya bir "üretim" Azure Cosmos DB veritabanına işaret edebilir.  Bu bağlantı dizesi, aşağıdaki-ml kodunda olduğu gibi Docker-Compose veya Visual Studio ile dağıtım yaparken kullanılan `docker-compose.override.yml` dosyalarda tanımlanan ortam değişkenlerinden gelir.

```yml
# docker-compose.override.yml
version: '3.4'
services:
  # Other services
  locations.api:
    environment:
      # Other settings
      - ConnectionString=${ESHOP_AZURE_COSMOSDB:-mongodb://nosql.data}

```

`ConnectionString` Ortam değişkeni şu şekilde çözümlenir: Genel değişken `.env` dosyada Azure Cosmos DB bağlantı dizesiyle tanımlanmışsa, Bulutta Azure Cosmos db veritabanına erişmek için onu kullanır. `ESHOP_AZURE_COSMOSDB` Tanımlı değilse, mongodb://nosql.data değerini alır ve geliştirme MongoDB kapsayıcısını kullanır.

Aşağıdaki kod, eshoponcontainers içinde uygulandığı gibi Azure Cosmos DB bağlantı dizesi genel ortam değişkeniyle birlikte `.env` dosyayı gösterir:

```yml
# .env file, in eShopOnContainers root folder
# Other Docker environment variables

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost
ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=<YourDockerHostIP>

#ESHOP_AZURE_COSMOSDB=<YourAzureCosmosDBConnData>

#Other environment variables for additional Azure infrastructure assets
#ESHOP_AZURE_REDIS_BASKET_DB=<YourAzureRedisBasketInfo>
#ESHOP_AZURE_STORAGE_CATALOG_URL=<YourAzureStorage_Catalog_BLOB_URL>
#ESHOP_AZURE_SERVICE_BUS=<YourAzureServiceBusInfo>
```

ESHOP_AZURE_COSMOSDB satırının açıklamasını kaldırın ve [bir MongoDB uygulamasını Azure Cosmos DB 'e bağlama](https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account)bölümünde açıklandığı gibi Azure Portal elde edilen Azure Cosmos DB bağlantı dizeniz ile güncelleştirmeniz gerekir.

Genel değişken boşsa, bu, `.env` dosyada açıklama eklendiğinde, bu durumda kapsayıcı, şu şekilde adlandırılan eshoponcontainers içinde dağıtılan yerel MongoDB kapsayıcısını işaret eden bir varsayılan MongoDB bağlantı dizesi kullanır. `ESHOP_AZURE_COSMOSDB` `nosql.data`ve, aşağıdaki. yıml kodunda gösterildiği gibi Docker-Compose dosyasında tanımlanmıştır. 

``` yml
# docker-compose.yml
version: '3.4'
services:
  # ...Other services...
  nosql.data:
    image: mongo
```

#### <a name="additional-resources"></a>Ek kaynaklar

- **NoSQL veritabanları için belge verilerini modelleme** \
  <https://docs.microsoft.com/azure/cosmos-db/modeling-data>

- **Vaughn versuz. Ideal etki alanı odaklı tasarım toplama deposu?** \
  <https://kalele.io/blog-posts/the-ideal-domain-driven-design-aggregate-store/>

- **Azure Cosmos DB giriş: MongoDB için API**  \
  <https://docs.microsoft.com/azure/cosmos-db/mongodb-introduction>

- **Azure Cosmos DB: .NET ve Azure portal bir MongoDB API web uygulaması oluşturun**  \
  [https://docs.microsoft.com/azure/cosmos-db/create-mongodb-dotnet](https://docs.microsoft.com/azure/cosmos-db/create-mongodb-dotnet )

- **Yerel geliştirme ve test için Azure Cosmos DB öykünücüsü kullanma**  \
  <https://docs.microsoft.com/azure/cosmos-db/local-emulator>

- **MongoDB uygulamasını Azure Cosmos DB bağlama**  \
  <https://docs.microsoft.com/azure/cosmos-db/connect-mongodb-account>

- **Cosmos DB öykünücü Docker görüntüsü (Windows kapsayıcısı)**   \
  <https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator/>

- **MongoDB Docker görüntüsü (Linux ve Windows kapsayıcısı)**   \
  <https://hub.docker.com/_/mongo/>

- **MongoChef (Studio 3T) öğesini bir Azure Cosmos DB kullanın: MongoDB hesabı için API**  \
  <https://docs.microsoft.com/azure/cosmos-db/mongodb-mongochef>

>[!div class="step-by-step"]
>[Önceki](infrastructure-persistence-layer-implemenation-entity-framework-core.md)İleri
>[](microservice-application-layer-web-api-design.md)
