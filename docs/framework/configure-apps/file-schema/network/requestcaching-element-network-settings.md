---
title: <requestCaching> Öğesi (Ağ Ayarları)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching
helpviewer_keywords:
- requestCaching element
- <requestCaching> element
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
ms.openlocfilehash: d78325438ba158c0c1d0e322d0b02d0a0a2a57f0
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277712"
---
# <a name="requestcaching-element-network-settings"></a><span data-ttu-id="37379-102">\<requestCaching > öğesi (ağ ayarları)</span><span class="sxs-lookup"><span data-stu-id="37379-102">\<requestCaching> Element (Network Settings)</span></span>
<span data-ttu-id="37379-103">Ağ istekleri için önbelleğe alma mekanizması denetler.</span><span class="sxs-lookup"><span data-stu-id="37379-103">Controls the caching mechanism for network requests.</span></span>  
  
 <span data-ttu-id="37379-104">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="37379-104">\<configuration></span></span>  
<span data-ttu-id="37379-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="37379-105">\<system.net></span></span>  
<span data-ttu-id="37379-106">\<requestCaching ></span><span class="sxs-lookup"><span data-stu-id="37379-106">\<requestCaching></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37379-107">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="37379-107">Syntax</span></span>  
  
```xml  
<requestCaching  
  isPrivateCache ="true|false"  
  disableAllCaching="true|false"  
  defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
  unspecifiedMaximumAge= "d.hh.mm.ss">  
    <defaultHttpCachePolicy>...</defaultHttpCachePolicy>  
    <defaultFtpCachePolicy>...</defaultFtpCachePolicy>  
</requestCaching>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37379-108">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="37379-108">Attributes and Elements</span></span>  
 <span data-ttu-id="37379-109">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="37379-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37379-110">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="37379-110">Attributes</span></span>  
  
|<span data-ttu-id="37379-111">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="37379-111">Attribute</span></span>|<span data-ttu-id="37379-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="37379-112">Description</span></span>|  
|---------------|-----------------|  
|`isPrivateCache`|<span data-ttu-id="37379-113">Önbellek bilgilerinin farklı kullanıcılar arasında yalıtım sağlayıp sağlamadığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="37379-113">Specifies whether the cache provides isolation between the information of different users.</span></span> <span data-ttu-id="37379-114">Varsayılan değer `true` şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="37379-114">The default value is `true`.</span></span> <span data-ttu-id="37379-115">Bu değer olmalıdır `false` orta katman uygulamaları için.</span><span class="sxs-lookup"><span data-stu-id="37379-115">This value should be `false` for middle tier applications.</span></span>|  
|`disableAllCaching`|<span data-ttu-id="37379-116">Önbelleğe alma için tüm Web yanıtları devre dışı bırakıldı ve programlı olarak geçersiz kılınamaz belirtir.</span><span class="sxs-lookup"><span data-stu-id="37379-116">Specifies that caching is disabled for all Web responses, and cannot be overridden programmatically.</span></span>|  
|`defaultPolicyLevel`|<span data-ttu-id="37379-117">Değerlerin birini <xref:System.Net.Cache.RequestCacheLevel> sabit listesi.</span><span class="sxs-lookup"><span data-stu-id="37379-117">One of the values in the <xref:System.Net.Cache.RequestCacheLevel> enumeration.</span></span> <span data-ttu-id="37379-118">Varsayılan değer `BypassCache` şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="37379-118">The default value is `BypassCache`.</span></span>|  
|`unspecifiedMaximumAge`|<span data-ttu-id="37379-119">Sonra içeriğin süresi dolmuş olarak işaretlenmiş varsayılan süreyi belirtir.</span><span class="sxs-lookup"><span data-stu-id="37379-119">Specifies the default time after which content is marked as expired.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="37379-120">policyLevel özniteliği</span><span class="sxs-lookup"><span data-stu-id="37379-120">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="37379-121">Değer</span><span class="sxs-lookup"><span data-stu-id="37379-121">Value</span></span>|<span data-ttu-id="37379-122">Açıklama</span><span class="sxs-lookup"><span data-stu-id="37379-122">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="37379-123">Önbelleğe alınmış kaynak sona erme, değiştirilmesi ve içerik uzunluğu öznitelikleri mevcut olduğundan yeni bir kaynaktır ve içerik uzunluğu doğru döndürür.</span><span class="sxs-lookup"><span data-stu-id="37379-123">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="37379-124">Kaynak sunucudan döndürür.</span><span class="sxs-lookup"><span data-stu-id="37379-124">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="37379-125">İçerik uzunluğu varsa ve giriş boyutu eşleşen önbelleğe alınmış kaynak döndürür.</span><span class="sxs-lookup"><span data-stu-id="37379-125">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="37379-126">İçerik uzunluğu sağlanır ve giriş boyutu eşleşiyorsa, önbelleğe alınmış kaynak döndürür; Aksi takdirde, kaynak sunucudan indirilir ve çağırana döndürülür.</span><span class="sxs-lookup"><span data-stu-id="37379-126">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="37379-127">Önbelleğe alınmış kaynak zaman damgası önbelleğe alınmış kaynak sunucusunda kaynak zaman damgası ile aynı olduğunda döndürür; Aksi takdirde, kaynak sunucudan önbelleğinde depolanan indirilir ve çağırana döndürülür.</span><span class="sxs-lookup"><span data-stu-id="37379-127">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and is returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="37379-128">Kaynak sunucudan indirir, önbellekte depolar ve kaynak çağırana döner.</span><span class="sxs-lookup"><span data-stu-id="37379-128">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="37379-129">Önbelleğe alınan bir kaynağın varolup olmadığını silinir.</span><span class="sxs-lookup"><span data-stu-id="37379-129">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="37379-130">Kaynak sunucudan indirilir ve çağırana döndürülür.</span><span class="sxs-lookup"><span data-stu-id="37379-130">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="37379-131">Bir istek, zaman damgası zaman damgasını kaynak sunucudaki aynı olduğunda, kaynağın önbelleğe alınmış kopyasını kullanarak karşılayan; Aksi takdirde, kaynak sunucudan arayana sunulan yüklenir ve önbellekte depolanır,</span><span class="sxs-lookup"><span data-stu-id="37379-131">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and is stored in the cache,</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="37379-132">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="37379-132">Child Elements</span></span>  
  
|<span data-ttu-id="37379-133">Öğe</span><span class="sxs-lookup"><span data-stu-id="37379-133">Element</span></span>|<span data-ttu-id="37379-134">Açıklama</span><span class="sxs-lookup"><span data-stu-id="37379-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37379-135">defaultHttpCachePolicy</span><span class="sxs-lookup"><span data-stu-id="37379-135">defaultHttpCachePolicy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaulthttpcachepolicy-element-network-settings.md)|<span data-ttu-id="37379-136">İsteğe bağlı öğe.</span><span class="sxs-lookup"><span data-stu-id="37379-136">Optional element.</span></span><br /><br /> <span data-ttu-id="37379-137">HTTP önbelleğe alma etkindir ve önbelleğe alma ilkesi varsayılan tanımlar olup olmadığını açıklar.</span><span class="sxs-lookup"><span data-stu-id="37379-137">Describes whether HTTP caching is active and describes the default caching policy.</span></span>|  
|[<span data-ttu-id="37379-138">\<defaultFtpCachePolicy > öğesi (ağ ayarları)</span><span class="sxs-lookup"><span data-stu-id="37379-138">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultftpcachepolicy-element-network-settings.md)|<span data-ttu-id="37379-139">İsteğe bağlı öğe.</span><span class="sxs-lookup"><span data-stu-id="37379-139">Optional element.</span></span><br /><br /> <span data-ttu-id="37379-140">FTP önbelleğe alma etkindir ve önbelleğe alma ilkesi varsayılan tanımlar olup olmadığını açıklar.</span><span class="sxs-lookup"><span data-stu-id="37379-140">Describes whether FTP caching is active and describes the default caching policy.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="37379-141">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="37379-141">Parent Elements</span></span>  
  
|<span data-ttu-id="37379-142">Öğe</span><span class="sxs-lookup"><span data-stu-id="37379-142">Element</span></span>|<span data-ttu-id="37379-143">Açıklama</span><span class="sxs-lookup"><span data-stu-id="37379-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37379-144">System.NET</span><span class="sxs-lookup"><span data-stu-id="37379-144">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="37379-145">.NET Framework ağa nasıl bağlandığını belirten ayarları içerir.</span><span class="sxs-lookup"><span data-stu-id="37379-145">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="37379-146">Örnek</span><span class="sxs-lookup"><span data-stu-id="37379-146">Example</span></span>  
 <span data-ttu-id="37379-147">Aşağıdaki örnek, tüm önbelleğe alma işlemlerini devre dışı bırakmak gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="37379-147">The following example shows how to disable all caching.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="37379-148">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="37379-148">See also</span></span>
- <xref:System.Net.Cache?displayProperty=nameWithType>
- [<span data-ttu-id="37379-149">Ağ Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="37379-149">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
