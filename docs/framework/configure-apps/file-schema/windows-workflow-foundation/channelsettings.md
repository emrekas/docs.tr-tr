---
title: <channelSettings>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 94a4457f-f43f-458d-a47e-2d11103ee75e
ms.openlocfilehash: f70e30c903fa9bfc3f5d6054ef2ec34bf1b3cba1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083029"
---
# <a name="channelsettings"></a><span data-ttu-id="7928a-101">\<channelSettings ></span><span class="sxs-lookup"><span data-stu-id="7928a-101">\<channelSettings></span></span>
<span data-ttu-id="7928a-102">Kanal önbellek ayarlarını belirtir.</span><span class="sxs-lookup"><span data-stu-id="7928a-102">Specifies the settings of the channel cache.</span></span>  
  
<span data-ttu-id="7928a-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7928a-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="7928a-104">\<davranışlar ></span><span class="sxs-lookup"><span data-stu-id="7928a-104">\<behaviors></span></span>  
<span data-ttu-id="7928a-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="7928a-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="7928a-106">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="7928a-106">\<behavior></span></span>  
<span data-ttu-id="7928a-107">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="7928a-107">\<sendMessageChannelCache></span></span>  
<span data-ttu-id="7928a-108">\<channelSettings ></span><span class="sxs-lookup"><span data-stu-id="7928a-108">\<channelSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7928a-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="7928a-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sendMessageChannelCache allowUnsafeCaching="Boolean">
        <channelSettings idleTimeout="TimeSpan" 
                         leaseTimeout="TimeSpan" 
                         maxItemsInCache="Integer" />
      </sendMessageChannelCache>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7928a-110">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="7928a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7928a-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="7928a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7928a-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="7928a-112">Attributes</span></span>  
  
