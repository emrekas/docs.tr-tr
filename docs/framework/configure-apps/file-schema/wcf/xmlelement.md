---
title: '&lt;XmlElement&gt;'
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 40703bdf62e8c69ac7e09a0d715e2a2f99408680
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612287"
---
# <a name="ltxmlelementgt"></a><span data-ttu-id="2407c-102">&lt;XmlElement&gt;</span><span class="sxs-lookup"><span data-stu-id="2407c-102">&lt;xmlElement&gt;</span></span>
<span data-ttu-id="2407c-103">İleti gövdesini güvenlik belirteci hizmeti için bir belirteç isterken gönderilen bir XML öğesi belirtir.</span><span class="sxs-lookup"><span data-stu-id="2407c-103">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="2407c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2407c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2407c-105">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="2407c-105">\<bindings></span></span>  
<span data-ttu-id="2407c-106">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="2407c-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="2407c-107">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="2407c-107">\<binding></span></span>  
<span data-ttu-id="2407c-108">\<Güvenlik ></span><span class="sxs-lookup"><span data-stu-id="2407c-108">\<security></span></span>  
<span data-ttu-id="2407c-109">\<İleti ></span><span class="sxs-lookup"><span data-stu-id="2407c-109">\<message></span></span>  
<span data-ttu-id="2407c-110">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="2407c-110">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2407c-111">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="2407c-111">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2407c-112">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="2407c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="2407c-113">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="2407c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2407c-114">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="2407c-114">Attributes</span></span>  
  
|<span data-ttu-id="2407c-115">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="2407c-115">Attribute</span></span>|<span data-ttu-id="2407c-116">Açıklama</span><span class="sxs-lookup"><span data-stu-id="2407c-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2407c-117">xmlElement</span><span class="sxs-lookup"><span data-stu-id="2407c-117">xmlElement</span></span>|<span data-ttu-id="2407c-118">İleti gövdesini güvenlik belirteci hizmeti için bir belirteç isterken gönderilen bir XML öğesi belirten bir dize.</span><span class="sxs-lookup"><span data-stu-id="2407c-118">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2407c-119">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="2407c-119">Child Elements</span></span>  
 <span data-ttu-id="2407c-120">Yok.</span><span class="sxs-lookup"><span data-stu-id="2407c-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2407c-121">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="2407c-121">Parent Elements</span></span>  
  
|<span data-ttu-id="2407c-122">Öğe</span><span class="sxs-lookup"><span data-stu-id="2407c-122">Element</span></span>|<span data-ttu-id="2407c-123">Açıklama</span><span class="sxs-lookup"><span data-stu-id="2407c-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2407c-124">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="2407c-124">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="2407c-125">Belirteç isteği parametreleri koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="2407c-125">A collection of token request parameters.</span></span> <span data-ttu-id="2407c-126">Her bir XML öğesi parametredir.</span><span class="sxs-lookup"><span data-stu-id="2407c-126">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2407c-127">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="2407c-127">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="2407c-128">Kimlik Doğrulama ile Hizmet Kimliği</span><span class="sxs-lookup"><span data-stu-id="2407c-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="2407c-129">Federasyon ve Verilen Belirteçler</span><span class="sxs-lookup"><span data-stu-id="2407c-129">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="2407c-130">Özel Bağlamalarla Güvenlik Özellikleri</span><span class="sxs-lookup"><span data-stu-id="2407c-130">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="2407c-131">Federasyon ve Verilen Belirteçler</span><span class="sxs-lookup"><span data-stu-id="2407c-131">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="2407c-132">Bağlamalar</span><span class="sxs-lookup"><span data-stu-id="2407c-132">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
