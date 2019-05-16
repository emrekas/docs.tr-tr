---
title: Ocelot ile API Ağ Geçitlerini uygulama
description: API ağ geçitleri ile Ocelot uygular ve kapsayıcı tabanlı bir ortamda Ocelot kullanmayı öğrenin.
ms.date: 10/02/2018
ms.openlocfilehash: 2a1c7b0f4baa979864ac32d555f65397531884b8
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644539"
---
# <a name="implement-api-gateways-with-ocelot"></a><span data-ttu-id="7455c-103">API ağ geçitleri ile Ocelot uygular</span><span class="sxs-lookup"><span data-stu-id="7455c-103">Implement API Gateways with Ocelot</span></span>

<span data-ttu-id="7455c-104">Mikro hizmet başvurusu [hizmetine](https://github.com/dotnet-architecture/eShopOnContainers) kullanıyor [Ocelot](https://github.com/ThreeMammals/Ocelot), basit ve basit API dağıtabileceğiniz herhangi bir yere, mikro hizmetler/kapsayıcılar ile birlikte olduğu gibi ağ geçidi herhangi bir hizmetine tarafından kullanılan aşağıdaki ortamları.</span><span class="sxs-lookup"><span data-stu-id="7455c-104">The reference microservice application [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) is using [Ocelot](https://github.com/ThreeMammals/Ocelot), a simple and lightweight API Gateway that you can deploy anywhere along with your microservices/containers, such as in any of the following environments used by eShopOnContainers.</span></span>

- <span data-ttu-id="7455c-105">Docker konağı, yerel geliştirme PC, şirket içinde veya bulutta.</span><span class="sxs-lookup"><span data-stu-id="7455c-105">Docker host, in your local dev PC, on-premises or in the cloud.</span></span>
- <span data-ttu-id="7455c-106">Kubernetes kümenizi şirket içinde veya Azure Kubernetes Service (AKS) gibi yönetilen bulut.</span><span class="sxs-lookup"><span data-stu-id="7455c-106">Kubernetes cluster, on-premises or in managed cloud such as Azure Kubernetes Service (AKS).</span></span>
- <span data-ttu-id="7455c-107">Service Fabric kümesi, şirket içi veya bulutta.</span><span class="sxs-lookup"><span data-stu-id="7455c-107">Service Fabric cluster, on-premises or in the cloud.</span></span>
- <span data-ttu-id="7455c-108">Azure PaaS/sunucusuz olarak Service Fabric kafes.</span><span class="sxs-lookup"><span data-stu-id="7455c-108">Service Fabric mesh, as PaaS/Serverless in Azure.</span></span>

## <a name="architect-and-design-your-api-gateways"></a><span data-ttu-id="7455c-109">Mimari ve tasarım, API ağ geçitleri</span><span class="sxs-lookup"><span data-stu-id="7455c-109">Architect and design your API Gateways</span></span>

<span data-ttu-id="7455c-110">Aşağıdaki Mimari diyagram, API ağ geçitleri ile Ocelot hizmetine içinde nasıl uygulandığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="7455c-110">The following architecture diagram shows how API Gateways are implemented with Ocelot in eShopOnContainers.</span></span>

![istemci uygulamaları, mikro hizmetler ve API ağ geçitleri arasında gösteren hizmetine mimarisi diyagramı](./media/image28.png)

<span data-ttu-id="7455c-112">**Şekil 6-28**.</span><span class="sxs-lookup"><span data-stu-id="7455c-112">**Figure 6-28**.</span></span> <span data-ttu-id="7455c-113">API ağ geçitleri ile hizmetine mimarisi</span><span class="sxs-lookup"><span data-stu-id="7455c-113">eShopOnContainers architecture with API Gateways</span></span>

<span data-ttu-id="7455c-114">Bu diyagram, tek bir Docker konağı ya da geliştirme PC "Windows için Docker" veya "Docker için Mac" tüm uygulamayı nasıl dağıtılacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="7455c-114">That diagram shows how the whole application is deployed into a single Docker host or development PC with “Docker for Windows” or “Docker for Mac”.</span></span> <span data-ttu-id="7455c-115">Tüm orchestrator dağıtma oldukça benzer olacaktır ancak diyagramında herhangi bir kapsayıcı orchestrator'da genişletilmiş.</span><span class="sxs-lookup"><span data-stu-id="7455c-115">However, deploying into any orchestrator would be pretty similar but any container in the diagram could be scaled-out in the orchestrator.</span></span>

<span data-ttu-id="7455c-116">Ayrıca, veritabanları, önbellek ve ileti aracıları gibi altyapı varlıkları orchestrator'dan boşaltılmamalıdır ve Azure Service Bus, Azure SQL veritabanı, Azure Cosmos DB, Azure Redis, altyapısı için yüksek kullanılabilir sistemleri içine dağıtılan, ya da şirket içi çözüm kümeleme herhangi bir HA.</span><span class="sxs-lookup"><span data-stu-id="7455c-116">In addition, the infrastructure assets such as databases, cache, and message brokers should be offloaded from the orchestrator and deployed into high available systems for infrastructure, like Azure SQL Database, Azure Cosmos DB, Azure Redis, Azure Service Bus, or any HA clustering solution on-premises.</span></span>

<span data-ttu-id="7455c-117">Diyagramda da olduğunu fark edebilirsiniz gibi birkaç API ağ geçidine sahip birden çok geliştirme takımları (Bu durumda özellikleri vs pazarlama. otonom olmasını sağlar Özellikleri alışveriş) geliştirme ve kendi mikro hizmetlerin yanı sıra kendi ilgili API ağ geçitleri dağıtma.</span><span class="sxs-lookup"><span data-stu-id="7455c-117">As you can also notice in the diagram, having several API Gateways allows multiple development teams to be autonomous (in this case Marketing features vs. Shopping features) when developing and deploying their microservices plus their own related API Gateways.</span></span>

<span data-ttu-id="7455c-118">Tek bir uygulamanın parçası tüm mikro hizmetler halinde birleştirebilir birkaç geliştirme takımı tarafından güncelleştirilmesi için tek bir nokta açardı bir tek tek parça API Gateway tablonuz varsa.</span><span class="sxs-lookup"><span data-stu-id="7455c-118">If you had a single monolithic API Gateway that would mean a single point to be updated by several development teams, which could couple all the microservices with a single part of the application.</span></span>

<span data-ttu-id="7455c-119">Çok daha tasarımında giderek, bazı durumlarda ayrıntılı bir API ağ geçidi de bir tek iş mikro hizmet seçilen mimarisine bağlı olarak sınırlı olabilir.</span><span class="sxs-lookup"><span data-stu-id="7455c-119">Going much further in the design, sometimes a fine-grained API Gateway can also be limited to a single business microservice depending on the chosen architecture.</span></span> <span data-ttu-id="7455c-120">API ağ geçidinin sınırları iş veya etki alanı tarafından dikte sahip daha iyi bir tasarım elde etmenize yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="7455c-120">Having the API Gateway’s boundaries dictated by the business or domain will help you to get a better design.</span></span>

<span data-ttu-id="7455c-121">Örneğin, kavramı ayrıntılı bir API ağ geçidi, bir kullanıcı Arabirimi oluşturma hizmetine benzer olduğundan ince ayrıntılı olmasını API ağ geçidi katmanındaki üzerinde mikro hizmetler, alan daha gelişmiş bileşik kullanıcı Arabirimi uygulamalar için özellikle kullanışlı olabilir.</span><span class="sxs-lookup"><span data-stu-id="7455c-121">For instance, fine granularity in the API Gateway tier can be especially useful for more advanced composite UI applications that are based on microservices, because the concept of a fine-grained API Gateway is similar to a UI composition service.</span></span>

<span data-ttu-id="7455c-122">Biz önceki bölümde daha fazla ayrıntıya delve [üzerinde mikro hizmet tabanlı bileşik kullanıcı Arabirimi oluşturma](../architect-microservice-container-applications/microservice-based-composite-ui-shape-layout.md).</span><span class="sxs-lookup"><span data-stu-id="7455c-122">We delve into more details in the previous section [Creating composite UI based on microservices](../architect-microservice-container-applications/microservice-based-composite-ui-shape-layout.md).</span></span>

<span data-ttu-id="7455c-123">Güvenebileceğinizdir özel olarak geliştirilmiş bir API ağ geçidi kullanarak birçok Orta ve büyük-ölçekli uygulamalar için genellikle iyi bir yaklaşım olduğu gibi ancak tek tek parça toplayıcısı veya benzersiz merkezi özel API ağ geçidi olarak değil, API ağ geçidi, birden çok bağımsız izin vermesi dışında otonom mikro hizmetler oluşturma birkaç geliştirme ekipleri için yapılandırma alanları.</span><span class="sxs-lookup"><span data-stu-id="7455c-123">As key takeaway, for many medium- and large-size applications, using a custom-built API Gateway product is usually a good approach, but not as a single monolithic aggregator or unique central custom API Gateway unless that API Gateway allows multiple independent configuration areas for the several development teams creating autonomous microservices.</span></span>

### <a name="sample-microservicescontainers-to-re-route-through-the-api-gateways"></a><span data-ttu-id="7455c-124">Örnek mikro hizmetler / API ağ geçitleri yeniden yönlendirmek için kapsayıcılar</span><span class="sxs-lookup"><span data-stu-id="7455c-124">Sample microservices/containers to re-route through the API Gateways</span></span>

<span data-ttu-id="7455c-125">Örneğin, hizmetine yaklaşık altı iç mikro hizmet-API ağ geçitleri yayımlanmasını aşağıdaki görüntüde gösterildiği gibi sahip türleri vardır.</span><span class="sxs-lookup"><span data-stu-id="7455c-125">As an example, eShopOnContainers has around six internal microservice-types that have to be published through the API Gateways, as shown in the following image.</span></span>

![Yalnızca sepet, katalog, konum, pazarlama, sıralama ve ödeme mikro hizmetler API ağ geçidi üzerinden yayımlanır.](./media/image29.png)

<span data-ttu-id="7455c-127">**Şekil 6-29**.</span><span class="sxs-lookup"><span data-stu-id="7455c-127">**Figure 6-29**.</span></span> <span data-ttu-id="7455c-128">Mikro hizmet klasörlerinde hizmetine çözümünü Visual Studio'da</span><span class="sxs-lookup"><span data-stu-id="7455c-128">Microservice folders in eShopOnContainers solution in Visual Studio</span></span>

<span data-ttu-id="7455c-129">Kimlik hizmeti hakkında tasarımında, API ile Ocelot da rerouting listeleri bir parçası olarak dahil etmek mümkündür ancak, çapraz önemli bir sistemde olduğundan yönlendirme ağ geçidi dışında bırakılır.</span><span class="sxs-lookup"><span data-stu-id="7455c-129">About the Identity service, in the design it's left out of the API Gateway routing because it's the only cross-cutting concern in the system, although with Ocelot it's also possible to include it as part of the rerouting lists.</span></span>

<span data-ttu-id="7455c-130">Koddan söyleyebilirsiniz gibi bu hizmetler şu anda ASP.NET Core Web API Hizmetleri olarak uygulanır.</span><span class="sxs-lookup"><span data-stu-id="7455c-130">All those services are currently implemented as ASP.NET Core Web API services, as you can tell from the code.</span></span> <span data-ttu-id="7455c-131">Bir mikro hizmet Kataloğu mikro hizmet kodu gibi odaklanalım.</span><span class="sxs-lookup"><span data-stu-id="7455c-131">Let’s focus on one of the microservices like the Catalog microservice code.</span></span>

![Çözüm Gezgini görünümü Catalog.API proje.](./media/image30.png)

<span data-ttu-id="7455c-133">**Şekil 6-30**.</span><span class="sxs-lookup"><span data-stu-id="7455c-133">**Figure 6-30**.</span></span> <span data-ttu-id="7455c-134">Örnek Web API'si mikro hizmet (katalog mikro hizmet)</span><span class="sxs-lookup"><span data-stu-id="7455c-134">Sample Web API microservice (Catalog microservice)</span></span>

<span data-ttu-id="7455c-135">Tipik bir ASP.NET Core Web API'si projesi birkaç denetleyicileriyle Kataloğu mikro hizmetidir ve yöntemleri aşağıdaki kodda ister görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7455c-135">You can see that the Catalog microservice is a typical ASP.NET Core Web API project with several controllers and methods like in the following code.</span></span>

```csharp
[HttpGet]
[Route("items/{id:int}")]
[ProducesResponseType((int)HttpStatusCode.BadRequest)]
[ProducesResponseType((int)HttpStatusCode.NotFound)]
[ProducesResponseType(typeof(CatalogItem),(int)HttpStatusCode.OK)]
public async Task<IActionResult> GetItemById(int id)
{
    if (id <= 0)
    {
        return BadRequest();
    }
    var item = await _catalogContext.CatalogItems.
                                          SingleOrDefaultAsync(ci => ci.Id == id);
    //…

    if (item != null)
    {
        return Ok(item);
    }
    return NotFound();
}
```

<span data-ttu-id="7455c-136">HTTP isteği, tür çalışan sona erecek C# kod mikro hizmet veritabanı ve gerekli herhangi bir ek eylem erişme.</span><span class="sxs-lookup"><span data-stu-id="7455c-136">The HTTP request will end up running that kind of C# code accessing the microservice database and any additional required action.</span></span>

<span data-ttu-id="7455c-137">Mikro hizmet URL'si ile ilgili kapsayıcıları, yerel geliştirme bilgisayar (yerel Docker konağı) dağıtıldığında, her bir mikro hizmetin ait kapsayıcı her zaman dahili bir bağlantı vardır. (genellikle, bağlantı noktası 80) aşağıdaki dockerfile olduğu gibi ilgili dockerfile içinde belirtilen:</span><span class="sxs-lookup"><span data-stu-id="7455c-137">Regarding the microservice URL, when the containers are deployed in your local development PC (local Docker host), each microservice’s container has always an internal port (usually port 80) specified in its dockerfile, as in the following dockerfile:</span></span>

```Dockerfile
FROM microsoft/aspnetcore:2.0.5 AS base
WORKDIR /app
EXPOSE 80
```

<span data-ttu-id="7455c-138">Bağlantı noktası 80 kodda gösterildiği bir Docker konağı içinde iç olduğundan istemci uygulamalar tarafından erişilemiyor.</span><span class="sxs-lookup"><span data-stu-id="7455c-138">The port 80 shown in the code is internal within the Docker host, so it can't be reached by client apps.</span></span>

<span data-ttu-id="7455c-139">İstemci uygulamaları ile dağıtım yaparken yayımlanan yalnızca dış bağlantı noktaları (varsa) erişim `docker-compose`.</span><span class="sxs-lookup"><span data-stu-id="7455c-139">Client apps can access only the external ports (if any) published when deploying with `docker-compose`.</span></span>

<span data-ttu-id="7455c-140">Dış bağlantı noktalarından bir üretim ortamına dağıtma yaparken yayımlanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="7455c-140">Those external ports shouldn't be published when deploying to a production environment.</span></span> <span data-ttu-id="7455c-141">API ağ geçidi istemci uygulamalar ve mikro hizmetler arasında doğrudan iletişim önlemek için kullanmak istediğiniz neden tam olarak budur.</span><span class="sxs-lookup"><span data-stu-id="7455c-141">This is precisely why you want to use the API Gateway, to avoid the direct communication between the client apps and the microservices.</span></span>

<span data-ttu-id="7455c-142">Ancak, geliştirirken, mikro hizmet/kapsayıcı doğrudan erişim Swagger çalıştırmak istediğiniz.</span><span class="sxs-lookup"><span data-stu-id="7455c-142">However, when developing, you want to access the microservice/container directly and run it through Swagger.</span></span> <span data-ttu-id="7455c-143">İşte bu nedenle hizmetine, bile bunlar API ağ geçidi veya istemci uygulamalar tarafından kullanılmayacak, dış bağlantı noktaları hala belirtilir.</span><span class="sxs-lookup"><span data-stu-id="7455c-143">That’s why in eShopOnContainers, the external ports are still specified even when they won’t be used by the API Gateway or the client apps.</span></span>

<span data-ttu-id="7455c-144">İşte bir örnek `docker-compose.override.yml` Kataloğu mikro hizmet dosyası:</span><span class="sxs-lookup"><span data-stu-id="7455c-144">Here’s an example of the `docker-compose.override.yml` file for the Catalog microservice:</span></span>

```yml
catalog.api:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - ASPNETCORE_URLS=http://0.0.0.0:80
    - ConnectionString=YOUR_VALUE
    - ... Other Environment Variables
  ports:
    - "5101:80"   # Important: In a production environment you should remove the external port (5101) kept here for microservice debugging purposes.
                  # The API Gateway redirects and access through the internal port (80).
```

<span data-ttu-id="7455c-145">Docker-compose.override.yml yapılandırmada Kataloğu kapsayıcı iç bağlantı noktası 80 numaralı bağlantı noktasını nasıl olduğunu görebilirsiniz, ancak 5101 dış erişim için bağlantı noktasıdır.</span><span class="sxs-lookup"><span data-stu-id="7455c-145">You can see how in the docker-compose.override.yml configuration the internal port for the Catalog container is port 80, but the port for external access is 5101.</span></span> <span data-ttu-id="7455c-146">Ancak, bu bağlantı noktası uygulama tarafından bir API ağ geçidi yalnızca hata ayıklama, çalıştırma ve test yalnızca katalog mikro hizmet kullanırken kullanılmamalıdır.</span><span class="sxs-lookup"><span data-stu-id="7455c-146">But this port shouldn’t be used by the application when using an API Gateway, only to debug, run and test just the Catalog microservice.</span></span>

<span data-ttu-id="7455c-147">Normalde, olmayacaktır ile dağıtma docker-compose bir üretim ortamına mikro Hizmetleri için doğru üretim dağıtım ortamı Kubernetes veya Service Fabric gibi bir orchestrator olduğundan.</span><span class="sxs-lookup"><span data-stu-id="7455c-147">Normally, you won’t be deploying with docker-compose into a production environment because the right production deployment environment for microservices is an orchestrator like Kubernetes or Service Fabric.</span></span> <span data-ttu-id="7455c-148">Bu ortamlar için dağıtım yaparken burada herhangi bir dış bağlantı işlemi mikro hizmetlere yönelik doğrudan yayınlama olmaz ancak API ağ geçidi ters Ara sunucuya her zaman kullanacağınız farklı yapılandırma dosyalarını kullanın.</span><span class="sxs-lookup"><span data-stu-id="7455c-148">When deploying to those environments you use different configuration files where you won’t publish directly any external port for the microservices but, you'll always use the reverse proxy from the API Gateway.</span></span>

<span data-ttu-id="7455c-149">Katalog mikro hizmet, yerel bir Docker konağı tam hizmetine çözüm Visual Studio'da çalıştırarak ya da Çalıştır (docker'da tüm hizmetleri çalıştıracaksınız-compose dosyası) veya yeni katalog mikro hizmet aşağıdaki docker ile başlayan-compose CMD ya da klasör konumlandırılmış PowerShell komutunu burada `docker-compose.yml` ve docker-compose.override.yml yerleştirilir.</span><span class="sxs-lookup"><span data-stu-id="7455c-149">Run the catalog microservice in your local Docker host either by running the full eShopOnContainers solution from Visual Studio (it’ll run all the services in the docker-compose files) or just starting the Catalog microservice with the following docker-compose command in CMD or PowerShell positioned at the folder where the `docker-compose.yml` and docker-compose.override.yml are placed.</span></span>

