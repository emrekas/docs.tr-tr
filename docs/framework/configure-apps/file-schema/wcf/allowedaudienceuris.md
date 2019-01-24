---
title: '&lt;allowedAudienceUris&gt;'
ms.date: 03/30/2017
ms.assetid: 0f4dc73d-d95d-4193-9755-7df4cf2b8e1c
ms.openlocfilehash: 5d1c1207486be3c6bfe25e7862a5674106ec5214
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498066"
---
# <a name="ltallowedaudienceurisgt"></a><span data-ttu-id="80a8e-102">&lt;allowedAudienceUris&gt;</span><span class="sxs-lookup"><span data-stu-id="80a8e-102">&lt;allowedAudienceUris&gt;</span></span>
<span data-ttu-id="80a8e-103">Koleksiyonunu temsil eder hedef URI, <xref:System.IdentityModel.Tokens.SamlSecurityToken> güvenlik belirteci hedef olarak kullanılabilir için tarafından geçerli kabul edilmesi için bir <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> örneği.</span><span class="sxs-lookup"><span data-stu-id="80a8e-103">Represents a collection of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>  
  
 <span data-ttu-id="80a8e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="80a8e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="80a8e-105">\<davranışlar ></span><span class="sxs-lookup"><span data-stu-id="80a8e-105">\<behaviors></span></span>  
<span data-ttu-id="80a8e-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="80a8e-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="80a8e-107">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="80a8e-107">\<behavior></span></span>  
<span data-ttu-id="80a8e-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="80a8e-108">\<serviceCredentials></span></span>  
<span data-ttu-id="80a8e-109">\<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="80a8e-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="80a8e-110">\<allowedAudienceUris ></span><span class="sxs-lookup"><span data-stu-id="80a8e-110">\<allowedAudienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80a8e-111">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="80a8e-111">Syntax</span></span>  
  
```xml  
<allowedAudienceUris>
  <add allowedAudienceUri="String" />
</allowedAudienceUris>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80a8e-112">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="80a8e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="80a8e-113">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="80a8e-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80a8e-114">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="80a8e-114">Attributes</span></span>  
 <span data-ttu-id="80a8e-115">Yok.</span><span class="sxs-lookup"><span data-stu-id="80a8e-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="80a8e-116">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="80a8e-116">Child Elements</span></span>  
  
|<span data-ttu-id="80a8e-117">Öğe</span><span class="sxs-lookup"><span data-stu-id="80a8e-117">Element</span></span>|<span data-ttu-id="80a8e-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="80a8e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80a8e-119">\<Ekle ></span><span class="sxs-lookup"><span data-stu-id="80a8e-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md)|<span data-ttu-id="80a8e-120">Bir hedef URI ekler, <xref:System.IdentityModel.Tokens.SamlSecurityToken> güvenlik belirteci hedef olarak kullanılabilir için tarafından geçerli kabul edilmesi için bir <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> örneği.</span><span class="sxs-lookup"><span data-stu-id="80a8e-120">Adds a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="80a8e-121">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="80a8e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="80a8e-122">Öğe</span><span class="sxs-lookup"><span data-stu-id="80a8e-122">Element</span></span>|<span data-ttu-id="80a8e-123">Açıklama</span><span class="sxs-lookup"><span data-stu-id="80a8e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80a8e-124">\<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="80a8e-124">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="80a8e-125">Bir hizmet kimlik bilgisi olarak verilen bir belirteç belirtir.</span><span class="sxs-lookup"><span data-stu-id="80a8e-125">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80a8e-126">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="80a8e-126">Remarks</span></span>  
 <span data-ttu-id="80a8e-127">Bu koleksiyon veren bir güvenlik belirteci hizmeti (STS) kullanan bir Federasyon uygulamasında kullanması gereken <xref:System.IdentityModel.Tokens.SamlSecurityToken> güvenlik belirteçleri.</span><span class="sxs-lookup"><span data-stu-id="80a8e-127">You should use this collection in a federated application that utilizes a security token service (STS) that issues <xref:System.IdentityModel.Tokens.SamlSecurityToken> security tokens.</span></span> <span data-ttu-id="80a8e-128">Güvenlik belirteci STS verdiğinde, kendisi için güvenlik belirteci amaçlanmıştır ekleyerek Web Hizmetleri URI'sini belirtebilirsiniz bir <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> için güvenlik belirteci.</span><span class="sxs-lookup"><span data-stu-id="80a8e-128">When the STS issues the security token, it can specify the URI of the Web services for which the security token is intended by adding a <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> to the security token.</span></span> <span data-ttu-id="80a8e-129">Veren <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> alıcı Web hizmetinin aşağıdakileri yaparak bu denetimi olacağını belirleyerek verilen güvenlik belirteci için bu Web hizmetini kullandığınızdan emin olun:</span><span class="sxs-lookup"><span data-stu-id="80a8e-129">That allows the <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> for the recipient Web service to verify that the issued security token is intended for this Web service by specifying that this check should happen by doing the following:</span></span>  
  
-   <span data-ttu-id="80a8e-130">Ayarlama `audienceUriMode` özniteliği `<issuedTokenAuthentication>` için <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> veya <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span><span class="sxs-lookup"><span data-stu-id="80a8e-130">Set the `audienceUriMode` attribute of `<issuedTokenAuthentication>` to <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> or <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span></span>  
  
-   <span data-ttu-id="80a8e-131">Bu koleksiyona bir URI'leri ekleyerek geçerli URI'lerin kümesini belirtin.</span><span class="sxs-lookup"><span data-stu-id="80a8e-131">Specify the set of valid URIs, by adding the URIs to this collection.</span></span>  
  
 <span data-ttu-id="80a8e-132">Daha fazla bilgi için bkz. <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="80a8e-132">For more information, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span></span>  
  
 <span data-ttu-id="80a8e-133">Bu yapılandırma öğesi kullanma hakkında daha fazla bilgi için bkz. [nasıl yapılır: Federe bir hizmette kimlik bilgilerini yapılandırma](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="80a8e-133">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80a8e-134">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="80a8e-134">See also</span></span>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>
- [<span data-ttu-id="80a8e-135">\<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="80a8e-135">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="80a8e-136">\<Ekle ></span><span class="sxs-lookup"><span data-stu-id="80a8e-136">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md)
- [<span data-ttu-id="80a8e-137">Güvenlik Davranışları</span><span class="sxs-lookup"><span data-stu-id="80a8e-137">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="80a8e-138">Hizmet ve İstemcileri Güvenli Hale Getirme</span><span class="sxs-lookup"><span data-stu-id="80a8e-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="80a8e-139">Nasıl yapılır: Federe bir hizmette kimlik bilgilerini yapılandırma</span><span class="sxs-lookup"><span data-stu-id="80a8e-139">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
