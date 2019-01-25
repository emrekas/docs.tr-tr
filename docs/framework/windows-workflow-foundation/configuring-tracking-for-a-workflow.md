---
title: Bir iş akışı için izlemeyi yapılandırma
ms.date: 03/30/2017
ms.assetid: 905adcc9-30a0-4918-acd6-563f86db988a
ms.openlocfilehash: 3740b88490fa829bc7bb369bc9ec44a81cede9b6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602708"
---
# <a name="configuring-tracking-for-a-workflow"></a><span data-ttu-id="94e0a-102">Bir iş akışı için izlemeyi yapılandırma</span><span class="sxs-lookup"><span data-stu-id="94e0a-102">Configuring Tracking for a Workflow</span></span>
<span data-ttu-id="94e0a-103">Bir iş akışı, üç şekilde yürütebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="94e0a-103">A workflow can execute in three ways:</span></span>  
  
-   <span data-ttu-id="94e0a-104">Barındırılan <xref:System.ServiceModel.Activities.WorkflowServiceHost></span><span class="sxs-lookup"><span data-stu-id="94e0a-104">Hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost></span></span>  
  
-   <span data-ttu-id="94e0a-105">Olarak yürütülen bir <xref:System.Activities.WorkflowApplication></span><span class="sxs-lookup"><span data-stu-id="94e0a-105">Executed as a <xref:System.Activities.WorkflowApplication></span></span>  
  
-   <span data-ttu-id="94e0a-106">Kullanarak doğrudan yürütüldü <xref:System.Activities.WorkflowInvoker></span><span class="sxs-lookup"><span data-stu-id="94e0a-106">Executed directly using <xref:System.Activities.WorkflowInvoker></span></span>  
  
 <span data-ttu-id="94e0a-107">Barındırma seçeneği iş akışı bağlı olarak, bir izleme katılımcı, kod veya yapılandırma dosyası aracılığıyla eklenebilir.</span><span class="sxs-lookup"><span data-stu-id="94e0a-107">Depending on the workflow hosting option, a tracking participant can be added either through code or through a configuration file.</span></span> <span data-ttu-id="94e0a-108">Bu konu, izleme için izleme katılımcı ekleyerek nasıl yapılandırıldığını açıklar. bir <xref:System.Activities.WorkflowApplication> ve bir <xref:System.ServiceModel.Activities.WorkflowServiceHost>ve kullanırken izlemeyi etkinleştirme <xref:System.Activities.WorkflowInvoker>.</span><span class="sxs-lookup"><span data-stu-id="94e0a-108">This topic describes how tracking is configured by adding a tracking participant to a <xref:System.Activities.WorkflowApplication> and to a <xref:System.ServiceModel.Activities.WorkflowServiceHost>, and how to enable tracking when using <xref:System.Activities.WorkflowInvoker>.</span></span>  
  
