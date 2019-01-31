---
title: <gcConcurrent> Öğesi
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae20e33f610acf77f2039b94803a19d371b771c0
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55265993"
---
# <a name="gcconcurrent-element"></a><span data-ttu-id="10f99-102">\<gcConcurrent > öğesi</span><span class="sxs-lookup"><span data-stu-id="10f99-102">\<gcConcurrent> Element</span></span>
<span data-ttu-id="10f99-103">Ortak dil çalışma zamanının atık toplama ayrı bir iş parçacığı üzerinde çalışıp çalışmayacağını belirtir.</span><span class="sxs-lookup"><span data-stu-id="10f99-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>  
  
 <span data-ttu-id="10f99-104">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="10f99-104">\<configuration></span></span>  
<span data-ttu-id="10f99-105">\<çalışma zamanı ></span><span class="sxs-lookup"><span data-stu-id="10f99-105">\<runtime></span></span>  
<span data-ttu-id="10f99-106">\<gcConcurrent ></span><span class="sxs-lookup"><span data-stu-id="10f99-106">\<gcConcurrent></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10f99-107">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="10f99-107">Syntax</span></span>  
  
```xml  
<gcConcurrent    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10f99-108">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="10f99-108">Attributes and Elements</span></span>  
 <span data-ttu-id="10f99-109">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="10f99-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10f99-110">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="10f99-110">Attributes</span></span>  
  
|<span data-ttu-id="10f99-111">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="10f99-111">Attribute</span></span>|<span data-ttu-id="10f99-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="10f99-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="10f99-113">Gerekli öznitelik.</span><span class="sxs-lookup"><span data-stu-id="10f99-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="10f99-114">Çalışma zamanının atık toplama eşzamanlı olarak çalışıp çalışmayacağını belirtir.</span><span class="sxs-lookup"><span data-stu-id="10f99-114">Specifies whether the runtime runs garbage collection concurrently.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="10f99-115">etkin Öznitelik</span><span class="sxs-lookup"><span data-stu-id="10f99-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="10f99-116">Değer</span><span class="sxs-lookup"><span data-stu-id="10f99-116">Value</span></span>|<span data-ttu-id="10f99-117">Açıklama</span><span class="sxs-lookup"><span data-stu-id="10f99-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="10f99-118">Çöp toplama, eşzamanlı olarak çalıştırmaz.</span><span class="sxs-lookup"><span data-stu-id="10f99-118">Does not run garbage collection concurrently.</span></span>|  
|`true`|<span data-ttu-id="10f99-119">Atık toplama eşzamanlı olarak çalışır.</span><span class="sxs-lookup"><span data-stu-id="10f99-119">Runs garbage collection concurrently.</span></span> <span data-ttu-id="10f99-120">Bu varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="10f99-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="10f99-121">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="10f99-121">Child Elements</span></span>  
 <span data-ttu-id="10f99-122">Yok.</span><span class="sxs-lookup"><span data-stu-id="10f99-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="10f99-123">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="10f99-123">Parent Elements</span></span>  
  
|<span data-ttu-id="10f99-124">Öğe</span><span class="sxs-lookup"><span data-stu-id="10f99-124">Element</span></span>|<span data-ttu-id="10f99-125">Açıklama</span><span class="sxs-lookup"><span data-stu-id="10f99-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="10f99-126">Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.</span><span class="sxs-lookup"><span data-stu-id="10f99-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="10f99-127">Derleme bağlama ve atık toplama hakkında bilgi içerir.</span><span class="sxs-lookup"><span data-stu-id="10f99-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10f99-128">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="10f99-128">Remarks</span></span>  
 <span data-ttu-id="10f99-129">Önce .NET Framework 4, atık toplama arka planda ayrı bir iş parçacığı üzerinde gerçekleştirilen eşzamanlı atık toplama, iş istasyonu çöp toplama desteklenir.</span><span class="sxs-lookup"><span data-stu-id="10f99-129">Prior to the .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="10f99-130">.NET Framework 4'te, eş zamanlı çöp toplama, arka plan da ayrı bir iş parçacığı üzerinde arka planda atık toplama gerçekleştirir GC, tarafından değiştirildi.</span><span class="sxs-lookup"><span data-stu-id="10f99-130">In the .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="10f99-131">.NET Framework 4.5 ile başlayarak, arka plan koleksiyonu sunucu çöp toplamada kullanıma sunulmuştur.</span><span class="sxs-lookup"><span data-stu-id="10f99-131">Starting with the .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="10f99-132">`<gcConcurrent>` Öğesi, çalışma zamanı ya da eşzamanlı gerçekleştirip gerçekleştirmediğini kontrol eder veya varsa veya ön planda atık toplama gerçekleştiğini plan çöp toplama.</span><span class="sxs-lookup"><span data-stu-id="10f99-132">The `<gcConcurrent>` element controls whether the runtime performs either concurrent or background garbage collection, if it is available, or whether it performs garbage collection in the foreground.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="10f99-133">.NET Framework 4 ile başlayarak, eşzamanlı atık toplama arka plan atık toplama işlemi tarafından değiştirilir.</span><span class="sxs-lookup"><span data-stu-id="10f99-133">Starting with the .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="10f99-134">Koşulları *eşzamanlı* ve *arka plan* .NET Framework belgelerinde birbirinin yerine kullanılır.</span><span class="sxs-lookup"><span data-stu-id="10f99-134">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="10f99-135">Arka plan çöp toplama devre dışı bırakmak için `<gcConcurrent>` bu makalede ele alınan öğesi.</span><span class="sxs-lookup"><span data-stu-id="10f99-135">To disable background garbage collection, use the `<gcConcurrent>` element, as discussed in this article.</span></span>  
  
 <span data-ttu-id="10f99-136">Varsayılan, çalışma zamanı kullanan eş zamanlı veya arka plan çöp toplama, hangi gecikme süresi için optimize edilmiştir.</span><span class="sxs-lookup"><span data-stu-id="10f99-136">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="10f99-137">Uygulamanız yoğun bir kullanıcı etkileşimi gerektiriyorsa, eşzamanlı çöp toplama atık toplama işini gerçekleştirmek için uygulamanın duraklatma süresi en aza indirmek için etkin bırakın.</span><span class="sxs-lookup"><span data-stu-id="10f99-137">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="10f99-138">Ayarlarsanız `enabled` özniteliği `<gcConcurrent>` öğesine `false`, aktarım hızı için en iyi duruma getirilmiş eşzamanlı olmayan çöp toplama, çalışma zamanı kullanır.</span><span class="sxs-lookup"><span data-stu-id="10f99-138">If you set the `enabled` attribute of the `<gcConcurrent>` element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span> <span data-ttu-id="10f99-139">Şu yapılandırma dosyasını arka plan çöp toplama devre dışı bırakır.</span><span class="sxs-lookup"><span data-stu-id="10f99-139">The following configuration file disables background garbage collection.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="10f99-140">Varsa bir `<gcConcurrentSetting>` makine yapılandırma dosyasında ayarı, tüm .NET Framework uygulamaları için varsayılan değer tanımlar.</span><span class="sxs-lookup"><span data-stu-id="10f99-140">If there is a `<gcConcurrentSetting>` setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="10f99-141">Makine yapılandırma dosyası ayarı, uygulama yapılandırma dosyası ayarı geçersiz kılar.</span><span class="sxs-lookup"><span data-stu-id="10f99-141">The machine configuration file setting overrides the application configuration file setting.</span></span>  
  
 <span data-ttu-id="10f99-142">Daha fazla eşzamanlı hakkında bilgi ve arka plan çöp toplama için "eş zamanlı çöp toplama" bölümüne bakın. [çöp toplamanın Temelleri](../../../../../docs/standard/garbage-collection/fundamentals.md) konu.</span><span class="sxs-lookup"><span data-stu-id="10f99-142">For more information on concurrent and background garbage collection, see the "Concurrent garbage collection" section in the [Fundamentals of Garbage Collection](../../../../../docs/standard/garbage-collection/fundamentals.md) topic.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10f99-143">Örnek</span><span class="sxs-lookup"><span data-stu-id="10f99-143">Example</span></span>  
 <span data-ttu-id="10f99-144">Aşağıdaki örnek, eş zamanlı çöp toplama sağlar.</span><span class="sxs-lookup"><span data-stu-id="10f99-144">The following example enables concurrent garbage collection.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="10f99-145">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="10f99-145">See also</span></span>
- [<span data-ttu-id="10f99-146">Çalışma Zamanı Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="10f99-146">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="10f99-147">Yapılandırma Dosyası Şeması</span><span class="sxs-lookup"><span data-stu-id="10f99-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="10f99-148">Atık Toplamanın Temelleri</span><span class="sxs-lookup"><span data-stu-id="10f99-148">Fundamentals of Garbage Collection</span></span>](../../../../../docs/standard/garbage-collection/fundamentals.md)
