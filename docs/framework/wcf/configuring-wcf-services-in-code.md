---
title: WCF Hizmetlerini Kodda Yapılandırma
ms.date: 03/30/2017
ms.assetid: 193c725d-134f-4d31-a8f8-4e575233bff6
ms.openlocfilehash: 8a1eeff76b02315143fb7b50ccc41aa18bb9eb0c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61779762"
---
# <a name="configuring-wcf-services-in-code"></a><span data-ttu-id="74e3c-102">WCF Hizmetlerini Kodda Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="74e3c-102">Configuring WCF Services in Code</span></span>
<span data-ttu-id="74e3c-103">Windows Communication Foundation (WCF) hizmetlerini yapılandırma dosyalarının veya kod kullanarak yapılandırmak geliştiricilerin sağlar.</span><span class="sxs-lookup"><span data-stu-id="74e3c-103">Windows Communication Foundation (WCF) allows developers to configure services using configuration files or code.</span></span>  <span data-ttu-id="74e3c-104">Yapılandırma dosyalarını, hizmet dağıtıldıktan sonra yapılandırılması gerektiğinde kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="74e3c-104">Configuration files are useful when a service needs to be configured after being deployed.</span></span> <span data-ttu-id="74e3c-105">Yapılandırma dosyalarını kullanarak, bir BT Uzmanı yalnızca yapılandırma dosyasını güncelleştirmeniz gerekir, hiçbir yeniden derleme gereklidir.</span><span class="sxs-lookup"><span data-stu-id="74e3c-105">When using configuration files, an IT professional only needs to update the configuration file, no recompilation is required.</span></span> <span data-ttu-id="74e3c-106">Yapılandırma dosyaları, ancak karmaşık ve sürdürülmesi zor olabilir.</span><span class="sxs-lookup"><span data-stu-id="74e3c-106">Configuration files, however, can be complex and difficult to maintain.</span></span> <span data-ttu-id="74e3c-107">Yapılandırma dosyalarında hata ayıklama desteği yoktur ve yapılandırma öğelerini yazma yapılandırma dosyalarını zor ve hata yapmaya açık olmasını sağlayan adlarına göre başvuru yapılır.</span><span class="sxs-lookup"><span data-stu-id="74e3c-107">There is no support for debugging configuration files and configuration elements are referenced by names which makes authoring configuration files error-prone and difficult.</span></span> <span data-ttu-id="74e3c-108">WCF hizmetlerini kodda yapılandırma sağlar.</span><span class="sxs-lookup"><span data-stu-id="74e3c-108">WCF also allows you to configure services in code.</span></span> <span data-ttu-id="74e3c-109">Önceki sürümlerinde (4.0 ve daha önceki) WCF yapılandırma Hizmetleri kod kendinden senaryolarda kolaydı <xref:System.ServiceModel.ServiceHost> uç noktalar ve davranışlar ServiceHost.Open çağırmadan önce yapılandırmanıza izin sınıfı.</span><span class="sxs-lookup"><span data-stu-id="74e3c-109">In earlier versions of WCF (4.0 and earlier) configuring services in code was easy in self-hosted scenarios, the <xref:System.ServiceModel.ServiceHost> class allowed you to configure endpoints and behaviors prior to calling ServiceHost.Open.</span></span> <span data-ttu-id="74e3c-110">Barındırılan web senaryolarda, ancak doğrudan için erişiminiz yoksa <xref:System.ServiceModel.ServiceHost> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="74e3c-110">In web hosted scenarios, however, you don’t have direct access to the <xref:System.ServiceModel.ServiceHost> class.</span></span> <span data-ttu-id="74e3c-111">Barındırılan hizmet oluşturmak için gerekli bir web yapılandırmak için bir `System.ServiceModel.ServiceHostFactory` oluşturulan <xref:System.ServiceModel.Activation.ServiceHostFactory> ve tüm gerekli yapılandırma.</span><span class="sxs-lookup"><span data-stu-id="74e3c-111">To configure a web hosted service you were required to create a `System.ServiceModel.ServiceHostFactory` that created the <xref:System.ServiceModel.Activation.ServiceHostFactory> and performed any needed configuration.</span></span> <span data-ttu-id="74e3c-112">.NET 4.5 ile başlayarak, her ikisi de yapılandırmak için daha kolay bir yolu şirket içinde barındırılan ve web hizmetleri kod barındırılan WCF sağlar.</span><span class="sxs-lookup"><span data-stu-id="74e3c-112">Starting with .NET 4.5, WCF provides an easier way to configure both self-hosted and web hosted services in code.</span></span>  
  