## <a name="configuring-workflow-application-tracking"></a><span data-ttu-id="94e0a-109">İzleme iş akışı uygulamasını yapılandırma</span><span class="sxs-lookup"><span data-stu-id="94e0a-109">Configuring Workflow Application Tracking</span></span>  
 <span data-ttu-id="94e0a-110">Bir iş akışı kullanarak çalıştırabilirsiniz <xref:System.Activities.WorkflowApplication> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="94e0a-110">A workflow can run using the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="94e0a-111">Bu konuda izleme için nasıl yapılandırıldığını gösterir. bir [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] iş akışı uygulama için izleme katılımcı ekleyerek <xref:System.Activities.WorkflowApplication> iş akışı ana bilgisayarı.</span><span class="sxs-lookup"><span data-stu-id="94e0a-111">This topic demonstrates how tracking is configured for a [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] workflow application by adding a tracking participant to the <xref:System.Activities.WorkflowApplication> workflow host.</span></span> <span data-ttu-id="94e0a-112">Bu durumda, iş akışını bir iş akışı uygulaması çalışır.</span><span class="sxs-lookup"><span data-stu-id="94e0a-112">In this case, the workflow runs as a workflow application.</span></span> <span data-ttu-id="94e0a-113">Şirket içinde barındırılan bir .exe olan bir iş akışı uygulama kodu (yerine bir yapılandırma dosyası kullanarak), yapılandırma dosyası kullanarak <xref:System.Activities.WorkflowApplication> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="94e0a-113">You configure a workflow application through code (rather than by using a configuration file), which is a self-hosted .exe file using the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="94e0a-114">İzleme katılımcı bir uzantısı olarak eklenmiş <xref:System.Activities.WorkflowApplication> örneği.</span><span class="sxs-lookup"><span data-stu-id="94e0a-114">The tracking participant is added as an extension to the <xref:System.Activities.WorkflowApplication> instance.</span></span> <span data-ttu-id="94e0a-115">Bu ekleyerek yapılır <xref:System.Activities.Tracking.TrackingParticipant> WorkflowApplication örneği için uzantıları koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="94e0a-115">This is done by adding the <xref:System.Activities.Tracking.TrackingParticipant> to the extensions collection for the WorkflowApplication instance.</span></span>  
  
 <span data-ttu-id="94e0a-116">Bir iş akışı uygulama için eklediğiniz <xref:System.Activities.Tracking.EtwTrackingParticipant> aşağıdaki kodda gösterildiği gibi davranış uzantısı.</span><span class="sxs-lookup"><span data-stu-id="94e0a-116">For a workflow application, you can add the <xref:System.Activities.Tracking.EtwTrackingParticipant> behavior extension as shown in the following code.</span></span>  
  
```csharp  
LogActivity activity = new LogActivity();  
  
WorkflowApplication instance = new WorkflowApplication(activity);  
EtwTrackingParticipant trackingParticipant =  
    new EtwTrackingParticipant  
{  
  
        TrackingProfile = new TrackingProfile  
           {  
               Name = "SampleTrackingProfile",  
               ActivityDefinitionId = "ProcessOrder",  
               Queries = new WorkflowInstanceQuery  
               {  
                  States = { "*" }  
              }  
          }  
       };  
instance.Extensions.Add(trackingParticipant);  
```  
  
### <a name="configuring-workflow-service-tracking"></a><span data-ttu-id="94e0a-117">Yapılandırma iş akışı hizmeti izleme</span><span class="sxs-lookup"><span data-stu-id="94e0a-117">Configuring Workflow Service Tracking</span></span>  
 <span data-ttu-id="94e0a-118">Bir iş akışı içinde barındırıldığında, bir WCF hizmeti olarak kullanıma sunulabilecek <xref:System.ServiceModel.Activities.WorkflowServiceHost> hizmet ana bilgisayarı.</span><span class="sxs-lookup"><span data-stu-id="94e0a-118">A workflow can be exposed as a WCF service when hosted in the <xref:System.ServiceModel.Activities.WorkflowServiceHost> service host.</span></span> <span data-ttu-id="94e0a-119"><xref:System.ServiceModel.Activities.WorkflowServiceHost> özel bir .NET ServiceHost uygulama iş akışı tabanlı bir hizmet için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="94e0a-119"><xref:System.ServiceModel.Activities.WorkflowServiceHost> is a specialized .NET ServiceHost implementation for a workflow-based service.</span></span> <span data-ttu-id="94e0a-120">Bu bölümde izleme için yapılandırma açıklanmaktadır bir [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] çalışan iş akışı hizmeti <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="94e0a-120">This section explains how to configure tracking for a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow service running in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="94e0a-121">Bu bir Web.config dosyası (bir Web barındırılan hizmeti) veya bir App.config dosyası (bir hizmeti bir konsol uygulaması gibi bir tek başına uygulama içinde barındırılan) aracılığıyla bir hizmet davranışını belirterek veya kod için bir izleme özgü davranışı ekleyerek yapılandırılır <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> koleksiyonu hizmet ana bilgisayarı.</span><span class="sxs-lookup"><span data-stu-id="94e0a-121">It is configured through a Web.config file (for a Web-hosted service) or an App.config file (for a service hosted in a stand-alone application, such as a console application) by specifying a service behavior or through code by adding a tracking-specific behavior to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection for the service host.</span></span>  
  
 <span data-ttu-id="94e0a-122">Barındırılan bir iş akışı hizmeti için <xref:System.ServiceModel.WorkflowServiceHost>, ekleyebileceğiniz <xref:System.Activities.Tracking.EtwTrackingParticipant> kullanarak <`behavior`> öğesinde aşağıdaki örnekte gösterildiği gibi bir yapılandırma dosyası.</span><span class="sxs-lookup"><span data-stu-id="94e0a-122">For a workflow service hosted in <xref:System.ServiceModel.WorkflowServiceHost>, you can add the <xref:System.Activities.Tracking.EtwTrackingParticipant> using the <`behavior`> element in a configuration file, as shown in the following example.</span></span>  
  