|<span data-ttu-id="7928a-113">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="7928a-113">Attribute</span></span>|<span data-ttu-id="7928a-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="7928a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7928a-115">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="7928a-115">idleTimeout</span></span>|<span data-ttu-id="7928a-116">En fazla kendisi için nesne önbellekte atıldı önce boşta kalacağını zaman aralığını belirten bir TimeSpan değeri.</span><span class="sxs-lookup"><span data-stu-id="7928a-116">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="7928a-117">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="7928a-117">leaseTimeout</span></span>|<span data-ttu-id="7928a-118">Önbellekten kaldırılır bir nesne sonra zaman aralığını belirten bir TimeSpan değeri.</span><span class="sxs-lookup"><span data-stu-id="7928a-118">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="7928a-119">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="7928a-119">maxItemsInCache</span></span>|<span data-ttu-id="7928a-120">Bir tamsayı önbellekte olabilir nesneleri sayısı üst sınırını belirtir.</span><span class="sxs-lookup"><span data-stu-id="7928a-120">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7928a-121">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="7928a-121">Child Elements</span></span>  
 <span data-ttu-id="7928a-122">Yok.</span><span class="sxs-lookup"><span data-stu-id="7928a-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7928a-123">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="7928a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7928a-124">Öğe</span><span class="sxs-lookup"><span data-stu-id="7928a-124">Element</span></span>|<span data-ttu-id="7928a-125">Açıklama</span><span class="sxs-lookup"><span data-stu-id="7928a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7928a-126">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="7928a-126">\<sendMessageChannelCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|<span data-ttu-id="7928a-127">Özelleştirme düzeyleri, kanal üreteci önbellek ayarlarını ve ileti göndermek için hizmet bitiş noktası etkinlikler ileti gönderme kullanarak iş akışları için kanal önbellek ayarlarını paylaşımı önbellek sağlayan bir hizmet davranışı.</span><span class="sxs-lookup"><span data-stu-id="7928a-127">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7928a-128">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="7928a-128">Remarks</span></span>  
 <span data-ttu-id="7928a-129">Bu hizmet davranışını ileti göndermek için hizmet bitiş noktası iş akışları için yöneliktir.</span><span class="sxs-lookup"><span data-stu-id="7928a-129">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="7928a-130">Bu iş akışları genellikle istemci iş akışlarıdır ancak içinde barındırılan iş akışı Hizmetleri ayrıca olabilir bir <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="7928a-130">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="7928a-131">Varsayılan olarak, bir iş akışı tarafından barındırılan bir <xref:System.ServiceModel.WorkflowServiceHost>, tarafından kullanılan önbellek <xref:System.ServiceModel.Activities.Send> etkinlikler ileti sistemi tüm iş akışı durumlarda arasında paylaşılır <xref:System.ServiceModel.WorkflowServiceHost> (ana bilgisayar önbelleğe alma düzeyi).</span><span class="sxs-lookup"><span data-stu-id="7928a-131">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="7928a-132">Tarafından barındırılmadığında bir istemci iş akışı için bir <xref:System.ServiceModel.WorkflowServiceHost>, önbelleğe yalnızca (örnek düzeyi önbelleğe alma) iş akışı örneği için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="7928a-132">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="7928a-133">Önbelleğe alma herhangi bir gönderme etkinlik bitiş noktaları yapılandırmasında tanımlandığı sahip akışınızın için varsayılan olarak devre dışıdır.</span><span class="sxs-lookup"><span data-stu-id="7928a-133">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="7928a-134">Düzeyleri ve kanal fabrikası ve kanal önbellek için önbellek ayarlarını paylaşımı varsayılan önbelleği değiştirmek konusunda daha fazla bilgi için bkz. [etkinlikleri göndermek için önbellek paylaşımı düzeylerini değiştirme](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="7928a-134">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7928a-135">Örnek</span><span class="sxs-lookup"><span data-stu-id="7928a-135">Example</span></span>  
 <span data-ttu-id="7928a-136">Barındırılan iş akışı hizmetinde, uygulama yapılandırma dosyasında üreteci önbellek ve kanal önbellek ayarları belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7928a-136">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="7928a-137">Bunu yapmak için üretecini ve kanal önbellek için önbellek ayarlarını içeren bir hizmet davranışını ekleyin ve bu hizmet davranışını hizmetinize ekleyin.</span><span class="sxs-lookup"><span data-stu-id="7928a-137">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="7928a-138">Aşağıdaki örnek, içeren bir yapılandırma dosyası içeriğini gösterir **MyChannelCacheBehavior** özel üreteci önbellek ve kanal önbellek ayarları ile hizmet davranışı.</span><span class="sxs-lookup"><span data-stu-id="7928a-138">The following example shows the contents of a configuration file that contains the **MyChannelCacheBehavior**  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="7928a-139">Bu hizmet davranışını hizmet aracılığıyla eklenen **behaviorConfiguarion** özniteliği.</span><span class="sxs-lookup"><span data-stu-id="7928a-139">This service behavior is added to the service through the **behaviorConfiguarion** attribute.</span></span>  
  
```xml  
<configuration>    
  <system.serviceModel>  
    <!-- List of other config sections here -->   
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyChannelCacheBehavior">  
          <sendMessageChannelCache allowUnsafeCaching ="false" >  
            <!-- Control only the host level settings -->   
            <factorySettings maxItemsInCache = "8" idleTimeout = "00:05:00" leaseTimeout="10:00:00" />  
            <channelSettings maxItemsInCache = "32" idleTimeout = "00:05:00" leaseTimeout="00:06:00" />  
          </sendMessageChannelCache>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="MyService" behaviorConfiguration="MyChannelCacheBehavior" />  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7928a-140">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="7928a-140">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.ChannelCacheSettings>
- [<span data-ttu-id="7928a-141">Gönderme İşlemleri için Önbellek Paylaşımı Düzeylerini Değiştirme</span><span class="sxs-lookup"><span data-stu-id="7928a-141">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
