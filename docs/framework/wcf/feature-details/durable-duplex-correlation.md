---
title: Dayanıklı Çift Yönlü Bağıntı
ms.date: 03/30/2017
ms.assetid: 8eb0e49a-6d3b-4f7e-a054-0d4febee2ffb
ms.openlocfilehash: f2f5fe557f1f8754758d0dd9b4042cacc62cc61f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61856615"
---
# <a name="durable-duplex-correlation"></a><span data-ttu-id="8c291-102">Dayanıklı Çift Yönlü Bağıntı</span><span class="sxs-lookup"><span data-stu-id="8c291-102">Durable Duplex Correlation</span></span>
<span data-ttu-id="8c291-103">Dayanıklı çift yönlü bağıntı, geri çağırma bağıntı olarak da bilinen bir iş akışı hizmeti ilk çağırana bir geri çağırma göndermek için bir gereksinimi olduğunda yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="8c291-103">Durable duplex correlation, also known as callback correlation, is useful when a workflow service has a requirement to send a callback to the initial caller.</span></span> <span data-ttu-id="8c291-104">WCF çift yönlü, farklı bir geri çağırma dilediğiniz zaman gelecekte oluşabilir ve aynı kanalı veya kanal ömrü bağlı değildir; çağıran bir etkin uç noktası için geri çağırma iletiyi dinleme sahip tek gereksinim olmasıdır.</span><span class="sxs-lookup"><span data-stu-id="8c291-104">Unlike WCF duplex, the callback can happen at any time in the future and is not tied to the same channel or the channel lifetime; the only requirement is that the caller have an active endpoint listening for the callback message.</span></span> <span data-ttu-id="8c291-105">Bu, uzun süre çalışan konuşmada iletişim kurmak iki iş akışı hizmetleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="8c291-105">This allows two workflow services to communicate in a long-running conversation.</span></span> <span data-ttu-id="8c291-106">Bu konu, dayanıklı çift yönlü bağıntı genel bir bakış sağlar.</span><span class="sxs-lookup"><span data-stu-id="8c291-106">This topic provides an overview of durable duplex correlation.</span></span>  
  