```console
docker-compose run --service-ports catalog.api
```

<span data-ttu-id="7455c-150">Bu komut yalnızca catalog.api hizmet kapsayıcı yanı sıra docker-compose.yml belirtilen bağımlılıkları çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="7455c-150">This command only runs the catalog.api service container plus dependencies that are specified in the docker-compose.yml.</span></span> <span data-ttu-id="7455c-151">Bu durumda SQL Server kapsayıcı ve RabbitMQ kapsayıcı.</span><span class="sxs-lookup"><span data-stu-id="7455c-151">In this case, the SQL Server container and RabbitMQ container.</span></span>

<span data-ttu-id="7455c-152">Ardından, doğrudan Kataloğu mikro hizmet erişebilir ve kendi yöntemlerini doğrudan aracılığıyla "dış", bu durumda numaralı bağlantı noktasını erişme Swagger UI aracılığıyla görmek `http://localhost:5101/swagger`:</span><span class="sxs-lookup"><span data-stu-id="7455c-152">Then, you can directly access the Catalog microservice and see its methods through the Swagger UI accessing directly through that “external” port, in this case `http://localhost:5101/swagger`:</span></span>

![Catalog.API REST API için Swagger kullanıcı arabirimini yaşında tarayıcı görünümü.](./media/image31.png)

