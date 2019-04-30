---
title: Düzen Dışı İleti İşleme
ms.date: 03/30/2017
ms.assetid: 33fc62a5-5d59-461c-a37a-0e1b51ac763d
ms.openlocfilehash: 4e1864b25a4dbe8192cd5c692c75645bebbb92d2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701248"
---
# <a name="out-of-order-message-processing"></a><span data-ttu-id="06990-102">Düzen Dışı İleti İşleme</span><span class="sxs-lookup"><span data-stu-id="06990-102">Out-of-Order Message Processing</span></span>
<span data-ttu-id="06990-103">İş akışı Hizmetleri, belirli bir sırada gönderilen iletiler bağlı olabilir.</span><span class="sxs-lookup"><span data-stu-id="06990-103">Workflow services may depend on messages being sent in a specific order.</span></span> <span data-ttu-id="06990-104">Bir iş akışı hizmeti bir veya daha fazla içeren <xref:System.ServiceModel.Activities.Receive> etkinlikleri ve her <xref:System.ServiceModel.Activities.Receive> etkinlik belirli bir ileti bekleniyor.</span><span class="sxs-lookup"><span data-stu-id="06990-104">A workflow service contains one or more <xref:System.ServiceModel.Activities.Receive> activities and each <xref:System.ServiceModel.Activities.Receive> activity is expecting a specific message.</span></span> <span data-ttu-id="06990-105">Belirli taşıma teslimat garantileriyle istemciler tarafından gönderilen iletileri Gecikmeli ve bu nedenle iş akışı hizmeti beklenmedik bir sırada teslim.</span><span class="sxs-lookup"><span data-stu-id="06990-105">Without particular transport delivery guarantees, messages sent by clients may be delayed and therefore delivered in an order the workflow service may not expect.</span></span> <span data-ttu-id="06990-106">Uygulama iletileri gerektirmeyen bir iş akışı hizmeti içinde belirli bir gönderme sırası normalde yapılır paralel bir etkinlik kullanılarak.</span><span class="sxs-lookup"><span data-stu-id="06990-106">Implementing a workflow service that does not require messages be sent in a specific order is normally done using a Parallel activity.</span></span> <span data-ttu-id="06990-107">Daha karmaşık bir uygulama protokolü için iş akışının çok hızlı bir şekilde çok karmaşık hale gelir.</span><span class="sxs-lookup"><span data-stu-id="06990-107">For a more complicated application protocol, the workflow would become very complex very quickly.</span></span>  <span data-ttu-id="06990-108">Düzen dışı ileti özelliği Windows Communication Foundation (WCF) işleme gibi tüm iç içe geçmiş paralel etkinliklerin karmaşıklık olmadan bir iş akışı oluşturmanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="06990-108">The out-of-order message processing feature in Windows Communication Foundation (WCF) allows you to create such a workflow without all of the complexity of nested Parallel activities.</span></span> <span data-ttu-id="06990-109">Düzen dışı ileti işleme destekleyen kanalları yalnızca desteklenen <xref:System.ServiceModel.Channels.ReceiveContext> MSMQ WCF bağlamaları gibi.</span><span class="sxs-lookup"><span data-stu-id="06990-109">Out-of-order message processing is only supported on channels that support <xref:System.ServiceModel.Channels.ReceiveContext> such as the WCF MSMQ bindings.</span></span>  
  
## <a name="enabling-out-of-order-message-processing"></a><span data-ttu-id="06990-110">Düzen dışı ileti işleme etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="06990-110">Enabling Out-Of-Order Message Processing</span></span>  
 <span data-ttu-id="06990-111">Düzen dışı ileti işleme ayarlayarak etkin <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> özelliğini `true` WorkflowService üzerinde.</span><span class="sxs-lookup"><span data-stu-id="06990-111">Out-of-order message processing is enabled by setting the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property to `true` on the WorkflowService.</span></span> <span data-ttu-id="06990-112">Aşağıdaki örnek nasıl ayarlanacağını gösterir <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> kod özelliği.</span><span class="sxs-lookup"><span data-stu-id="06990-112">The following example shows how to set the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property in code.</span></span>  
  
```csharp  
// Code: Opt-in to Buffered Receive processing...  
WorkflowService service = new WorkflowService  
{  
    Name="MyService",  
    Body = workflow,  
    AllowBufferedReceive = true  
};  
```  
  
 <span data-ttu-id="06990-113">Ayrıca uygulayabilirsiniz `AllowBufferedReceive` özniteliği bir XAML iş akışı hizmetinde aşağıdaki örnekte gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="06990-113">You can also apply the `AllowBufferedReceive` attribute to a workflow service in XAML as shown in the following example.</span></span>  
  
```xaml  
// Xaml: Opt-in to Buffered Receive processing...  
<WorkflowService AllowBufferedReceive="True">  
   <!--the actual children activities -->  
</Sequence>  
```  
  
## <a name="see-also"></a><span data-ttu-id="06990-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="06990-114">See also</span></span>

- <xref:System.ServiceModel.Channels.ReceiveContext>
- [<span data-ttu-id="06990-115">İş Akışı Hizmetleri</span><span class="sxs-lookup"><span data-stu-id="06990-115">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [<span data-ttu-id="06990-116">Kuyruklar ve Güvenilir Oturumlar</span><span class="sxs-lookup"><span data-stu-id="06990-116">Queues and Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
