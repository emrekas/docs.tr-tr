---
title: '&lt;authorizationPolicies&gt; &lt;ekleme&gt;'
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: c283f99bedc16352ffca4c41c3d4628271200695
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577531"
---
# <a name="ltaddgt-of-ltauthorizationpoliciesgt"></a><span data-ttu-id="ad8a0-102">&lt;authorizationPolicies&gt; &lt;ekleme&gt;</span><span class="sxs-lookup"><span data-stu-id="ad8a0-102">&lt;add&gt; of &lt;authorizationPolicies&gt;</span></span>
<span data-ttu-id="ad8a0-103">Talep dönüştürme için bir yetkilendirme ilkesi belirtir.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-103">Specifies an authorization policy for claim transformation.</span></span>  
  
 <span data-ttu-id="ad8a0-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ad8a0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ad8a0-105">\<davranışlar ></span><span class="sxs-lookup"><span data-stu-id="ad8a0-105">\<behaviors></span></span>  
<span data-ttu-id="ad8a0-106">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="ad8a0-106">\<behavior></span></span>  
<span data-ttu-id="ad8a0-107">\<serviceAuthorization ></span><span class="sxs-lookup"><span data-stu-id="ad8a0-107">\<serviceAuthorization></span></span>  
<span data-ttu-id="ad8a0-108">\<authorizationPolicies ></span><span class="sxs-lookup"><span data-stu-id="ad8a0-108">\<authorizationPolicies></span></span>  
<span data-ttu-id="ad8a0-109">\<Ekle ></span><span class="sxs-lookup"><span data-stu-id="ad8a0-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad8a0-110">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="ad8a0-110">Syntax</span></span>  
  
```xml  
<authorizationPolicies>
  <add policyType="String" />
</authorizationPolicies>
```  
  
## <a name="type"></a><span data-ttu-id="ad8a0-111">Tür</span><span class="sxs-lookup"><span data-stu-id="ad8a0-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad8a0-112">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="ad8a0-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ad8a0-113">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad8a0-114">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="ad8a0-114">Attributes</span></span>  
  
|<span data-ttu-id="ad8a0-115">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="ad8a0-115">Attribute</span></span>|<span data-ttu-id="ad8a0-116">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ad8a0-116">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="ad8a0-117">Gerekli dize özniteliği.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-117">A required String attribute.</span></span><br /><br /> <span data-ttu-id="ad8a0-118">Windows Communication Foundation (WCF) erişim denetimi modeli, sağlama türü olarak yetkilendirme ilkeleri kümesini destekler.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-118">The Windows Communication Foundation (WCF) access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="ad8a0-119">Bu öznitelik, bir giriş talep kümesini talep başka bir dizi dönüşümünü sağlayan bir yetkilendirme ilkesi belirtir.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-119">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="ad8a0-120">Erişim denetimi verilen veya reddedilen oturum tabanlı.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-120">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ad8a0-121">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="ad8a0-121">Child Elements</span></span>  
 <span data-ttu-id="ad8a0-122">Yok.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ad8a0-123">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="ad8a0-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ad8a0-124">Öğe</span><span class="sxs-lookup"><span data-stu-id="ad8a0-124">Element</span></span>|<span data-ttu-id="ad8a0-125">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ad8a0-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ad8a0-126">\<authorizationPolicies ></span><span class="sxs-lookup"><span data-stu-id="ad8a0-126">\<authorizationPolicies></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authorizationpolicies.md)|<span data-ttu-id="ad8a0-127">Yetkilendirme İlkesi türü koleksiyonu belirtir.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-127">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad8a0-128">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ad8a0-128">Remarks</span></span>  
 <span data-ttu-id="ad8a0-129">Gereken tek bir her yetkilendirme ilkesi içeren `policyType` dize özniteliği.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-129">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="ad8a0-130">Öznitelik, bir giriş talep kümesini talep başka bir dizi dönüşümünü sağlayan bir yetkilendirme ilkesi belirtir.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-130">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="ad8a0-131">Erişim denetimi verilen veya reddedilen oturum tabanlı.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-131">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="ad8a0-132">Bir yetkilendirme ilkesi birlikte nasıl çalıştığı hakkında daha fazla bilgi için bkz. <xref:System.IdentityModel.Policy.IAuthorizationPolicy> ve [yetkilendirme ilkesi](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="ad8a0-132">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad8a0-133">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-133">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="ad8a0-134">Hizmet İşlemlerine Erişimi Yetkilendirme</span><span class="sxs-lookup"><span data-stu-id="ad8a0-134">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="ad8a0-135">Nasıl yapılır: Bir hizmet için özel Yetkilendirme Yöneticisi oluşturma</span><span class="sxs-lookup"><span data-stu-id="ad8a0-135">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="ad8a0-136">\<Ekle ></span><span class="sxs-lookup"><span data-stu-id="ad8a0-136">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)
- [<span data-ttu-id="ad8a0-137">Yetkilendirme İlkesi</span><span class="sxs-lookup"><span data-stu-id="ad8a0-137">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)
