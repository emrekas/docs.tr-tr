---
title: '&lt;enableWebScript&gt;'
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 1115b598776ca7d28698815974e06f3de57be598
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600108"
---
# <a name="ltenablewebscriptgt"></a><span data-ttu-id="ba517-102">&lt;enableWebScript&gt;</span><span class="sxs-lookup"><span data-stu-id="ba517-102">&lt;enableWebScript&gt;</span></span>
<span data-ttu-id="ba517-103">Bu öğe, ASP.NET AJAX web sayfalarından hizmet kullanmayı mümkün kılan uç nokta davranışını etkinleştirir.</span><span class="sxs-lookup"><span data-stu-id="ba517-103">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="ba517-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ba517-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ba517-105">\<davranışlar ></span><span class="sxs-lookup"><span data-stu-id="ba517-105">\<behaviors></span></span>  
<span data-ttu-id="ba517-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="ba517-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="ba517-107">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="ba517-107">\<behavior></span></span>  
<span data-ttu-id="ba517-108">\<enableWebScript ></span><span class="sxs-lookup"><span data-stu-id="ba517-108">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba517-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="ba517-109">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba517-110">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="ba517-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ba517-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="ba517-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba517-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="ba517-112">Attributes</span></span>  
 <span data-ttu-id="ba517-113">Yok.</span><span class="sxs-lookup"><span data-stu-id="ba517-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ba517-114">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="ba517-114">Child Elements</span></span>  
 <span data-ttu-id="ba517-115">Yok.</span><span class="sxs-lookup"><span data-stu-id="ba517-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ba517-116">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="ba517-116">Parent Elements</span></span>  
  
|<span data-ttu-id="ba517-117">Öğe</span><span class="sxs-lookup"><span data-stu-id="ba517-117">Element</span></span>|<span data-ttu-id="ba517-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ba517-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba517-119">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="ba517-119">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="ba517-120">Uç nokta davranışları kümesini belirtir.</span><span class="sxs-lookup"><span data-stu-id="ba517-120">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba517-121">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ba517-121">Remarks</span></span>  
 <span data-ttu-id="ba517-122">Bu davranış yalnızca ya da birlikte kullanılmalıdır [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standart bağlama veya [ \<webMessageEncoding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) bağlama öğesi.</span><span class="sxs-lookup"><span data-stu-id="ba517-122">This behavior should only be used in conjunction with either the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="ba517-123">Bu davranışı hakkında daha fazla bilgi için bkz. <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="ba517-123">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba517-124">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="ba517-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="ba517-125">AJAX Tümleştirme ve JSON Desteği</span><span class="sxs-lookup"><span data-stu-id="ba517-125">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="ba517-126">\<webHttp ></span><span class="sxs-lookup"><span data-stu-id="ba517-126">\<webHttp></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)