## <a name="using-durable-duplex-correlation"></a><span data-ttu-id="8c291-107">Dayanıklı çift yönlü bağıntı kullanma</span><span class="sxs-lookup"><span data-stu-id="8c291-107">Using Durable Duplex Correlation</span></span>  
 <span data-ttu-id="8c291-108">Dayanıklı çift yönlü bağıntı kullanmak için iki hizmet gibi çift yönlü işlemleri destekleyen bir bağlamı etkin bağlama kullanmalısınız <xref:System.ServiceModel.NetTcpContextBinding> veya <xref:System.ServiceModel.WSHttpContextBinding>.</span><span class="sxs-lookup"><span data-stu-id="8c291-108">To use durable duplex correlation, the two services must use a context-enabled binding that supports two-way operations, such as <xref:System.ServiceModel.NetTcpContextBinding> or <xref:System.ServiceModel.WSHttpContextBinding>.</span></span> <span data-ttu-id="8c291-109">Arama hizmeti kayıtları bir <xref:System.ServiceModel.WSHttpContextBinding.ClientCallbackAddress%2A> kendi istemci üzerinde istenen bağlama <xref:System.ServiceModel.Endpoint>.</span><span class="sxs-lookup"><span data-stu-id="8c291-109">The calling service registers a <xref:System.ServiceModel.WSHttpContextBinding.ClientCallbackAddress%2A> with the desired binding on their client <xref:System.ServiceModel.Endpoint>.</span></span> <span data-ttu-id="8c291-110">Alan hizmeti ilk çağrıda bu verileri alır ve ardından, kendi kullanır <xref:System.ServiceModel.Endpoint> içinde <xref:System.ServiceModel.Activities.Send> çağrıda arama hizmeti etkinlik.</span><span class="sxs-lookup"><span data-stu-id="8c291-110">The receiving service receives this data in the initial call and then uses it on its own <xref:System.ServiceModel.Endpoint> in the <xref:System.ServiceModel.Activities.Send> activity that makes the call back to the calling service.</span></span> <span data-ttu-id="8c291-111">Bu örnekte, iki hizmet birbiriyle iletişim kurar.</span><span class="sxs-lookup"><span data-stu-id="8c291-111">In this example, two services communicate with each other.</span></span> <span data-ttu-id="8c291-112">İlk hizmet ikinci hizmet üzerinde bir yöntemi çağırır ve ardından bir yanıt bekler.</span><span class="sxs-lookup"><span data-stu-id="8c291-112">The first service invokes a method on the second service and then waits for a reply.</span></span> <span data-ttu-id="8c291-113">İkinci hizmet adını geri çağırma yöntemi bilir, ancak bu yöntem hizmetinin uç noktası, tasarım zamanında bilinmiyor.</span><span class="sxs-lookup"><span data-stu-id="8c291-113">The second service knows the name of the callback method, but the endpoint of the service that implements this method is not known at design time.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8c291-114">Dayanıklı çift yönlü yalnızca olabilir kullanılabilir <xref:System.ServiceModel.Channels.AddressingVersion> uç noktası ile yapılandırılmış <xref:System.ServiceModel.Channels.AddressingVersion.WSAddressing10%2A>.</span><span class="sxs-lookup"><span data-stu-id="8c291-114">Durable duplex can only be used when the <xref:System.ServiceModel.Channels.AddressingVersion> of the endpoint is configured with <xref:System.ServiceModel.Channels.AddressingVersion.WSAddressing10%2A>.</span></span> <span data-ttu-id="8c291-115">Bu, yoksa bir <xref:System.InvalidOperationException> şu ileti ile özel durum oluştu: "İletiyi içeren bir uç nokta başvurusu için bir geri çağırma bağlam üstbilgiyle [AddressingVersion değerini](http://schemas.xmlsoap.org/ws/2004/08/addressing).</span><span class="sxs-lookup"><span data-stu-id="8c291-115">If it is not, then an <xref:System.InvalidOperationException> exception is thrown with the following message: "The message contains a callback context header with an endpoint reference for [AddressingVersion](http://schemas.xmlsoap.org/ws/2004/08/addressing).</span></span> <span data-ttu-id="8c291-116">Geri çağırma bağlam AddressingVersion değerini 'WSAddressing10' ile yapılandırıldığında, yalnızca iletilebilir.</span><span class="sxs-lookup"><span data-stu-id="8c291-116">Callback context can only be transmitted when the AddressingVersion is configured with 'WSAddressing10'.</span></span>
  
 <span data-ttu-id="8c291-117">Aşağıdaki örnekte, bir geri çağırma oluşturan bir iş akışı hizmeti barındırılan <xref:System.ServiceModel.Endpoint> kullanarak <xref:System.ServiceModel.WSHttpContextBinding>.</span><span class="sxs-lookup"><span data-stu-id="8c291-117">In the following example, a workflow service is hosted that creates a callback <xref:System.ServiceModel.Endpoint> using <xref:System.ServiceModel.WSHttpContextBinding>.</span></span>  
  
```csharp  
// Host WF Service 1.  
string baseAddress1 = "http://localhost:8080/Service1";  
WorkflowServiceHost host1 = new WorkflowServiceHost(GetWF1(), new Uri(baseAddress1));  
  
// Add the callback endpoint.  
WSHttpContextBinding Binding1 = new WSHttpContextBinding();  
host1.AddServiceEndpoint("ICallbackItemsReady", Binding1, "ItemsReady");  
  
// Add the service endpoint.  
host1.AddServiceEndpoint("IService1", Binding1, baseAddress1);  
  
// Open the first workflow service.  
host1.Open();  
Console.WriteLine("Service1 waiting at: {0}", baseAddress1);  
```  
  
 <span data-ttu-id="8c291-118">Bu iş akışı hizmeti uygulayan bir iş akışı geri çağırma yurt içi hasıla ile başlatır, <xref:System.ServiceModel.Activities.Send> etkinliği ve bu geri çağırma uç noktasından başvurur <xref:System.ServiceModel.Activities.Receive> ile karşılık gelen etkinlik <xref:System.ServiceModel.Activities.Send>.</span><span class="sxs-lookup"><span data-stu-id="8c291-118">The workflow that implements this workflow service initializes the callback correlation with its <xref:System.ServiceModel.Activities.Send> activity, and references this callback endpoint from the <xref:System.ServiceModel.Activities.Receive> activity that correlates with the <xref:System.ServiceModel.Activities.Send>.</span></span> <span data-ttu-id="8c291-119">Aşağıdaki örnek öğesinden döndürülen iş akışını temsil eden `GetWF1` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="8c291-119">The following example represents the workflow that is returned from the `GetWF1` method.</span></span>  
  
```csharp  
Variable<CorrelationHandle> CallbackHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = "IService1",  
    OperationName = "StartOrder"  
};  
  
Send GetItems = new Send  
{  
    CorrelationInitializers =   
    {  
        new CallbackCorrelationInitializer  
        {  
            CorrelationHandle = CallbackHandle  
        }  
    },  
    ServiceContractName = "IService2",  
    OperationName = "StartItems",  
    Endpoint = new Endpoint  
    {  
        AddressUri = new Uri("http://localhost:8081/Service2"),  
        Binding = new WSHttpContextBinding  
        {  
            ClientCallbackAddress = new Uri("http://localhost:8080/Service1/ItemsReady")                          
        }  
    }  
};  
  
Receive ItemsReady = new Receive  
{  
    ServiceContractName = "ICallbackItemsReady",  
    OperationName = "ItemsReady",  
    CorrelatesWith = CallbackHandle,  
};  
  
Activity wf = new Sequence  
{  
    Variables =  
    {  
        CallbackHandle  
    },  
    Activities =  
    {  
        StartOrder,  
        new WriteLine  
        {  
            Text = "WF1 - Started"  
        },  
        GetItems,  
        new WriteLine  
        {  
            Text = "WF1 - Request Submitted"  
        },  
        ItemsReady,  
        new WriteLine  
        {  
            Text = "WF1 - Items Received"  
        }  
     }  
};  
```  
  
 <span data-ttu-id="8c291-120">İkinci iş akışı hizmeti kullanarak sistem tarafından sağlanan, içerik tabanlı bir bağlama barındırılır.</span><span class="sxs-lookup"><span data-stu-id="8c291-120">The second workflow service is hosted using a system-provided, context-based binding.</span></span>  
  
```csharp  
// Host WF Service 2.  
string baseAddress2 = "http://localhost:8081/Service2";  
WorkflowServiceHost host2 = new WorkflowServiceHost(GetWF2(), new Uri(baseAddress2));  
  
// Add the service endpoint.  
WSHttpContextBinding Binding2 = new WSHttpContextBinding();  
host2.AddServiceEndpoint("IService2", Binding2, baseAddress2);  
  
// Open the second workflow service.  
host2.Open();  
Console.WriteLine("Service2 waiting at: {0}", baseAddress2);  
```  
  
 <span data-ttu-id="8c291-121">Bu iş akışı hizmeti uygulayan bir iş akışı ile başlayan bir <xref:System.ServiceModel.Activities.Receive> etkinlik.</span><span class="sxs-lookup"><span data-stu-id="8c291-121">The workflow that implements this workflow service begins with a <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="8c291-122">Bu geri çağırma bağıntı gecikmeleri uzun süre çalışan işler ve hizmete ilk çağrıda geçirilen geri çağırma bağlamı kullanarak ilk hizmet geri çağırıyor benzetimini yapmak için bir süre için bu hizmet için etkinlik başlatır alırsınız.</span><span class="sxs-lookup"><span data-stu-id="8c291-122">This receive activity initializes the callback correlation for this service, delays for a period of time to simulate long-running work, and then calls back into the first service using the callback context that was passed in the first call into the service.</span></span> <span data-ttu-id="8c291-123">Aşağıdaki örnek çağrısından döndürülen iş akışını temsil eden `GetWF2`.</span><span class="sxs-lookup"><span data-stu-id="8c291-123">The following example represents the workflow that is returned from a call to `GetWF2`.</span></span> <span data-ttu-id="8c291-124">Unutmayın <xref:System.ServiceModel.Activities.Send> etkinliğinde bir yer tutucu adresini `http://www.contoso.com`; çalışma zamanında kullanılan gerçek adresi sağlanan geri çağırma adresidir.</span><span class="sxs-lookup"><span data-stu-id="8c291-124">Note that the <xref:System.ServiceModel.Activities.Send> activity has a placeholder address of `http://www.contoso.com`; the actual address used at runtime is the supplied callback address.</span></span>  
  
```csharp  
Variable<CorrelationHandle> ItemsCallbackHandle = new Variable<CorrelationHandle>();  
  
Receive StartItems = new Receive  
{  
    CorrelationInitializers =   
    {  
        new CallbackCorrelationInitializer  
        {  
            CorrelationHandle = ItemsCallbackHandle  
        }  
    },  
    CanCreateInstance = true,  
    ServiceContractName = "IService2",  
    OperationName = "StartItems"  
};  
  
Send ItemsReady = new Send  
{  
    CorrelatesWith = ItemsCallbackHandle,  
    Endpoint = new Endpoint  
    {  
        // The callback address on the binding is used  
        // instead of this placeholder address.  
        AddressUri = new Uri("http://www.contoso.com"),  
  
        Binding = new WSHttpContextBinding()  
    },  
    OperationName = "ItemsReady",  
    ServiceContractName = "ICallbackItemsReady"  
};  
  
Activity wf = new Sequence  
{  
    Variables =  
    {  
        ItemsCallbackHandle  
    },  
    Activities =  
    {  
        StartItems,  
        new WriteLine  
        {  
            Text = "WF2 - Request Received"  
        },  
        new Delay  
        {  
            Duration = TimeSpan.FromMinutes(90)  
        },  
        new WriteLine  
        {  
            Text = "WF2 - Sending items"  
        },  
        ItemsReady,  
        new WriteLine  
        {  
            Text = "WF2 - Items sent"  
        }  
     }  
};  
```  
  
 <span data-ttu-id="8c291-125">Zaman `StartOrder` ilk iş akışını yöntemi çağrıldığında, iki iş akışları aracılığıyla akışını gösterir aşağıdaki çıktıyı görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="8c291-125">When the `StartOrder` method is invoked on the first workflow, the following output is displayed, which shows the flow of execution through the two workflows.</span></span>  
  
```Output  
Service1 waiting at: http://localhost:8080/Service1  
Service2 waiting at: http://localhost:8081/Service2  
Press enter to exit.   
WF1 - Started  
WF2 - Request Received  
WF1 - Request Submitted  
WF2 - Sending items  
WF2 - Items sent  
WF1 - Items Received  
```  
  
 <span data-ttu-id="8c291-126">Bağıntı kullanarak açıkça Bu örnekte, her iki iş akışlarını yönetme bir <xref:System.ServiceModel.Activities.CallbackCorrelationInitializer>.</span><span class="sxs-lookup"><span data-stu-id="8c291-126">In this example, both workflows explicitly manage correlation using a <xref:System.ServiceModel.Activities.CallbackCorrelationInitializer>.</span></span> <span data-ttu-id="8c291-127">Bu örnek iş akışları, varsayılan olarak yalnızca tek bir bağıntı olduğundan <xref:System.ServiceModel.Activities.CorrelationHandle> yönetim olabilirdi yeterli.</span><span class="sxs-lookup"><span data-stu-id="8c291-127">Because there was only a single correlation in these sample workflows, the default <xref:System.ServiceModel.Activities.CorrelationHandle> management would have been sufficient.</span></span>
