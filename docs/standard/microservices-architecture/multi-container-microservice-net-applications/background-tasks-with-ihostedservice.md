---
title: Ihostedservice ve BackgroundService sınıfı ile mikro hizmetler içindeki arka plan görevlerini uygulama
description: Kapsayıcılı .NET uygulamaları için .NET mikro hizmet mimarisi | .NET Core mikro hizmetler arka plan görevleri uygulamak için Ihostedservice ve BackgroundService kullanılacak yeni seçeneklerini anlayın.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 01/07/2019
ms.openlocfilehash: 638c9b9bae97b90b94c0ca9b421bc20cd3eb41ee
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967197"
---
# <a name="implement-background-tasks-in-microservices-with-ihostedservice-and-the-backgroundservice-class"></a>Ihostedservice ve BackgroundService sınıfı ile mikro hizmetler içindeki arka plan görevlerini uygulama

Arka plan görevleri ve zamanlanmış işleri, sonuç olarak, bir mikro hizmet tabanlı uygulama veya uygulama herhangi bir türden uygulamak için ihtiyacınız olabilecek bir şey var. Bir mikro hizmet mimarisi kullanırken, bir tek bir mikro hizmet işlemi/ihtiyacınız veya bile, tek bir örneği çalıştığından emin olmak, aşağı/yukarı ölçeklendirebilirsiniz bu arka plan görevlerinin barındırılması için kapsayıcı uygulayabileceğiniz fark mikro hizmet işlemi/kapsayıcı.

Bir genel bakış açısıyla, .NET Core Biz bu tür bir görev çağrılır *barındırılan Hizmetler*, çünkü bunlar, ana bilgisayar/uygulama/mikro hizmet içinde ana bilgisayar Hizmetleri/mantığı. Bu durumda, barındırılan hizmetin yalnızca bir sınıf ile arka plan görevi mantıksal anlamına gelir.

.NET Core 2.0 beri framework adlı yeni bir arabirim sağlar. <xref:Microsoft.Extensions.Hosting.IHostedService> kolayca barındırılan uygulama hizmetleri için yardımcı olur. Temel web ana arka planda çalışan birden fazla arka plan görevleri (barındırılan hizmetler) kaydedebilirsiniz veya konağın çalıştığından, 6-26 görüntüde gösterildiği gibi olur.

