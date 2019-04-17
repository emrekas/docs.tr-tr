---
title: Dayanıklı Entity Framework Core SQL bağlantıları uygulama
description: Dayanıklı Entity Framework Core SQL bağlantıları uygulama hakkında bilgi edinin. Bu yöntem Azure SQL veritabanı bulutta kullanırken özellikle önemlidir.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/16/2018
ms.openlocfilehash: b056df033a584bc51fed5ccd52a58a6331298aa6
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612257"
---
# <a name="implement-resilient-entity-framework-core-sql-connections"></a><span data-ttu-id="dc31c-104">Dayanıklı Entity Framework Core SQL bağlantıları uygulama</span><span class="sxs-lookup"><span data-stu-id="dc31c-104">Implement resilient Entity Framework Core SQL connections</span></span>

<span data-ttu-id="dc31c-105">Azure SQL DB için Entity Framework (EF) çekirdek zaten iç veritabanı bağlantı dayanıklılığı ve yeniden deneme mantığı sağlar.</span><span class="sxs-lookup"><span data-stu-id="dc31c-105">For Azure SQL DB, Entity Framework (EF) Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="dc31c-106">Ancak her biri için Entity Framework yürütme stratejisini etkinleştirmek gereken <xref:Microsoft.EntityFrameworkCore.DbContext> olmasını istiyorsanız bağlantı [dayanıklı EF Core bağlantıları](/ef/core/miscellaneous/connection-resiliency).</span><span class="sxs-lookup"><span data-stu-id="dc31c-106">But you need to enable the Entity Framework execution strategy for each <xref:Microsoft.EntityFrameworkCore.DbContext> connection if you want to have [resilient EF Core connections](/ef/core/miscellaneous/connection-resiliency).</span></span>

<span data-ttu-id="dc31c-107">Örneğin, aşağıdaki kodu EF Core bağlantı düzeyinde bağlantı başarısız olursa şartıyla dayanıklı SQL bağlantısı sağlar.</span><span class="sxs-lookup"><span data-stu-id="dc31c-107">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

```csharp
// Startup.cs from any ASP.NET Core Web API
public class Startup
{
    // Other code ...
    public IServiceProvider ConfigureServices(IServiceCollection services)
    {
        // ...
        services.AddDbContext<CatalogContext>(options =>
        {
            options.UseSqlServer(Configuration["ConnectionString"],
            sqlServerOptionsAction: sqlOptions =>
            {
                sqlOptions.EnableRetryOnFailure(
                maxRetryCount: 10,
                maxRetryDelay: TimeSpan.FromSeconds(30),
                errorNumbersToAdd: null);
            });
        });
    }
//...
}
```

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="dc31c-108">Yürütme stratejileri ve BeginTransaction ve birden çok DbContexts kullanarak açık işlemleri</span><span class="sxs-lookup"><span data-stu-id="dc31c-108">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span>

<span data-ttu-id="dc31c-109">EF Core bağlantıları yeniden deneme etkinleştirildiğinde, EF Core kullanarak gerçekleştirdiğiniz her işlem yeniden denenebilir kendi işlem olur.</span><span class="sxs-lookup"><span data-stu-id="dc31c-109">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retriable operation.</span></span> <span data-ttu-id="dc31c-110">Her sorgu ve her çağrı `SaveChanges` geçici bir hata oluşursa bir birim olarak yeniden denenecek.</span><span class="sxs-lookup"><span data-stu-id="dc31c-110">Each query and each call to `SaveChanges` will be retried as a unit if a transient failure occurs.</span></span>

<span data-ttu-id="dc31c-111">Ancak, kodunuzu kullanarak bir işlem başlatırsa `BeginTransaction`, bir birim olarak kabul edilmesi için gereken işlemleri kendi grubu tanımlayacağınız.</span><span class="sxs-lookup"><span data-stu-id="dc31c-111">However, if your code initiates a transaction using `BeginTransaction`, you're defining your own group of operations that need to be treated as a unit.</span></span> <span data-ttu-id="dc31c-112">İşlem içinde her şeyi bir hata oluşursa geri alınması gerekir.</span><span class="sxs-lookup"><span data-stu-id="dc31c-112">Everything inside the transaction has to be rolled back if a failure occurs.</span></span>