## <a name="the-configure-method"></a><span data-ttu-id="74e3c-113">Yapılandırma yöntemi</span><span class="sxs-lookup"><span data-stu-id="74e3c-113">The Configure method</span></span>  
 <span data-ttu-id="74e3c-114">Adlı bir ortak statik metodun yalnızca tanımlama `Configure` aşağıdaki hizmet uygulaması sınıfınızın imzasında ile:</span><span class="sxs-lookup"><span data-stu-id="74e3c-114">Simply define a public static method called `Configure` with the following signature in your service implementation class:</span></span>  
  
```csharp  
public static void Configure(ServiceConfiguration config)  
```  
  
 <span data-ttu-id="74e3c-115">Yapılandırma yöntemi alır bir <xref:System.ServiceModel.ServiceConfiguration> uç noktalar ve davranışlar eklemek geliştiricinin örneği.</span><span class="sxs-lookup"><span data-stu-id="74e3c-115">The Configure method takes a <xref:System.ServiceModel.ServiceConfiguration> instance that enables the developer to add endpoints and behaviors.</span></span> <span data-ttu-id="74e3c-116">Bu yöntem, hizmet ana bilgisayarı açılmadan önce WCF tarafından çağrılır.</span><span class="sxs-lookup"><span data-stu-id="74e3c-116">This method is called by WCF before the service host is opened.</span></span> <span data-ttu-id="74e3c-117">Tanımlandığında, bir app.config veya web.config dosyasında belirtilen tüm hizmet yapılandırma ayarları göz ardı edilir.</span><span class="sxs-lookup"><span data-stu-id="74e3c-117">When defined, any service configuration settings specified in an app.config or web.config file will be ignored.</span></span>  
  
 <span data-ttu-id="74e3c-118">Aşağıdaki kod parçacığını nasıl tanımlanacağı anlatılmakta `Configure` yöntemi ve bir hizmet uç noktası, bir uç nokta davranışı ve hizmet davranışlarını ekleyin:</span><span class="sxs-lookup"><span data-stu-id="74e3c-118">The following code snippet illustrates how to define the `Configure` method and add a service endpoint, an endpoint behavior and service behaviors:</span></span>  
  
```csharp  
public class Service1 : IService1  
    {  
        public static void Configure(ServiceConfiguration config)  
        {  
            ServiceEndpoint se = new ServiceEndpoint(new ContractDescription("IService1"), new BasicHttpBinding(), new EndpointAddress("basic"));  
            se.Behaviors.Add(new MyEndpointBehavior());  
            config.AddServiceEndpoint(se);  
  
            config.Description.Behaviors.Add(new ServiceMetadataBehavior { HttpGetEnabled = true });  
            config.Description.Behaviors.Add(new ServiceDebugBehavior { IncludeExceptionDetailInFaults = true });  
        }  
  
        public string GetData(int value)  
        {  
            return $"You entered: {value}";
        }  
  
        public CompositeType GetDataUsingDataContract(CompositeType composite)  
        {  
            if (composite == null)  
            {  
                throw new ArgumentNullException("composite");  
            }  
            if (composite.BoolValue)  
            {  
                composite.StringValue += "Suffix";  
            }  
            return composite;  
        }  
    }  
```  
  
 <span data-ttu-id="74e3c-119">Https için bir hizmet gibi bir protokolü etkinleştirmek için ya da açıkça protokolünü kullanan bir uç nokta ekleyebilirsiniz veya otomatik olarak, her bir temel adres için bir uç nokta ekleyen ServiceConfiguration.EnableProtocol(Binding) çağırarak uç noktalar ekleyebilirsiniz protokol ve tanımlanan her bir hizmet sözleşmesi ile uyumlu.</span><span class="sxs-lookup"><span data-stu-id="74e3c-119">To enable a protocol such as https for a service, you can either explicitly add an endpoint that uses the protocol or you can automatically add endpoints by calling ServiceConfiguration.EnableProtocol(Binding) which adds an endpoint for each base address compatible with the protocol and each service contract defined.</span></span> <span data-ttu-id="74e3c-120">Aşağıdaki kod ServiceConfiguration.EnableProtocol yönteminin nasıl kullanılacağını göstermektedir:</span><span class="sxs-lookup"><span data-stu-id="74e3c-120">The following code illustrates how to use the ServiceConfiguration.EnableProtocol method:</span></span>  
  
