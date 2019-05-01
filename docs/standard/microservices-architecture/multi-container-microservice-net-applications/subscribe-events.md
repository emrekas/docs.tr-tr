---
title: Olaylara abone olma
description: Kapsayıcılı .NET uygulamaları için .NET mikro hizmet mimarisi | Yayımlama ve tümleştirme olayları için abonelik ayrıntılarını anlayın.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/02/2018
ms.openlocfilehash: 962d12c054bed3b2623283e17f83b8466ab2811b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864624"
---
# <a name="subscribing-to-events"></a><span data-ttu-id="b5ea1-103">Olaylara abone olma</span><span class="sxs-lookup"><span data-stu-id="b5ea1-103">Subscribing to events</span></span>

<span data-ttu-id="b5ea1-104">Olay veri yolu kullanmanın ilk adımı, mikro hizmetler almak istediği olaylara abone olmaktır.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-104">The first step for using the event bus is to subscribe the microservices to the events they want to receive.</span></span> <span data-ttu-id="b5ea1-105">Alıcı mikro Hizmetleri yapılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-105">That should be done in the receiver microservices.</span></span>

<span data-ttu-id="b5ea1-106">Aşağıdaki basit kod her alıcı mikro hizmete uygulamak gereken gösterir (diğer bir deyişle, `Startup` sınıfı) şekilde bu olayları, ihtiyaçlarını kaydeder.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-106">The following simple code shows what each receiver microservice needs to implement when starting the service (that is, in the `Startup` class) so it subscribes to the events it needs.</span></span> <span data-ttu-id="b5ea1-107">Bu durumda, `basket.api` mikro hizmet abone olmak için gereksinim duyduğu `ProductPriceChangedIntegrationEvent` ve `OrderStartedIntegrationEvent` iletileri.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-107">In this case, the `basket.api` microservice needs to subscribe to `ProductPriceChangedIntegrationEvent` and the `OrderStartedIntegrationEvent` messages.</span></span>

<span data-ttu-id="b5ea1-108">Örneğin, abone olduğunda `ProductPriceChangedIntegrationEvent` sepet mikro hizmet herhangi farkında sağlayan bir olay ürün fiyatı değiştirir ve bu ürünün kullanıcının sepetteki ise değişiklik hakkında kullanıcıyı uyarmak olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-108">For instance, when subscribing to the `ProductPriceChangedIntegrationEvent` event, that makes the basket microservice aware of any changes to the product price and lets it warn the user about the change if that product is in the user’s basket.</span></span>

```csharp
var eventBus = app.ApplicationServices.GetRequiredService<IEventBus>();

eventBus.Subscribe<ProductPriceChangedIntegrationEvent,
                   ProductPriceChangedIntegrationEventHandler>();

eventBus.Subscribe<OrderStartedIntegrationEvent,
                   OrderStartedIntegrationEventHandler>();

```

<span data-ttu-id="b5ea1-109">Bu kod çalıştırıldıktan sonra abone mikro hizmet RabbitMQ kanallar aracılığıyla dinleniyor olması.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-109">After this code runs, the subscriber microservice will be listening through RabbitMQ channels.</span></span> <span data-ttu-id="b5ea1-110">ProductPriceChangedIntegrationEvent türünde herhangi bir ileti geldiğinde, ona iletilen ve olayı işleyen olayı işleyicisi kodu çağırır.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-110">When any message of type ProductPriceChangedIntegrationEvent arrives, the code invokes the event handler that is passed to it and processes the event.</span></span>

## <a name="publishing-events-through-the-event-bus"></a><span data-ttu-id="b5ea1-111">Olay veri yolu üzerinden olayları yayımlama</span><span class="sxs-lookup"><span data-stu-id="b5ea1-111">Publishing events through the event bus</span></span>

<span data-ttu-id="b5ea1-112">Son olarak, aşağıdaki örneğe benzer bir kod ile tümleştirme olayları (kaynak mikro hizmet) iletiyi gönderenin yayımlar.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-112">Finally, the message sender (origin microservice) publishes the integration events with code similar to the following example.</span></span> <span data-ttu-id="b5ea1-113">(Bu kararlılık dikkate almaz basitleştirilmiş bir örnek niteliğindedir.) Her olaya birden fazla mikro hizmetler, veri veya kaynak mikro hizmet içi işlemlerden uyguladıktan sonra genellikle doğru arasında dağıtılmalıdır benzer bir kod uygulayabilir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-113">(This is a simplified example that does not take atomicity into account.) You would implement similar code whenever an event must be propagated across multiple microservices, usually right after committing data or transactions from the origin microservice.</span></span>

