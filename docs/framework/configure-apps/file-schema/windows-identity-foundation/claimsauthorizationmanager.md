---
title: <claimsAuthorizationManager>
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
ms.openlocfilehash: 59d47eda97e97629408ece12a1d1dfbe804feb3e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667320"
---
# <a name="claimsauthorizationmanager"></a><span data-ttu-id="53f7a-101">\<claimsAuthorizationManager ></span><span class="sxs-lookup"><span data-stu-id="53f7a-101">\<claimsAuthorizationManager></span></span>
<span data-ttu-id="53f7a-102">Bir gelen talep için talep Yetkilendirme Yöneticisi kaydeder.</span><span class="sxs-lookup"><span data-stu-id="53f7a-102">Registers a claims authorization manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="53f7a-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="53f7a-103">\<system.identityModel></span></span>  
<span data-ttu-id="53f7a-104">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="53f7a-104">\<identityConfiguration></span></span>  
<span data-ttu-id="53f7a-105">\<claimsAuthorizationManager ></span><span class="sxs-lookup"><span data-stu-id="53f7a-105">\<claimsAuthorizationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53f7a-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="53f7a-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53f7a-107">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="53f7a-107">Attributes and Elements</span></span>  
 <span data-ttu-id="53f7a-108">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="53f7a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53f7a-109">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="53f7a-109">Attributes</span></span>  
  
|<span data-ttu-id="53f7a-110">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="53f7a-110">Attribute</span></span>|<span data-ttu-id="53f7a-111">Açıklama</span><span class="sxs-lookup"><span data-stu-id="53f7a-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="53f7a-112">türü</span><span class="sxs-lookup"><span data-stu-id="53f7a-112">type</span></span>|<span data-ttu-id="53f7a-113">Öğesinden türetilen özel bir tür <xref:System.Security.Claims.ClaimsAuthorizationManager> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="53f7a-113">A custom type that derives from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class.</span></span> <span data-ttu-id="53f7a-114">Belirtme hakkında daha fazla bilgi için `type` özniteliği için bkz: [özel tür başvurularını](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="53f7a-114">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53f7a-115">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="53f7a-115">Child Elements</span></span>  
 <span data-ttu-id="53f7a-116">Yoksa hiçbir `type` özniteliği veya `type` başvuruları öznitelik <xref:System.Security.Claims.ClaimsAuthenticationManager> sınıfı `<claimsAuthorizationManager>` öğenin alt öğeleri almaz; ancak, türetilmiş sınıflar <xref:System.Security.Claims.ClaimsAuthorizationManager> alt yapılandırma öğeleri tanımlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="53f7a-116">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthorizationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthorizationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="53f7a-117">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="53f7a-117">Parent Elements</span></span>  
  
