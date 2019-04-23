---
title: 'Nasıl yapılır: WorkflowServiceHost ile İzlemeyi Yapılandırma'
ms.date: 03/30/2017
ms.assetid: ed1485fe-7529-4351-bca3-8bb915260b17
ms.openlocfilehash: e0631cdb47bc88f7f588f4dfe6c44ea3d44f4e60
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59336570"
---
# <a name="how-to-configure-tracking-with-workflowservicehost"></a><span data-ttu-id="b110e-102">Nasıl yapılır: WorkflowServiceHost ile İzlemeyi Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="b110e-102">How to: Configure Tracking with WorkflowServiceHost</span></span>
<span data-ttu-id="b110e-103">Yapılandırma izleme için bu konu açıklar bir [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] barındırılan iş akışı <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="b110e-103">This topic explains how to configure tracking for a [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="b110e-104">Bir hizmet davranışını belirterek, bir Web.config dosyası aracılığıyla yapılandırılır.</span><span class="sxs-lookup"><span data-stu-id="b110e-104">It is configured through a Web.config file by specifying a service behavior.</span></span>  
  
### <a name="configure-tracking-in-configuration"></a><span data-ttu-id="b110e-105">Yapılandırmada izlemeyi yapılandırma</span><span class="sxs-lookup"><span data-stu-id="b110e-105">Configure Tracking in Configuration</span></span>  
  
1. <span data-ttu-id="b110e-106">Ekleme <xref:System.Activities.Tracking.EtwTrackingParticipant> kullanarak <`behavior`> öğesinde aşağıdaki örnekte gösterildiği gibi bir yapılandırma dosyası.</span><span class="sxs-lookup"><span data-stu-id="b110e-106">Add the <xref:System.Activities.Tracking.EtwTrackingParticipant> using the <`behavior`> element in a configuration file, as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
         <behavior>  
           <etwTracking profileName="Sample Tracking Profile" />  
         </behavior>              
       </serviceBehaviors>  
    <behaviors>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="b110e-107">Önceki yapılandırma örneği Basitleştirilmiş yapılandırma kullanıyor.</span><span class="sxs-lookup"><span data-stu-id="b110e-107">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="b110e-108">Daha fazla bilgi için [Basitleştirilmiş yapılandırma](../../../../docs/framework/wcf/simplified-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="b110e-108">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="b110e-109">Önceki yapılandırma örneği ekler bir <xref:System.Activities.Tracking.EtwTrackingParticipant> ve belirten bir izleme profili adı.</span><span class="sxs-lookup"><span data-stu-id="b110e-109">The preceding configuration sample adds a <xref:System.Activities.Tracking.EtwTrackingParticipant> and specifies a tracking profile name.</span></span> <span data-ttu-id="b110e-110">İzleme profilleri oluşturulan bir <`trackingProfile`> öğesinde bir <`tracking`> öğesi.</span><span class="sxs-lookup"><span data-stu-id="b110e-110">Tracking profiles are created in a <`trackingProfile`> element within a <`tracking`> element.</span></span> <span data-ttu-id="b110e-111">İzleme profili çalışma zamanında bir iş akışı örneği durumu değiştiğinde yayılan iş akışı olayları abone olmak için izleme katılımcı izin izleme sorguları içerir.</span><span class="sxs-lookup"><span data-stu-id="b110e-111">The tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="b110e-112">Aşağıdaki örnek, bir izleme profili oluşturma işlemi gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="b110e-112">The following example shows how to create a tracking profile.</span></span>  
  
    ```xml  
    <system.serviceModel>  
        <tracking>   
         <trackingProfile name="Sample Tracking Profile">  
            <workflow activityDefinitionId="*">  
               <workflowInstanceQueries>  
                 <workflowInstanceQuery>  
                    <states>  
                       <state name="Started"/>  
                       <state name="Completed"/>  
                    </states>  
                </workflowInstanceQuery>  
             </workflowInstanceQueries>  
           </workflow>  
         </trackingProfile>   
       </tracking>  
    </system.serviceModel>  
    ```  
  
     <span data-ttu-id="b110e-113">İzleme profilleri hakkında daha fazla bilgi için bkz. [izleme profilleri](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b110e-113">For more information about tracking profiles, see [Tracking Profiles](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
     <span data-ttu-id="b110e-114">Genel olarak izleme hakkında daha fazla bilgi için bkz. [takip ve izleme iş akışı](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="b110e-114">For more information about tracking in general, see [Workflow Tracking and Tracing](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span></span>  
  
### <a name="configure-tracking-in-code"></a><span data-ttu-id="b110e-115">Kodda izlemeyi yapılandırma</span><span class="sxs-lookup"><span data-stu-id="b110e-115">Configure Tracking in Code</span></span>  
  
1. <span data-ttu-id="b110e-116">Ekleme <xref:System.Activities.Tracking.EtwTrackingParticipant> kullanarak <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior> kodda, aşağıdaki örnekte gösterildiği gibi davranış.</span><span class="sxs-lookup"><span data-stu-id="b110e-116">Add the <xref:System.Activities.Tracking.EtwTrackingParticipant> using the <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior> behavior in code, as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new EtwTrackingBehavior { ProfileName = "Sample Tracking Profile" });  
    ```  
  
     <span data-ttu-id="b110e-117">Yukarıdaki kod örneğinde ekler bir <xref:System.Activities.Tracking.EtwTrackingParticipant> ve belirten bir izleme profili adı.</span><span class="sxs-lookup"><span data-stu-id="b110e-117">The preceding code sample adds a <xref:System.Activities.Tracking.EtwTrackingParticipant> and specifies a tracking profile name.</span></span> <span data-ttu-id="b110e-118">İzleme profilleri oluşturulan bir <`trackingProfile`> öğesinde bir <`tracking`> önceki bölümde gösterildiği gibi bir öğe.</span><span class="sxs-lookup"><span data-stu-id="b110e-118">Tracking profiles are created in a <`trackingProfile`> element within a <`tracking`> element as shown in the previous section.</span></span>  
  
     <span data-ttu-id="b110e-119">İzleme profilleri hakkında daha fazla bilgi için bkz. [izleme profilleri](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b110e-119">For more information about tracking profiles, see [Tracking Profiles](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
     <span data-ttu-id="b110e-120">Genel olarak izleme hakkında daha fazla bilgi için bkz. [takip ve izleme iş akışı](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="b110e-120">For more information about tracking in general, see [Workflow Tracking and Tracing](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span></span> <span data-ttu-id="b110e-121">Program aracılığıyla izleme yapılandırma örneği için bkz. [yapılandırma izleme için bir iş akışı](../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="b110e-121">For an example of configuring tracking programmatically see [Configuring Tracking for a Workflow](../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b110e-122">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="b110e-122">See also</span></span>

- [<span data-ttu-id="b110e-123">WCF Hizmetleri için Basitleştirilmiş Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="b110e-123">Simplified Configuration for WCF Services</span></span>](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)
- [<span data-ttu-id="b110e-124">İş Akışı Hizmetleri</span><span class="sxs-lookup"><span data-stu-id="b110e-124">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [<span data-ttu-id="b110e-125">İzleme Profilleri</span><span class="sxs-lookup"><span data-stu-id="b110e-125">Tracking Profiles</span></span>](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