![Web uygulamaları, .NET Core, ASP.NET Core 1.x ve 2.x'i desteği IWebHost arka plan 2,1 destekler IHost düz konsol uygulamaları ile arka plan işlemleri için işler.](./media/image26.png)

**Şekil 6-26**. Bir ana bilgisayar ve bir Web barındırma Ihostedservice kullanma

Yapılan arasındaki farka dikkat edin `WebHost` ve `Host`. 

A `WebHost` (temel sınıf uygulama `IWebHost`) HTTP sunucusu özellikleri IF gibi işleme sağlamak için kullandığınız altyapı yapıt uygulayan bir MVC web uygulaması veya Web API'si hizmeti ASP.NET Core 2.0 sürümünde olduğu. ASP.NET Core, bağımlılık ekleme, istek ardışık düzeni, vb. middlewares eklemek ve tam olarak bu kullanmak sağlayarak yeni tüm altyapı özelliği sağlar `IHostedServices` arka plan görevleri için.

A `Host` (temel sınıf uygulama `IHost`) .NET Core 2.1 içinde kullanılmaya başlandı. Temel olarak, bir `Host` ile sahip daha benzer bir altyapıya sahip sağlar `WebHost` (bağımlılık ekleme, barındırılan hizmetler, vb.), ancak bu durumda, yalnızca basit ve daha hafif bir işlem, MVC için ilgili hiçbir şey barındırmasını istiyorsanız , Web API'si veya HTTP sunucusu özellikleri.

Bu nedenle, seçebileceğiniz ve barındırılan hizmetler ve başka bir şey işlemek için yalnızca barındırmak için yapılan mikro IHost ile özel bir ana bilgisayar işlemi oluşturun `IHostedServices`, veya alternatif olarak, mevcut bir ASP.NET Core genişletebilirsiniz `WebHost` , mevcut bir ASP.NET Core Web API'si veya MVC uygulaması gibi. 

Artıları ve eksileri iş ve ölçeklenebilirlik ihtiyaçlarınıza bağlı olarak her bir yaklaşıma sahiptir. Alt çizgi, temelde arka plan görevlerinizi HTTP (IWebHost IHost kullanmanız gerekir) ile hiçbir ilişkisi varsa ortaya olmasıdır.

## <a name="registering-hosted-services-in-your-webhost-or-host"></a>WebHost veya konak Hizmetleri'nde barındırılan kaydediliyor

Şimdi ayrıntıya azaltma hakkında daha fazla `IHostedService` kullanımını oldukça benzer olduğundan arabirim bir `WebHost` veya bir `Host`. 

SignalR, barındırılan hizmetler kullanarak bir yapıt örneği olmakla birlikte, gibi çok daha kolay şeyler için kullanabilirsiniz:

-   Değişiklikleri isteyen bir veritabanı yoklama bir arka plan görevi.
-   Bazı önbellek düzenli olarak güncelleştirme, zamanlanmış bir görev.
-   Arka plan iş parçacığında çalıştırılacak bir görev sağlar QueueBackgroundWorkItem uygulaması.
-   Ortak Hizmetleri paylaşırken arka planda bir web uygulamasının bir ileti kuyruktan ileti işleme `ILogger`.
-   Bir arka plan görevi kullanmaya `Task.Run()`.

Ihostedservice tabanlı bir arka plan görevi için bu eylemlerden herhangi birini temel boşaltabilirsiniz.

Bir veya daha çok eklediğiniz şekilde `IHostedServices` içine, `WebHost` veya `Host` bunları oluşturan bir ASP.NET Core, standard DI (bağımlılık ekleme) aracılığıyla kaydederek olan `WebHost` (veya bir `Host` .NET Core 2.1 ve üzeri). Barındırılan hizmetler bilinen içinde kaydetmek zorunda temelde, `ConfigureServices()` yöntemi `Startup` aşağıdaki kod tipik bir ASP.NET Web barındırma olduğu gibi bir sınıf. 

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{            
    //Other DI registrations;

    // Register Hosted Services
    services.AddSingleton<IHostedService, GracePeriodManagerService>();
    services.AddSingleton<IHostedService, MyHostedServiceB>();
    services.AddSingleton<IHostedService, MyHostedServiceC>();
    //...
}
```

Bu kodda, `GracePeriodManagerService` barındırılan hizmet gerçek koddan sıralama iş mikro hizmetine, diğer iki yalnızca iki ek örnekleri.

`IHostedService` Arka plan görev yürütme uygulaması (konak veya mikro hizmet sorgunuzun) ömrünü koordine. Uygulama başladığında ve bazı normal eylemi gerçekleştirin veya uygulama kapatılıyor, temizleme fırsatına sahip görevleri kaydedin.

Kullanmadan `IHostedService`, herhangi bir görev çalıştırmak için bir arka plan iş parçacığı her zaman başlatabilir. Tam olarak uygulamanın kapatma zaman zaman iş parçacığı yalnızca fırsatı Normal temizleme eylemleri çalıştırmak zorunda kalmadan sonlandırılan farktır.

## <a name="the-ihostedservice-interface"></a>Ihostedservice arabirimi

Kaydettiğinizde bir `IHostedService`, .NET Core çağıracaktır `StartAsync()` ve `StopAsync()` yöntemleri, `IHostedService` uygulama başlatma sırasında yazın ve durdurur. Özellikle, sunucu yeniden başlatıldıktan sonra start çağrılır ve `IApplicationLifetime.ApplicationStarted` tetiklenir.

`IHostedService` ' De .NET Core tanımlandığı gibi aşağıdaki gibi görünür.

```csharp
namespace Microsoft.Extensions.Hosting
{
    //
    // Summary:
    //     Defines methods for objects that are managed by the host.
    public interface IHostedService
    {
        //
        // Summary:
        // Triggered when the application host is ready to start the service.
        Task StartAsync(CancellationToken cancellationToken);
        //
        // Summary:
        // Triggered when the application host is performing a graceful shutdown.
        Task StopAsync(CancellationToken cancellationToken);
    }
}
```
Hayal edebileceğiniz gibi birden çok Ihostedservice uygulamaları oluşturabilir ve onları kaydetmek `ConfigureService()` yöntemi daha önce gösterildiği gibi DI kapsayıcıya alın. Bu barındırılan hizmetleri kullanmaya ve yanı sıra uygulama/mikro hizmet durduruldu.

Bir geliştirici olarak durdurma eylemi veya hizmetlerinizi işlenmesinden sorumludur olduğunda `StopAsync()` yöntemi, ana bilgisayar tarafından tetiklenir.

## <a name="implementing-ihostedservice-with-a-custom-hosted-service-class-deriving-from-the-backgroundservice-base-class"></a>Ihostedservice ile BackgroundService temel sınıfından türetilen özel barındırılan hizmet sınıf uygulama

Durmayın sıfırdan özel bir barındırılan hizmet sınıfınızı oluşturma ve uygulama `IHostedService`gibi .NET Core 2.0 kullanarak yapmanız gerekir. 

Ancak, çoğu arka plan görevleri iptal belirteçlerini yönetimi ve diğer normal işlemleri in regard to benzer gereksinimleri olduğundan, yoktur, türetilebilir kullanışlı soyut temel sınıf adlı `BackgroundService` (.NET Core 2.1 sürümünden itibaren kullanılabilir).

Bu sınıf, arka plan görev oluşturmak için gereken ana çalışma sağlar.

' De .NET Core uygulanan aynıdır, sonraki kodu BackgroundService soyut taban sınıfını kullanır.

```csharp
// Copyright (c) .NET Foundation. Licensed under the Apache License, Version 2.0. 
/// <summary>
/// Base class for implementing a long running <see cref="IHostedService"/>.
/// </summary>
public abstract class BackgroundService : IHostedService, IDisposable
{
    private Task _executingTask;
    private readonly CancellationTokenSource _stoppingCts = 
                                                   new CancellationTokenSource();

    protected abstract Task ExecuteAsync(CancellationToken stoppingToken);

    public virtual Task StartAsync(CancellationToken cancellationToken)
    {
        // Store the task we're executing
        _executingTask = ExecuteAsync(_stoppingCts.Token);

        // If the task is completed then return it, 
        // this will bubble cancellation and failure to the caller
        if (_executingTask.IsCompleted)
        {
            return _executingTask;
        }

        // Otherwise it's running
        return Task.CompletedTask;
    }
    
    public virtual async Task StopAsync(CancellationToken cancellationToken)
    {
        // Stop called without start
        if (_executingTask == null)
        {
            return;
        }

        try
        {
            // Signal cancellation to the executing method
            _stoppingCts.Cancel();
        }
        finally
        {
            // Wait until the task completes or the stop token triggers
            await Task.WhenAny(_executingTask, Task.Delay(Timeout.Infinite,
                                                          cancellationToken));
        }

    }

    public virtual void Dispose()
    {
        _stoppingCts.Cancel();
    }
}
```

Önceki Özet temel sınıf, devralınmış bu uygulama sayesinde'den türetilirken uygulamak yeterlidir `ExecuteAsync()` yöntemi kendi özel barındırılan hizmet sınıfı, aşağıda gösterildiği gibi sorgulanır hizmetine koddan Basitleştirilmiş bir veritabanı ve tümleştirme olayları olay gerektiğinde yoluna yayımlama.

```csharp
public class GracePeriodManagerService : BackgroundService
{        
    private readonly ILogger<GracePeriodManagerService> _logger;
    private readonly OrderingBackgroundSettings _settings;

    private readonly IEventBus _eventBus;

    public GracePeriodManagerService(IOptions<OrderingBackgroundSettings> settings,
                                     IEventBus eventBus,
                                     ILogger<GracePeriodManagerService> logger)
    {
        //Constructor’s parameters validations...       
    }

    protected override async Task ExecuteAsync(CancellationToken stoppingToken)
    {
        _logger.LogDebug($"GracePeriodManagerService is starting.");

        stoppingToken.Register(() => 
            _logger.LogDebug($" GracePeriod background task is stopping."));

        while (!stoppingToken.IsCancellationRequested)
        {
            _logger.LogDebug($"GracePeriod task doing background work.");

            // This eShopOnContainers method is querying a database table 
            // and publishing events into the Event Bus (RabbitMS / ServiceBus)
            CheckConfirmedGracePeriodOrders();

            await Task.Delay(_settings.CheckUpdateTime, stoppingToken);
        }
            
        _logger.LogDebug($"GracePeriod background task is stopping.");
    }

    .../...
}
```

Bu belirli durumda hizmetine için belirli bir durumu siparişleri isteyen bir veritabanı tablosu sorgulanırken bir uygulama yöntemi yürütme ve değişiklikleri uygulanırken, olay veri yolu (underneath olabilir aracılığıyla tümleştirme olayları yayımlama RabbitMQ veya Azure Service Bus kullanarak).

Elbette, bunun yerine herhangi diğer iş arka plan görevini çalıştırabilirsiniz.

Oluştururken bu değeri değiştirebilirsiniz ancak varsayılan olarak 5 ikinci zaman aşımı ile iptal belirteci ayarladıktan, `WebHost` kullanarak `UseShutdownTimeout` uzantısı `IWebHostBuilder`. Bu, hizmetimiz 5 daha aniden sonlandırılacak saniye içinde aksi takdirde iptal beklenir anlamına gelir.

Aşağıdaki kodu bu süre 10 saniye olarak değiştirilmesi.

```csharp
WebHost.CreateDefaultBuilder(args)
    .UseShutdownTimeout(TimeSpan.FromSeconds(10))
    ...
```

### <a name="summary-class-diagram"></a>Özet sınıf diyagramı

Aşağıdaki resimde bir görsel Özet sınıflarının ve interfaced IHostedServices uygularken ilgili gösterir.
 
![Sınıf diyagramı: Ihostedservice uygulayan BackgroundService devralır birçok hizmet IWebHost ve IHost barındırabilirsiniz.](./media/image27.png)

**Şekil 6-27**. Birden çok gösteren sınıf diyagramı Ihostedservice için ilgili sınıflar ve arabirimler

### <a name="deployment-considerations-and-takeaways"></a>Dağıtım hakkında önemli noktalar ve paketler

ASP.NET Core dağıtma şeklinizi dikkat etmeniz önemlidir `WebHost` veya .NET Core `Host` nihai çözüm etkileyebilir. Örneğin, dağıtırsanız, `WebHost` IIS veya normal bir Azure App Service, ana uygulama havuzu geri dönüştürülmeden nedeniyle kapatılabilir. Ancak bir orchestrator Kubernetes veya Service Fabric uygulamasına kapsayıcı olarak konağınız dağıtıyorsanız, dinamik ana bilgisayar örneklerini garantili sayısını kontrol edebilirsiniz. Ayrıca, Azure işlevleri gibi bu senaryolar için özellikle yapılan bulutta diğer yaklaşımlar deneyebilirsiniz. Son olarak, hizmetinin her zaman çalışıyor gerekir ve bir Windows sunucusuna dağıttığınız bir Windows hizmetini kullanabilirsiniz.

Ancak için bile bir `WebHost` bir uygulama havuzuna dağıtılmış, yeniden veya hala geçerli olacak uygulamanın bellek içi önbellek, temizleme gibi senaryolar vardır.

`IHostedService` Arabirimi, web uygulaması (.NET Core 2.0 içinde) arka plan görevleri de bir ASP.NET Core başlatmak için kolay bir yol sağlar veya herhangi bir işlem/ana (.NET Core 2.1 ile başlayan `IHost`). Konak kapatılıyor, arka plan görevlerinizi temizleme kodu için normal iptal ile alma fırsatı kendi ana avantajdır.

#### <a name="additional-resources"></a>Ek kaynaklar

-   **ASP.NET Core/Standard 2.0 zamanlanmış bir görev oluşturma** <br/>
    [*https://blog.maartenballiauw.be/post/2017/08/01/building-a-scheduled-cache-updater-in-aspnet-core-2.html*](https://blog.maartenballiauw.be/post/2017/08/01/building-a-scheduled-cache-updater-in-aspnet-core-2.html)

-   **ASP.NET Core 2.0 Ihostedservice uygulama** <br/>
    [*https://www.stevejgordon.co.uk/asp-net-core-2-ihostedservice*](https://www.stevejgordon.co.uk/asp-net-core-2-ihostedservice)

-   **GenericHost ASP.NET Core 2.1 kullanma örneği** <br/>
    [*https://github.com/aspnet/Hosting/tree/release/2.1/samples/GenericHostSample*](https://github.com/aspnet/Hosting/tree/release/2.1/samples/GenericHostSample)

>[!div class="step-by-step"]
>[Önceki](test-aspnet-core-services-web-apps.md)
>[İleri](implement-api-gateways-with-ocelot.md)
