---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 462a06e5a773310b6364838ae2ebc14da0a2ee1b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925883"
---
# <a name="defaultports"></a><span data-ttu-id="0a2d9-101">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="0a2d9-101">\<defaultPorts></span></span>
<span data-ttu-id="0a2d9-102">Varsayılan bağlantı noktalarının, istemci uygulamanın dinlediği varsayılan iletişim uç noktalarını listelemesi.</span><span class="sxs-lookup"><span data-stu-id="0a2d9-102">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="0a2d9-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0a2d9-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="0a2d9-104">\<davranışlar ></span><span class="sxs-lookup"><span data-stu-id="0a2d9-104">\<behaviors></span></span>  
<span data-ttu-id="0a2d9-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="0a2d9-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="0a2d9-106">\<davranış ></span><span class="sxs-lookup"><span data-stu-id="0a2d9-106">\<behavior></span></span>  
<span data-ttu-id="0a2d9-107">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="0a2d9-107">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="0a2d9-108">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="0a2d9-108">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a2d9-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="0a2d9-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a2d9-110">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="0a2d9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0a2d9-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="0a2d9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a2d9-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="0a2d9-112">Attributes</span></span>  
 <span data-ttu-id="0a2d9-113">Yok.</span><span class="sxs-lookup"><span data-stu-id="0a2d9-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0a2d9-114">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="0a2d9-114">Child Elements</span></span>  
  
|<span data-ttu-id="0a2d9-115">Öğe</span><span class="sxs-lookup"><span data-stu-id="0a2d9-115">Element</span></span>|<span data-ttu-id="0a2d9-116">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0a2d9-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a2d9-117">\<\<defaultPort > ekleyin ></span><span class="sxs-lookup"><span data-stu-id="0a2d9-117">\<add> of \<defaultPorts></span></span>](add-of-defaultports.md)|<span data-ttu-id="0a2d9-118">İstemci uygulamanın dinlediği varsayılan bir iletişim uç noktası.</span><span class="sxs-lookup"><span data-stu-id="0a2d9-118">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0a2d9-119">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="0a2d9-119">Parent Elements</span></span>  
  
|<span data-ttu-id="0a2d9-120">Öğe</span><span class="sxs-lookup"><span data-stu-id="0a2d9-120">Element</span></span>|<span data-ttu-id="0a2d9-121">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0a2d9-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a2d9-122">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="0a2d9-122">\<useRequestHeadersForMetadataAddress></span></span>](userequestheadersformetadataaddress.md)|<span data-ttu-id="0a2d9-123">Varsayılan bağlantı noktalarının listesi.</span><span class="sxs-lookup"><span data-stu-id="0a2d9-123">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0a2d9-124">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="0a2d9-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
