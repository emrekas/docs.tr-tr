---
title: <issuer> , <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: 690ab14ea33ba9bef29788b2eb35f86ed945ce2b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113548"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="37d0c-102">\<veren >, \<İssuermetadata ></span><span class="sxs-lookup"><span data-stu-id="37d0c-102">\<issuer> of \<issuedTokenParameters></span></span>
<span data-ttu-id="37d0c-103">Güvenlik belirteci hizmeti (güvenlik belirteçlerini çıkartan STS) belirtir.</span><span class="sxs-lookup"><span data-stu-id="37d0c-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="37d0c-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="37d0c-104">\<system.serviceModel></span></span>  
<span data-ttu-id="37d0c-105">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="37d0c-105">\<bindings></span></span>  
<span data-ttu-id="37d0c-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="37d0c-106">\<customBinding></span></span>  
<span data-ttu-id="37d0c-107">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="37d0c-107">\<binding></span></span>  
<span data-ttu-id="37d0c-108">\<Güvenlik ></span><span class="sxs-lookup"><span data-stu-id="37d0c-108">\<security></span></span>  
<span data-ttu-id="37d0c-109">\<İssuermetadata ></span><span class="sxs-lookup"><span data-stu-id="37d0c-109">\<issuedTokenParameters></span></span>  
<span data-ttu-id="37d0c-110">\<veren ></span><span class="sxs-lookup"><span data-stu-id="37d0c-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37d0c-111">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="37d0c-111">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37d0c-112">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="37d0c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="37d0c-113">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="37d0c-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37d0c-114">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="37d0c-114">Attributes</span></span>  
  
|<span data-ttu-id="37d0c-115">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="37d0c-115">Attribute</span></span>|<span data-ttu-id="37d0c-116">Açıklama</span><span class="sxs-lookup"><span data-stu-id="37d0c-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="37d0c-117">adres</span><span class="sxs-lookup"><span data-stu-id="37d0c-117">address</span></span>|<span data-ttu-id="37d0c-118">Zorunlu dize.</span><span class="sxs-lookup"><span data-stu-id="37d0c-118">Required string.</span></span> <span data-ttu-id="37d0c-119">STS URL'si.</span><span class="sxs-lookup"><span data-stu-id="37d0c-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="37d0c-120">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="37d0c-120">Child Elements</span></span>  
  
|<span data-ttu-id="37d0c-121">Öğe</span><span class="sxs-lookup"><span data-stu-id="37d0c-121">Element</span></span>|<span data-ttu-id="37d0c-122">Açıklama</span><span class="sxs-lookup"><span data-stu-id="37d0c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37d0c-123">\<üstbilgiler ></span><span class="sxs-lookup"><span data-stu-id="37d0c-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="37d0c-124">Adres üstbilgileri Oluşturucu oluşturabilirsiniz uç noktaları koleksiyonudur.</span><span class="sxs-lookup"><span data-stu-id="37d0c-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="37d0c-125">\<Kimliği ></span><span class="sxs-lookup"><span data-stu-id="37d0c-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="37d0c-126">Verilen bir belirteç kullanırken, sunucu kimlik doğrulaması istemci etkinleştiren ayarları belirtir.</span><span class="sxs-lookup"><span data-stu-id="37d0c-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="37d0c-127">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="37d0c-127">Parent Elements</span></span>  
  
|<span data-ttu-id="37d0c-128">Öğe</span><span class="sxs-lookup"><span data-stu-id="37d0c-128">Element</span></span>|<span data-ttu-id="37d0c-129">Açıklama</span><span class="sxs-lookup"><span data-stu-id="37d0c-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37d0c-130">\<İssuermetadata ></span><span class="sxs-lookup"><span data-stu-id="37d0c-130">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="37d0c-131">Geçerli verilen belirteç belirtir.</span><span class="sxs-lookup"><span data-stu-id="37d0c-131">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="37d0c-132">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="37d0c-132">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="37d0c-133">Kimlik Doğrulama ile Hizmet Kimliği</span><span class="sxs-lookup"><span data-stu-id="37d0c-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="37d0c-134">Federasyon ve Verilen Belirteçler</span><span class="sxs-lookup"><span data-stu-id="37d0c-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="37d0c-135">Özel Bağlamalarla Güvenlik Özellikleri</span><span class="sxs-lookup"><span data-stu-id="37d0c-135">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="37d0c-136">Federasyon ve Verilen Belirteçler</span><span class="sxs-lookup"><span data-stu-id="37d0c-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="37d0c-137">Bağlamalar</span><span class="sxs-lookup"><span data-stu-id="37d0c-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="37d0c-138">Bağlamaları Genişletme</span><span class="sxs-lookup"><span data-stu-id="37d0c-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="37d0c-139">Özel Bağlamalar</span><span class="sxs-lookup"><span data-stu-id="37d0c-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="37d0c-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="37d0c-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="37d0c-141">Nasıl yapılır: SecurityBindingElement Kullanarak Özel Bağlama Oluşturma</span><span class="sxs-lookup"><span data-stu-id="37d0c-141">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="37d0c-142">Özel Bağlama Güvenliği</span><span class="sxs-lookup"><span data-stu-id="37d0c-142">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
