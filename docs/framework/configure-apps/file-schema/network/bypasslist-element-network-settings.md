---
title: <bypasslist> Öğesi (Ağ Ayarları)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: db975d44db96f605767d7320737ff3c162bbc8a5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55282964"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="8cc4d-102">\<bypasslist > öğesi (ağ ayarları)</span><span class="sxs-lookup"><span data-stu-id="8cc4d-102">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="8cc4d-103">Bir proxy sunucu kullanmaması adresleri açıklayan normal bir ifade kümesi sağlar.</span><span class="sxs-lookup"><span data-stu-id="8cc4d-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  
  
 <span data-ttu-id="8cc4d-104">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="8cc4d-104">\<configuration></span></span>  
<span data-ttu-id="8cc4d-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="8cc4d-105">\<system.net></span></span>  
<span data-ttu-id="8cc4d-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="8cc4d-106">\<defaultProxy></span></span>  
<span data-ttu-id="8cc4d-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="8cc4d-107">\<bypasslist></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cc4d-108">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="8cc4d-108">Syntax</span></span>  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8cc4d-109">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="8cc4d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8cc4d-110">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="8cc4d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8cc4d-111">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="8cc4d-111">Attributes</span></span>  
 <span data-ttu-id="8cc4d-112">Yok.</span><span class="sxs-lookup"><span data-stu-id="8cc4d-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8cc4d-113">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="8cc4d-113">Child Elements</span></span>  
  
|<span data-ttu-id="8cc4d-114">**Öğe**</span><span class="sxs-lookup"><span data-stu-id="8cc4d-114">**Element**</span></span>|<span data-ttu-id="8cc4d-115">**Açıklama**</span><span class="sxs-lookup"><span data-stu-id="8cc4d-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8cc4d-116">add</span><span class="sxs-lookup"><span data-stu-id="8cc4d-116">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="8cc4d-117">Bir IP adresi veya DNS adı için proxy atlama listesi ekler.</span><span class="sxs-lookup"><span data-stu-id="8cc4d-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="8cc4d-118">Temizle</span><span class="sxs-lookup"><span data-stu-id="8cc4d-118">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="8cc4d-119">Atlama listesi temizler.</span><span class="sxs-lookup"><span data-stu-id="8cc4d-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="8cc4d-120">remove</span><span class="sxs-lookup"><span data-stu-id="8cc4d-120">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="8cc4d-121">Bir IP adresi veya DNS adı proxy atlama listeden kaldırır.</span><span class="sxs-lookup"><span data-stu-id="8cc4d-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8cc4d-122">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="8cc4d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="8cc4d-123">**Öğe**</span><span class="sxs-lookup"><span data-stu-id="8cc4d-123">**Element**</span></span>|<span data-ttu-id="8cc4d-124">**Açıklama**</span><span class="sxs-lookup"><span data-stu-id="8cc4d-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8cc4d-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="8cc4d-125">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="8cc4d-126">Köprü Metni Aktarım Protokolü (HTTP) proxy sunucusunu yapılandırır.</span><span class="sxs-lookup"><span data-stu-id="8cc4d-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8cc4d-127">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="8cc4d-127">Remarks</span></span>  
 <span data-ttu-id="8cc4d-128">Atlama listesi içeren URI'leri açıklayan normal ifadeler, <xref:System.Net.WebRequest> örneklere erişmek doğrudan veya proxy sunucusu üzerinden.</span><span class="sxs-lookup"><span data-stu-id="8cc4d-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="8cc4d-129">Bu öğe için normal bir ifade belirtirken dikkatli olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="8cc4d-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="8cc4d-130">Normal ifade "[a-z] +\\.contoso\\.com" eşleşme barındıran tüm contoso.com etki alanı, ancak bunu ayrıca contoso.com.cpandl.com etki alanındaki herhangi bir ana bilgisayara eşleşen.</span><span class="sxs-lookup"><span data-stu-id="8cc4d-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="8cc4d-131">Contoso.com etki alanındaki bir konak eşleştirmek için bir yer işareti ("$") kullanın: "[a-z] +\\.contoso\\.com$".</span><span class="sxs-lookup"><span data-stu-id="8cc4d-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="8cc4d-132">Normal ifadeler hakkında daha fazla bilgi için bkz. [.NET framework normal ifadelerinde](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="8cc4d-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8cc4d-133">Yapılandırma Dosyaları</span><span class="sxs-lookup"><span data-stu-id="8cc4d-133">Configuration Files</span></span>  
 <span data-ttu-id="8cc4d-134">Bu öğe, uygulama yapılandırma dosyası veya makine yapılandırma dosyası (Machine.config) kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="8cc4d-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8cc4d-135">Örnek</span><span class="sxs-lookup"><span data-stu-id="8cc4d-135">Example</span></span>  
 <span data-ttu-id="8cc4d-136">Aşağıdaki örnek iki adres atlama listesine ekler.</span><span class="sxs-lookup"><span data-stu-id="8cc4d-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="8cc4d-137">İlk contoso.com etki alanındaki tüm sunucular için proxy atlar; İkinci IP adresi ile başlayan tüm sunucuların 192.168 ile proxy atlar.</span><span class="sxs-lookup"><span data-stu-id="8cc4d-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8cc4d-138">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="8cc4d-138">See also</span></span>
- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="8cc4d-139">Ağ Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="8cc4d-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