```xml  
<behaviors>  
   <serviceBehaviors>  
        <behavior>  
          <etwTracking profileName="Sample Tracking Profile" />  
        </behavior>              
   </serviceBehaviors>  
<behaviors>  
```  
  
 <span data-ttu-id="94e0a-123">Alternatif olarak, bir iş akışı hizmeti için barındırılan <xref:System.ServiceModel.WorkflowServiceHost>, ekleyebileceğiniz <xref:System.Activities.Tracking.EtwTrackingParticipant> kod aracılığıyla davranış uzantısı.</span><span class="sxs-lookup"><span data-stu-id="94e0a-123">Alternatively, for a workflow service hosted in <xref:System.ServiceModel.WorkflowServiceHost>, you can add the <xref:System.Activities.Tracking.EtwTrackingParticipant> behavior extension through code.</span></span> <span data-ttu-id="94e0a-124">Özel İzleme Katılımcı eklemek için yeni bir davranış uzantısı oluşturun ve eklemek <xref:System.ServiceModel.ServiceHost> aşağıdaki örnekte gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="94e0a-124">To add a custom tracking participant, create a new behavior extension and add it to the <xref:System.ServiceModel.ServiceHost> as shown in the following example code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94e0a-125">Özel İzleme katılımcı ekleyen bir özel davranış öğesi oluşturmak nasıl gösteren örnek kodunu görüntülemek istiyorsanız, başvurmak [izleme](../../../docs/framework/windows-workflow-foundation/samples/tracking.md) örnekleri.</span><span class="sxs-lookup"><span data-stu-id="94e0a-125">If you want to view sample code that shows how to create a custom behavior element that adds a custom tracking participant, refer to the [Tracking](../../../docs/framework/windows-workflow-foundation/samples/tracking.md) samples.</span></span>  
  
```  
ServiceHost svcHost = new ServiceHost(typeof(WorkflowService), new   
                                 Uri("http://localhost:8001/Sample"));  
EtwTrackingBehavior trackingBehavior =   
    new EtwTrackingBehavior  
    {  
        ProfileName = "Sample Tracking Profile"  
    };  
svcHost.Description.Behaviors.Add(trackingBehavior);  
svcHost.Open();  
```  
  
 <span data-ttu-id="94e0a-126">İzleme katılımcı için iş akışı hizmeti konağı davranışı için bir genişletme olarak eklenir.</span><span class="sxs-lookup"><span data-stu-id="94e0a-126">The tracking participant is added to the workflow service host as an extension to the behavior.</span></span>  
  
 <span data-ttu-id="94e0a-127">Bu örnek kod, bir izleme profili yapılandırma dosyasından okuma işlemi gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="94e0a-127">This sample code below shows how to read a tracking profile from configuration file.</span></span>  
  
```  
TrackingProfile GetProfile(string profileName, string displayName)  
        {  
            TrackingProfile trackingProfile = null;  
            TrackingSection trackingSection = (TrackingSection)WebConfigurationManager.GetSection("system.serviceModel/tracking");  
            if (trackingSection == null)   
            {  
                return null;  
            }  
  
            if (profileName == null)   
            {  
                profileName = "";  
            }  
  
            //Find the profile with the specified profile name in the list of profile found in config  
            var match = from p in new List<TrackingProfile>(trackingSection.TrackingProfiles)  
                        where (p.Name == profileName) && ((p.ActivityDefinitionId == displayName) || (p.ActivityDefinitionId == "*"))  
                        select p;  
  
            if (match.Count() == 0)  
            {  
                //return an empty profile  
                trackingProfile = new TrackingProfile()  
                {  
                    ActivityDefinitionId = displayName  
                };  
  
            }  
            else  
            {  
                trackingProfile = match.First();  
            }  
  
            return trackingProfile;  
```  
  
 <span data-ttu-id="94e0a-128">Bu örnek kod, bir iş akışı ana bilgisayarı için bir izleme profili ekleme işlemi gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="94e0a-128">This sample code shows how to add a tracking profile to a workflow host.</span></span>  
  
