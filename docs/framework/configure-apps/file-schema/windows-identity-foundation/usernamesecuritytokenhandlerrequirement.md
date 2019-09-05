---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: 5863c01e97e7f5fb6fe07c43174c0d6cb7a0a25d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251741"
---
# <a name="usernamesecuritytokenhandlerrequirement"></a><span data-ttu-id="12978-101">\<userNameSecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="12978-101">\<userNameSecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="12978-102"><xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> Sınıf veya türetilmiş sınıflar için yapılandırma sağlar.</span><span class="sxs-lookup"><span data-stu-id="12978-102">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="12978-103">[ **\<Yapılandırma >** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="12978-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="12978-104">&nbsp;&nbsp;[ **\<System. IdentityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="12978-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="12978-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<IdentityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="12978-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="12978-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="12978-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="12978-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> Ekle**](add.md)</span><span class="sxs-lookup"><span data-stu-id="12978-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="12978-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<userNameSecurityTokenHandlerRequirement >**</span><span class="sxs-lookup"><span data-stu-id="12978-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameSecurityTokenHandlerRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12978-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="12978-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
        <userNameSecurityTokenHandlerRequirement membershipProviderName=xs:string >  
        </userNameSecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12978-110">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="12978-110">Attributes and Elements</span></span>  
 <span data-ttu-id="12978-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="12978-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12978-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="12978-112">Attributes</span></span>  
  
|<span data-ttu-id="12978-113">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="12978-113">Attribute</span></span>|<span data-ttu-id="12978-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="12978-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="12978-115">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="12978-115">membershipProviderName</span></span>|<span data-ttu-id="12978-116"><xref:System.Web.Security.MembershipProvider> Güvenlik belirteci işleyicisi tarafından kullanılması gereken öğesini belirtir.</span><span class="sxs-lookup"><span data-stu-id="12978-116">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="12978-117">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="12978-117">Child Elements</span></span>  
 <span data-ttu-id="12978-118">Yok.</span><span class="sxs-lookup"><span data-stu-id="12978-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="12978-119">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="12978-119">Parent Elements</span></span>  
  
|<span data-ttu-id="12978-120">Öğe</span><span class="sxs-lookup"><span data-stu-id="12978-120">Element</span></span>|<span data-ttu-id="12978-121">Açıklama</span><span class="sxs-lookup"><span data-stu-id="12978-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12978-122">\<> Ekle</span><span class="sxs-lookup"><span data-stu-id="12978-122">\<add></span></span>](add.md)|<span data-ttu-id="12978-123">Belirtilen güvenlik belirteci işleyicisini belirteç işleyici koleksiyonuna ekler.</span><span class="sxs-lookup"><span data-stu-id="12978-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12978-124">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="12978-124">Remarks</span></span>  
 <span data-ttu-id="12978-125"><xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> Bir `<userNameSecurityTokenHandlerRequirement>` nesne<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> yapılandırmadan başlatıldığında öğesi özelliği ayarlar.</span><span class="sxs-lookup"><span data-stu-id="12978-125">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12978-126">Örnek</span><span class="sxs-lookup"><span data-stu-id="12978-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