<span data-ttu-id="7455c-154">**Şekil 6-31**.</span><span class="sxs-lookup"><span data-stu-id="7455c-154">**Figure 6-31**.</span></span> <span data-ttu-id="7455c-155">Katalog mikro hizmet kendi Swagger kullanıcı Arabirimi ile test etme</span><span class="sxs-lookup"><span data-stu-id="7455c-155">Testing the Catalog microservice with its Swagger UI</span></span>

<span data-ttu-id="7455c-156">Bu noktada, Visual Studio'da C# kod bir kesme noktası ayarlayın, mikro hizmet Swagger kullanıcı Arabiriminde kullanıma sunulan yöntemleri test ve son olan her şeyi Temizleme `docker-compose down` komutu.</span><span class="sxs-lookup"><span data-stu-id="7455c-156">At this point, you could set a breakpoint in C# code in Visual Studio, test the microservice with the methods exposed in Swagger UI, and finally clean-up everything with the `docker-compose down` command.</span></span>

<span data-ttu-id="7455c-157">Ancak, doğrudan erişim mikro hizmet için bu durumda harici bağlantı noktası üzerinden 5101 tam olarak uygulamanızda önlemek istediğiniz iletişimdir.</span><span class="sxs-lookup"><span data-stu-id="7455c-157">However, direct-access communication to the microservice, in this case through the external port 5101, is precisely what you want to avoid in your application.</span></span> <span data-ttu-id="7455c-158">Ve ek API ağ geçidinin (Bu durumda, Ocelot) yöneltme düzeyi ayarlayarak, önleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7455c-158">And you can avoid that by setting the additional level of indirection of the API Gateway (Ocelot, in this case).</span></span> <span data-ttu-id="7455c-159">Bu şekilde, istemci uygulaması doğrudan mikro hizmet erişimi olmaz.</span><span class="sxs-lookup"><span data-stu-id="7455c-159">That way, the client app won’t directly access the microservice.</span></span>

## <a name="implementing-your-api-gateways-with-ocelot"></a><span data-ttu-id="7455c-160">API ağ Geçitlerinizi Ocelot ile uygulama</span><span class="sxs-lookup"><span data-stu-id="7455c-160">Implementing your API Gateways with Ocelot</span></span>

<span data-ttu-id="7455c-161">Ocelot temel olarak, belirli bir sırayla uygulayabileceğiniz middlewares kümesidir.</span><span class="sxs-lookup"><span data-stu-id="7455c-161">Ocelot is basically a set of middlewares that you can apply in a specific order.</span></span>

<span data-ttu-id="7455c-162">Ocelot, yalnızca ASP.NET Core ile çalışacak şekilde tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="7455c-162">Ocelot is designed to work with ASP.NET Core only.</span></span> <span data-ttu-id="7455c-163">Bu nedenle, .NET Standard 2.0 desteklenir, .NET Core 2.0 çalışma zamanı ve .NET Framework 4.6.1 çalışma zamanı dahil her yerde kullanılabilir ve yedekleme netstandard2.0 hedefler.</span><span class="sxs-lookup"><span data-stu-id="7455c-163">It targets netstandard2.0 so it can be used anywhere .NET Standard 2.0 is supported, including .NET Core 2.0 runtime and .NET Framework 4.6.1 runtime and up.</span></span>