|<span data-ttu-id="53f7a-118">Öğe</span><span class="sxs-lookup"><span data-stu-id="53f7a-118">Element</span></span>|<span data-ttu-id="53f7a-119">Açıklama</span><span class="sxs-lookup"><span data-stu-id="53f7a-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53f7a-120">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="53f7a-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="53f7a-121">Hizmet düzeyi kimlik ayarlarını belirtir.</span><span class="sxs-lookup"><span data-stu-id="53f7a-121">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53f7a-122">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="53f7a-122">Remarks</span></span>  
 <span data-ttu-id="53f7a-123">Sağlanan varsayılan davranışı <xref:System.Security.Claims.ClaimsAuthorizationManager> sınıfı, gelen talepler her zaman yetkilendirir.</span><span class="sxs-lookup"><span data-stu-id="53f7a-123">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthorizationManager> class always authorizes the incoming claims.</span></span> <span data-ttu-id="53f7a-124">Hayır ise `type` özniteliği veya `type` özniteliği belirtir <xref:System.Security.Claims.ClaimsAuthorizationManager> sınıfı `<claimsAuthorizationManager>` öğenin alt öğeleri almaz.</span><span class="sxs-lookup"><span data-stu-id="53f7a-124">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthorizationManager> class, the `<claimsAuthorizationManager>` element does not take child elements.</span></span> <span data-ttu-id="53f7a-125">Belirtebileceğiniz `type` sınıfından türetilen bir tür kaydetmek için öznitelik <xref:System.Security.Claims.ClaimsAuthorizationManager> özel davranışı uygulamak sınıfı.</span><span class="sxs-lookup"><span data-stu-id="53f7a-125">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class to implement custom behavior.</span></span> <span data-ttu-id="53f7a-126">Türetilen sınıflar, alt öğelerinin konfigürasyonuyla destekleyebilir `<claimsAuthorizationManager>` kılarak öğesi <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> bu öğelerini işlemek için yöntemi.</span><span class="sxs-lookup"><span data-stu-id="53f7a-126">Derived classes can support configuration through child elements of the `<claimsAuthorizationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="53f7a-127">Sınıf Tasarımcısı kadar alt öğeleri için tanımlanan şema var.</span><span class="sxs-lookup"><span data-stu-id="53f7a-127">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="53f7a-128">Kullanırken <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> veya <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> sınıfı tarafından başvurulan kimlik yapılandırması kodunuzda beyana dayalı erişim denetimi sağlamak için `<federationConfiguration>` öğesi, talep Yetkilendirme Yöneticisi'ni ve yapmak için kullanılan ilke yapılandırır yetkilendirme kararları.</span><span class="sxs-lookup"><span data-stu-id="53f7a-128">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="53f7a-129">Bu durum bile pasif Web senaryoları, örneğin Windows Communication Foundation (WCF) uygulamaları veya Web tabanlı yer almayan bir uygulama olmayan senaryolarda geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="53f7a-129">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="53f7a-130">Uygulama Pasif bir Web uygulaması değilse `<claimsAuthorizationManager>` öğesini (ve alt ilke öğelerine, varsa) başvurulan kimlik yapılandırmasını uygulanan yalnızca ayarlarıdır.</span><span class="sxs-lookup"><span data-stu-id="53f7a-130">If the application is not a passive Web application, the `<claimsAuthorizationManager>` element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="53f7a-131">Diğer tüm ayarları göz ardı edilir.</span><span class="sxs-lookup"><span data-stu-id="53f7a-131">All other settings are ignored.</span></span> <span data-ttu-id="53f7a-132">Daha fazla bilgi için [ \<Federationconfiguration'a >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) öğesi.</span><span class="sxs-lookup"><span data-stu-id="53f7a-132">For more information, see the [\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="53f7a-133">Bu öğe ayarlar <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> özelliği.</span><span class="sxs-lookup"><span data-stu-id="53f7a-133">This element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53f7a-134">Örnek</span><span class="sxs-lookup"><span data-stu-id="53f7a-134">Example</span></span>  
 <span data-ttu-id="53f7a-135">Aşağıdaki XML kaynak Eylem çiftleri oluşan ilke her biri kaynak eylemi gerçekleştirmek için bir istek sahibine sahip olması gerekir talepleri Boole birleşimlerini belirtir uygulayan manager talep yetkilendirme yapılandırmasını gösterir.</span><span class="sxs-lookup"><span data-stu-id="53f7a-135">The following XML shows the configuration for a claims authorization manager that implements policy composed of resource-action pairs each of which specifies boolean combinations of the claims that a requestor must possess to perform the action on the resource.</span></span> <span data-ttu-id="53f7a-136">Bu ilke kullanma yeteneği talep Yetkilendirme Yöneticisi uygulayan kod bulunabilir `ClaimsBasedAuthorization` örnek.</span><span class="sxs-lookup"><span data-stu-id="53f7a-136">The code that implements the claims authorization manager capable of using this policy can be found in the `ClaimsBasedAuthorization` sample.</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration>  
      <claimsAuthorizationManager type="ClaimsAuthorizationLibrary.MyClaimsAuthorizationManager, ClaimsAuthorizationLibrary">  
        <policy resource="http://localhost:28491/Developers.aspx" action="GET">  
          <or>  
            <claim claimType="http://schemas.microsoft.com/ws/2008/06/identity/claims/role" claimValue="developer" />  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
          </or>  
        </policy>  
        <policy resource="http://localhost:28491/Administrators.aspx" action="GET">  
          <and>  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
            <claim claimType="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/country" claimValue="USA" />  
          </and>  
        </policy>  
        <policy resource="http://localhost:28491/Default.aspx" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/Claims.aspx" action="GET">  
        </policy>  
      </claimsAuthorizationManager>  
    <identityConfiguration>  
<system.identityModel>  
```