<span data-ttu-id="b5ea1-114">İlk olarak, (RabbitMQ alarak veya temel bir service bus üzerinde) olay veri yolu uygulama nesnesi denetleyici Oluşturucu aşağıdaki kodu olduğu gibi eklenen:</span><span class="sxs-lookup"><span data-stu-id="b5ea1-114">First, the event bus implementation object (based on RabbitMQ or based on a service bus) would be injected at the controller constructor, as in the following code:</span></span>

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    private readonly CatalogContext _context;
    private readonly IOptionsSnapshot<Settings> _settings;
    private readonly IEventBus _eventBus;

    public CatalogController(CatalogContext context,
        IOptionsSnapshot<Settings> settings,
        IEventBus eventBus)
    {
        _context = context;
        _settings = settings;
        _eventBus = eventBus;
    }
    // ...
}
```

<span data-ttu-id="b5ea1-115">Ardından, bu denetleyicinizin yöntemlerinden gibi UpdateProduct yöntemi kullanın:</span><span class="sxs-lookup"><span data-stu-id="b5ea1-115">Then you use it from your controller’s methods, like in the UpdateProduct method:</span></span>

```csharp
[Route("items")]
[HttpPost]
public async Task<IActionResult> UpdateProduct([FromBody]CatalogItem product)
{
    var item = await _context.CatalogItems.SingleOrDefaultAsync(
        i => i.Id == product.Id);
    // ...
    if (item.Price != product.Price)
    {
        var oldPrice = item.Price;
        item.Price = product.Price;
        _context.CatalogItems.Update(item);
        var @event = new ProductPriceChangedIntegrationEvent(item.Id,
            item.Price,
            oldPrice);
        // Commit changes in original transaction
        await _context.SaveChangesAsync();
        // Publish integration event to the event bus
        // (RabbitMQ or a service bus underneath)
        _eventBus.Publish(@event);
        // ...
    }
    // ...
}
```

<span data-ttu-id="b5ea1-116">Bu durumda, kaynak mikro hizmet basit CRUD mikro hizmeti olduğundan, bu kodu bir Web API denetleyicisi sağ yerleştirilir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-116">In this case, since the origin microservice is a simple CRUD microservice, that code is placed right into a Web API controller.</span></span>

<span data-ttu-id="b5ea1-117">Mikro hizmetlerde CQRS yaklaşımı kullanırken gibi daha gelişmiş, onu uygulanabilen `CommandHandler` içinde sınıf `Handle()` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-117">In more advanced microservices, like when using CQRS approaches, it can be implemented in the `CommandHandler` class, within the `Handle()` method.</span></span>

### <a name="designing-atomicity-and-resiliency-when-publishing-to-the-event-bus"></a><span data-ttu-id="b5ea1-118">Kararlılık ve dayanıklılık olay veri yoluna yayımlanırken tasarlama</span><span class="sxs-lookup"><span data-stu-id="b5ea1-118">Designing atomicity and resiliency when publishing to the event bus</span></span>

<span data-ttu-id="b5ea1-119">Dağıtılmış Mesajlaşma aracılığıyla tümleştirme olayları yayımladığınızda, olay veri yolu gibi sistem, başarısızlığa uğrar özgün veritabanının güncelleştirilmesi ve olay (diğer bir deyişle, hem tam işlemleri veya bunların hiçbiri) yayımlama sorununu vardır.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-119">When you publish integration events through a distributed messaging system like your event bus, you have the problem of atomically updating the original database and publishing an event (that is, either both operations complete or none of them).</span></span> <span data-ttu-id="b5ea1-120">Ürün fiyatı değiştirilir ve ardından bir ProductPriceChangedIntegrationEvent ileti yayımlar örneği için Basitleştirilmiş örnekte, daha önce gösterilen kodu verilerini veritabanına kaydeder.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-120">For instance, in the simplified example shown earlier, the code commits data to the database when the product price is changed and then publishes a ProductPriceChangedIntegrationEvent message.</span></span> <span data-ttu-id="b5ea1-121">Başlangıçta, bu iki işlemler atomik olarak gerçekleştirilmesini temel görünebilir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-121">Initially, it might look essential that these two operations be performed atomically.</span></span> <span data-ttu-id="b5ea1-122">İlgili bir dağıtılmış işlem kullanıyorsanız gibi eski sistemlerde olduğu gibi ancak, veritabanı ve ileti, aracı [Microsoft Message Queuing (MSMQ)](https://msdn.microsoft.com/library/windows/desktop/ms711472(v=vs.85).aspx), bu tarafındanaçıklanannedenleriyleönerilmez[CAP Teoremi](https://www.quora.com/What-Is-CAP-Theorem-1).</span><span class="sxs-lookup"><span data-stu-id="b5ea1-122">However, if you are using a distributed transaction involving the database and the message broker, as you do in older systems like [Microsoft Message Queuing (MSMQ)](https://msdn.microsoft.com/library/windows/desktop/ms711472(v=vs.85).aspx), this is not recommended for the reasons described by the [CAP theorem](https://www.quora.com/What-Is-CAP-Theorem-1).</span></span>

<span data-ttu-id="b5ea1-123">Temelde, mikro hizmetler, ölçeklenebilir ve yüksek oranda kullanılabilir sistemleri oluşturmak için kullanın.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-123">Basically, you use microservices to build scalable and highly available systems.</span></span> <span data-ttu-id="b5ea1-124">CAP Teoremi (dağıtılmış) bir veritabanı (veya kendi modelini sahibi olan bir mikro hizmet) derlenemiyor diyor biraz basitleştirme, sürekli olarak kullanılabilir ve son derece tutarlı *ve* dayanıklı herhangi bir bölümü için.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-124">Simplifying somewhat, the CAP theorem says that you cannot build a (distributed) database (or a microservice that owns its model) that is continually available, strongly consistent, *and* tolerant to any partition.</span></span> <span data-ttu-id="b5ea1-125">Bu üç özellik ikilisi seçmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-125">You must choose two of these three properties.</span></span>

<span data-ttu-id="b5ea1-126">Mikro hizmet tabanlı mimariler, kullanılabilirlik ve dayanıklılık seçmelisiniz ve, güçlü tutarlılık devamlı müşterilerine göre ayarlayabilirler.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-126">In microservices-based architectures, you should choose availability and tolerance, and you should deemphasize strong consistency.</span></span> <span data-ttu-id="b5ea1-127">Uygulamanız olarak bu nedenle, çoğu modern mikro hizmet tabanlı uygulamalar, genellikle mesajlaşmada, dağıtılmış işlemler kullanmak istediğiniz değil [dağıtılmış işlemler](https://docs.microsoft.com/previous-versions/windows/desktop/ms681205(v=vs.85)) Windows Dağıtılmış İşlem üzerinde temel Düzenleyicisi (DTC) ile [MSMQ](https://msdn.microsoft.com/library/windows/desktop/ms711472(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="b5ea1-127">Therefore, in most modern microservice-based applications, you usually do not want to use distributed transactions in messaging, as you do when you implement [distributed transactions](https://docs.microsoft.com/previous-versions/windows/desktop/ms681205(v=vs.85)) based on the Windows Distributed Transaction Coordinator (DTC) with [MSMQ](https://msdn.microsoft.com/library/windows/desktop/ms711472(v=vs.85).aspx).</span></span>

<span data-ttu-id="b5ea1-128">Şimdi ilk sorun ve kendi örnek geçelim.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-128">Let’s go back to the initial issue and its example.</span></span> <span data-ttu-id="b5ea1-129">Veritabanı güncelleştirildikten sonra hizmetin kilitlenmesi durumunda (Bu durumda, kod satırının sonra sağ \_bağlamı. SaveChangesAsync()), ancak tümleştirme olay yayımlanmadan önce sistemin tutarsız hale gelebilir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-129">If the service crashes after the database is updated (in this case, right after the line of code with \_context.SaveChangesAsync()), but before the integration event is published, the overall system could become inconsistent.</span></span> <span data-ttu-id="b5ea1-130">Bu, ilgilendiğiniz belirli iş işleme bağlı olarak kritik bir iş olabilir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-130">This might be business critical, depending on the specific business operation you are dealing with.</span></span>

<span data-ttu-id="b5ea1-131">Mimari bölümünde daha önce bahsedildiği gibi bu sorunu uğraşmanızı için çeşitli yaklaşımlar olabilir:</span><span class="sxs-lookup"><span data-stu-id="b5ea1-131">As mentioned earlier in the architecture section, you can have several approaches for dealing with this issue:</span></span>

- <span data-ttu-id="b5ea1-132">Tam kullanarak [olay kaynağını belirleme düzeni](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing).</span><span class="sxs-lookup"><span data-stu-id="b5ea1-132">Using the full [Event Sourcing pattern](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing).</span></span>

- <span data-ttu-id="b5ea1-133">Kullanarak [işlem oturum araştırma](https://www.scoop.it/t/sql-server-transaction-log-mining).</span><span class="sxs-lookup"><span data-stu-id="b5ea1-133">Using [transaction log mining](https://www.scoop.it/t/sql-server-transaction-log-mining).</span></span>

- <span data-ttu-id="b5ea1-134">Kullanarak [giden deseni](http://gistlabs.com/2014/05/the-outbox/).</span><span class="sxs-lookup"><span data-stu-id="b5ea1-134">Using the [Outbox pattern](http://gistlabs.com/2014/05/the-outbox/).</span></span> <span data-ttu-id="b5ea1-135">(Yerel işlem genişletme) tümleştirme olayları depolamak için bu işlem bir tablodur.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-135">This is a transactional table to store the integration events (extending the local transaction).</span></span>

<span data-ttu-id="b5ea1-136">Bu senaryo için tam olay kaynağını belirleme (ES) deseni en iyi yaklaşımlardan biri değilse kullanmaktır *en* iyi.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-136">For this scenario, using the full Event Sourcing (ES) pattern is one of the best approaches, if not *the* best.</span></span> <span data-ttu-id="b5ea1-137">Ancak, birçok uygulama senaryolarında, tam bir ES sistemi uygulamak mümkün olmayabilir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-137">However, in many application scenarios, you might not be able to implement a full ES system.</span></span> <span data-ttu-id="b5ea1-138">Geçerli durumu verilerini depolamak yerine işlemsel veritabanı, yalnızca etki alanı olayları depolamak ES anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-138">ES means storing only domain events in your transactional database, instead of storing current state data.</span></span> <span data-ttu-id="b5ea1-139">Yalnızca etki alanı olayları depolamadan gibi sistem geçmişini sahip olunması ve geçmişteki herhangi bir anda, sistem durumunu belirlemek için harika avantajlar, olabilir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-139">Storing only domain events can have great benefits, such as having the history of your system available and being able to determine the state of your system at any moment in the past.</span></span> <span data-ttu-id="b5ea1-140">Ancak, tam bir ES sistemi uygulama sisteminizi çoğunu yeniden oluşturma gerektiren ve diğer birçok karmaşıklık ve gereksinimler sunar.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-140">However, implementing a full ES system requires you to rearchitect most of your system and introduces many other complexities and requirements.</span></span> <span data-ttu-id="b5ea1-141">Örneğin, özellikle olay kaynağını belirleme için gibi yapılan bir veritabanı kullanmak isteyebilirsiniz [olay Store](https://eventstore.org/), veya bir Azure Cosmos DB, MongoDB, Cassandra, CouchDB veya RavenDB gibi belge yönelimli veritabanı.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-141">For example, you would want to use a database specifically made for event sourcing, such as [Event Store](https://eventstore.org/), or a document-oriented database such as Azure Cosmos DB, MongoDB, Cassandra, CouchDB, or RavenDB.</span></span> <span data-ttu-id="b5ea1-142">Olay kaynağını belirleme ile bilginiz sürece ES Bu sorun, ancak kolay çözümü için harika bir yaklaşımdır.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-142">ES is a great approach for this problem, but not the easiest solution unless you are already familiar with event sourcing.</span></span>

<span data-ttu-id="b5ea1-143">İşlem günlüğü başlangıçta araştırma kullanma seçeneği çok saydam arar.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-143">The option to use transaction log mining initially looks very transparent.</span></span> <span data-ttu-id="b5ea1-144">Ancak, bu yaklaşımı kullanmak için SQL Server işlem günlüğü gibi RDBMS işlem günlüğü için eşleştirilmek mikro hizmet vardır.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-144">However, to use this approach, the microservice has to be coupled to your RDBMS transaction log, such as the SQL Server transaction log.</span></span> <span data-ttu-id="b5ea1-145">Bu tercih edilir olmayabilir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-145">This is probably not desirable.</span></span> <span data-ttu-id="b5ea1-146">Başka bir dezavantajı, işlem günlüğüne kaydedilen bir alt düzey güncelleştirmeleri, üst düzey tümleştirme olayları ile aynı düzeyde olmayabilir olmasıdır.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-146">Another drawback is that the low-level updates recorded in the transaction log might not be at the same level as your high-level integration events.</span></span> <span data-ttu-id="b5ea1-147">Bu durumda, bu işlem günlüğü işlemleri tersine mühendislik işlemi zor olabilir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-147">If so, the process of reverse-engineering those transaction log operations can be difficult.</span></span>

<span data-ttu-id="b5ea1-148">İşlemsel veritabanı tablosu ve Basitleştirilmiş bir ES deseni bir karışımını buna dengeli bir yaklaşımdır.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-148">A balanced approach is a mix of a transactional database table and a simplified ES pattern.</span></span> <span data-ttu-id="b5ea1-149">"Tümleştirme olayları tabloya işlerseniz özgün olay ayarlanan olayı yayımlamak için hazır" gibi bir durum kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-149">You can use a state such as “ready to publish the event,” which you set in the original event when you commit it to the integration events table.</span></span> <span data-ttu-id="b5ea1-150">Ardından, olay, olay veri yoluna yayımlayamadı deneyin.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-150">You then try to publish the event to the event bus.</span></span> <span data-ttu-id="b5ea1-151">Yayımlama olayı eylem başarılı olursa, başka bir işlem kaynağını hizmetini ve durumu "den olay yayımlanmaya hazır" taşıma "zaten yayımlanan olaya."</span><span class="sxs-lookup"><span data-stu-id="b5ea1-151">If the publish-event action succeeds, you start another transaction in the origin service and move the state from “ready to publish the event” to “event already published.”</span></span>

<span data-ttu-id="b5ea1-152">Yayımlama olayı eylem başarısız olay veri yolu, veriler yine de kaynak mikro hizmet içinde tutarsız olmaz; yine de "hazır olarak olayı yayımlamak" işaretlenmiş olması ve ilgili rest Hizmetleri sonunda tutarlı olur.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-152">If the publish-event action in the event bus fails, the data still will not be inconsistent within the origin microservice—it is still marked as “ready to publish the event,” and with respect to the rest of the services, it will eventually be consistent.</span></span> <span data-ttu-id="b5ea1-153">Her zaman, işlemler veya tümleştirme olayları durumunu denetleme arka plan işleri de sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-153">You can always have background jobs checking the state of the transactions or integration events.</span></span> <span data-ttu-id="b5ea1-154">İş "olayı yayımlamak hazır" durumunda bir olay bulunursa, bu olay Olay Bus yeniden yayımlamayı deneyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-154">If the job finds an event in the “ready to publish the event” state, it can try to republish that event to the event bus.</span></span>

<span data-ttu-id="b5ea1-155">Bu yaklaşımda, yalnızca tümleştirme olayları için her kaynak mikro hizmet ve diğer mikro hizmetler veya dış sistemler için kurmak istediğiniz olayları kalıcı hale getirmeniz dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-155">Notice that with this approach, you are persisting only the integration events for each origin microservice, and only the events that you want to communicate to other microservices or external systems.</span></span> <span data-ttu-id="b5ea1-156">Buna karşılık, tam bir ES sistemde, tüm etki alanı olayları de depolar.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-156">In contrast, in a full ES system, you store all domain events as well.</span></span>

<span data-ttu-id="b5ea1-157">Bu nedenle, dengeli bu yaklaşım bir Basitleştirilmiş ES sistemidir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-157">Therefore, this balanced approach is a simplified ES system.</span></span> <span data-ttu-id="b5ea1-158">Tümleştirme olayları ile bunların geçerli durumunu listesi gerekir ("yayımlamak"yayımlanan "hazır").</span><span class="sxs-lookup"><span data-stu-id="b5ea1-158">You need a list of integration events with their current state (“ready to publish” versus “published”).</span></span> <span data-ttu-id="b5ea1-159">Ancak bu durumlar için tümleştirme olayları uygulamak yeterlidir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-159">But you only need to implement these states for the integration events.</span></span> <span data-ttu-id="b5ea1-160">Ve tam bir ES sisteminde olduğu gibi Bu yaklaşımda, olaylar işlemsel veritabanında olarak tüm etki alanı verileri depolamak ihtiyacınız yoktur.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-160">And in this approach, you do not need to store all your domain data as events in the transactional database, as you would in a full ES system.</span></span>

<span data-ttu-id="b5ea1-161">İlişkisel bir veritabanı zaten kullanıyorsanız, tümleştirme olayları depolamak için bir işlem tablo kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-161">If you are already using a relational database, you can use a transactional table to store integration events.</span></span> <span data-ttu-id="b5ea1-162">Kararlılık, uygulamanızda elde etmek için iki adımlı bir işlem yerel işlemlerden yola çıkarak kullanın.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-162">To achieve atomicity in your application, you use a two-step process based on local transactions.</span></span> <span data-ttu-id="b5ea1-163">Temel olarak, etki alanı varlıklarınızı sahip olduğu aynı veritabanında IntegrationEvent tablo sahip.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-163">Basically, you have an IntegrationEvent table in the same database where you have your domain entities.</span></span> <span data-ttu-id="b5ea1-164">Bu tablo, bir sigorta dahil bir kararlılık elde etmek için etki alanı verilerinizi yürütülmekte olan aynı işlemleri tümleştirme olayları kalıcı olarak çalışır.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-164">That table works as an insurance for achieving atomicity so that you include persisted integration events into the same transactions that are committing your domain data.</span></span>

<span data-ttu-id="b5ea1-165">Adım adım işlemi şu şekilde geçer:</span><span class="sxs-lookup"><span data-stu-id="b5ea1-165">Step by step, the process goes like this:</span></span>

1. <span data-ttu-id="b5ea1-166">Uygulama yerel veritabanı işlemi başlar.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-166">The application begins a local database transaction.</span></span>

2. <span data-ttu-id="b5ea1-167">Etki alanı varlıklarınızın durumunu güncelleştirir ve bir olay tümleştirme olay tablosuna ekler.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-167">It then updates the state of your domain entities and inserts an event into the integration event table.</span></span>

3. <span data-ttu-id="b5ea1-168">Son olarak, bu işlem işlemeler istenen kararlılık alabilmeniz ve ardından</span><span class="sxs-lookup"><span data-stu-id="b5ea1-168">Finally, it commits the transaction, so you get the desired atomicity and then</span></span>

4. <span data-ttu-id="b5ea1-169">Olayı şekilde yayımlamak (İleri).</span><span class="sxs-lookup"><span data-stu-id="b5ea1-169">You publish the event somehow (next).</span></span>

<span data-ttu-id="b5ea1-170">Olayları yayımlama adımları uygularken bu seçeneğiniz vardır:</span><span class="sxs-lookup"><span data-stu-id="b5ea1-170">When implementing the steps of publishing the events, you have these choices:</span></span>

- <span data-ttu-id="b5ea1-171">Tümleştirme olay sağ işlem uyguladıktan sonra yayımlayın ve yayımlanan olarak tablo olayları işaretlemek için başka bir yerel işlem'ı kullanın.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-171">Publish the integration event right after committing the transaction and use another local transaction to mark the events in the table as being published.</span></span> <span data-ttu-id="b5ea1-172">Ardından uzak mikro hizmetler sorunları yaşanması tümleştirme olayları izlemek için yalnızca bir yapıt tabloyu kullanın ve saklı tümleştirme etkinliklere göre telafi izin eylemleri gerçekleştirin.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-172">Then, use the table just as an artifact to track the integration events in case of issues in the remote microservices, and perform compensatory actions based on the stored integration events.</span></span>

- <span data-ttu-id="b5ea1-173">Tablo, kuyruk bir tür olarak kullanın.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-173">Use the table as a kind of queue.</span></span> <span data-ttu-id="b5ea1-174">Ayrı uygulama iş parçacığı veya işlem tümleştirme olay tablo sorguları, olayları olay veri yoluna yayımlar ve olayları yayınlanan olarak işaretlemek için bir yerel işlem'i kullanır.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-174">A separate application thread or process queries the integration event table, publishes the events to the event bus, and then uses a local transaction to mark the events as published.</span></span>

<span data-ttu-id="b5ea1-175">Şekil 6-22 Bu yaklaşımların ilk mimarisi gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-175">Figure 6-22 shows the architecture for the first of these approaches.</span></span>

![Kararlılık olayları yayımlarken işlemek için bir yaklaşım: (kullanılan hizmetine) yayımlamak için bir işlem tamamlama olayına bir olay günlüğü tablosu ve başka bir işlem kullanma](./media/image23.png)

<span data-ttu-id="b5ea1-177">**Şekil 6-22**.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-177">**Figure 6-22**.</span></span> <span data-ttu-id="b5ea1-178">Olaylar olay veri yoluna yayımlanırken kararlılık</span><span class="sxs-lookup"><span data-stu-id="b5ea1-178">Atomicity when publishing events to the event bus</span></span>

<span data-ttu-id="b5ea1-179">Şekil 6-22'de gösterilen yaklaşımına denetleniyor ve yayımlanan tümleştirme olayları başarısını onaylayan sorumlu ek çalışan mikro hizmet eksik.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-179">The approach illustrated in Figure 6-22 is missing an additional worker microservice that is in charge of checking and confirming the success of the published integration events.</span></span> <span data-ttu-id="b5ea1-180">Hata oluşması halinde, bu ek denetleyicisi çalışan mikro hizmet olayları tablodan okuyabilir ve bunları, 2. adımı yineleyin sayısı diğer bir deyişle, yeniden yayımlayın.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-180">In case of failure, that additional checker worker microservice can read events from the table and republish them, that is, repeat step number 2.</span></span>

<span data-ttu-id="b5ea1-181">İkinci yaklaşım hakkında: olay günlüğü tablosu bir kuyruk kullanın ve her zaman iletileri yayımlamak için bir çalışan mikro hizmet kullanın.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-181">About the second approach: you use the EventLog table as a queue and always use a worker microservice to publish the messages.</span></span> <span data-ttu-id="b5ea1-182">Bu durumda, işlem gibi Şekil 6-23 gösterilir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-182">In that case, the process is like that shown in Figure 6-23.</span></span> <span data-ttu-id="b5ea1-183">Bu ek bir mikro hizmet gösterir ve tek kaynak olayları yayımlarken tablosudur.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-183">This shows an additional microservice, and the table is the single source when publishing events.</span></span>

![Kararlılık işlemek için başka bir yaklaşım için: Bir olay günlüğü tabloya yayımlayın ve ardından olan başka bir mikro hizmet (arka plan çalışanı) yayımlama olayı.](./media/image24.png)

<span data-ttu-id="b5ea1-185">**Şekil 6-23**.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-185">**Figure 6-23**.</span></span> <span data-ttu-id="b5ea1-186">Olayları çalışan mikro hizmet ile olay veri yoluna yayımlanırken kararlılık</span><span class="sxs-lookup"><span data-stu-id="b5ea1-186">Atomicity when publishing events to the event bus with a worker microservice</span></span>

<span data-ttu-id="b5ea1-187">Kolaylık olması için hizmetine örnek olay veri yolu (ile hiçbir ek işlemler veya denetleyicisi mikro hizmetler) ilk yaklaşımı kullanır.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-187">For simplicity, the eShopOnContainers sample uses the first approach (with no additional processes or checker microservices) plus the event bus.</span></span> <span data-ttu-id="b5ea1-188">Ancak, hizmetine tüm olası hata koşulları işlenmiyor.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-188">However, the eShopOnContainers is not handling all possible failure cases.</span></span> <span data-ttu-id="b5ea1-189">Buluta dağıtılan gerçek bir uygulamada denetleyin ve yeniden mantıksal sorunları sonuçta ortaya çıkar ve uygulamanız gereken gerçeği benimseyin gerekir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-189">In a real application deployed to the cloud, you must embrace the fact that issues will arise eventually, and you must implement that check and resend logic.</span></span> <span data-ttu-id="b5ea1-190">Bunları (ile çalışan) olay veri yolu yayımlarken olay tek bir kaynak olarak bu tablonuz varsa tabloyu sırası olarak kullanarak bir ilk yaklaşım daha etkili olabilir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-190">Using the table as a queue can be more effective than the first approach if you have that table as a single source of events when publishing them (with the worker) through the event bus.</span></span>

### <a name="implementing-atomicity-when-publishing-integration-events-through-the-event-bus"></a><span data-ttu-id="b5ea1-191">Kararlılık tümleştirme olayları olay veri yolu üzerinden yayımlarken uygulama</span><span class="sxs-lookup"><span data-stu-id="b5ea1-191">Implementing atomicity when publishing integration events through the event bus</span></span>

<span data-ttu-id="b5ea1-192">Aşağıdaki kod, birden çok DbContext nesnelerini içeren tek bir işlem nasıl oluşturabileceğinizi gösterir; güncelleştirilen özgün verilerle ilgili bir içerik ve ilgili IntegrationEventLog tablonun ikinci bağlam.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-192">The following code shows how you can create a single transaction involving multiple DbContext objects—one context related to the original data being updated, and the second context related to the IntegrationEventLog table.</span></span>

<span data-ttu-id="b5ea1-193">Aşağıdaki örnek kod işlemde veritabanı bağlantılarını kodun çalıştığı sırada herhangi bir sorun varsa esnek olmayacağını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-193">Note that the transaction in the example code below will not be resilient if connections to the database have any issue at the time when the code is running.</span></span> <span data-ttu-id="b5ea1-194">Veritabanlarını sunucular arasında taşınmasını gerektirecek Azure SQL veritabanı gibi bulut tabanlı sistemlerde oluşabilir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-194">This can happen in cloud-based systems like Azure SQL DB, which might move databases across servers.</span></span> <span data-ttu-id="b5ea1-195">Dayanıklı işlemler arasında birden fazla bağlamı uygulamak için bkz: [dayanıklı Entity Framework Core SQL bağlantıları uygulama](../implement-resilient-applications/implement-resilient-entity-framework-core-sql-connections.md) bu kılavuzun devamında bölümü.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-195">For implementing resilient transactions across multiple contexts, see the [Implementing resilient Entity Framework Core SQL connections](../implement-resilient-applications/implement-resilient-entity-framework-core-sql-connections.md) section later in this guide.</span></span>

<span data-ttu-id="b5ea1-196">Daha anlaşılır olması için aşağıdaki örnek, bu işlem tek bir kod parçasını gösterir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-196">For clarity, the following example shows the whole process in a single piece of code.</span></span> <span data-ttu-id="b5ea1-197">Ancak, hizmetine uygulama gerçekten bulunanad ve sürdürmek daha kolay olacak şekilde bu mantığı birden çok sınıflara bölme.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-197">However, the eShopOnContainers implementation is actually refactored and split this logic into multiple classes so it is easier to maintain.</span></span>

```csharp
// Update Product from the Catalog microservice
//
public async Task<IActionResult> UpdateProduct([FromBody]CatalogItem productToUpdate)
{
  var catalogItem =
       await _catalogContext.CatalogItems.SingleOrDefaultAsync(i => i.Id ==
                                                               productToUpdate.Id);
  if (catalogItem == null) return NotFound();

  bool raiseProductPriceChangedEvent = false;
  IntegrationEvent priceChangedEvent = null;

  if (catalogItem.Price != productToUpdate.Price)
          raiseProductPriceChangedEvent = true;

  if (raiseProductPriceChangedEvent) // Create event if price has changed
  {
      var oldPrice = catalogItem.Price;
      priceChangedEvent = new ProductPriceChangedIntegrationEvent(catalogItem.Id,
                                                                  productToUpdate.Price,
                                                                  oldPrice);
  }
  // Update current product
  catalogItem = productToUpdate;

  // Just save the updated product if the Product's Price hasn't changed.
  if (!raiseProductPriceChangedEvent)
  {
      await _catalogContext.SaveChangesAsync();
  }
  else  // Publish to event bus only if product price changed
  {
        // Achieving atomicity between original DB and the IntegrationEventLog
        // with a local transaction
        using (var transaction = _catalogContext.Database.BeginTransaction())
        {
           _catalogContext.CatalogItems.Update(catalogItem);
           await _catalogContext.SaveChangesAsync();

           // Save to EventLog only if product price changed
           if(raiseProductPriceChangedEvent)
               await _integrationEventLogService.SaveEventAsync(priceChangedEvent);

           transaction.Commit();
        }

      // Publish the integration event through the event bus
      _eventBus.Publish(priceChangedEvent);

      integrationEventLogService.MarkEventAsPublishedAsync(
                                                priceChangedEvent);
  }

  return Ok();
}