<span data-ttu-id="7455c-164">ASP.NET Core projenizdeki Ocelot ve bağımlılıklarını yüklemek [Ocelot'ın NuGet paketini](https://www.nuget.org/packages/Ocelot/), Visual Studio'dan.</span><span class="sxs-lookup"><span data-stu-id="7455c-164">You install Ocelot and its dependencies in your ASP.NET Core project with [Ocelot's NuGet package](https://www.nuget.org/packages/Ocelot/), from Visual Studio.</span></span>

```powershell
Install-Package Ocelot
```

<span data-ttu-id="7455c-165">Hizmetine, basit bir ASP.NET Core Web barındırma proje kendi API ağ geçidi uygulamasıdır ve Ocelot'ın middlewares API ağ geçidi özellikleri aşağıdaki görüntüde gösterildiği gibi işleme:</span><span class="sxs-lookup"><span data-stu-id="7455c-165">In eShopOnContainers, its API Gateway implementation is a simple ASP.NET Core WebHost project, and Ocelot’s middlewares handle all the API Gateway features, as shown in the following image:</span></span>

![Çözüm Gezgini görünümü Ocelot API ağ geçidi proje.](./media/image32.png)

<span data-ttu-id="7455c-167">**Şekil 6-32**.</span><span class="sxs-lookup"><span data-stu-id="7455c-167">**Figure 6-32**.</span></span> <span data-ttu-id="7455c-168">Hizmetine OcelotApiGw temel proje</span><span class="sxs-lookup"><span data-stu-id="7455c-168">The OcelotApiGw base project in eShopOnContainers</span></span>

<span data-ttu-id="7455c-169">Bu ASP.NET Core Web barındırma proje temelde iki basit dosyalarıyla oluşturulmuştur: `Program.cs` ve `Startup.cs`.</span><span class="sxs-lookup"><span data-stu-id="7455c-169">This ASP.NET Core WebHost project is basically built with two simple files:  `Program.cs` and `Startup.cs`.</span></span>

<span data-ttu-id="7455c-170">Program.cs yalnızca oluşturulup tipik ASP.NET Core BuildWebHost yapılandırılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="7455c-170">The Program.cs just needs to create and configure the typical ASP.NET Core BuildWebHost.</span></span>

```csharp
namespace OcelotApiGw
{
    public class Program
    {
        public static void Main(string[] args)
        {
            BuildWebHost(args).Run();
        }

        public static IWebHost BuildWebHost(string[] args)
        {
            var builder = WebHost.CreateDefaultBuilder(args);

            builder.ConfigureServices(s => s.AddSingleton(builder))
                    .ConfigureAppConfiguration(
                          ic => ic.AddJsonFile(Path.Combine("configuration",
                                                            "configuration.json")))
                    .UseStartup<Startup>();
            var host = builder.Build();
            return host;
        }
    }
}
```

<span data-ttu-id="7455c-171">Önemli nokta burada Ocelot için `configuration.json` Oluşturucu sağlaması gereken dosya `AddJsonFile()` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="7455c-171">The important point here for Ocelot is the `configuration.json` file that you must provide to the builder through the `AddJsonFile()` method.</span></span> <span data-ttu-id="7455c-172">Olduğunu `configuration.json` , tüm API ağ geçidi belirli bağlantı noktaları ile dış uç noktaları ve ilişkili iç uç nokta yani genellikle farklı bağlantı noktalarını kullanarak ReRoutes, belirttiğiniz yerdir.</span><span class="sxs-lookup"><span data-stu-id="7455c-172">That `configuration.json` is where you specify all the API Gateway ReRoutes, meaning the external endpoints with specific ports and the correlated internal endpoints, usually using different ports.</span></span>

```json
{
    "ReRoutes": [],
    "GlobalConfiguration": {}
}
```

<span data-ttu-id="7455c-173">Yapılandırma için iki bölümü vardır.</span><span class="sxs-lookup"><span data-stu-id="7455c-173">There are two sections to the configuration.</span></span> <span data-ttu-id="7455c-174">Yeniden yönlendirir ve bir GlobalConfiguration dizisi.</span><span class="sxs-lookup"><span data-stu-id="7455c-174">An array of Re-Routes and a GlobalConfiguration.</span></span> <span data-ttu-id="7455c-175">Yeniden yönlendiren bir Yukarı Akış isteği işlemek nasıl Ocelot bildiren nesneleridir.</span><span class="sxs-lookup"><span data-stu-id="7455c-175">The Re-Routes are the objects that tell Ocelot how to treat an upstream request.</span></span> <span data-ttu-id="7455c-176">Genel yapılandırma geçersiz kılmalarına yönelik özel ayarları yeniden yönlendirme sağlar.</span><span class="sxs-lookup"><span data-stu-id="7455c-176">The Global configuration allows overrides of Re-Route specific settings.</span></span> <span data-ttu-id="7455c-177">Yeniden yönlendirme belirli ayarları çok sayıda yönetmek istemiyorsanız yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="7455c-177">It’s useful if you don’t want to manage lots of Re-Route specific settings.</span></span>

<span data-ttu-id="7455c-178">İşte basit bir örnek [yöneltme yapılandırma dosyası](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/ApiGateways/Web.Bff.Shopping/apigw/configuration.json) hizmetine API Gateway'lerinden birinin.</span><span class="sxs-lookup"><span data-stu-id="7455c-178">Here’s a simplified example of [ReRoute configuration file](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/ApiGateways/Web.Bff.Shopping/apigw/configuration.json) from one of the API Gateways from eShopOnContainers.</span></span>

```json
{
  "ReRoutes": [
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "catalog.api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/c/{everything}",
      "UpstreamHttpMethod": [ "POST", "PUT", "GET" ]
    },
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket.api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/b/{everything}",
      "UpstreamHttpMethod": [ "POST", "PUT", "GET" ],
      "AuthenticationOptions": {
        "AuthenticationProviderKey": "IdentityApiKey",
        "AllowedScopes": []
      }
    }

  ],
    "GlobalConfiguration": {
      "RequestIdKey": "OcRequestId",
      "AdministrationPath": "/administration"
    }
  }
```

<span data-ttu-id="7455c-179">Bir Ocelot API ağ geçidi ana işlevlerini olan gelen HTTP isteklerini almak ve bunları bir aşağı akış hizmeti açın iletebilir, şu anda başka bir HTTP isteği.</span><span class="sxs-lookup"><span data-stu-id="7455c-179">The main functionality of an Ocelot API Gateway is to take incoming HTTP requests and forward them on to a downstream service, currently as another HTTP request.</span></span> <span data-ttu-id="7455c-180">Ocelot'ın başka bir yeniden yönlendirmek için bir istek yönlendirme açıklar.</span><span class="sxs-lookup"><span data-stu-id="7455c-180">Ocelot’s describes the routing of one request to another as a Re-Route.</span></span>

<span data-ttu-id="7455c-181">Örneğin, şimdi yeniden yönlendirir, yukarıdaki, sepet mikro hizmet yapılandırmasını configuration.json birini odaklanır.</span><span class="sxs-lookup"><span data-stu-id="7455c-181">For instance, let’s focus on one of the Re-Routes in the configuration.json from above, the configuration for the Basket microservice.</span></span>

```json
{
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket.api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/b/{everything}",
      "UpstreamHttpMethod": [ "POST", "PUT", "GET" ],
      "AuthenticationOptions": {
        "AuthenticationProviderKey": "IdentityApiKey",
        "AllowedScopes": []
      }
}
```

<span data-ttu-id="7455c-182">Bu istek için iletilir iç mikro hizmet URL'si DownstreamPathTemplate, şema ve DownstreamHostAndPorts olun.</span><span class="sxs-lookup"><span data-stu-id="7455c-182">The DownstreamPathTemplate, Scheme, and DownstreamHostAndPorts make the internal microservice URL that this request will be forwarded to.</span></span>

<span data-ttu-id="7455c-183">Bağlantı, hizmet tarafından kullanılan iç bağlantı noktasıdır.</span><span class="sxs-lookup"><span data-stu-id="7455c-183">The port is the internal port used by the service.</span></span> <span data-ttu-id="7455c-184">Kapsayıcıları kullanarak, bağlantı noktası ilgili dockerfile belirtilmiş.</span><span class="sxs-lookup"><span data-stu-id="7455c-184">When using containers, the port specified at its dockerfile.</span></span>

<span data-ttu-id="7455c-185">`Host` Kullandığınız hizmet adı çözünürlüğüne bağlıdır hizmet adıdır.</span><span class="sxs-lookup"><span data-stu-id="7455c-185">The `Host` is a service name that depends on the service name resolution you are using.</span></span> <span data-ttu-id="7455c-186">Kullanarak docker-compose adları docker'da sağlanan hizmet adları kullanarak Docker konağı tarafından sağlanan hizmetleri-compose dosyası.</span><span class="sxs-lookup"><span data-stu-id="7455c-186">When using docker-compose, the services names are provided by the Docker Host, which is using the service names provided in the docker-compose files.</span></span> <span data-ttu-id="7455c-187">Kubernetes veya Service Fabric gibi bir orchestrator kullanıyorsanız, bu ad DNS ile çözümlenip ya da her orchestrator tarafından sağlanan ad çözümlemesi.</span><span class="sxs-lookup"><span data-stu-id="7455c-187">If using an orchestrator like Kubernetes or Service Fabric, that name should be resolved by the DNS or name resolution provided by each orchestrator.</span></span>

<span data-ttu-id="7455c-188">DownstreamHostAndPorts isteklerini iletmek istediğiniz herhangi bir aşağı akış hizmetleriyle bağlantı noktası ve ana bilgisayar içeren bir dizidir.</span><span class="sxs-lookup"><span data-stu-id="7455c-188">DownstreamHostAndPorts is an array that contains the host and port of any downstream services that you wish to forward requests to.</span></span> <span data-ttu-id="7455c-189">Genellikle bu yalnızca bir giriş içerir, ancak bazen Yük Dengeleme isteklerini, aşağı akış hizmetleriyle isteyebilirsiniz ve Ocelot birden fazla giriş ekleyin ve ardından Yük Dengeleyici seçmenizi sağlar.</span><span class="sxs-lookup"><span data-stu-id="7455c-189">Usually this will just contain one entry but sometimes you might want to load balance requests to your downstream services and Ocelot lets you add more than one entry and then select a load balancer.</span></span> <span data-ttu-id="7455c-190">Ancak, Azure ve tüm orchestrator kullanıyorsanız, Bulut ve orchestrator altyapısıyla dengelemek için çok iyi bir fikir olabilir.</span><span class="sxs-lookup"><span data-stu-id="7455c-190">But if using Azure and any orchestrator it is probably a better idea to load balance with the cloud and orchestrator infrastructure.</span></span>

<span data-ttu-id="7455c-191">UpstreamPathTemplate Ocelot istemciden gelen belirli bir istek için kullanmak için hangi DownstreamPathTemplate tanımlamak için kullanacağı URL'dir.</span><span class="sxs-lookup"><span data-stu-id="7455c-191">The UpstreamPathTemplate is the URL that Ocelot will use to identify which DownstreamPathTemplate to use for a given request from the client.</span></span> <span data-ttu-id="7455c-192">Son olarak, Ocelot farklı isteklerini aynı URL'yi (POST, Al koy) arasında ayrım yapabilme kolaylığı için UpstreamHttpMethod kullanılır.</span><span class="sxs-lookup"><span data-stu-id="7455c-192">Finally, the UpstreamHttpMethod is used so Ocelot can distinguish between different requests (GET, POST, PUT) to the same URL.</span></span>

<span data-ttu-id="7455c-193">Bu noktada, tek bir Ocelot API'sini kullanarak ağ geçidi (ASP.NET Core Web barındırma) sahip olabilir veya [birden çok birleştirilmiş configuration.json dosyaları](https://ocelot.readthedocs.io/en/latest/features/configuration.html#merging-configuration-files) ya da depolayabilirsiniz [yapılandırma Consul KV deposundaki](https://ocelot.readthedocs.io/en/latest/features/configuration.html#store-configuration-in-consul).</span><span class="sxs-lookup"><span data-stu-id="7455c-193">At this point, you could have a single Ocelot API Gateway (ASP.NET Core WebHost) using one or [multiple merged configuration.json files](https://ocelot.readthedocs.io/en/latest/features/configuration.html#merging-configuration-files) or you can also store the [configuration in a Consul KV store](https://ocelot.readthedocs.io/en/latest/features/configuration.html#store-configuration-in-consul).</span></span>

<span data-ttu-id="7455c-194">Ancak gerçekten otonom mikro hizmetler olmasını istiyorsanız, mimari ve tasarım bölümlerinde sunulan gibi birden çok API ağ geçitleri ve/veya BFF (ön uç için arka uç), tek tek parça API ağ geçidi bölün daha iyi olabilir.</span><span class="sxs-lookup"><span data-stu-id="7455c-194">But as introduced in the architecture and design sections, if you really want to have autonomous microservices, it might be better to split that single monolithic API Gateway into multiple API Gateways and/or BFF (Backend for Frontend).</span></span> <span data-ttu-id="7455c-195">Bu amaçla, Docker kapsayıcıları ile bu yaklaşımı uygulamak nasıl bir bakalım.</span><span class="sxs-lookup"><span data-stu-id="7455c-195">For that purpose, let’s see how to implement that approach with Docker containers.</span></span>

### <a name="using-a-single-docker-container-image-to-run-multiple-different-api-gateway--bff-container-types"></a><span data-ttu-id="7455c-196">Birden çok farklı API ağ geçidi'ni çalıştırmak için tek bir Docker kapsayıcı görüntüsü kullanarak / BFF kapsayıcı türleri</span><span class="sxs-lookup"><span data-stu-id="7455c-196">Using a single Docker container image to run multiple different API Gateway / BFF container types</span></span>

<span data-ttu-id="7455c-197">Hizmetine içinde tek bir Docker kapsayıcı görüntüsü Ocelot API ağ geçidi ile kullanıyoruz ancak ardından, çalışma zamanında farklı Hizmetleri/kapsayıcılar API-ağ geçidi/BFF her tür için bir farklı configuration.json dosyası sağlayarak kullanarak bir docker birime oluştururuz Her hizmet için farklı bir bilgisayar klasöre erişin.</span><span class="sxs-lookup"><span data-stu-id="7455c-197">In eShopOnContainers we’re using a single Docker container image with the Ocelot API Gateway but then, at run time, we create different services/containers for each type of API-Gateway/BFF by providing a different configuration.json file, using a docker volume to access a different PC folder for each service.</span></span>

![İçin dört tüm API ağ geçitleri Ocelot API ağ geçidi için tek bir Docker görüntüsü kullanılır](./media/image33.png)

<span data-ttu-id="7455c-199">**Şekil 6-33**.</span><span class="sxs-lookup"><span data-stu-id="7455c-199">**Figure 6-33**.</span></span> <span data-ttu-id="7455c-200">Birden çok API ağ geçidi türleri arasında yeniden tek Ocelot Docker görüntüsü kullanma</span><span class="sxs-lookup"><span data-stu-id="7455c-200">Re-using a single Ocelot Docker image across multiple API Gateway types</span></span>

<span data-ttu-id="7455c-201">Hizmetine "Genel Ocelot API ağ geçidi Docker görüntüsünü" 'OcelotApiGw' adlı proje ile oluşturulur ve görüntünün adı "Elektronik Mağaza/ocelotapigw" yani docker-compose.yml dosyası içinde belirtilen.</span><span class="sxs-lookup"><span data-stu-id="7455c-201">In eShopOnContainers, the “Generic Ocelot API Gateway Docker Image” is created with the project named 'OcelotApiGw' and the image name “eshop/ocelotapigw” that is specified in the docker-compose.yml file.</span></span> <span data-ttu-id="7455c-202">Ardından, Docker için dağıtırken, olacaktır o aynı Docker görüntüden oluşturulan dört API ağ geçidi kapsayıcılar aşağıdaki docker-compose.yml dosyasını ayıklayın de gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="7455c-202">Then, when deploying to Docker, there will be four API-Gateway containers created from that same Docker image, as shown in the following extract from the docker-compose.yml file.</span></span>

```yml
  mobileshoppingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile

  mobilemarketingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile

  webshoppingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile

  webmarketingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile
```

<span data-ttu-id="7455c-203">Ayrıca, aşağıdaki docker-compose.override.yml dosya görebileceğiniz gibi her bir hizmet kapsayıcısı için farklı Ocelot yapılandırma dosyası API ağ geçidi kapsayıcıların arasındaki tek fark, ve çalışma zamanında belirtilen bir Docker birim.</span><span class="sxs-lookup"><span data-stu-id="7455c-203">Additionally, as you can see in the following docker-compose.override.yml file, the only difference between those API Gateway containers is the Ocelot configuration file, which is different for each service container and it's specified at runtime through a Docker volume.</span></span>

```yml
mobileshoppingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity.api
  ports:
    - "5200:80"
  volumes:
    - ./src/ApiGateways/Mobile.Bff.Shopping/apigw:/app/configuration

mobilemarketingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity.api
  ports:
    - "5201:80"
  volumes:
    - ./src/ApiGateways/Mobile.Bff.Marketing/apigw:/app/configuration

webshoppingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity.api
  ports:
    - "5202:80"
  volumes:
    - ./src/ApiGateways/Web.Bff.Shopping/apigw:/app/configuration

webmarketingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity.api
  ports:
    - "5203:80"
  volumes:
    - ./src/ApiGateways/Web.Bff.Marketing/apigw:/app/configuration
```

<span data-ttu-id="7455c-204">Dört API ağ geçitleri üzerindeki aynı Docker görüntüsü tabanlı olduğundan dolayı önceki kod ve Visual Studio Gezgini her belirli iş/BFF tanımlamak için gerekli tek dosya aşağıda gösterildiği gibi API ağ geçidi yalnızca bir configuration.json dosyasıdır.</span><span class="sxs-lookup"><span data-stu-id="7455c-204">Because of that previous code, and as shown in the Visual Studio Explorer below, the only file needed to define each specific business/BFF API Gateway is just a configuration.json file, because the four API Gateways are based on the same Docker image.</span></span>

![Tüm API ağ geçitleri arasındaki tek fark, her birinde bir configuration.json dosyasıdır.](./media/image34.png)

<span data-ttu-id="7455c-206">**Şekil 6-34**.</span><span class="sxs-lookup"><span data-stu-id="7455c-206">**Figure 6-34**.</span></span> <span data-ttu-id="7455c-207">Her API ağ geçidi tanımlamak için gerekli tek dosya / BFF Ocelot ile bir yapılandırma dosyası</span><span class="sxs-lookup"><span data-stu-id="7455c-207">The only file needed to define each API Gateway / BFF with Ocelot is a configuration file</span></span>

<span data-ttu-id="7455c-208">API ağ geçidi ile birden çok API ağ geçitleri arasında bölünmesi sayesinde mikro hizmetler farklı alt kümelerinde üzerinde odaklanarak farklı geliştirme ekipleri bağımsız Ocelot yapılandırma dosyalarını kullanarak kendi API ağ geçitleri yönetebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7455c-208">By splitting the API Gateway into multiple API Gateways, different development teams focusing on different subsets of microservices can manage their own API Gateways by using independent Ocelot configuration files.</span></span> <span data-ttu-id="7455c-209">Ayrıca, aynı anda aynı Ocelot Docker görüntüsünü yeniden kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7455c-209">Plus, at the same time they can reuse the same Ocelot Docker image.</span></span>

<span data-ttu-id="7455c-210">Şimdi, (varsayılan olarak VS hizmetine ServicesAndWebApps.sln solution açarken veya çalışıyor "docker compose up ise" dahil) API ağ geçitleri ile hizmetine çalıştırırsanız, aşağıdaki örnek yolları gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="7455c-210">Now, if you run eShopOnContainers with the API Gateways (included by default in VS when opening eShopOnContainers-ServicesAndWebApps.sln solution or if running “docker-compose up”), the following sample routes will be performed.</span></span>

<span data-ttu-id="7455c-211">Örneğin, Yukarı Akış URL'sini ziyaret `http://localhost:5202/api/v1/c/catalog/items/2/` webshoppingapigw API ağ geçidi tarafından sunulan, aynı sonucu iç akış URL'den aldığınız `http://catalog.api/api/v1/2` aşağıdaki tarayıcı olduğu gibi bir Docker konağı içinde.</span><span class="sxs-lookup"><span data-stu-id="7455c-211">For instance, when visiting the upstream URL `http://localhost:5202/api/v1/c/catalog/items/2/` served by the webshoppingapigw API Gateway, you get the same result from the internal Downstream URL `http://catalog.api/api/v1/2` within the Docker host, as in the following browser.</span></span>

![Bir API ağ geçidi üzerinden giderek Catalog.api yanıt tarayıcı görünümü.](./media/image35.png)

<span data-ttu-id="7455c-213">**Şekil 6-35**.</span><span class="sxs-lookup"><span data-stu-id="7455c-213">**Figure 6-35**.</span></span> <span data-ttu-id="7455c-214">API ağ geçidi tarafından sağlanan URL ile bir mikro hizmet erişme</span><span class="sxs-lookup"><span data-stu-id="7455c-214">Accessing a microservice through a URL provided by the API Gateway</span></span>

<span data-ttu-id="7455c-215">Test veya API 'catalog.api' Docker Konağı (hizmet dahili bir DNS çözümlemesi olduğundan ağ geçidi üzerinden geçirmeden Kataloğu Docker kapsayıcısı (yalnızca, geliştirme ortamı) doğrudan erişmek isterseniz nedeniyle, hata ayıklama nedeniyle tarafından işlenen bulma docker-compose hizmet adları), docker-yalnızca geliştirme testleri için gibi sağlanan compose.override.yml içinde yayımlanan dış bağlantı noktası üzerinden doğrudan kapsayıcısına erişmek için tek yolu olduğundan `http://localhost:5101/api/v1/Catalog/items/1` aşağıdaki Tarayıcı.</span><span class="sxs-lookup"><span data-stu-id="7455c-215">Because of testing or debugging reasons, if you wanted to directly access to the Catalog Docker container (only at the development environment) without passing through the API Gateway, since 'catalog.api' is a DNS resolution internal to the Docker host (service discovery handled by docker-compose service names), the only way to directly access the container is through the external port published in the docker-compose.override.yml, which is provided only for development tests, such as `http://localhost:5101/api/v1/Catalog/items/1` in the following browser.</span></span>

![Tarayıcı Görünümü Catalog.api Catalog.api özdeş bir API ağ geçidi aracılığıyla doğrudan gidip bir yanıt.](./media/image36.png)

<span data-ttu-id="7455c-217">**Şekil 6-36**.</span><span class="sxs-lookup"><span data-stu-id="7455c-217">**Figure 6-36**.</span></span> <span data-ttu-id="7455c-218">Sınama amacıyla bir mikro hizmet doğrudan erişim</span><span class="sxs-lookup"><span data-stu-id="7455c-218">Direct access to a microservice for testing purposes</span></span>

<span data-ttu-id="7455c-219">Ancak, uygulamanın tüm mikro Hizmetleri API ağ geçitleri değil ancak doğrudan bağlantı noktası "kısayolları" eriştiği şekilde yapılandırılır.</span><span class="sxs-lookup"><span data-stu-id="7455c-219">But the application is configured so it accesses all the microservices through the API Gateways, not though the direct port “shortcuts”.</span></span>

### <a name="the-gateway-aggregation-pattern-in-eshoponcontainers"></a><span data-ttu-id="7455c-220">Hizmetine ağ geçidi toplama düzeni</span><span class="sxs-lookup"><span data-stu-id="7455c-220">The Gateway aggregation pattern in eShopOnContainers</span></span>

<span data-ttu-id="7455c-221">Daha önce sunulan, istekleri toplama uygulamak için esnek bir şekilde kod tarafından özel hizmetler ile aynıdır.</span><span class="sxs-lookup"><span data-stu-id="7455c-221">As introduced previously, a flexible way to implement requests aggregation is with custom services, by code.</span></span> <span data-ttu-id="7455c-222">Ayrıca istek toplama uygulayabileceğine [Ocelot istek toplama özelliği](https://ocelot.readthedocs.io/en/latest/features/requestaggregation.html#request-aggregation), ancak gereksinim duyduğunuz kadar esnek olmayabilir.</span><span class="sxs-lookup"><span data-stu-id="7455c-222">You could also implement request aggregation with the [Request Aggregation feature in Ocelot](https://ocelot.readthedocs.io/en/latest/features/requestaggregation.html#request-aggregation), but it might not be as flexible as you need.</span></span> <span data-ttu-id="7455c-223">Bu nedenle, toplama içinde hizmetine uygulamak için seçilen her toplayıcı için açık bir ASP.NET Core Web API'si hizmetleriyle yoludur.</span><span class="sxs-lookup"><span data-stu-id="7455c-223">Therefore, the selected way to implement aggregation in eShopOnContainers is with an explicit ASP.NET Core Web API services for each aggregator.</span></span>

<span data-ttu-id="7455c-224">Bu yaklaşım göre biraz daha Basitleştirilmiş genel mimari diyagramında daha önce gösterilen gösterilmez toplayıcısı Hizmetleri değerlendirirken genişletilmiş gerçeklik API ağ geçidi oluşturma diyagram bileşenidir.</span><span class="sxs-lookup"><span data-stu-id="7455c-224">According to that approach, the API Gateway composition diagram is in reality a bit more extended when considering the aggregator services that are not shown in the simplified global architecture diagram shown previously.</span></span>

<span data-ttu-id="7455c-225">Aşağıdaki diyagramda, toplayıcısı Hizmetleri kendi ilgili API ağ geçitleri ile nasıl çalıştığını görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7455c-225">In the following diagram, you can also see how the aggregator services work with their related API Gateways.</span></span>

![toplayıcısı hizmetlerini gösteren hizmetine mimari.](./media/image37.png)

<span data-ttu-id="7455c-227">**Şekil 6-37**.</span><span class="sxs-lookup"><span data-stu-id="7455c-227">**Figure 6-37**.</span></span> <span data-ttu-id="7455c-228">toplayıcısı Hizmetleri ile hizmetine mimarisi</span><span class="sxs-lookup"><span data-stu-id="7455c-228">eShopOnContainers architecture with aggregator services</span></span>

<span data-ttu-id="7455c-229">Aşağıdaki görüntüde, "Alışveriş" iş alanının üzerinde daha fazla yakınlaştırma toplayıcısı Hizmetleri API ağ geçitleri kullanırken istemci uygulamalar ve mikro hizmetler arasındaki iletişim yoğunluğunu azaltılır görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7455c-229">Zooming in further, on the “Shopping” business area in the following image, you can see that chattiness between the client apps and the microservices is reduced when using the aggregator services in the API Gateways.</span></span>

!["" son istemcisi ile iletişim yoğunluğunu azaltmak için birçok mikro hizmetler yanıttan birleştirme"yanıt çeviren" içinde toplayıcısı hizmetlerini gösteren hizmetine mimarisi yakınlaştırma.](./media/image38.png)

<span data-ttu-id="7455c-231">**Şekil 6-38**.</span><span class="sxs-lookup"><span data-stu-id="7455c-231">**Figure 6-38**.</span></span> <span data-ttu-id="7455c-232">Görüntü toplayıcısı Hizmetleri içinde Yakınlaştır</span><span class="sxs-lookup"><span data-stu-id="7455c-232">Zoom in vision of the Aggregator services</span></span>

<span data-ttu-id="7455c-233">API ağ geçitleri gelen olası istekleri diyagramda gösterilmektedir, nasıl oldukça karmaşık elde edeceğinizi olduğunu fark edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7455c-233">You can notice how when the diagram shows the possible requests coming from the API Gateways it can get pretty complex.</span></span> <span data-ttu-id="7455c-234">Nasıl mavi ok, istemci uygulamalar açısından bakıldığında, Toplayıcı düzeni iletişim yoğunluğu ve iletişimde gecikme süresini azaltarak kullanırken Basitleştirilmiş görebilir, ancak sonuç olarak önemli ölçüde kullanıcı geliştirme deneyimi için Uzak uygulamalara ( uygulamalarını ve mobil uygulamaları SPA), özellikle.</span><span class="sxs-lookup"><span data-stu-id="7455c-234">Although you can see how the arrows in blue would be simplified, from a client apps perspective, when using the aggregator pattern by reducing chattiness and latency in the communication, ultimately significantly improving the user experience for the remote apps (mobile and SPA apps), especially.</span></span>

<span data-ttu-id="7455c-235">"Pazarlama" iş alan ve mikro hizmetler söz konusu olduğunda, toplayıcılardan verileri kullanılmasına gerek yoktu, ancak aynı zamanda gerekirse mümkün olabilir çok basit bir kullanım durumu gösterir.</span><span class="sxs-lookup"><span data-stu-id="7455c-235">In the case of the “Marketing” business area and microservices, it is a very simple use case so there was no need to use aggregators, but it could also be possible, if needed.</span></span>

### <a name="authentication-and-authorization-in-ocelot-api-gateways"></a><span data-ttu-id="7455c-236">Kimlik doğrulama ve yetkilendirme Ocelot API ağ geçitleri</span><span class="sxs-lookup"><span data-stu-id="7455c-236">Authentication and authorization in Ocelot API Gateways</span></span>

<span data-ttu-id="7455c-237">Bir Ocelot API ağ geçidi kullanarak bir ASP.NET Core Web API'si hizmeti gibi kimlik doğrulama hizmeti yerleştirilebilir [IdentityServer](https://identityserver.io/) ölçeği genişletin veya içinde API Ağ Geçidi kimlik doğrulama belirteci sağlama.</span><span class="sxs-lookup"><span data-stu-id="7455c-237">In an Ocelot API Gateway you can sit the authentication service, such as an ASP.NET Core Web API service using [IdentityServer](https://identityserver.io/) providing the auth token, either out or inside the API Gateway.</span></span>

<span data-ttu-id="7455c-238">Hizmetine olduğundan BFF üzerinde birden çok API ağ geçitleri ile sınırlarını kullanarak alan ve işletme alanlarına, kimlik/kimlik doğrulama hizmeti, aşağıdaki diyagramda sarı renkle vurgulandığı API ağ geçitleri dışında bırakılır.</span><span class="sxs-lookup"><span data-stu-id="7455c-238">Since eShopOnContainers is using multiple API Gateways with boundaries based on BFF and business areas, the Identity/Auth service is left out of the API Gateways, as highlighted in yellow in the following diagram.</span></span>

![API ağ geçidi altındaki kimlik mikro hizmet gösteren hizmetine mimarisi diyagramı.](./media/image39.png)

<span data-ttu-id="7455c-240">**Şekil 6-39**.</span><span class="sxs-lookup"><span data-stu-id="7455c-240">**Figure 6-39**.</span></span> <span data-ttu-id="7455c-241">Hizmetine kimlik service konumu</span><span class="sxs-lookup"><span data-stu-id="7455c-241">Position of the Identity service in eShopOnContainers</span></span>

<span data-ttu-id="7455c-242">Ancak, Ocelot ayrıca kimlik/Auth mikro hizmet, bu diğer diyagram olduğu gibi bir API ağ geçidi sınırında oturan destekler.</span><span class="sxs-lookup"><span data-stu-id="7455c-242">However, Ocelot also supports sitting the Identity/Auth microservice within the API Gateway boundary, as in this other diagram.</span></span>

![API ağ geçidi (ağ) altındaki kimlik mikro hizmet ile kimlik doğrulaması: (1) AG kimlik mikro hizmet bir kimlik doğrulama belirteci isteklerini, 2) kimlik mikro hizmet toke AG, kimlik doğrulaması belirtecini kullanarak mikro hizmetler gelen ağ istekleri 3 - 4) döndürür.](./media/image40.png)

<span data-ttu-id="7455c-244">**Şekil 6-40**.</span><span class="sxs-lookup"><span data-stu-id="7455c-244">**Figure 6-40**.</span></span> <span data-ttu-id="7455c-245">Ocelot kimlik doğrulaması</span><span class="sxs-lookup"><span data-stu-id="7455c-245">Authentication in Ocelot</span></span>

<span data-ttu-id="7455c-246">Birden çok BFF (ön uç için arka uç) içinde API ağ geçidi hizmetine uygulama bölündü ve işletme alanlarına API ağ geçitleri, başka bir seçenek gerekir çünkü geniş kapsamlı kritik konular için ek bir API ağ geçidi oluşturmak için eklenmiştir.</span><span class="sxs-lookup"><span data-stu-id="7455c-246">Because eShopOnContainers application has split the API Gateway into multiple BFF (Backend for Frontend) and business areas API Gateways, another option would had been to create an additional API Gateway for cross-cutting concerns.</span></span> <span data-ttu-id="7455c-247">Seçim daha karmaşık bir mikro hizmet adil İmparatoru birden çok geniş kapsamlı kritik konular mikro hizmet mimarisiyle temel.</span><span class="sxs-lookup"><span data-stu-id="7455c-247">That choice would be fair in a more complex microservice based architecture with multiple cross-cutting concerns microservices.</span></span> <span data-ttu-id="7455c-248">Hizmetine içinde yalnızca bir çapraz önemli olduğundan, yalnızca güvenlik hizmeti API ağ geçidi bölgesi dışında Basitlik'ın çok işlemek için karar verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="7455c-248">Since there's only one cross-cutting concern in eShopOnContainers, it was decided to just handle the security service out of the API Gateway realm, for simplicity’s sake.</span></span>

<span data-ttu-id="7455c-249">Uygulama API ağ geçidi düzeyinde güvenli hale getirilmişse, herhangi bir durumda, kimlik doğrulama modülü Ocelot API ağ geçidinin ilk başta güvenli bir mikro hizmet kullanmaya çalışırken ziyaret edilen.</span><span class="sxs-lookup"><span data-stu-id="7455c-249">In any case, if the app is secured at the API Gateway level, the authentication module of the Ocelot API Gateway is visited at first when trying to use any secured microservice.</span></span> <span data-ttu-id="7455c-250">HTTP isteği access_token ile korunan hizmetlerini ziyaret ettiğiniz için erişim belirteci almak için kimliği veya kimlik doğrulama mikro hizmet ziyaret etmek için yeniden yönlendirir.</span><span class="sxs-lookup"><span data-stu-id="7455c-250">That re-directs the HTTP request to visit the Identity or auth microservice to get the access token so you can visit the protected services with the access_token.</span></span>

<span data-ttu-id="7455c-251">Herhangi bir hizmeti API ağ geçidi düzeyinde kimlik doğrulama ile güvenli, ilgili ayarlarının configuration.json AuthenticationProviderKey ayarlayarak yoludur.</span><span class="sxs-lookup"><span data-stu-id="7455c-251">The way you secure with authentication any service at the API Gateway level is by setting the AuthenticationProviderKey in its related settings at the configuration.json.</span></span>

```json
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket.api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/b/{everything}",
      "UpstreamHttpMethod": [],
      "AuthenticationOptions": {
        "AuthenticationProviderKey": "IdentityApiKey",
        "AllowedScopes": []
      }
    }
```

<span data-ttu-id="7455c-252">Ocelot çalıştığında, yeniden yönlendiren AuthenticationOptions.AuthenticationProviderKey bakın ve verilen anahtarla bir kimlik doğrulama sağlayıcısı kayıtlı olup olmadığını denetleyin.</span><span class="sxs-lookup"><span data-stu-id="7455c-252">When Ocelot runs, it will look at the Re-Routes AuthenticationOptions.AuthenticationProviderKey and check that there is an Authentication Provider registered with the given key.</span></span> <span data-ttu-id="7455c-253">Yoksa, ardından Ocelot başlatılamaz.</span><span class="sxs-lookup"><span data-stu-id="7455c-253">If there isn't, then Ocelot will not start up.</span></span> <span data-ttu-id="7455c-254">Ardından varsa, yürütüldüğünde yöneltme bu sağlayıcı kullanacaktır.</span><span class="sxs-lookup"><span data-stu-id="7455c-254">If there is, then the ReRoute will use that provider when it executes.</span></span>

<span data-ttu-id="7455c-255">Ocelot WebHost ile yapılandırıldığından `authenticationProviderKey = "IdentityApiKey"`, ilgili hizmete tüm istekleri herhangi bir kimlik doğrulama belirteci olmadan olduğunda kimlik doğrulama gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="7455c-255">Because the Ocelot WebHost is configured with the `authenticationProviderKey = "IdentityApiKey"`, that will require authentication whenever that service has any requests without any auth token.</span></span>

```csharp
namespace OcelotApiGw
{
    public class Startup
    {
        private readonly IConfiguration _cfg;

        public Startup(IConfiguration configuration) => _cfg = configuration;

        public void ConfigureServices(IServiceCollection services)
        {
            var identityUrl = _cfg.GetValue<string>("IdentityUrl");
            var authenticationProviderKey = "IdentityApiKey";
                         //…
            services.AddAuthentication()
                .AddJwtBearer(authenticationProviderKey, x =>
                {
                    x.Authority = identityUrl;
                    x.RequireHttpsMetadata = false;
                    x.TokenValidationParameters = new Microsoft.IdentityModel.Tokens.TokenValidationParameters()
                    {
                        ValidAudiences = new[] { "orders", "basket", "locations", "marketing", "mobileshoppingagg", "webshoppingagg" }
                    };
                });
            //...
        }
    }
}
```

<span data-ttu-id="7455c-256">Ardından, ayrıca yetkilendirme [Authorize] özniteliği ile mikro hizmetler gibi sepet mikro hizmet denetleyicisi gibi erişilecek herhangi bir kaynak üzerinde ayarlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="7455c-256">Then, you also need to set authorization with the [Authorize] attribute on any resource to be accessed like the microservices, such as in the following Basket microservice controller.</span></span>

```csharp
namespace Microsoft.eShopOnContainers.Services.Basket.API.Controllers
{
    [Route("api/v1/[controller]")]
    [Authorize]
    public class BasketController : Controller
    {
      //...
    }
}
```

<span data-ttu-id="7455c-257">Her bir mikro hizmet içinde tanımlanan hedef kitle ile "sepet" gibi ValidAudiences bağıntılı `AddJwtBearer()` ConfigureServices() başlangıç sınıfın, aşağıdaki kod gibi.</span><span class="sxs-lookup"><span data-stu-id="7455c-257">The ValidAudiences such as “basket” are correlated with the audience defined in each microservice with `AddJwtBearer()` at the ConfigureServices() of the Startup class, such as in the code below.</span></span>

```csharp
// prevent from mapping "sub" claim to nameidentifier.
JwtSecurityTokenHandler.DefaultInboundClaimTypeMap.Clear();

var identityUrl = Configuration.GetValue<string>("IdentityUrl");

services.AddAuthentication(options =>
{
    options.DefaultAuthenticateScheme = JwtBearerDefaults.AuthenticationScheme;
    options.DefaultChallengeScheme = JwtBearerDefaults.AuthenticationScheme;

}).AddJwtBearer(options =>
{
    options.Authority = identityUrl;
    options.RequireHttpsMetadata = false;
    options.Audience = "basket";
});
```

<span data-ttu-id="7455c-258">Güvenli bir mikro hizmet erişmeye çalışırsanız, sepet gibi API ağ geçidi gibi bir yeniden yönlendirme URL'si ile mikro hizmet tabanlı `http://localhost:5202/api/v1/b/basket/1`, sonra da geçerli bir belirteç sağladığınız sürece bir 401 Yetkisiz elde edersiniz.</span><span class="sxs-lookup"><span data-stu-id="7455c-258">If you try to access any secured microservice, like the Basket microservice with a Re-Route URL based on the API Gateway like `http://localhost:5202/api/v1/b/basket/1`, then you’ll get a 401 Unauthorized unless you provide a valid token.</span></span> <span data-ttu-id="7455c-259">Öte yandan, bir yeniden yönlendirme URL'si doğrulanırsa Ocelot herhangi bir aşağı akış düzeni onunla (iç mikro hizmet URL'si) ilişkilendirilen çağırın.</span><span class="sxs-lookup"><span data-stu-id="7455c-259">On the other hand, if a Re-Route URL is authenticated, Ocelot will invoke whatever downstream scheme is associated with it (the internal microservice URL).</span></span>

<span data-ttu-id="7455c-260">**Yetkilendirme Ocelot'ın ReRoutes katmanında.**</span><span class="sxs-lookup"><span data-stu-id="7455c-260">**Authorization at Ocelot’s ReRoutes tier.**</span></span>  <span data-ttu-id="7455c-261">Beyana dayalı yetkilendirme kimlik doğrulamasından sonra hesaplanan ocelot destekler.</span><span class="sxs-lookup"><span data-stu-id="7455c-261">Ocelot supports claims-based authorization evaluated after the authentication.</span></span> <span data-ttu-id="7455c-262">Bir rota düzeyinde yetkilendirme için yöneltme yapılandırma aşağıdaki satırı ekleyerek ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="7455c-262">You set the authorization at a route level by adding the following lines to the ReRoute configuration.</span></span>

```json
"RouteClaimsRequirement": {
    "UserType": "employee"
}
```

<span data-ttu-id="7455c-263">Yetkilendirme ara yazılımı çağrıldığında, bu örnekte, kullanıcının belirtecinde talep türü 'UserType' varsa ve bu talebi değerini 'çalışanı' ise Ocelot bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7455c-263">In that example, when the authorization middleware is called, Ocelot will find if the user has the claim type 'UserType' in the token and if the value of that claim is 'employee'.</span></span> <span data-ttu-id="7455c-264">Aksi takdirde kullanıcı yetkilendirilmemiş ve yanıt 403 Yasak olacaktır.</span><span class="sxs-lookup"><span data-stu-id="7455c-264">If it isn’t, then the user will not be authorized and the response will be 403 forbidden.</span></span>

## <a name="using-kubernetes-ingress-plus-ocelot-api-gateways"></a><span data-ttu-id="7455c-265">Kubernetes giriş artı Ocelot API ağ geçidi kullanma</span><span class="sxs-lookup"><span data-stu-id="7455c-265">Using Kubernetes Ingress plus Ocelot API Gateways</span></span>

<span data-ttu-id="7455c-266">Kubernetes (like Azure Kubernetes Service kümesinde) kullanırken, tüm HTTP isteklerini genellikle birleştirin [Kubernetes giriş katmanı](https://kubernetes.io/docs/concepts/services-networking/ingress/) göre *Ngınx*.</span><span class="sxs-lookup"><span data-stu-id="7455c-266">When using Kubernetes (like in an Azure Kubernetes Service cluster), you usually unify all the HTTP requests through the [Kubernetes Ingress tier](https://kubernetes.io/docs/concepts/services-networking/ingress/) based on *Nginx*.</span></span>

<span data-ttu-id="7455c-267">Herhangi bir giriş yaklaşım kullanmazsanız Kubernetes'te, ardından hizmet ve pod'ların yalnızca yönlendirilebilir IP'leri tarafından küme ağı var.</span><span class="sxs-lookup"><span data-stu-id="7455c-267">In Kubernetes, if you don’t use any ingress approach, then your services and pods have IPs only routable by the cluster network.</span></span>

<span data-ttu-id="7455c-268">Ancak, bir giriş yaklaşımı kullanırsanız, bir ters proxy olarak görev yapan Internet ve hizmetlerinizi (API ağ Geçitlerinizi dahil) arasında bir orta katman sahip olacaksınız.</span><span class="sxs-lookup"><span data-stu-id="7455c-268">But if you use an ingress approach, you'll have a middle tier between the Internet and your services (including your API Gateways), acting as a reverse proxy.</span></span>

<span data-ttu-id="7455c-269">Bir tanım, bir giriş küme hizmetlere erişmek gelen bağlantılara izin veren kuralları koleksiyonudur.</span><span class="sxs-lookup"><span data-stu-id="7455c-269">As a definition, an Ingress is a collection of rules that allow inbound connections to reach the cluster services.</span></span> <span data-ttu-id="7455c-270">Bir giriş genellikle harici olarak erişilebilen URL'leri sağlamak için trafiğin yükünü dengelemenizi, SSL sonlandırma ve daha fazlasını yüklemek için yapılandırılır.</span><span class="sxs-lookup"><span data-stu-id="7455c-270">An ingress is usually configured to provide services externally reachable URLs, load balance traffic, SSL termination and more.</span></span> <span data-ttu-id="7455c-271">Kullanıcılar, API sunucusu giriş kaynağa göndererek giriş ister.</span><span class="sxs-lookup"><span data-stu-id="7455c-271">Users request ingress by POSTing the Ingress resource to the API server.</span></span>

<span data-ttu-id="7455c-272">Docker konağı olarak yalnızca geliştirme makinenizde yerel olarak geliştirme ve kullanırken hizmetine, tüm giriş ancak yalnızca birden çok API ağ geçitleri kullanmıyorsunuz.</span><span class="sxs-lookup"><span data-stu-id="7455c-272">In eShopOnContainers, when developing locally and using just your development machine as the Docker host, you are not using any ingress but only the multiple API Gateways.</span></span>

<span data-ttu-id="7455c-273">Ancak, azure'da Kubernetes göre bir "üretim" ortam hedeflenirken hizmetine API ağ geçitleri önünde bir giriş kullanıyor.</span><span class="sxs-lookup"><span data-stu-id="7455c-273">However, when targeting a “production” environment based on Kubernetes, eShopOnContainers is using an ingress in front of the API gateways.</span></span> <span data-ttu-id="7455c-274">Bu şekilde, istemciler hala aynı temel URL'yi çağrı ancak istekleri birden çok API ağ geçitleri veya BFF yönlendirilir.</span><span class="sxs-lookup"><span data-stu-id="7455c-274">That way, the clients still call the same base URL but the requests are routed to multiple API Gateways or BFF.</span></span>

<span data-ttu-id="7455c-275">API ağ geçitleri ön uç veya yalnızca Hizmetleri ancak genellikle kendi kapsamı dışında olan web uygulamaları görünmesini façades olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="7455c-275">Note that API Gateways are front-ends or façades surfacing only the services but not the web applications that are usually out of their scope.</span></span> <span data-ttu-id="7455c-276">Ayrıca, API ağ geçitleri belirli iç mikro hizmetler gizlemek.</span><span class="sxs-lookup"><span data-stu-id="7455c-276">In addition, the API Gateways might hide certain internal microservices.</span></span>

<span data-ttu-id="7455c-277">Giriş, ancak yalnızca HTTP isteklerini yönlendirerek, ancak herhangi bir mikro hizmet veya web uygulamasının gizlemek çalışıyor değil.</span><span class="sxs-lookup"><span data-stu-id="7455c-277">The ingress, however, is just redirecting HTTP requests but not trying to hide any microservice or web app.</span></span>

<span data-ttu-id="7455c-278">Web uygulamalarının yanı sıra birkaç Ocelot API ağ geçitleri önünde bir giriş Ngınx katmanı Kubernetes'te sahip / BFF ideal mimarisi, aşağıdaki diyagramda gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="7455c-278">Having an ingress Nginx tier in Kubernetes in front of the web applications plus the several Ocelot API Gateways / BFF is the ideal architecture, as shown in the following diagram.</span></span>

![Kubernetes giriş, giden tüm trafik, genellikle API ağ geçidi kapsam dışına web uygulamaları da dahil olmak üzere, uygulama için ters Ara sunucu görevi görür.](./media/image41.png)

<span data-ttu-id="7455c-280">**Şekil 6-41**.</span><span class="sxs-lookup"><span data-stu-id="7455c-280">**Figure 6-41**.</span></span> <span data-ttu-id="7455c-281">Kubernetes dağıtıldığında hizmetine giriş katmanı</span><span class="sxs-lookup"><span data-stu-id="7455c-281">The ingress tier in eShopOnContainers when deployed into Kubernetes</span></span>

<span data-ttu-id="7455c-282">Kubernetes hizmetine dağıtın, yalnızca birkaç hizmet veya uç noktaları aracılığıyla kullanıma sunduğu _giriş_, temelde aşağıdaki listede yer alan postfixes URL'leri üzerinde:</span><span class="sxs-lookup"><span data-stu-id="7455c-282">When you deploy eShopOnContainers into Kubernetes, it exposes just a few services or endpoints via _ingress_, basically the following list of postfixes on the URLs:</span></span>

- <span data-ttu-id="7455c-283">`/` SPA istemci için web uygulaması</span><span class="sxs-lookup"><span data-stu-id="7455c-283">`/` for the client SPA web application</span></span>
- <span data-ttu-id="7455c-284">`/webmvc` MVC web uygulaması istemci için</span><span class="sxs-lookup"><span data-stu-id="7455c-284">`/webmvc` for the client MVC web application</span></span>
- <span data-ttu-id="7455c-285">`/webstatus` İstemci web uygulaması için durum/healthchecks gösteriliyor</span><span class="sxs-lookup"><span data-stu-id="7455c-285">`/webstatus` for the client web app showing the status/healthchecks</span></span>
- <span data-ttu-id="7455c-286">`/webshoppingapigw` alışveriş iş süreçleri ve web BFF için</span><span class="sxs-lookup"><span data-stu-id="7455c-286">`/webshoppingapigw` for the web BFF and shopping business processes</span></span>
- <span data-ttu-id="7455c-287">`/webmarketingapigw` Pazarlama iş süreçleri ve web BFF için</span><span class="sxs-lookup"><span data-stu-id="7455c-287">`/webmarketingapigw` for the web BFF and marketing business processes</span></span>
- <span data-ttu-id="7455c-288">`/mobileshoppingapigw` Mobil BFF ve iş süreçlerini alışveriş için</span><span class="sxs-lookup"><span data-stu-id="7455c-288">`/mobileshoppingapigw` for the mobile BFF and shopping business processes</span></span>
- <span data-ttu-id="7455c-289">`/mobilemarketingapigw` Mobil BFF ve iş süreçlerini pazarlama için</span><span class="sxs-lookup"><span data-stu-id="7455c-289">`/mobilemarketingapigw` for the mobile BFF and marketing business processes</span></span>

<span data-ttu-id="7455c-290">Kubernetes için dağıtırken her Ocelot API ağ geçidi farklı "configuration.json" dosya her biri için kullanan _pod_ API ağ geçitleri çalışıyor.</span><span class="sxs-lookup"><span data-stu-id="7455c-290">When deploying to Kubernetes, each Ocelot API Gateway is using a different “configuration.json” file for each _pod_ running the API Gateways.</span></span> <span data-ttu-id="7455c-291">Bu "configuration.json" dosyaları (başlangıçta deploy.ps1 betikle) azure'da bir Kubernetes göre oluşturulan birim bağlama tarafından sağlanan _yapılandırma eşlemesi_ 'ocelot' adlı.</span><span class="sxs-lookup"><span data-stu-id="7455c-291">Those “configuration.json” files are provided by mounting (originally with the deploy.ps1 script) a volume created based on a Kubernetes _config map_ named ‘ocelot’.</span></span> <span data-ttu-id="7455c-292">Her kapsayıcı, ilgili yapılandırma dosyası adlı kapsayıcının klasör içinde bağlar `/app/configuration`.</span><span class="sxs-lookup"><span data-stu-id="7455c-292">Each container mounts its related configuration file in the container’s folder named `/app/configuration`.</span></span>

<span data-ttu-id="7455c-293">İçinde özgün "configuration.json" dosyaları hizmetine, kaynak kodu dosyalarında bulunabilir `k8s/ocelot/` klasör.</span><span class="sxs-lookup"><span data-stu-id="7455c-293">In the source code files of eShopOnContainers, the original “configuration.json” files can be found within the `k8s/ocelot/` folder.</span></span> <span data-ttu-id="7455c-294">Her BFF/APIGateway için bir dosya yok.</span><span class="sxs-lookup"><span data-stu-id="7455c-294">There’s one file for each BFF/APIGateway.</span></span>

## <a name="additional-cross-cutting-features-in-an-ocelot-api-gateway"></a><span data-ttu-id="7455c-295">Bir Ocelot API ağ geçidi ek çapraz özellikleri</span><span class="sxs-lookup"><span data-stu-id="7455c-295">Additional cross-cutting features in an Ocelot API Gateway</span></span>

<span data-ttu-id="7455c-296">Araştırma ve aşağıdaki bağlantıları açıklanan bir Ocelot API Gateway kullanırken, diğer önemli özellikleri vardır.</span><span class="sxs-lookup"><span data-stu-id="7455c-296">There are other important features to research and use, when using an Ocelot API Gateway, described in the following links.</span></span>

- <span data-ttu-id="7455c-297">**Ocelot Consul veya Eureka tümleştirmek istemci tarafı hizmet bulmayı** \\</span><span class="sxs-lookup"><span data-stu-id="7455c-297">**Service discovery in the client side integrating Ocelot with Consul or Eureka** \\</span></span>
  <https://ocelot.readthedocs.io/en/latest/features/servicediscovery.html>

- <span data-ttu-id="7455c-298">**API ağ geçidi katmanında önbelleğe alma** \\</span><span class="sxs-lookup"><span data-stu-id="7455c-298">**Caching at the API Gateway tier** \\</span></span>
  <https://ocelot.readthedocs.io/en/latest/features/caching.html>

- <span data-ttu-id="7455c-299">**API ağ geçidi katmanında günlüğe kaydetme** \\</span><span class="sxs-lookup"><span data-stu-id="7455c-299">**Logging at the API Gateway tier** \\</span></span>
  <https://ocelot.readthedocs.io/en/latest/features/logging.html>

- <span data-ttu-id="7455c-300">**API ağ geçidi katmanında (yeniden denemeler ve devre Kesiciler) hizmet kalitesi** \\</span><span class="sxs-lookup"><span data-stu-id="7455c-300">**Quality of Service (Retries and Circuit breakers) at the API Gateway tier** \\</span></span>
  <https://ocelot.readthedocs.io/en/latest/features/qualityofservice.html>

- <span data-ttu-id="7455c-301">**Oran sınırlandırma** \\</span><span class="sxs-lookup"><span data-stu-id="7455c-301">**Rate limiting** \\</span></span>
  [https://ocelot.readthedocs.io/en/latest/features/ratelimiting.html](https://ocelot.readthedocs.io/en/latest/features/ratelimiting.html )

> [!div class="step-by-step"]
> <span data-ttu-id="7455c-302">[Önceki](background-tasks-with-ihostedservice.md)
> [İleri](../microservice-ddd-cqrs-patterns/index.md)</span><span class="sxs-lookup"><span data-stu-id="7455c-302">[Previous](background-tasks-with-ihostedservice.md)
[Next](../microservice-ddd-cqrs-patterns/index.md)</span></span>
