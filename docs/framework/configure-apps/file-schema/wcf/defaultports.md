---
title: '&lt;defaultPorts&gt;'
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 2c742f98315c0e497ac4117953424bae913cb5b9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614503"
---
# <a name="ltdefaultportsgt"></a><span data-ttu-id="334ef-102">&lt;defaultPorts&gt;</span><span class="sxs-lookup"><span data-stu-id="334ef-102">&lt;defaultPorts&gt;</span></span>
<span data-ttu-id="334ef-103">İstemci uygulamasının dinleyeceği, varsayılan iletişim bitiş noktalarını listeleyen varsayılan bağlantı noktaları koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="334ef-103">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="334ef-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="334ef-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="334ef-105">\<davranışlar ></span><span class="sxs-lookup"><span data-stu-id="334ef-105">\<behaviors></span></span>  
<span data-ttu-id="334ef-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="334ef-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="334ef-107">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="334ef-107">\<behavior></span></span>  
<span data-ttu-id="334ef-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="334ef-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="334ef-109">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="334ef-109">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="334ef-110">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="334ef-110">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="334ef-111">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="334ef-111">Attributes and Elements</span></span>  
 <span data-ttu-id="334ef-112">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="334ef-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="334ef-113">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="334ef-113">Attributes</span></span>  
 <span data-ttu-id="334ef-114">Yok.</span><span class="sxs-lookup"><span data-stu-id="334ef-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="334ef-115">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="334ef-115">Child Elements</span></span>  
  
|<span data-ttu-id="334ef-116">Öğe</span><span class="sxs-lookup"><span data-stu-id="334ef-116">Element</span></span>|<span data-ttu-id="334ef-117">Açıklama</span><span class="sxs-lookup"><span data-stu-id="334ef-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="334ef-118">\<Ekle >, \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="334ef-118">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="334ef-119">İstemci uygulamasının dinleyeceği bir varsayılan iletişim bitiş noktaları.</span><span class="sxs-lookup"><span data-stu-id="334ef-119">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="334ef-120">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="334ef-120">Parent Elements</span></span>  
  
|<span data-ttu-id="334ef-121">Öğe</span><span class="sxs-lookup"><span data-stu-id="334ef-121">Element</span></span>|<span data-ttu-id="334ef-122">Açıklama</span><span class="sxs-lookup"><span data-stu-id="334ef-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="334ef-123">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="334ef-123">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="334ef-124">Varsayılan bağlantı noktalarının listesi.</span><span class="sxs-lookup"><span data-stu-id="334ef-124">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="334ef-125">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="334ef-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