<span data-ttu-id="dc31c-113">EF yürütme stratejisi (yeniden deneme ilkesi) kullanılırken, işlem yürütme denerseniz ve çağırmanızı `SaveChanges` birden çok DbContexts bunun gibi bir özel durum elde edersiniz:</span><span class="sxs-lookup"><span data-stu-id="dc31c-113">If you try to execute that transaction when using an EF execution strategy (retry policy) and you call `SaveChanges` from multiple DbContexts, you'll get an exception like this one:</span></span>

> <span data-ttu-id="dc31c-114">System.InvalidOperationException: 'SqlServerRetryingExecutionStrategy' yapılandırılmış yürütme stratejisi, kullanıcı tarafından başlatılan işlemleri desteklemiyor.</span><span class="sxs-lookup"><span data-stu-id="dc31c-114">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="dc31c-115">İşlem yeniden denenebilir bir birim olarak tüm işlemleri yürütmek için 'DbContext.Database.CreateExecutionStrategy()' tarafından döndürülen yürütme stratejisi kullanın.</span><span class="sxs-lookup"><span data-stu-id="dc31c-115">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retriable unit.</span></span>

<span data-ttu-id="dc31c-116">El ile yürütülmesi gereken her şeyi temsil eden bir temsilci ile EF yürütme stratejisi çağırmak için kullanılan çözümüdür.</span><span class="sxs-lookup"><span data-stu-id="dc31c-116">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="dc31c-117">Geçici bir hata oluşursa yürütme stratejisi temsilciyi yeniden çağırır.</span><span class="sxs-lookup"><span data-stu-id="dc31c-117">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="dc31c-118">Örneğin, aşağıdaki kodu göster nasıl, iki hizmetine birden çok DbContexts gerçekleştirdiğini (\_catalogContext ve IntegrationEventLogContext) ürün ve sonra kaydetme güncelleştirilirken Farklı bir DbContext kullanması gereken ProductPriceChangedIntegrationEvent nesnesi.</span><span class="sxs-lookup"><span data-stu-id="dc31c-118">For example, the following code show how it's implemented in eShopOnContainers with two multiple DbContexts (\_catalogContext and the IntegrationEventLogContext) when updating a product and then saving the ProductPriceChangedIntegrationEvent object, which needs to use a different DbContext.</span></span>

```csharp
public async Task<IActionResult> UpdateProduct(
    [FromBody]CatalogItem productToUpdate)
{
    // Other code ...

    var oldPrice = catalogItem.Price;
    var raiseProductPriceChangedEvent = oldPrice != productToUpdate.Price;

    // Update current product
    catalogItem = productToUpdate;

    // Save product's data and publish integration event through the Event Bus
    // if price has changed
    if (raiseProductPriceChangedEvent)
    {
        //Create Integration Event to be published through the Event Bus
        var priceChangedEvent = new ProductPriceChangedIntegrationEvent(
          catalogItem.Id, productToUpdate.Price, oldPrice);

       // Achieving atomicity between original Catalog database operation and the
       // IntegrationEventLog thanks to a local transaction
       await _catalogIntegrationEventService.SaveEventAndCatalogContextChangesAsync(
           priceChangedEvent);

       // Publish through the Event Bus and mark the saved event as published
       await _catalogIntegrationEventService.PublishThroughEventBusAsync(
           priceChangedEvent);
    }
    // Just save the updated product because the Product's Price hasn't changed.
    else
    {
        await _catalogContext.SaveChangesAsync();
    }
}
```

<span data-ttu-id="dc31c-119">İlk <xref:Microsoft.EntityFrameworkCore.DbContext> olduğu `_catalogContext` ve ikinci `DbContext` içindeki `_integrationEventLogService` nesne.</span><span class="sxs-lookup"><span data-stu-id="dc31c-119">The first <xref:Microsoft.EntityFrameworkCore.DbContext> is `_catalogContext` and the second `DbContext` is within the `_integrationEventLogService` object.</span></span> <span data-ttu-id="dc31c-120">Tüm işleme eylemi gerçekleştiren `DbContext` bir EF yürütme stratejisi kullanarak nesneleri.</span><span class="sxs-lookup"><span data-stu-id="dc31c-120">The Commit action is performed across all `DbContext` objects using an EF execution strategy.</span></span>

