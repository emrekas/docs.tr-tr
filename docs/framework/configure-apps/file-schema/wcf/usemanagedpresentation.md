---
title: '&lt;useManagedPresentation&gt;'
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: 96490421addfadd9cef6b65bddaed0aae3370d15
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720281"
---
# <a name="ltusemanagedpresentationgt"></a><span data-ttu-id="e8ac7-102">&lt;useManagedPresentation&gt;</span><span class="sxs-lookup"><span data-stu-id="e8ac7-102">&lt;useManagedPresentation&gt;</span></span>
<span data-ttu-id="e8ac7-103">CardSpace güvenlik belirteci WS-Trust öğesinin CardSpace profilini destekleyen hizmeti ile iletişim kurmak için kullanılan bir bağlama öğesi.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-103">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="e8ac7-104">Bu öğe yok özniteliği var ve boş bir anahtar vardır.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-104">This element has no attribute and is present as an empty switch.</span></span>  
  
 <span data-ttu-id="e8ac7-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e8ac7-105">\<system.serviceModel></span></span>  
<span data-ttu-id="e8ac7-106">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="e8ac7-106">\<bindings></span></span>  
<span data-ttu-id="e8ac7-107">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="e8ac7-107">\<customBinding></span></span>  
<span data-ttu-id="e8ac7-108">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="e8ac7-108">\<binding></span></span>  
<span data-ttu-id="e8ac7-109">\<useManagedPresentation ></span><span class="sxs-lookup"><span data-stu-id="e8ac7-109">\<useManagedPresentation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8ac7-110">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="e8ac7-110">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8ac7-111">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="e8ac7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e8ac7-112">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8ac7-113">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="e8ac7-113">Attributes</span></span>  
 <span data-ttu-id="e8ac7-114">Yok.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e8ac7-115">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="e8ac7-115">Child Elements</span></span>  
 <span data-ttu-id="e8ac7-116">Hiçbiri</span><span class="sxs-lookup"><span data-stu-id="e8ac7-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e8ac7-117">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="e8ac7-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e8ac7-118">Öğe</span><span class="sxs-lookup"><span data-stu-id="e8ac7-118">Element</span></span>|<span data-ttu-id="e8ac7-119">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e8ac7-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8ac7-120">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="e8ac7-120">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="e8ac7-121">Özel bağlama tüm bağlama yeteneklerini tanımlar.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8ac7-122">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e8ac7-122">Remarks</span></span>  
 <span data-ttu-id="e8ac7-123">Bu öğe, WS-Trust öğesinin CardSpace profilini destekleyen olgu, ilkede ifade etmek için bir kimlik sağlayıcısı tarafından kullanılır.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-123">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="e8ac7-124">Bu tür bir ilke onaylama yayımlama kimlik sağlayıcıları, CardSpace profilini temel alan sorunu belirteçleri görüyor olmalısınız.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-124">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8ac7-125">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="e8ac7-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="e8ac7-126">Bağlamalar</span><span class="sxs-lookup"><span data-stu-id="e8ac7-126">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="e8ac7-127">Bağlamaları Genişletme</span><span class="sxs-lookup"><span data-stu-id="e8ac7-127">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e8ac7-128">Özel Bağlamalar</span><span class="sxs-lookup"><span data-stu-id="e8ac7-128">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="e8ac7-129">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="e8ac7-129">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
