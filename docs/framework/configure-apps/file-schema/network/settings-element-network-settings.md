---
title: '&lt;ayarları&gt; öğesi (ağ ayarları)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
ms.openlocfilehash: 7db55dd9d2ca79342cadb2320d08ca9235223def
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671861"
---
# <a name="ltsettingsgt-element-network-settings"></a><span data-ttu-id="976cf-102">&lt;ayarları&gt; öğesi (ağ ayarları)</span><span class="sxs-lookup"><span data-stu-id="976cf-102">&lt;settings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="976cf-103">Temel ağ seçeneklerini yapılandırır <xref:System.Net?displayProperty=nameWithType> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="976cf-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="976cf-104">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="976cf-104">\<configuration></span></span>  
<span data-ttu-id="976cf-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="976cf-105">\<system.net></span></span>  
<span data-ttu-id="976cf-106">\<Ayarlar ></span><span class="sxs-lookup"><span data-stu-id="976cf-106">\<settings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="976cf-107">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="976cf-107">Syntax</span></span>  
  
```xml  
<settings>  
  <httpListener>...</httpListener>  
  <httpWebRequest>...</httpWebRequest>  
  <ipv6>...</ipv6>  
  <performanceCounters>...</performanceCounters>  
  <servicePointManager>...</servicePointManager>  
  <socket>...</socket>  
  <webProxyScript>...</webProxyScript>  
</settings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="976cf-108">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="976cf-108">Attributes and Elements</span></span>  
 <span data-ttu-id="976cf-109">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="976cf-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="976cf-110">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="976cf-110">Attributes</span></span>  
 <span data-ttu-id="976cf-111">Yok.</span><span class="sxs-lookup"><span data-stu-id="976cf-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="976cf-112">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="976cf-112">Child Elements</span></span>  
  
|<span data-ttu-id="976cf-113">Öğe</span><span class="sxs-lookup"><span data-stu-id="976cf-113">Element</span></span>|<span data-ttu-id="976cf-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="976cf-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="976cf-115">HttpListener</span><span class="sxs-lookup"><span data-stu-id="976cf-115">httpListener</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/httplistener-element-network-settings.md)|<span data-ttu-id="976cf-116">Tarafından kullanılan parametreler özelleştirir <xref:System.Net.HttpListener> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="976cf-116">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="976cf-117">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="976cf-117">httpWebRequest</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md)|<span data-ttu-id="976cf-118">Web isteği parametreleri özelleştirir.</span><span class="sxs-lookup"><span data-stu-id="976cf-118">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="976cf-119">IPv6</span><span class="sxs-lookup"><span data-stu-id="976cf-119">ipv6</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)|<span data-ttu-id="976cf-120">Internet Protokolü sürüm 6 (IPv6) sağlayan destekler.</span><span class="sxs-lookup"><span data-stu-id="976cf-120">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="976cf-121">\<performanceCounter > öğesi (ağ ayarları)</span><span class="sxs-lookup"><span data-stu-id="976cf-121">\<performanceCounter> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/performancecounter-element-network-settings.md)|<span data-ttu-id="976cf-122">Ağ performans sayaçları sağlar.</span><span class="sxs-lookup"><span data-stu-id="976cf-122">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="976cf-123">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="976cf-123">servicePointManager</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/servicepointmanager-element-network-settings.md)|<span data-ttu-id="976cf-124">Ağ kaynaklarına bağlantılarını yapılandırır.</span><span class="sxs-lookup"><span data-stu-id="976cf-124">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="976cf-125">Yuva</span><span class="sxs-lookup"><span data-stu-id="976cf-125">socket</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/socket-element-network-settings.md)|<span data-ttu-id="976cf-126">Yuva işlemleri tamamlama bağlantı noktalarını kullanıp kullanmadığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="976cf-126">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="976cf-127">\<webProxyScript > öğesi (ağ ayarları)</span><span class="sxs-lookup"><span data-stu-id="976cf-127">\<webProxyScript> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webproxyscript-element-network-settings.md)|<span data-ttu-id="976cf-128">Web proxy'leri bulmak için kullanılan komut dosyası özelliklerini yapılandırır.</span><span class="sxs-lookup"><span data-stu-id="976cf-128">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="976cf-129">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="976cf-129">Parent Elements</span></span>  
  
|<span data-ttu-id="976cf-130">Öğe</span><span class="sxs-lookup"><span data-stu-id="976cf-130">Element</span></span>|<span data-ttu-id="976cf-131">Açıklama</span><span class="sxs-lookup"><span data-stu-id="976cf-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="976cf-132">System.NET</span><span class="sxs-lookup"><span data-stu-id="976cf-132">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="976cf-133">.NET Framework ağa nasıl bağlandığını belirten ayarları içerir.</span><span class="sxs-lookup"><span data-stu-id="976cf-133">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="976cf-134">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="976cf-134">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="976cf-135">Yapılandırma Dosyaları</span><span class="sxs-lookup"><span data-stu-id="976cf-135">Configuration Files</span></span>  
 <span data-ttu-id="976cf-136">Bu öğe, uygulama yapılandırma dosyası veya makine yapılandırma dosyası (Machine.config) kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="976cf-136">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="976cf-137">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="976cf-137">See also</span></span>
- <xref:System.Net?displayProperty=nameWithType>
- [<span data-ttu-id="976cf-138">Ağ Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="976cf-138">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
