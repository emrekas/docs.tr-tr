---
title: '&lt;mexHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: e50b2e1f-9668-41a5-8077-dee7abff9f0f
ms.openlocfilehash: f22ac3beb5ee90a543e65734bd89123293c2dd3e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680423"
---
# <a name="ltmexhttpbindinggt"></a><span data-ttu-id="f87bf-102">&lt;mexHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="f87bf-102">&lt;mexHttpBinding&gt;</span></span>
<span data-ttu-id="f87bf-103">HTTP üzerinde WS-MetadataExchange (WS-MEX) ileti değişimi için kullanılan bir bağlama için olan ayarları belirler.</span><span class="sxs-lookup"><span data-stu-id="f87bf-103">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTP.</span></span>  
  
 <span data-ttu-id="f87bf-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f87bf-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f87bf-105">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="f87bf-105">\<bindings></span></span>  
<span data-ttu-id="f87bf-106">\<mexHttpBinding></span><span class="sxs-lookup"><span data-stu-id="f87bf-106">\<mexHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f87bf-107">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="f87bf-107">Syntax</span></span>  
  
```xml  
<mexHttpBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f87bf-108">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="f87bf-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f87bf-109">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="f87bf-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f87bf-110">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="f87bf-110">Attributes</span></span>  
  
|<span data-ttu-id="f87bf-111">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="f87bf-111">Attribute</span></span>|<span data-ttu-id="f87bf-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="f87bf-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="f87bf-113">A <xref:System.TimeSpan> bir kapatma işlemi tamamlamak sağlanan zaman aralığını belirten bir değer.</span><span class="sxs-lookup"><span data-stu-id="f87bf-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="f87bf-114">Bu değer, büyük veya buna eşit olmalıdır <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="f87bf-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f87bf-115">Varsayılan değer 00:01:00 ' dir.</span><span class="sxs-lookup"><span data-stu-id="f87bf-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="f87bf-116">Bağlama yapılandırma adını içeren bir dize.</span><span class="sxs-lookup"><span data-stu-id="f87bf-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="f87bf-117">Bağlama için bir tanımlayıcı olarak kullanıldığından, bu değer benzersiz olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="f87bf-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="f87bf-118">Her bağlama sahip bir `name` ve `namespace` birlikte benzersiz özniteliği hizmetinin meta verilerde tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="f87bf-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="f87bf-119">Ayrıca, bu ad aynı türdeki bağlamaları arasında benzersizdir.</span><span class="sxs-lookup"><span data-stu-id="f87bf-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="f87bf-120">İle başlayarak [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bağlamalar ve davranışları için gerekli değildir bir ada sahip.</span><span class="sxs-lookup"><span data-stu-id="f87bf-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="f87bf-121">Varsayılan yapılandırma ve adsız bağlamaları ve davranışları hakkında daha fazla bilgi için bkz: [Basitleştirilmiş yapılandırma](../../../../../docs/framework/wcf/simplified-configuration.md) ve [WCF hizmetleri için Basitleştirilmiş yapılandırma](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="f87bf-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="f87bf-122">A <xref:System.TimeSpan> tamamlamak açık işlem için sağlanan zaman aralığını belirten bir değer.</span><span class="sxs-lookup"><span data-stu-id="f87bf-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="f87bf-123">Bu değer, büyük veya buna eşit olmalıdır <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="f87bf-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f87bf-124">Varsayılan değer 00:01:00 ' dir.</span><span class="sxs-lookup"><span data-stu-id="f87bf-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="f87bf-125">A <xref:System.TimeSpan> tamamlamak alma işlemi için sağlanan zaman aralığını belirten bir değer.</span><span class="sxs-lookup"><span data-stu-id="f87bf-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="f87bf-126">Bu değer, büyük veya buna eşit olmalıdır <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="f87bf-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f87bf-127">Varsayılan değer 00:10:00 ' dir.</span><span class="sxs-lookup"><span data-stu-id="f87bf-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="f87bf-128">A <xref:System.TimeSpan> tamamlamak bir gönderme işlemi için sağlanan zaman aralığını belirten bir değer.</span><span class="sxs-lookup"><span data-stu-id="f87bf-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="f87bf-129">Bu değer, büyük veya buna eşit olmalıdır <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="f87bf-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f87bf-130">Varsayılan değer 00:01:00 ' dir.</span><span class="sxs-lookup"><span data-stu-id="f87bf-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f87bf-131">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="f87bf-131">Child Elements</span></span>  
 <span data-ttu-id="f87bf-132">Yok.</span><span class="sxs-lookup"><span data-stu-id="f87bf-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f87bf-133">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="f87bf-133">Parent Elements</span></span>  
  
|<span data-ttu-id="f87bf-134">Öğe</span><span class="sxs-lookup"><span data-stu-id="f87bf-134">Element</span></span>|<span data-ttu-id="f87bf-135">Açıklama</span><span class="sxs-lookup"><span data-stu-id="f87bf-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f87bf-136">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="f87bf-136">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="f87bf-137">Bu öğe, standart ve özel bağlamalar koleksiyonunu tutar.</span><span class="sxs-lookup"><span data-stu-id="f87bf-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f87bf-138">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="f87bf-138">Remarks</span></span>  
 <span data-ttu-id="f87bf-139">Bu bağlamanın temelde olduğu bir `WSHttpBinding` devre dışı güvenlikle bağlama.</span><span class="sxs-lookup"><span data-stu-id="f87bf-139">This binding is essentially a `WSHttpBinding` binding with security disabled.</span></span> <span data-ttu-id="f87bf-140">Bu, çoğu meta veri isteklerini destekler.</span><span class="sxs-lookup"><span data-stu-id="f87bf-140">It supports most metadata requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f87bf-141">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="f87bf-141">See also</span></span>
- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpBindingElement>
- [<span data-ttu-id="f87bf-142">Nasıl yapılır: Bir yapılandırma dosyası kullanarak bir hizmet için meta verileri yayımlama</span><span class="sxs-lookup"><span data-stu-id="f87bf-142">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="f87bf-143">Özel Bağlama Üzerinden Meta Veri Yayımlama ve Alma</span><span class="sxs-lookup"><span data-stu-id="f87bf-143">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="f87bf-144">Meta Veriler</span><span class="sxs-lookup"><span data-stu-id="f87bf-144">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)
- [<span data-ttu-id="f87bf-145">Bağlamalar</span><span class="sxs-lookup"><span data-stu-id="f87bf-145">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="f87bf-146">Sistem Tarafından Sağlanan Bağlamaları Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="f87bf-146">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f87bf-147">Hizmetler ve İstemcileri Yapılandırmak için Bağlamaları Kullanma</span><span class="sxs-lookup"><span data-stu-id="f87bf-147">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="f87bf-148">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="f87bf-148">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
