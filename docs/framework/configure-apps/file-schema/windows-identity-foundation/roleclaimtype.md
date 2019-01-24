---
title: '&lt;RoleClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 6114a95f3942c367849785ce981858f276c0b8fc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54599952"
---
# <a name="ltroleclaimtypegt"></a><span data-ttu-id="29ff4-102">&lt;RoleClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="29ff4-102">&lt;roleClaimType&gt;</span></span>
<span data-ttu-id="29ff4-103">Rol türü talep koleksiyonunda tanımlayan talep türünü belirtir <xref:System.Security.Claims.ClaimsIdentity> tarafından döndürülen nesne <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> belirteci işleyicisi yöntemi.</span><span class="sxs-lookup"><span data-stu-id="29ff4-103">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="29ff4-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="29ff4-104">\<system.identityModel></span></span>  
<span data-ttu-id="29ff4-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="29ff4-105">\<identityConfiguration></span></span>  
<span data-ttu-id="29ff4-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="29ff4-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="29ff4-107">\<Ekle ></span><span class="sxs-lookup"><span data-stu-id="29ff4-107">\<add></span></span>  
<span data-ttu-id="29ff4-108">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="29ff4-108">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="29ff4-109">\<roleClaimType ></span><span class="sxs-lookup"><span data-stu-id="29ff4-109">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29ff4-110">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="29ff4-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <roleClaimType value=xs:string>  
          </roleClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29ff4-111">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="29ff4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="29ff4-112">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="29ff4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29ff4-113">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="29ff4-113">Attributes</span></span>  
  
|<span data-ttu-id="29ff4-114">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="29ff4-114">Attribute</span></span>|<span data-ttu-id="29ff4-115">Açıklama</span><span class="sxs-lookup"><span data-stu-id="29ff4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="29ff4-116">value</span><span class="sxs-lookup"><span data-stu-id="29ff4-116">value</span></span>|<span data-ttu-id="29ff4-117">Talep türü rol talep türü için kullanılacak talep temsil eden URI belirten bir dize.</span><span class="sxs-lookup"><span data-stu-id="29ff4-117">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="29ff4-118">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="29ff4-118">Child Elements</span></span>  
 <span data-ttu-id="29ff4-119">Hiçbiri</span><span class="sxs-lookup"><span data-stu-id="29ff4-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="29ff4-120">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="29ff4-120">Parent Elements</span></span>  
  
|<span data-ttu-id="29ff4-121">Öğe</span><span class="sxs-lookup"><span data-stu-id="29ff4-121">Element</span></span>|<span data-ttu-id="29ff4-122">Açıklama</span><span class="sxs-lookup"><span data-stu-id="29ff4-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="29ff4-123">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="29ff4-123">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="29ff4-124">İçin yapılandırma sağlar <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> sınıfı <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> sınıfı veya türetilmiş bir sınıf ya da bu sınıflarının biri.</span><span class="sxs-lookup"><span data-stu-id="29ff4-124">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29ff4-125">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="29ff4-125">Remarks</span></span>  
 <span data-ttu-id="29ff4-126">`<roleClaimType>` Öğe kümeleri <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> özelliği, bir <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> nesne yapılandırmadan başlatılır.</span><span class="sxs-lookup"><span data-stu-id="29ff4-126">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29ff4-127">Örnek</span><span class="sxs-lookup"><span data-stu-id="29ff4-127">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="29ff4-128">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="29ff4-128">See also</span></span>
- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
