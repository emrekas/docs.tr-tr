---
title: webRequestModules için <remove> Öğesi (Ağ Ayarları)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, webRequestModules
- webRequestModules, remove element
- <remove> element, webRequestModules
- <webRequestModules>, remove element
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
ms.openlocfilehash: c57e2849d608b1706c41beca91ff8026ebd9ca45
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085408"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="f8e22-102">\<kaldırma > webRequestModules (ağ ayarları) için</span><span class="sxs-lookup"><span data-stu-id="f8e22-102">\<remove> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="f8e22-103">Özel bir Web isteği modülü uygulamadan kaldırır.</span><span class="sxs-lookup"><span data-stu-id="f8e22-103">Removes a custom Web request module from the application.</span></span>  
  
 <span data-ttu-id="f8e22-104">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="f8e22-104">\<configuration></span></span>  
<span data-ttu-id="f8e22-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="f8e22-105">\<system.net></span></span>  
<span data-ttu-id="f8e22-106">\<webRequestModules ></span><span class="sxs-lookup"><span data-stu-id="f8e22-106">\<webRequestModules></span></span>  
<span data-ttu-id="f8e22-107">\<kaldırma ></span><span class="sxs-lookup"><span data-stu-id="f8e22-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8e22-108">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="f8e22-108">Syntax</span></span>  
  
```xml  
<remove   
  prefix="URI prefix"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8e22-109">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="f8e22-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f8e22-110">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="f8e22-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8e22-111">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="f8e22-111">Attributes</span></span>  
  
|<span data-ttu-id="f8e22-112">**Öznitelik**</span><span class="sxs-lookup"><span data-stu-id="f8e22-112">**Attribute**</span></span>|<span data-ttu-id="f8e22-113">**Açıklama**</span><span class="sxs-lookup"><span data-stu-id="f8e22-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="f8e22-114">Bu Web isteği modülü tarafından işlenen isteklerin için URI öneki.</span><span class="sxs-lookup"><span data-stu-id="f8e22-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f8e22-115">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="f8e22-115">Child Elements</span></span>  
 <span data-ttu-id="f8e22-116">Yok.</span><span class="sxs-lookup"><span data-stu-id="f8e22-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f8e22-117">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="f8e22-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f8e22-118">**Öğe**</span><span class="sxs-lookup"><span data-stu-id="f8e22-118">**Element**</span></span>|<span data-ttu-id="f8e22-119">**Açıklama**</span><span class="sxs-lookup"><span data-stu-id="f8e22-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f8e22-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="f8e22-120">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="f8e22-121">Ağ konaklarından bilgi istemek için modüller belirtir.</span><span class="sxs-lookup"><span data-stu-id="f8e22-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8e22-122">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="f8e22-122">Remarks</span></span>  
 <span data-ttu-id="f8e22-123">`remove` Belirtilen URI öneki kayıtlı Web isteği modülü öğeyi kaldırır.</span><span class="sxs-lookup"><span data-stu-id="f8e22-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="f8e22-124">Değeri `prefix` özniteliği olmalıdır geçerli bir URI'ın önde gelen karakter Örneğin, "`http`", veya "`http://www.contoso.com`".</span><span class="sxs-lookup"><span data-stu-id="f8e22-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f8e22-125">Yapılandırma Dosyaları</span><span class="sxs-lookup"><span data-stu-id="f8e22-125">Configuration Files</span></span>  
 <span data-ttu-id="f8e22-126">Bu öğe, uygulama yapılandırma dosyası veya makine yapılandırma dosyası (Machine.config) kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="f8e22-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8e22-127">Örnek</span><span class="sxs-lookup"><span data-stu-id="f8e22-127">Example</span></span>  

<span data-ttu-id="f8e22-128">Aşağıdaki örnek, HTTP için mevcut Web isteği modülü kaldırır ve ardından kayıtları için yeni özel bir Web isteği modülü için HTTP istekleri `www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="f8e22-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <remove prefix="http">  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f8e22-129">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="f8e22-129">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="f8e22-130">Ağ Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="f8e22-130">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