```

<span data-ttu-id="b5ea1-198">ProductPriceChangedIntegrationEvent tümleştirme olayı oluşturulduktan sonra özgün etki alanı işlemi (katalog öğesi güncelleştirme) depolayan işlem olayın Kalıcılık EventLog tabloda da içerir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-198">After the ProductPriceChangedIntegrationEvent integration event is created, the transaction that stores the original domain operation (update the catalog item) also includes the persistence of the event in the EventLog table.</span></span> <span data-ttu-id="b5ea1-199">Bu tek bir işlem yapar ve her zaman gönderilen olay iletileri olup olmadığını denetlemek mümkün olacaktır.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-199">This makes it a single transaction, and you will always be able to check whether event messages were sent.</span></span>

<span data-ttu-id="b5ea1-200">Olay günlüğü tablosu ile aynı veritabanında yerel bir işlem kullanarak özgün veritabanı işlemi, atomik olarak güncelleştirilir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-200">The event log table is updated atomically with the original database operation, using a local transaction against the same database.</span></span> <span data-ttu-id="b5ea1-201">İşlemleri başarısız olursa, bir özel durum ve işlem bu nedenle etki alanı işlemleri ve tabloya kaydedilen olay iletileri arasında tutarlılığı koruma herhangi bir tamamlanmış işlem geri alınır.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-201">If any of the operations fail, an exception is thrown and the transaction rolls back any completed operation, thus maintaining consistency between the domain operations and the event messages saved to the table.</span></span>

### <a name="receiving-messages-from-subscriptions-event-handlers-in-receiver-microservices"></a><span data-ttu-id="b5ea1-202">Aboneliklerden iletiler almaya: alıcısı, mikro hizmetler olay işleyicileri</span><span class="sxs-lookup"><span data-stu-id="b5ea1-202">Receiving messages from subscriptions: event handlers in receiver microservices</span></span>

<span data-ttu-id="b5ea1-203">Olay aboneliği mantığı ek olarak, iç kod (örneğin, bir geri arama yöntemi) tümleştirme olay işleyicileri için uygulamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-203">In addition to the event subscription logic, you need to implement the internal code for the integration event handlers (like a callback method).</span></span> <span data-ttu-id="b5ea1-204">Burada belirli bir türde olay iletileri işlenen ve alınacak belirttiğiniz olay işleyicisidir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-204">The event handler is where you specify where the event messages of a certain type will be received and processed.</span></span>

<span data-ttu-id="b5ea1-205">Bir olay işleyicisi, olay örneği ilk olay veri yolundan iletiyi alır.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-205">An event handler first receives an event instance from the event bus.</span></span> <span data-ttu-id="b5ea1-206">Ardından bu tümleştirme, yayma ve olay alıcısı mikro hizmet durumunda bir değişiklik olarak kalıcı hale olay, ilgili işlenecek bileşeni bulur.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-206">Then it locates the component to be processed related to that integration event, propagating and persisting the event as a change in state in the receiver microservice.</span></span> <span data-ttu-id="b5ea1-207">Örneğin, ProductPriceChanged olay Kataloğu mikro kaynaklanıyorsa, sepet mikro hizmet içinde işlenir ve aşağıdaki kodda gösterildiği gibi bu alıcı sepet mikro hizmet olarak iyi durumda değiştirir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-207">For example, if a ProductPriceChanged event originates in the catalog microservice, it is handled in the basket microservice and changes the state in this receiver basket microservice as well, as shown in the following code.</span></span>

```csharp
namespace Microsoft.eShopOnContainers.Services.Basket.API.IntegrationEvents.EventHandling
{
    public class ProductPriceChangedIntegrationEventHandler :
        IIntegrationEventHandler<ProductPriceChangedIntegrationEvent>
    {
        private readonly IBasketRepository _repository;

        public ProductPriceChangedIntegrationEventHandler(
            IBasketRepository repository)
        {
            _repository = repository;
        }

        public async Task Handle(ProductPriceChangedIntegrationEvent @event)
        {
            var userIds = await _repository.GetUsers();
            foreach (var id in userIds)
            {
                var basket = await _repository.GetBasket(id);
                await UpdatePriceInBasketItems(@event.ProductId, @event.NewPrice, basket);
            }
        }

        private async Task UpdatePriceInBasketItems(int productId, decimal newPrice,
            CustomerBasket basket)
        {
            var itemsToUpdate = basket?.Items?.Where(x => int.Parse(x.ProductId) ==
                productId).ToList();
            if (itemsToUpdate != null)
            {
                foreach (var item in itemsToUpdate)
                {
                    if(item.UnitPrice != newPrice)
                    {
                        var originalPrice = item.UnitPrice;
                        item.UnitPrice = newPrice;
                        item.OldUnitPrice = originalPrice;
                    }
                }
                await _repository.UpdateBasket(basket);
            }
        }
    }
}
```

<span data-ttu-id="b5ea1-208">Ürün sepet örneği hiçbirinde var olup olmadığını doğrulamak olay işleyicisi gerekir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-208">The event handler needs to verify whether the product exists in any of the basket instances.</span></span> <span data-ttu-id="b5ea1-209">Ayrıca, her ilgili sepet satır öğesi için öğe fiyat güncelleştirir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-209">It also updates the item price for each related basket line item.</span></span> <span data-ttu-id="b5ea1-210">Son olarak, Şekil 6-24'te gösterildiği gibi fiyat değişikliği hakkında kullanıcıya görüntülenecek bir uyarı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-210">Finally, it creates an alert to be displayed to the user about the price change, as shown in Figure 6-24.</span></span>

![Tarayıcı Görünümü işleminin kullanıcı sepet bildirim değiştirin.](./media/image25.png)

<span data-ttu-id="b5ea1-212">**Şekil 6-24**.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-212">**Figure 6-24**.</span></span> <span data-ttu-id="b5ea1-213">Bir öğe fiyat değişikliği sepet, tümleştirme olayları tarafından iletilen olarak görüntüleme</span><span class="sxs-lookup"><span data-stu-id="b5ea1-213">Displaying an item price change in a basket, as communicated by integration events</span></span>

## <a name="idempotency-in-update-message-events"></a><span data-ttu-id="b5ea1-214">Teklik update ileti olayları içinde</span><span class="sxs-lookup"><span data-stu-id="b5ea1-214">Idempotency in update message events</span></span>

<span data-ttu-id="b5ea1-215">Update ileti olayları önemli bir yönüdür iletişimde herhangi bir noktada bir arıza denenmesi için iletiyi neden olmamalıdır olup.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-215">An important aspect of update message events is that a failure at any point in the communication should cause the message to be retried.</span></span> <span data-ttu-id="b5ea1-216">Aksi takdirde bir arka plan görevi, bir yarış durumu oluşturma yayımlanmış olduğu bir olay yayımlaması deneyebilir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-216">Otherwise a background task might try to publish an event that has already been published, creating a race condition.</span></span> <span data-ttu-id="b5ea1-217">Güncelleştirmelerin etkili veya yinelenen bir algılayabilir emin olmak için yeterli bilgi sağladıkları olduğunu emin olmak için atmak ve tek geri yanıt gönderir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-217">You need to make sure that the updates are either idempotent or that they provide enough information to ensure that you can detect a duplicate, discard it, and send back only one response.</span></span>

<span data-ttu-id="b5ea1-218">Daha önce belirtildiği gibi sonuç değiştirmeden bir işlem birden çok kez gerçekleştirilebilir Teklik anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-218">As noted earlier, idempotency means that an operation can be performed multiple times without changing the result.</span></span> <span data-ttu-id="b5ea1-219">İleti bir ortamda, birden çok kez alıcı mikro hizmet için sonucu değiştirmeden edinebilir, olayları iletişim kurarken, bir olay etkili olduğu gibi.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-219">In a messaging environment, as when communicating events, an event is idempotent if it can be delivered multiple times without changing the result for the receiver microservice.</span></span> <span data-ttu-id="b5ea1-220">Bu olayın yapısı nedeniyle gerekli olabilir veya şekli nedeniyle sistem olayını işler.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-220">This may be necessary because of the nature of the event itself, or because of the way the system handles the event.</span></span> <span data-ttu-id="b5ea1-221">İleti Teklik Mesajlaşma deposu kullanan herhangi bir uygulama, yalnızca olay veri yolu tasarımın uygulamalarda önemlidir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-221">Message idempotency is important in any application that uses messaging, not just in applications that implement the event bus pattern.</span></span>

<span data-ttu-id="b5ea1-222">Yalnızca bu veri tablosunda yoksa bir tabloya veri ekleyen bir SQL deyimi bir kez etkili işlem örneğidir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-222">An example of an idempotent operation is a SQL statement that inserts data into a table only if that data is not already in the table.</span></span> <span data-ttu-id="b5ea1-223">SQL deyimi ekleyin kaç kez çalıştırdığınız önemli değildir; Sonuç aynı olacaktır — tablo verileri içerir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-223">It does not matter how many times you run that insert SQL statement; the result will be the same—the table will contain that data.</span></span> <span data-ttu-id="b5ea1-224">Bu gibi Teklik, iletilerin potansiyel olarak gönderilebilir, iletileri ile ilgilenirken gerekirse ve bu nedenle işlenen defadan de olabilir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-224">Idempotency like this can also be necessary when dealing with messages if the messages could potentially be sent and therefore processed more than once.</span></span> <span data-ttu-id="b5ea1-225">Örneğin, bir gönderici tam olarak aynı iletiyi birden çok kez göndermek yeniden deneme mantığı neden olursa, kez etkili olduğundan emin olmak gerekir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-225">For instance, if retry logic causes a sender to send exactly the same message more than once, you need to make sure that it is idempotent.</span></span>

<span data-ttu-id="b5ea1-226">Tasarım ıdempotent iletileri mümkündür.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-226">It is possible to design idempotent messages.</span></span> <span data-ttu-id="b5ea1-227">Örneğin, "25 ABD Doları ürün fiyatı"$5 ürün fiyatı eklemek yerine."set" ifadesini içeren bir olay oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-227">For example, you can create an event that says "set the product price to $25" instead of "add $5 to the product price."</span></span> <span data-ttu-id="b5ea1-228">İlk iletinin herhangi sayıda güvenli bir şekilde işleyebilir ve sonuç aynı olacaktır.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-228">You could safely process the first message any number of times and the result will be the same.</span></span> <span data-ttu-id="b5ea1-229">Bu ikinci bir ileti için doğru değil.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-229">That is not true for the second message.</span></span> <span data-ttu-id="b5ea1-230">Ancak, hatta ilk durumda, sistem, daha yeni bir fiyat değişikliği olay gönderebilmesini ve yeni fiyatın üzerine yazılması çünkü ilk olayı işlemek istemeyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-230">But even in the first case, you might not want to process the first event, because the system could also have sent a newer price-change event and you would be overwriting the new price.</span></span>

<span data-ttu-id="b5ea1-231">Başka bir örnek, bir sipariş tamamlandı olay birden fazla aboneye yayılmamış olmasından olabilir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-231">Another example might be an order-completed event being propagated to multiple subscribers.</span></span> <span data-ttu-id="b5ea1-232">Sipariş tamamlandı aynı etkinlik için yinelenen ileti olayları olsa bile, sipariş bilgilerini yalnızca bir kez, diğer sistemler güncelleştirilmesi önemlidir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-232">It is important that order information be updated in other systems just once, even if there are duplicated message events for the same order-completed event.</span></span>

<span data-ttu-id="b5ea1-233">Bir tür olay başına kimlik her olay alıcı yalnızca bir kez işlenir zorlar mantıksal oluşturabilmesi uygundur.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-233">It is convenient to have some kind of identity per event so that you can create logic that enforces that each event is processed only once per receiver.</span></span>

<span data-ttu-id="b5ea1-234">Bazı ileti işleme kendiliğinden etkilidir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-234">Some message processing is inherently idempotent.</span></span> <span data-ttu-id="b5ea1-235">Bir sistem görüntüsü küçük resimler oluşturur, örneğin, kaç kez oluşturulan küçük resim hakkında bir ileti işlendikten önemli değil; küçük resimler oluşturulur ve her seferinde oldukları aynı sonuç elde edilir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-235">For example, if a system generates image thumbnails, it might not matter how many times the message about the generated thumbnail is processed; the outcome is that the thumbnails are generated and they are the same every time.</span></span> <span data-ttu-id="b5ea1-236">Öte yandan, bir kredi kartından çekim ödeme ağ geçidi çağırma gibi işlemler ıdempotent hiç olmayabilir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-236">On the other hand, operations such as calling a payment gateway to charge a credit card may not be idempotent at all.</span></span> <span data-ttu-id="b5ea1-237">Bu gibi durumlarda birden çok kez bir iletiyi işlemeyi beklediğiniz etkin olduğundan emin olmak gerekir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-237">In these cases, you need to ensure that processing a message multiple times has the effect that you expect.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="b5ea1-238">Ek kaynaklar</span><span class="sxs-lookup"><span data-stu-id="b5ea1-238">Additional resources</span></span>

- <span data-ttu-id="b5ea1-239">**İleti Teklik uygularken**</span><span class="sxs-lookup"><span data-stu-id="b5ea1-239">**Honoring message idempotency**</span></span> <br/>
    <https://docs.microsoft.com/previous-versions/msp-n-p/jj591565(v=pandp.10)#honoring-message-idempotency>

## <a name="deduplicating-integration-event-messages"></a><span data-ttu-id="b5ea1-240">Tümleştirme olay iletileri alanında yinelenenleri kaldırma</span><span class="sxs-lookup"><span data-stu-id="b5ea1-240">Deduplicating integration event messages</span></span>

<span data-ttu-id="b5ea1-241">İleti olayları gönderilen ve farklı düzeylerde abonelik başına yalnızca bir kez işlenen emin olmak isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-241">You can make sure that message events are sent and processed just once per subscriber at different levels.</span></span> <span data-ttu-id="b5ea1-242">Kullanmakta olduğunuz Mesajlaşma altyapısı tarafından sunulan bir yinelenenleri kaldırma özelliğini kullanan bir yoludur.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-242">One way is to use a deduplication feature offered by the messaging infrastructure you are using.</span></span> <span data-ttu-id="b5ea1-243">Başka bir özel mantığı, hedef mikro uygulamaktır.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-243">Another is to implement custom logic in your destination microservice.</span></span> <span data-ttu-id="b5ea1-244">Hem aktarım düzeyi ve uygulama düzeyinde doğrulamaları sahip, en iyi sonucu var.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-244">Having validations at both the transport level and the application level is your best bet.</span></span>

### <a name="deduplicating-message-events-at-the-eventhandler-level"></a><span data-ttu-id="b5ea1-245">İleti olayları EventHandler düzeyinde alanında yinelenenleri kaldırma</span><span class="sxs-lookup"><span data-stu-id="b5ea1-245">Deduplicating message events at the EventHandler level</span></span>

<span data-ttu-id="b5ea1-246">Bir olay yalnızca bir kez herhangi bir alıcı tarafından işlendiğinden emin olmak için bir olay işleyicileri ileti olayları işlerken belirli mantığı uygulayarak yoludur.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-246">One way to make sure that an event is processed just once by any receiver is by implementing certain logic when processing the message events in event handlers.</span></span> <span data-ttu-id="b5ea1-247">Örneğin, olan hizmetine uygulamada kullanılan yaklaşım de görebileceğiniz gibi [kaynak kodu UserCheckoutAcceptedIntegrationEventHandler sınıfın](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/IntegrationEvents/EventHandling/UserCheckoutAcceptedIntegrationEventHandler.cs) bir UserCheckoutAcceptedIntegrationEvent aldığında Tümleştirme olay.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-247">For example, that is the approach used in the eShopOnContainers application, as you can see in the [source code of the UserCheckoutAcceptedIntegrationEventHandler class](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/IntegrationEvents/EventHandling/UserCheckoutAcceptedIntegrationEventHandler.cs) when it receives an UserCheckoutAcceptedIntegrationEvent integration event.</span></span> <span data-ttu-id="b5ea1-248">(Bu durumda biz CreateOrderCommand eventMsg.RequestId komut işleyicisi için göndermeden önce bir tanımlayıcı olarak kullanarak, bir IdentifiedCommand ile sarmalamanız).</span><span class="sxs-lookup"><span data-stu-id="b5ea1-248">(In this case we wrap the CreateOrderCommand with an IdentifiedCommand, using the eventMsg.RequestId as an identifier, before sending it to the command handler).</span></span>

### <a name="deduplicating-messages-when-using-rabbitmq"></a><span data-ttu-id="b5ea1-249">RabbitMQ kullanırken alanında yinelenenleri kaldırma iletileri</span><span class="sxs-lookup"><span data-stu-id="b5ea1-249">Deduplicating messages when using RabbitMQ</span></span>

<span data-ttu-id="b5ea1-250">Aralıklı ağ hataları meydana geldiğinde iletileri çoğaltılabilir ve ileti alıcısı şu yinelenen iletileri işlemeye hazır olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-250">When intermittent network failures happen, messages can be duplicated, and the message receiver must be ready to handle these duplicated messages.</span></span> <span data-ttu-id="b5ea1-251">Mümkünse, alıcılar, bunları yinelenenleri kaldırma ile açıkça işlenmesi daha iyidir bir kere etkili olacak şekilde iletileri işlemesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-251">If possible, receivers should handle messages in an idempotent way, which is better than explicitly handling them with deduplication.</span></span>

<span data-ttu-id="b5ea1-252">Şunlara göre [RabbitMQ belgeleri](https://www.rabbitmq.com/reliability.html#consumer), "ileti bir tüketici teslim ve ardından (tüketici bağlantı kesildi, örneğin önce onu onaylanır değil çünkü) yeniden kuyruğa durumunda RabbitMQ üzerinde redelivered bayrağı ayarlayacak Bu (aynı tüketici mı farklı bir için) yeniden iletildiğinde.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-252">According to the [RabbitMQ documentation](https://www.rabbitmq.com/reliability.html#consumer), “If a message is delivered to a consumer and then requeued (because it was not acknowledged before the consumer connection dropped, for example) then RabbitMQ will set the redelivered flag on it when it is delivered again (whether to the same consumer or a different one).</span></span>

<span data-ttu-id="b5ea1-253">"Redelivered" bayrağı ayarlandıysa, ileti zaten işlenmiş çünkü alıcı, dikkate almalısınız.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-253">If the “redelivered” flag is set, the receiver must take that into account, because the message might already have been processed.</span></span> <span data-ttu-id="b5ea1-254">Ancak bu garanti edilmez. ağ sorunları nedeniyle ileti Aracısı, belki de sol sonra yapılacak hiçbir zaman alıcı ulaşmış olabilir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-254">But that is not guaranteed; the message might never have reached the receiver after it left the message broker, perhaps because of network issues.</span></span> <span data-ttu-id="b5ea1-255">"Redelivered" bayrak ayarlanmazsa, diğer yandan, bu iletiyi birden çok kez gönderildiğini değil garanti edilir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-255">On the other hand, if the “redelivered” flag is not set, it is guaranteed that the message has not been sent more than once.</span></span> <span data-ttu-id="b5ea1-256">Bu nedenle, yalnızca "redelivered" bayrak iletisinde ayarlanırsa iletiler veya işlem iletileri bir kere etkili olacak şekilde alanında yinelenenleri kaldırma alıcı gerekir.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-256">Therefore, the receiver needs to deduplicate messages or process messages in an idempotent way only if the “redelivered” flag is set in the message.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="b5ea1-257">Ek kaynaklar</span><span class="sxs-lookup"><span data-stu-id="b5ea1-257">Additional resources</span></span>

- <span data-ttu-id="b5ea1-258">**Çatalı hizmetine NServiceBus (yazılım) kullanma** \\</span><span class="sxs-lookup"><span data-stu-id="b5ea1-258">**Forked eShopOnContainers using NServiceBus (Particular Software)** \\</span></span>
    <https://go.particular.net/eShopOnContainers>

- <span data-ttu-id="b5ea1-259">**Mesajlaşma typu EventDriven** \\</span><span class="sxs-lookup"><span data-stu-id="b5ea1-259">**Event Driven Messaging** \\</span></span>
    [http://soapatterns.org/design\_patterns/event\_driven\_messaging](http://soapatterns.org/design_patterns/event_driven_messaging)

- <span data-ttu-id="b5ea1-260">**Jimmy Bogard. Doğru dayanıklılığı yeniden düzenleme: Bağlantı değerlendirme** \\</span><span class="sxs-lookup"><span data-stu-id="b5ea1-260">**Jimmy Bogard. Refactoring Towards Resilience: Evaluating Coupling** \\</span></span>
    <https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/>

- <span data-ttu-id="b5ea1-261">**Kanal Yayımla-abone ol** \\</span><span class="sxs-lookup"><span data-stu-id="b5ea1-261">**Publish-Subscribe channel** \\</span></span>
    <https://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html>

- <span data-ttu-id="b5ea1-262">**Sınırlanmış Bağlamlar arasında iletişim kurma** \\</span><span class="sxs-lookup"><span data-stu-id="b5ea1-262">**Communicating Between Bounded Contexts** \\</span></span>
    <https://docs.microsoft.com/previous-versions/msp-n-p/jj591572(v=pandp.10)>

- <span data-ttu-id="b5ea1-263">**Son tutarlılık** \\</span><span class="sxs-lookup"><span data-stu-id="b5ea1-263">**Eventual Consistency** \\</span></span>
    [https://en.wikipedia.org/wiki/Eventual\_consistency](https://en.wikipedia.org/wiki/Eventual_consistency)

- <span data-ttu-id="b5ea1-264">**Philip Brown. Tümleştirmeye yönelik stratejiler sınırlanmış bağlamlar** \\</span><span class="sxs-lookup"><span data-stu-id="b5ea1-264">**Philip Brown. Strategies for Integrating Bounded Contexts** \\</span></span>
    <https://www.culttt.com/2014/11/26/strategies-integrating-bounded-contexts/>

- <span data-ttu-id="b5ea1-265">**Chris Richardson. Toplamlar, olay kaynağını belirleme ve CQRS - bölüm 2 kullanarak işlem mikro Hizmetleri Geliştirme** \\</span><span class="sxs-lookup"><span data-stu-id="b5ea1-265">**Chris Richardson. Developing Transactional Microservices Using Aggregates, Event Sourcing and CQRS - Part 2** \\</span></span>
    <https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson>

- <span data-ttu-id="b5ea1-266">**Chris Richardson. Olay kaynağını belirleme düzeni** \\</span><span class="sxs-lookup"><span data-stu-id="b5ea1-266">**Chris Richardson. Event Sourcing pattern** \\</span></span>
    <https://microservices.io/patterns/data/event-sourcing.html>

- <span data-ttu-id="b5ea1-267">**Olay kaynağını belirleme ile tanışın** \\</span><span class="sxs-lookup"><span data-stu-id="b5ea1-267">**Introducing Event Sourcing** \\</span></span>
    <https://docs.microsoft.com/previous-versions/msp-n-p/jj591559(v=pandp.10)>

- <span data-ttu-id="b5ea1-268">**Olay Store veritabanı**.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-268">**Event Store database**.</span></span> <span data-ttu-id="b5ea1-269">Resmi sitesi.</span><span class="sxs-lookup"><span data-stu-id="b5ea1-269">Official site.</span></span> \
    <https://geteventstore.com/>

- <span data-ttu-id="b5ea1-270">**Patrick Nommensen. Mikro hizmetlere yönelik olay odaklı veri yönetimi** \\</span><span class="sxs-lookup"><span data-stu-id="b5ea1-270">**Patrick Nommensen. Event-Driven Data Management for Microservices** \\</span></span>
    <https://dzone.com/articles/event-driven-data-management-for-microservices-1>

- <span data-ttu-id="b5ea1-271">**CAP Teoremi** \\</span><span class="sxs-lookup"><span data-stu-id="b5ea1-271">**The CAP Theorem** \\</span></span>
    [https://en.wikipedia.org/wiki/CAP\_theorem](https://en.wikipedia.org/wiki/CAP_theorem)

- <span data-ttu-id="b5ea1-272">**CAP Teoremi nedir?**</span><span class="sxs-lookup"><span data-stu-id="b5ea1-272">**What is CAP Theorem?**</span></span> \
    <https://www.quora.com/What-Is-CAP-Theorem-1>

- <span data-ttu-id="b5ea1-273">**Veri tutarlılığı temel bilgileri** \\</span><span class="sxs-lookup"><span data-stu-id="b5ea1-273">**Data Consistency Primer** \\</span></span>
    <https://docs.microsoft.com/previous-versions/msp-n-p/dn589800(v=pandp.10)>

- <span data-ttu-id="b5ea1-274">**Saling rick. CAP Teoremi: "Her şey farklı Bulut ve Internet ile budur"** \\</span><span class="sxs-lookup"><span data-stu-id="b5ea1-274">**Rick Saling. The CAP Theorem: Why “Everything is Different” with the Cloud and Internet** \\</span></span>
    <https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/>

- <span data-ttu-id="b5ea1-275">**Eric Brewer. CAP on yıl: "Kurallar" nasıl değişti** \\</span><span class="sxs-lookup"><span data-stu-id="b5ea1-275">**Eric Brewer. CAP Twelve Years Later: How the "Rules" Have Changed** \\</span></span>
    <https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed>

- <span data-ttu-id="b5ea1-276">**Azure hizmet veri yolu. Aracılı Mesajlaşma: Yinelenen algılama**  \\</span><span class="sxs-lookup"><span data-stu-id="b5ea1-276">**Azure Service Bus. Brokered Messaging: Duplicate Detection**  \\</span></span>
    <https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25>

- <span data-ttu-id="b5ea1-277">**Güvenilirlik Kılavuzu** (RabbitMQ belgeleri) \\</span><span class="sxs-lookup"><span data-stu-id="b5ea1-277">**Reliability Guide** (RabbitMQ documentation) \\</span></span>
    [https://www.rabbitmq.com/reliability.html\#consumer](https://www.rabbitmq.com/reliability.html#consumer)

- <span data-ttu-id="b5ea1-278">**Azure hizmet veri yolu. Aracılı Mesajlaşma: Yinelenen algılama** \\</span><span class="sxs-lookup"><span data-stu-id="b5ea1-278">**Azure Service Bus. Brokered Messaging: Duplicate Detection** \\</span></span>
    <https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25>

- <span data-ttu-id="b5ea1-279">**Güvenilirlik Kılavuzu** (RabbitMQ belgeleri) \\</span><span class="sxs-lookup"><span data-stu-id="b5ea1-279">**Reliability Guide** (RabbitMQ documentation) \\</span></span>
    [https://www.rabbitmq.com/reliability.html\#consumer](https://www.rabbitmq.com/reliability.html%23consumer)

> [!div class="step-by-step"]
> <span data-ttu-id="b5ea1-280">[Önceki](rabbitmq-event-bus-development-test-environment.md)
> [İleri](test-aspnet-core-services-web-apps.md)</span><span class="sxs-lookup"><span data-stu-id="b5ea1-280">[Previous](rabbitmq-event-bus-development-test-environment.md)
[Next](test-aspnet-core-services-web-apps.md)</span></span>
