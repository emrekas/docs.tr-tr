---
title: '&lt;performanceCounter&gt; öğesi (ağ ayarları)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounter element
- <performanceCounter> element
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
ms.openlocfilehash: ea0eba097505741aba31bce4f23e0cc9ca1d4608
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712489"
---
# <a name="ltperformancecountergt-element-network-settings"></a><span data-ttu-id="3056f-102">&lt;performanceCounter&gt; öğesi (ağ ayarları)</span><span class="sxs-lookup"><span data-stu-id="3056f-102">&lt;performanceCounter&gt; Element (Network Settings)</span></span>
<span data-ttu-id="3056f-103">Etkinleştirir veya ağ performans sayaçları devre dışı bırakır.</span><span class="sxs-lookup"><span data-stu-id="3056f-103">Enables or disables networking performance counters.</span></span>  
  
 <span data-ttu-id="3056f-104">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="3056f-104">\<configuration></span></span>  
<span data-ttu-id="3056f-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="3056f-105">\<system.net></span></span>  
<span data-ttu-id="3056f-106">\<Ayarlar ></span><span class="sxs-lookup"><span data-stu-id="3056f-106">\<settings></span></span>  
<span data-ttu-id="3056f-107">\<performanceCounters ></span><span class="sxs-lookup"><span data-stu-id="3056f-107">\<performanceCounters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3056f-108">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="3056f-108">Syntax</span></span>  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3056f-109">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="3056f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3056f-110">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="3056f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3056f-111">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="3056f-111">Attributes</span></span>  
  
|<span data-ttu-id="3056f-112">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="3056f-112">Attribute</span></span>|<span data-ttu-id="3056f-113">Açıklama</span><span class="sxs-lookup"><span data-stu-id="3056f-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="3056f-114">Ağ performans sayaçlarının etkin olup olmadığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="3056f-114">Specifies whether the networking performance counters are enabled.</span></span> <span data-ttu-id="3056f-115">Varsayılan değer `false` şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="3056f-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3056f-116">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="3056f-116">Child Elements</span></span>  
 <span data-ttu-id="3056f-117">Yok.</span><span class="sxs-lookup"><span data-stu-id="3056f-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3056f-118">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="3056f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="3056f-119">Öğe</span><span class="sxs-lookup"><span data-stu-id="3056f-119">Element</span></span>|<span data-ttu-id="3056f-120">Açıklama</span><span class="sxs-lookup"><span data-stu-id="3056f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3056f-121">Ayarlar</span><span class="sxs-lookup"><span data-stu-id="3056f-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="3056f-122">Temel ağ seçeneklerini yapılandırır <xref:System.Net> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="3056f-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3056f-123">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="3056f-123">Remarks</span></span>  
 <span data-ttu-id="3056f-124">Bu öğe, uygulama yapılandırma dosyası veya makine yapılandırma dosyası (Machine.config) kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="3056f-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="3056f-125">Ağ performans sayaçları yapılandırma dosyasında kullanılacak etkinleştirilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="3056f-125">Networking performance counters need to be enabled in the configuration file to be used.</span></span> <span data-ttu-id="3056f-126">Tüm ağ performans sayaçları etkin veya yapılandırma dosyasında tek bir ayarı ile devre dışı.</span><span class="sxs-lookup"><span data-stu-id="3056f-126">All networking performance counters are enabled or disabled with a single setting in the configuration file.</span></span> <span data-ttu-id="3056f-127">Ağ performans sayaçları tek etkin veya devre dışı.</span><span class="sxs-lookup"><span data-stu-id="3056f-127">Individual networking performance counters cannot be enabled or disabled.</span></span> <span data-ttu-id="3056f-128">Belirli ağ performans sayaçları hakkında daha fazla bilgi için bkz. [ağ performans sayaçları](../../../../../docs/framework/debug-trace-profile/performance-counters.md#networking).</span><span class="sxs-lookup"><span data-stu-id="3056f-128">For more information on the specific networking performance counters, see [Networking Performance Counters](../../../../../docs/framework/debug-trace-profile/performance-counters.md#networking).</span></span>  
  
 <span data-ttu-id="3056f-129">Ağ performans sayaçları devre dışı bırakıldı varsayılan değerdir.</span><span class="sxs-lookup"><span data-stu-id="3056f-129">The default value is that networking performance counters are disabled.</span></span>  
  
 <span data-ttu-id="3056f-130"><xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> Özelliği, geçerli değerini almak için kullanılabilir **etkin** ilgili yapılandırma dosyaları özniteliği.</span><span class="sxs-lookup"><span data-stu-id="3056f-130">The <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> property can be used to get the current value of the **enabled** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3056f-131">Örnek</span><span class="sxs-lookup"><span data-stu-id="3056f-131">Example</span></span>  
 <span data-ttu-id="3056f-132">Aşağıdaki örnek nasıl yapılandırılacağı gösterilmektedir <xref:System.Net> ve ilgili ağ performans sayaçları etkinleştirmek için ad alanları.</span><span class="sxs-lookup"><span data-stu-id="3056f-132">The following example shows how to configure the <xref:System.Net> and related namespaces to enable networking performance counters.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <performanceCounters  
        enabled="true"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3056f-133">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="3056f-133">See also</span></span>
- <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="3056f-134">Ağ Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="3056f-134">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
- [<span data-ttu-id="3056f-135">Ağ performans sayaçları</span><span class="sxs-lookup"><span data-stu-id="3056f-135">Networking Performance Counters</span></span>](../../../../../docs/framework/debug-trace-profile/performance-counters.md#networking)