<span data-ttu-id="dc31c-121">Bu çok elde etmek için `DbContext` işlemenin `SaveEventAndCatalogContextChangesAsync` kullanan bir `ResilientTransaction` aşağıdaki kodda gösterildiği gibi sınıfı:</span><span class="sxs-lookup"><span data-stu-id="dc31c-121">To achieve this multiple `DbContext` commit, the `SaveEventAndCatalogContextChangesAsync` uses a `ResilientTransaction` class, as shown in the following code:</span></span>

```csharp
public class CatalogIntegrationEventService : ICatalogIntegrationEventService
{
    //…
    public async Task SaveEventAndCatalogContextChangesAsync(
        IntegrationEvent evt)
    {
        // Use of an EF Core resiliency strategy when using multiple DbContexts
        // within an explicit BeginTransaction():
        // https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency
        await ResilientTransaction.New(_catalogContext).ExecuteAsync(async () =>
        {
            // Achieving atomicity between original catalog database 
            // operation and the IntegrationEventLog thanks to a local transaction
            await _catalogContext.SaveChangesAsync();
            await _eventLogService.SaveEventAsync(evt,
                _catalogContext.Database.CurrentTransaction.GetDbTransaction());
        });
    }
}
```

<span data-ttu-id="dc31c-122">`ResilientTransaction.ExecuteAsync` Yöntemi temel bir işlemden geçirilen başlar `DbContext` (`_catalogContext`) ve ardından `EventLogService` değişiklikleri kaydetmek için bu işlem kullanmak `IntegrationEventLogContext` ve ardından tüm hareketi tamamlar.</span><span class="sxs-lookup"><span data-stu-id="dc31c-122">The `ResilientTransaction.ExecuteAsync` method basically begins a transaction from the passed `DbContext` (`_catalogContext`) and then makes the `EventLogService` use that transaction to save changes from the `IntegrationEventLogContext` and then commits the whole transaction.</span></span>

```csharp
public class ResilientTransaction
{
    private DbContext _context;
    private ResilientTransaction(DbContext context) =>
        _context = context ?? throw new ArgumentNullException(nameof(context));

    public static ResilientTransaction New (DbContext context) =>
        new ResilientTransaction(context);

    public async Task ExecuteAsync(Func<Task> action)
    {
        // Use of an EF Core resiliency strategy when using multiple DbContexts 
        // within an explicit BeginTransaction():
        // https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency
        var strategy = _context.Database.CreateExecutionStrategy();
        await strategy.ExecuteAsync(async () =>
        {
            using (var transaction = _context.Database.BeginTransaction())
            {
                await action();
                transaction.Commit();
            }
        });
    }
}
```

## <a name="additional-resources"></a><span data-ttu-id="dc31c-123">Ek kaynaklar</span><span class="sxs-lookup"><span data-stu-id="dc31c-123">Additional resources</span></span>

- <span data-ttu-id="dc31c-124">**Bağlantı dayanıklılığı ve komut durdurma bir ASP.NET MVC uygulamasındaki EF ile** \\</span><span class="sxs-lookup"><span data-stu-id="dc31c-124">**Connection Resiliency and Command Interception with EF in an ASP.NET MVC Application** \\</span></span>
  [https://docs.microsoft.com/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/connection-resiliency-and-command-interception-with-the-entity-framework-in-an-asp-net-mvc-application](/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/connection-resiliency-and-command-interception-with-the-entity-framework-in-an-asp-net-mvc-application)

- <span data-ttu-id="dc31c-125">**Cesar de la Torre. Dayanıklı Entity Framework Core SQL bağlantıları ve işlemleri kullanma** \\</span><span class="sxs-lookup"><span data-stu-id="dc31c-125">**Cesar de la Torre. Using Resilient Entity Framework Core SQL Connections and Transactions** \\</span></span>
  <https://devblogs.microsoft.com/cesardelatorre/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/>

>[!div class="step-by-step"]
><span data-ttu-id="dc31c-126">[Önceki](implement-retries-exponential-backoff.md)
>[İleri](explore-custom-http-call-retries-exponential-backoff.md)</span><span class="sxs-lookup"><span data-stu-id="dc31c-126">[Previous](implement-retries-exponential-backoff.md)
[Next](explore-custom-http-call-retries-exponential-backoff.md)</span></span>