```csharp  
public class Service1 : IService1   
{   
    public string GetData(int value);   
    public static void Configure(ServiceConfiguration config)   
    {   
        // Enable "Add Service Reference" support   
       config.Description.Behaviors.Add( new ServiceMetadataBehavior { HttpGetEnabled = true });   
       // set up support for http, https, net.tcp, net.pipe   
       config.EnableProtocol(new BasicHttpBinding());   
       config.EnableProtocol(new BasicHttpBinding());   
       config.EnableProtocol(new NetTcpBinding());   
       config.EnableProtocol(new NetNamedPipeBinding());   
       // add an extra BasicHttpBinding endpoint at http:///basic   
       config.AddServiceEndpoint(typeof(IService1), new BasicHttpBinding(),"basic");   
    }   
}   
```  
  
 <span data-ttu-id="74e3c-121">Ayarları <`protocolMappings`> bölüm yalnızca uygulama uç nokta için eklenirse kullanılan <xref:System.ServiceModel.ServiceConfiguration> programlı olarak. Çağırarak hizmet yapılandırmasını varsayılan uygulama yapılandırma dosyasından isteğe bağlı olarak yükleyebilir <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> ve ayarlarını değiştirin.</span><span class="sxs-lookup"><span data-stu-id="74e3c-121">The settings in the <`protocolMappings`> section are only used if no application endpoints are added to the <xref:System.ServiceModel.ServiceConfiguration> programmatically.You can optionally load the service configuration from the default application configuration file by calling <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> and then change the settings.</span></span> <span data-ttu-id="74e3c-122"><xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration> Sınıfı ayrıca yapılandırma merkezi yapılandırmasından yük olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="74e3c-122">The <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration> class also allows you to load configuration from a centralized configuration.</span></span> <span data-ttu-id="74e3c-123">Aşağıdaki kod bunu uygulamak nasıl gösterir:</span><span class="sxs-lookup"><span data-stu-id="74e3c-123">The following code illustrates how to implement this:</span></span>  
  
```  
public class Service1 : IService1   
{   
    public void DoWork();   
    public static void Configure(ServiceConfiguration config)   
    {   
          config.LoadFromConfiguration(ConfigurationManager.OpenMappedExeConfiguration(new ExeConfigurationFileMap { ExeConfigFilename = @"c:\sharedConfig\MyConfig.config" }, ConfigurationUserLevel.None));   
    }   
}  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="74e3c-124">Unutmayın <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> yoksayar <`host`> ayarlarında <`service`> etiketi <`system.serviceModel`>.</span><span class="sxs-lookup"><span data-stu-id="74e3c-124">Note that <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> ignores <`host`> settings within the <`service`> tag of <`system.serviceModel`>.</span></span> <span data-ttu-id="74e3c-125">Kavramsal olarak, <`host`> ana bilgisayar yapılandırması, olmayan hizmet yapılandırması ve onu hakkında yapılandırma yöntemi yürütülmeden önce yüklenen alır.</span><span class="sxs-lookup"><span data-stu-id="74e3c-125">Conceptually, <`host`> is about host configuration, not service configuration, and it gets loaded before the Configure method executes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74e3c-126">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="74e3c-126">See also</span></span>

- [<span data-ttu-id="74e3c-127">Yapılandırma Dosyalarını Kullanarak Hizmetleri Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="74e3c-127">Configuring Services Using Configuration Files</span></span>](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)
- [<span data-ttu-id="74e3c-128">İstemci Davranışlarını Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="74e3c-128">Configuring Client Behaviors</span></span>](../../../docs/framework/wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="74e3c-129">Basitleştirilmiş Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="74e3c-129">Simplified Configuration</span></span>](../../../docs/framework/wcf/simplified-configuration.md)
- [<span data-ttu-id="74e3c-130">Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="74e3c-130">Configuration</span></span>](../../../docs/framework/wcf/samples/configuration-sample.md)
- [<span data-ttu-id="74e3c-131">IIS ve WAS'ta Yapılandırma Temelli Etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="74e3c-131">Configuration-Based Activation in IIS and WAS</span></span>](../../../docs/framework/wcf/feature-details/configuration-based-activation-in-iis-and-was.md)
- [<span data-ttu-id="74e3c-132">Yapılandırma ve Meta Veri Desteği</span><span class="sxs-lookup"><span data-stu-id="74e3c-132">Configuration and Metadata Support</span></span>](../../../docs/framework/wcf/extending/configuration-and-metadata-support.md)
- [<span data-ttu-id="74e3c-133">Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="74e3c-133">Configuration</span></span>](../../../docs/framework/wcf/diagnostics/exceptions-reference/configuration.md)
- [<span data-ttu-id="74e3c-134">Nasıl yapılır: Yapılandırmada hizmet bağlaması belirtme</span><span class="sxs-lookup"><span data-stu-id="74e3c-134">How to: Specify a Service Binding in Configuration</span></span>](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)
- [<span data-ttu-id="74e3c-135">Nasıl yapılır: Yapılandırma içinde hizmet uç noktası oluşturma</span><span class="sxs-lookup"><span data-stu-id="74e3c-135">How to: Create a Service Endpoint in Configuration</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
- [<span data-ttu-id="74e3c-136">Nasıl yapılır: Bir yapılandırma dosyası kullanarak bir hizmet için meta verileri yayımlama</span><span class="sxs-lookup"><span data-stu-id="74e3c-136">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="74e3c-137">Nasıl yapılır: Yapılandırmada istemci bağlama belirtme</span><span class="sxs-lookup"><span data-stu-id="74e3c-137">How to: Specify a Client Binding in Configuration</span></span>](../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)
