---
title: İzleme ve İletileri Günlüğe Kaydetme için Önerilen Ayarlar
ms.date: 03/30/2017
ms.assetid: c6aca6e8-704e-4779-a9ef-50c46850249e
ms.openlocfilehash: fa6dc74a26f6a76591a15c549a892f31a65c521e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132372"
---
# <a name="recommended-settings-for-tracing-and-message-logging"></a><span data-ttu-id="3e864-102">İzleme ve İletileri Günlüğe Kaydetme için Önerilen Ayarlar</span><span class="sxs-lookup"><span data-stu-id="3e864-102">Recommended Settings for Tracing and Message Logging</span></span>
<span data-ttu-id="3e864-103">Bu konu, önerilen izleme ve farklı işletim ortamlarının için ileti günlüğe kaydetme ayarlarını açıklar.</span><span class="sxs-lookup"><span data-stu-id="3e864-103">This topic describes recommended tracing and message logging settings for different operating environments.</span></span>  
  
## <a name="recommended-settings-for-a-production-environment"></a><span data-ttu-id="3e864-104">Bir üretim ortamı için önerilen ayarlar</span><span class="sxs-lookup"><span data-stu-id="3e864-104">Recommended Settings for a Production Environment</span></span>  
 <span data-ttu-id="3e864-105">WCF izleme kaynakları kullanıyorsanız, bir üretim ortamı için ayarlanmış `switchValue` uyarı.</span><span class="sxs-lookup"><span data-stu-id="3e864-105">For a production environment, if you are using WCF trace sources, set the `switchValue` to Warning.</span></span> <span data-ttu-id="3e864-106">WCF kullanıyorsanız `System.ServiceModel` izleme kaynağı, Ayarla `switchValue` özniteliğini `Warning` ve `propagateActivity` özniteliğini `true`.</span><span class="sxs-lookup"><span data-stu-id="3e864-106">If you are using the WCF `System.ServiceModel` trace source, set the `switchValue` attribute to `Warning` and the `propagateActivity` attribute to `true`.</span></span> <span data-ttu-id="3e864-107">Bir kullanıcı tanımlı izleme kaynağı kullanıyorsanız `switchValue` özniteliğini `Warning, ActivityTracing`.</span><span class="sxs-lookup"><span data-stu-id="3e864-107">If you are using a user-defined trace source, set the `switchValue` attribute to `Warning, ActivityTracing`.</span></span> <span data-ttu-id="3e864-108">Bu kullanarak el ile yapılabilir [Yapılandırma Aracı (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="3e864-108">This can be done manually using the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span> <span data-ttu-id="3e864-109">İsabet performans düşünmüyoruz, ayarlayabileceğiniz `switchValue` özniteliğini `Information` tüm daha önce de belirtildiği durumlarda, izleme verilerinin oldukça büyük bir miktarını oluşturduğu.</span><span class="sxs-lookup"><span data-stu-id="3e864-109">If you do not anticipate a hit in performance, you can set the `switchValue` attribute to `Information` in all the previously mentioned cases, which generates a fairly large amount of trace data.</span></span> <span data-ttu-id="3e864-110">Aşağıdaki örnek, bu önerilen ayarları gösterir.</span><span class="sxs-lookup"><span data-stu-id="3e864-110">The following example demonstrates these recommended settings.</span></span>  
  
```xml  
<configuration>  
 <system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel"  
            switchValue="Warning"  
            propagateActivity="true" >  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="myUserTraceSource"  
            switchValue="Warning, ActivityTracing">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="xml"  
         type="System.Diagnostics.XmlWriterTraceListener"  
               initializeData="C:\logs\Traces.svclog" />  
  </sharedListeners>  
 </system.diagnostics>  
  
<system.serviceModel>  
  <diagnostics wmiProviderEnabled="true">  
  </diagnostics>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="recommended-settings-for-deployment-or-debugging"></a><span data-ttu-id="3e864-111">Dağıtım veya hata ayıklama için önerilen ayarlar</span><span class="sxs-lookup"><span data-stu-id="3e864-111">Recommended Settings for Deployment or Debugging</span></span>  
 <span data-ttu-id="3e864-112">Dağıtım veya hata ayıklama ortamı seçin `Information` veya `Verbose`, birlikte `ActivityTracing` ya da kullanıcı tanımlı bir için veya `System.ServiceModel` izleme kaynağı.</span><span class="sxs-lookup"><span data-stu-id="3e864-112">For deployment or debugging environment, choose `Information` or `Verbose`, along with `ActivityTracing` for either a user-defined or `System.ServiceModel` trace source.</span></span> <span data-ttu-id="3e864-113">Hata ayıklamayı iyileştirme için de bir ek izleme kaynağı eklemeniz gerekir (`System.ServiceModel.MessageLogging`) ileti günlüğe kaydetmeyi etkinleştirmek için yapılandırma.</span><span class="sxs-lookup"><span data-stu-id="3e864-113">To enhance debugging, you should also add an additional trace source (`System.ServiceModel.MessageLogging`) to the configuration to enable message logging.</span></span> <span data-ttu-id="3e864-114">Dikkat `switchValue` özniteliği bu iz herhangi bir etkisi vardır.</span><span class="sxs-lookup"><span data-stu-id="3e864-114">Notice that the `switchValue` attribute has no impact on this trace source.</span></span>  
  
 <span data-ttu-id="3e864-115">Aşağıdaki örnek, önerilen ayarları kullanan bir paylaşılan dinleyici kullanarak gösterir `XmlWriterTraceListener`.</span><span class="sxs-lookup"><span data-stu-id="3e864-115">The following example demonstrates the recommended settings, using a shared listener that utilizes the `XmlWriterTraceListener`.</span></span>  
  
```xml  
<configuration>  
 <system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel"  
            switchValue="Information, ActivityTracing"  
            propagateActivity="true" >  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="System.ServiceModel.MessageLogging">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="myUserTraceSource"  
            switchValue="Information, ActivityTracing">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="xml"  
         type="System.Diagnostics.XmlWriterTraceListener"  
               initializeData="C:\logs\Traces.svclog" />  
  </sharedListeners>  
 </system.diagnostics>  
  
 <system.serviceModel>  
  <diagnostics wmiProviderEnabled="true">  
      <messageLogging   
           logEntireMessage="true"   
           logMalformedMessages="true"  
           logMessagesAtServiceLevel="true"   
           logMessagesAtTransportLevel="true"  
           maxMessagesToLog="3000"   
       />  
  </diagnostics>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="using-wmi-to-modify-settings"></a><span data-ttu-id="3e864-116">Ayarları değiştirmek için WMI'yı kullanarak</span><span class="sxs-lookup"><span data-stu-id="3e864-116">Using WMI to Modify Settings</span></span>  
 <span data-ttu-id="3e864-117">WMI zamanında yapılandırma ayarlarını değiştirmek için kullanabileceğiniz (etkinleştirerek `wmiProviderEnabled` gösterildiği şekilde yapılandırmada özniteliği daha önce yapılandırma örneği).</span><span class="sxs-lookup"><span data-stu-id="3e864-117">You can use WMI to change configuration settings at runtime (by enabling the `wmiProviderEnabled` attribute in the configuration, as demonstrated in the previously configuration example).</span></span> <span data-ttu-id="3e864-118">Örneğin, WMI CIM Studio'dan izleme kaynak düzeylerini uyarıyı bilgi çalışma zamanında değiştirmek için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3e864-118">For example, you can use WMI within the CIM Studio to change the trace source levels from Warning to Information at runtime.</span></span> <span data-ttu-id="3e864-119">Bu şekilde Canlı hata ayıklama performans maliyeti çok yüksek olduğunu bilmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="3e864-119">You should be aware that the performance cost of live debugging in this way can be very high.</span></span> <span data-ttu-id="3e864-120">WMI kullanma hakkında daha fazla bilgi için bkz. [tanılama için Windows Yönetim araçları kullanarak](../../../../../docs/framework/wcf/diagnostics/wmi/index.md) konu.</span><span class="sxs-lookup"><span data-stu-id="3e864-120">For more information about using WMI, see the [Using Windows Management Instrumentation for Diagnostics](../../../../../docs/framework/wcf/diagnostics/wmi/index.md) topic.</span></span>  
  
## <a name="enable-correlated-events-in-aspnet-tracing"></a><span data-ttu-id="3e864-121">ASP.NET izleme, bağıntılı olaylar etkinleştir</span><span class="sxs-lookup"><span data-stu-id="3e864-121">Enable Correlated Events in ASP.NET Tracing</span></span>  
 <span data-ttu-id="3e864-122">ASP.NET olay izleme etkinleştirilmemişse, ASP.NET olayları bağıntı Kimliğini (ActivityID) ayarlamayın.</span><span class="sxs-lookup"><span data-stu-id="3e864-122">ASP.NET events do not set the correlation ID (ActivityID) unless ASP.NET event tracing is turned on.</span></span> <span data-ttu-id="3e864-123">ASP.NET olaylarına açmak zorunda bağıntılı olaylar düzgün şekilde görmek için komut konsolunda aşağıdaki komutu kullanarak izleme, hangi çağrılacak giderek **Başlat**, **çalıştırma** ve türü **cmd** ,</span><span class="sxs-lookup"><span data-stu-id="3e864-123">To see correlated events properly, you have to turn on ASP.NET events tracing using the following command in the command console, which can be invoked by going to **Start**, **Run** and type **cmd**,</span></span>  
  
```  
logman start mytrace -pf logman.providers -o test.etl –ets  
```  
  
 <span data-ttu-id="3e864-124">ASP.NET olaylarını izlemeyi devre dışı bırakmak için aşağıdaki komutu kullanın,</span><span class="sxs-lookup"><span data-stu-id="3e864-124">To turn off tracing of ASP.NET events, use the following command,</span></span>  
  
```  
logman stop mytrace -ets  
```  
  
## <a name="see-also"></a><span data-ttu-id="3e864-125">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="3e864-125">See also</span></span>

- [<span data-ttu-id="3e864-126">Tanılama için Windows Yönetim İzlemesini Kullanma</span><span class="sxs-lookup"><span data-stu-id="3e864-126">Using Windows Management Instrumentation for Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/index.md)