```  
WorkflowServiceHost workflowServiceHost = serviceHostBase as WorkflowServiceHost;  
if (null != workflowServiceHost)  
{  
              string workflowDisplayName = workflowServiceHost.Activity.DisplayName;  
               TrackingProfile trackingProfile = GetProfile(this.profileName, workflowDisplayName);  
                workflowServiceHost.WorkflowExtensions.Add(()  => new EtwTrackingParticipant  {  
               TrackingProfile = trackingProfile  
                        });  
 }  
```  
  
> [!NOTE]
>  <span data-ttu-id="94e0a-129">İzleme profilleri ile ilgili daha fazla bilgi için [izleme profilleri](https://go.microsoft.com/fwlink/?LinkId=201310).</span><span class="sxs-lookup"><span data-stu-id="94e0a-129">For more information on tracking profiles, refer to [Tracking Profiles](https://go.microsoft.com/fwlink/?LinkId=201310).</span></span>  
  
### <a name="configuring-tracking-using-workflowinvoker"></a><span data-ttu-id="94e0a-130">Workflowınvoker kullanarak izlemeyi yapılandırma</span><span class="sxs-lookup"><span data-stu-id="94e0a-130">Configuring tracking using WorkflowInvoker</span></span>  
 <span data-ttu-id="94e0a-131">İzleme kullanarak çalıştırılan bir iş akışı için yapılandırmak için <xref:System.Activities.WorkflowInvoker>, izleme sağlayıcısı için bir genişletme olarak ekleme bir <xref:System.Activities.WorkflowInvoker> örneği.</span><span class="sxs-lookup"><span data-stu-id="94e0a-131">To configure tracking for a workflow executed using <xref:System.Activities.WorkflowInvoker>, add the tracking provider as an extension to a <xref:System.Activities.WorkflowInvoker> instance.</span></span> <span data-ttu-id="94e0a-132">Aşağıdaki kod örneği dandır [özel izleme](../../../docs/framework/windows-workflow-foundation/samples/custom-tracking.md) örnek.</span><span class="sxs-lookup"><span data-stu-id="94e0a-132">The following code example is from the [Custom Tracking](../../../docs/framework/windows-workflow-foundation/samples/custom-tracking.md) sample.</span></span>  
  
```  
WorkflowInvoker invoker = new WorkflowInvoker(BuildSampleWorkflow());  
invoker.Extensions.Add(customTrackingParticipant);  
invoker.Invoke();  
```  
  
### <a name="viewing-tracking-records-in-event-viewer"></a><span data-ttu-id="94e0a-133">Olay Görüntüleyicisi'nde kayıtları izleme görüntüleme</span><span class="sxs-lookup"><span data-stu-id="94e0a-133">Viewing tracking records in Event Viewer</span></span>  
 <span data-ttu-id="94e0a-134">Analitik günlüğünü ve hata ayıklama günlüğünü WF yürütme - izleme zaman görüntülemek için belirli ilgilenilen iki Olay Görüntüleyicisi günlükleri vardır.</span><span class="sxs-lookup"><span data-stu-id="94e0a-134">There are two Event Viewer logs of particular interest to view when tracking WF execution - the Analytic log and the Debug log.</span></span> <span data-ttu-id="94e0a-135">Hem de Microsoft altında bulunan&#124;Windows&#124;uygulama uygulamalarının düğümü.</span><span class="sxs-lookup"><span data-stu-id="94e0a-135">Both reside under the Microsoft&#124;Windows&#124;Application Server-Applications node.</span></span>  <span data-ttu-id="94e0a-136">Bu bölümde günlüklere tek bir uygulama olayları yerine tüm sistem üzerinde bir etkisi olan olayları içerir.</span><span class="sxs-lookup"><span data-stu-id="94e0a-136">Logs within this section contain events from a single application rather than events that have an impact on the entire system.</span></span>  
  
 <span data-ttu-id="94e0a-137">Hata ayıklama izleme olayları hata ayıklama günlüğüne yazılır.</span><span class="sxs-lookup"><span data-stu-id="94e0a-137">Debug trace events are written to the Debug Log.</span></span> <span data-ttu-id="94e0a-138">Olay Görüntüleyicisi'nde WF hata ayıklama izleme olaylarını toplamak için hata ayıklama günlüğünü etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="94e0a-138">To collect WF debug trace events in the Event Viewer, enable the Debug Log.</span></span>  
  
1.  <span data-ttu-id="94e0a-139">Olay Görüntüleyicisi'ni açmak için **Başlat**ve ardından **çalıştırın.**</span><span class="sxs-lookup"><span data-stu-id="94e0a-139">To open Event Viewer, click **Start**, and then click **Run.**</span></span> <span data-ttu-id="94e0a-140">Çalıştır iletişim kutusuna `eventvwr`.</span><span class="sxs-lookup"><span data-stu-id="94e0a-140">In the Run dialog, type `eventvwr`.</span></span>  
  
2.  <span data-ttu-id="94e0a-141">Olay Görüntüleyicisi'ni iletişim kutusunda Genişlet **uygulama ve hizmet günlükleri** düğümü.</span><span class="sxs-lookup"><span data-stu-id="94e0a-141">In the Event Viewer dialog, expand the **Applications and Services Logs** node.</span></span>  
  
3.  <span data-ttu-id="94e0a-142">Genişletin **Microsoft**, **Windows**, ve **uygulama uygulamalarının** düğümleri.</span><span class="sxs-lookup"><span data-stu-id="94e0a-142">Expand the **Microsoft**, **Windows**, and **Application Server-Applications** nodes.</span></span>  
  
4.  <span data-ttu-id="94e0a-143">Sağ **hata ayıklama** düğümü altında **uygulama uygulamalarının** düğüm ve select **günlüğü etkinleştir**.</span><span class="sxs-lookup"><span data-stu-id="94e0a-143">Right-click the **Debug** node under the **Application Server-Applications** node, and select **Enable Log**.</span></span>  
  
5.  <span data-ttu-id="94e0a-144">İzlemenin etkin uygulamanızı izleme olayları oluşturmak üzere yürütün.</span><span class="sxs-lookup"><span data-stu-id="94e0a-144">Execute your tracing-enabled application to generate tracing events.</span></span>  
  
6.  <span data-ttu-id="94e0a-145">Sağ **hata ayıklama** düğümünü seçip alt **yenileyin.**</span><span class="sxs-lookup"><span data-stu-id="94e0a-145">Right-click the **Debug** node and select **Refresh.**</span></span> <span data-ttu-id="94e0a-146">Olayları izleme Orta bölmede görünür olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="94e0a-146">Tracing events should be visible in the center pane.</span></span>  
  
 <span data-ttu-id="94e0a-147">WF 4, izleme kayıtları bir ETW (olay izleme için Windows) oturumu Yazar izleme katılımcı sağlar.</span><span class="sxs-lookup"><span data-stu-id="94e0a-147">WF 4 provides a tracking participant that writes tracking records to an ETW (Event Tracing for Windows) session.</span></span> <span data-ttu-id="94e0a-148">ETW İzleme katılımcı abone izleme kayıtları için bir izleme profili ile yapılandırılır.</span><span class="sxs-lookup"><span data-stu-id="94e0a-148">The ETW tracking participant is configured with a tracking profile to subscribe to tracking records.</span></span>  <span data-ttu-id="94e0a-149">İzleme etkin olduğunda, hataları kayıtları izleme için ETW gönderilir.</span><span class="sxs-lookup"><span data-stu-id="94e0a-149">When tracking is enabled, errors tracking records are emitted to ETW.</span></span> <span data-ttu-id="94e0a-150">ETW olayları (100 113 aralığını arasında) izleme ETW İzleme katılımcı tarafından yayılan izleme olaylarını karşılık gelen yazılmış analitik günlüğü için.</span><span class="sxs-lookup"><span data-stu-id="94e0a-150">ETW tracking events (between the range of 100-113) corresponding to the tracking events emitted by the ETW tracking participant are written to the Analytic Log.</span></span>  
  
 <span data-ttu-id="94e0a-151">İzleme kayıtları görüntülemek için aşağıdaki adımları izleyin.</span><span class="sxs-lookup"><span data-stu-id="94e0a-151">To view tracking records, follow these steps.</span></span>  
  
1.  <span data-ttu-id="94e0a-152">Olay Görüntüleyicisi'ni açmak için **Başlat**ve ardından **çalıştırın.**</span><span class="sxs-lookup"><span data-stu-id="94e0a-152">To open Event Viewer, click **Start**, and then click **Run.**</span></span> <span data-ttu-id="94e0a-153">Çalıştır iletişim kutusuna `eventvwr`.</span><span class="sxs-lookup"><span data-stu-id="94e0a-153">In the Run dialog, type `eventvwr`.</span></span>  
  
2.  <span data-ttu-id="94e0a-154">Olay Görüntüleyicisi'ni iletişim kutusunda Genişlet **uygulama ve hizmet günlükleri** düğümü.</span><span class="sxs-lookup"><span data-stu-id="94e0a-154">In the Event Viewer dialog, expand the **Applications and Services Logs** node.</span></span>  
  
3.  <span data-ttu-id="94e0a-155">Genişletin **Microsoft**, **Windows**, ve **uygulama uygulamalarının** düğümleri.</span><span class="sxs-lookup"><span data-stu-id="94e0a-155">Expand the **Microsoft**, **Windows**, and **Application Server-Applications** nodes.</span></span>  
  
4.  <span data-ttu-id="94e0a-156">Sağ **analitik** düğümünde **uygulama uygulamalarının** düğüm ve Seç **günlüğü etkinleştir**.</span><span class="sxs-lookup"><span data-stu-id="94e0a-156">Right-click the **Analytic** node under the **Application Server-Applications** node, and select **Enable Log**.</span></span>  
  
5.  <span data-ttu-id="94e0a-157">İzleme etkinleştirilmiş uygulamanızı izleme kayıtları oluşturmak için yürütün.</span><span class="sxs-lookup"><span data-stu-id="94e0a-157">Execute your tracking-enabled application to generate tracking records.</span></span>  
  
6.  <span data-ttu-id="94e0a-158">Sağ **analitik** düğümünü seçip alt **yenileyin.**</span><span class="sxs-lookup"><span data-stu-id="94e0a-158">Right-click the **Analytic** node and select **Refresh.**</span></span> <span data-ttu-id="94e0a-159">Kayıtları İzleme Orta bölmede görünür olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="94e0a-159">Tracking records should be visible in the center pane.</span></span>  
  
 <span data-ttu-id="94e0a-160">Aşağıdaki görüntüde, Olay Görüntüleyicisi'nde izleme olayları gösterir.</span><span class="sxs-lookup"><span data-stu-id="94e0a-160">The following image shows tracking events in the event viewer.</span></span>  
  
 <span data-ttu-id="94e0a-161">![Kayıtları İzleme Olay Görüntüleyicisi'ni gösteren](../../../docs/framework/windows-workflow-foundation/media/trackingeventviewer.PNG "TrackingEventViewer")</span><span class="sxs-lookup"><span data-stu-id="94e0a-161">![Event Viewer showing tracking records](../../../docs/framework/windows-workflow-foundation/media/trackingeventviewer.PNG "TrackingEventViewer")</span></span>  
  
### <a name="registering-an-application-specific-provider-id"></a><span data-ttu-id="94e0a-162">Bir uygulamaya özgü sağlayıcı kimliği kaydediliyor</span><span class="sxs-lookup"><span data-stu-id="94e0a-162">Registering an application-specific provider ID</span></span>  
 <span data-ttu-id="94e0a-163">Olayları bir belirli uygulama günlüğüne yazılması gerekirse, yeni sağlayıcı bildirimi kaydetmek için şu adımları izleyin.</span><span class="sxs-lookup"><span data-stu-id="94e0a-163">If events need to be written to a specific application log, follow these steps to register the new provider manifest.</span></span>  
  
1.  <span data-ttu-id="94e0a-164">Sağlayıcı Kimliği uygulama yapılandırma dosyasında bildirin.</span><span class="sxs-lookup"><span data-stu-id="94e0a-164">Declare the provider ID in the application configuration file.</span></span>  
  
    ```xml  
    <system.serviceModel>  
        <diagnostics etwProviderId="2720e974-9fe9-477a-bb60-81fe3bf91eec"/>  
    </system.serviceModel>  
    ```  
  
2.  <span data-ttu-id="94e0a-165">Bildirim dosyası %windir%\Microsoft.NET\Framework kopyalayın\\< en son sürümünü [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]> \Microsoft.Windows.ApplicationServer.Applications.man geçici bir konuma ve yeniden adlandırın Microsoft.Windows.ApplicationServer.Applications_Provider1.man</span><span class="sxs-lookup"><span data-stu-id="94e0a-165">Copy the manifest file from %windir%\Microsoft.NET\Framework\\<latest version of [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]>\Microsoft.Windows.ApplicationServer.Applications.man to a temporary location, and rename it to Microsoft.Windows.ApplicationServer.Applications_Provider1.man</span></span>  
  
3.  <span data-ttu-id="94e0a-166">Bildirim dosyasında GUID, yeni bir GUID ile değiştirin.</span><span class="sxs-lookup"><span data-stu-id="94e0a-166">Change the GUID in the manifest file to the new GUID.</span></span>  
  
    ```xml  
    <provider name="Microsoft-Windows-Application Server-Applications" guid="{2720e974-9fe9-477a-bb60-81fe3bf91eec}"  
    ```  
  
4.  <span data-ttu-id="94e0a-167">Varsayılan sağlayıcıyı kaldırmak istemiyorsanız sağlayıcı adını değiştirin.</span><span class="sxs-lookup"><span data-stu-id="94e0a-167">Change the provider name if you do not want to uninstall the default provider.</span></span>  
  
    ```xml  
    <provider name="Microsoft-Windows-Application Server-Applications" guid="{2720e974-9fe9-477a-bb60-81fe3bf91eec}"  
    ```  
  
5.  <span data-ttu-id="94e0a-168">Sağlayıcı adı önceki adımda değiştirdiyseniz, bildirim dosyasında kanal adları yeni sağlayıcı ad ile değiştirin.</span><span class="sxs-lookup"><span data-stu-id="94e0a-168">If you changed the provider name in the previous step, change the channel names in the manifest file to the new provider name.</span></span>  
  
    ```xml  
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Admin" chid="ADMIN_CHANNEL" symbol="ADMIN_CHANNEL" type="Admin" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ADMIN_CHANNEL.message)" />  
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Operational" chid="OPERATIONAL_CHANNEL" symbol="OPERATIONAL_CHANNEL" type="Operational" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.OPERATIONAL_CHANNEL.message)" />  
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" />  
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Debug" chid="DEBUG_CHANNEL" symbol="DEBUG_CHANNEL" type="Debug" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.DEBUG_CHANNEL.message)" />  
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Perf" chid="PERF_CHANNEL" symbol="PERF_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.PERF_CHANNEL.message)" />  
    ```  
  
6.  <span data-ttu-id="94e0a-169">Aşağıdaki adımları izleyerek kaynak DLL'si oluşturur.</span><span class="sxs-lookup"><span data-stu-id="94e0a-169">Generate the resource DLL by following these steps.</span></span>  
  
    1.  <span data-ttu-id="94e0a-170">Windows SDK'sını yükleyin.</span><span class="sxs-lookup"><span data-stu-id="94e0a-170">Install the Windows SDK.</span></span> <span data-ttu-id="94e0a-171">Windows SDK'sı ileti derleyicisi içerir ([mc.exe](https://go.microsoft.com/fwlink/?LinkId=184606)) ve kaynak derleyicisi ([rc.exe](https://go.microsoft.com/fwlink/?LinkId=184605)).</span><span class="sxs-lookup"><span data-stu-id="94e0a-171">The Windows SDK includes the message compiler ([mc.exe](https://go.microsoft.com/fwlink/?LinkId=184606)) and resource compiler ([rc.exe](https://go.microsoft.com/fwlink/?LinkId=184605)).</span></span>  
  
    2.  <span data-ttu-id="94e0a-172">Windows SDK Komut İstemi'nde mc.exe yeni bildirim dosyasını çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="94e0a-172">In a Windows SDK command prompt, run mc.exe on the new manifest file.</span></span>  
  
        ```  
        mc.exe Microsoft.Windows.ApplicationServer.Applications_Provider1.man  
        ```  
  
    3.  <span data-ttu-id="94e0a-173">Önceki adımda oluşturulan kaynak dosyada RC.exe çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="94e0a-173">Run rc.exe on the resource file generated in the previous step.</span></span>  
  
        ```  
        rc.exe  Microsoft.Windows.ApplicationServer.Applications_Provider1.rc  
        ```  
  
    4.  <span data-ttu-id="94e0a-174">NewProviderReg.cs adlı bir boş cs dosyası oluşturun.</span><span class="sxs-lookup"><span data-stu-id="94e0a-174">Create an empty cs file called NewProviderReg.cs.</span></span>  
  
    5.  <span data-ttu-id="94e0a-175">Bir kaynak DLL'si C# derleyicisi kullanarak oluşturun.</span><span class="sxs-lookup"><span data-stu-id="94e0a-175">Create a resource DLL using the C# compiler.</span></span>  
  
        ```  
        csc /target:library /win32res:Microsoft.Windows.ApplicationServer.Applications_Provider1.res NewProviderReg.cs /out:Microsoft.Windows.ApplicationServer.Applications_Provider1.dll  
        ```  
  
    6.  <span data-ttu-id="94e0a-176">Kaynak ve ileti dl namel bildirim dosyasında değişiklik `Microsoft.Windows.ApplicationServer.Applications.Provider1.man` yeni dll adı.</span><span class="sxs-lookup"><span data-stu-id="94e0a-176">Change the resource and message dl namel in the manifest file from `Microsoft.Windows.ApplicationServer.Applications.Provider1.man` to the new dll name.</span></span>  
  
        ```xml  
        <provider name="Microsoft-Windows-Application Server-Applications_Provider1" guid="{2720e974-9fe9-477a-bb60-81fe3bf91eec}" symbol="Microsoft_Windows_ApplicationServer_ApplicationEvents" resourceFileName="<dll directory>\Microsoft.Windows.ApplicationServer.Applications_Provider1.dll" messageFileName="<dll directory>\Microsoft.Windows.ApplicationServer.Applications_Provider1.dll">  
        ```  
  
    7.  <span data-ttu-id="94e0a-177">Kullanım [wevtutil](https://go.microsoft.com/fwlink/?LinkId=184608) bildirim kaydedilecek.</span><span class="sxs-lookup"><span data-stu-id="94e0a-177">Use [wevtutil](https://go.microsoft.com/fwlink/?LinkId=184608) to register the manifest.</span></span>  
  
        ```  
        wevtutil im Microsoft.Windows.ApplicationServer.Applications_Provider1.man  
        ```  
  
## <a name="see-also"></a><span data-ttu-id="94e0a-178">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="94e0a-178">See also</span></span>
- [<span data-ttu-id="94e0a-179">Windows Server App Fabric izleme</span><span class="sxs-lookup"><span data-stu-id="94e0a-179">Windows Server App Fabric Monitoring</span></span>](https://go.microsoft.com/fwlink/?LinkId=201273)
- [<span data-ttu-id="94e0a-180">App Fabric ile uygulamaları izleme</span><span class="sxs-lookup"><span data-stu-id="94e0a-180">Monitoring Applications with App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkId=201275)
