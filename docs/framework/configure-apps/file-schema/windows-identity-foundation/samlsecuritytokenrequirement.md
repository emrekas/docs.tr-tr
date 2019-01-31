---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: e1b8acd48ee185b3c6c50f70321bb9ca66e8e02b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55284628"
---
# <a name="samlsecuritytokenrequirement"></a><span data-ttu-id="ef547-101">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="ef547-101">\<samlSecurityTokenRequirement></span></span>
<span data-ttu-id="ef547-102">İçin yapılandırma sağlar <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> sınıfı <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> sınıfı veya türetilmiş bir sınıf ya da bu sınıflarının biri.</span><span class="sxs-lookup"><span data-stu-id="ef547-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="ef547-103">Tarafından temsil edilen <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="ef547-103">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
 <span data-ttu-id="ef547-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="ef547-104">\<system.identityModel></span></span>  
<span data-ttu-id="ef547-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="ef547-105">\<identityConfiguration></span></span>  
<span data-ttu-id="ef547-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="ef547-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="ef547-107">\<Ekle ></span><span class="sxs-lookup"><span data-stu-id="ef547-107">\<add></span></span>  
<span data-ttu-id="ef547-108">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="ef547-108">\<samlSecurityTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef547-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="ef547-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement   
            issuerCertificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
            issuerCertificateRevocationMode="NoCheck||Offline||Online"  
            issuerCertificateTrustedStoreLocation="CurrentLocation||LocalMachine"  
            issuerCertificateValidator="Namespace.Class Assembly"  
            mapToWindows=xs:boolean  
          <nameClaimType value=xs:string />  
          <roleClaimType value=xs:string />  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef547-110">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="ef547-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ef547-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="ef547-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef547-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="ef547-112">Attributes</span></span>  
  
|<span data-ttu-id="ef547-113">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="ef547-113">Attribute</span></span>|<span data-ttu-id="ef547-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ef547-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ef547-115">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="ef547-115">mapToWindows</span></span>|<span data-ttu-id="ef547-116">Belirteci işleyicisi doğrulama belirteci için bir Windows hesabı gelen UPN Talebi kullanarak eşlemelisiniz olup olmadığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="ef547-116">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="ef547-117">Varsayılan değer "false" dir.</span><span class="sxs-lookup"><span data-stu-id="ef547-117">The default is "false".</span></span>|  
|<span data-ttu-id="ef547-118">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="ef547-118">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="ef547-119">Bir <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> X.509 sertifikası için İptal modu belirten bir değer.</span><span class="sxs-lookup"><span data-stu-id="ef547-119">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="ef547-120">Varsayılan değer "Çevrimiçi" olur.</span><span class="sxs-lookup"><span data-stu-id="ef547-120">The default value is "Online".</span></span>|  
|<span data-ttu-id="ef547-121">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="ef547-121">issuerCertificateValidationMode</span></span>|<span data-ttu-id="ef547-122">Bir <xref:System.ServiceModel.Security.X509CertificateValidationMode> X.509 sertifikası için kullanılacak doğrulama modu belirten bir değer.</span><span class="sxs-lookup"><span data-stu-id="ef547-122">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="ef547-123">"PeerOrChainTrust" varsayılan değerdir.</span><span class="sxs-lookup"><span data-stu-id="ef547-123">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="ef547-124">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="ef547-124">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="ef547-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> X.509 Sertifika deposunun belirten bir değer.</span><span class="sxs-lookup"><span data-stu-id="ef547-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="ef547-126">"LocalMachine" varsayılan değerdir.</span><span class="sxs-lookup"><span data-stu-id="ef547-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="ef547-127">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="ef547-127">issuerCertificateValidator</span></span>|<span data-ttu-id="ef547-128">Öğesinden türetilen özel bir tür <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="ef547-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="ef547-129">Varsa `issuerCertificateValidationMode` özniteliktir "Özel", bu türden veren sertifika doğrulaması için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="ef547-129">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ef547-130">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="ef547-130">Child Elements</span></span>  
  
|<span data-ttu-id="ef547-131">Öğe</span><span class="sxs-lookup"><span data-stu-id="ef547-131">Element</span></span>|<span data-ttu-id="ef547-132">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ef547-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef547-133">\<nameClaimType ></span><span class="sxs-lookup"><span data-stu-id="ef547-133">\<nameClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/nameclaimtype.md)|<span data-ttu-id="ef547-134">Talep türünü belirleyen ayarlar <xref:System.Security.Principal.IIdentity.Name%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="ef547-134">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="ef547-135">\<roleClaimType ></span><span class="sxs-lookup"><span data-stu-id="ef547-135">\<roleClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/roleclaimtype.md)|<span data-ttu-id="ef547-136">Rol türü talep koleksiyonunda tanımlayan talep türünü belirtir <xref:System.Security.Claims.ClaimsIdentity> tarafından döndürülen nesne <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> belirteci işleyicisi yöntemi.</span><span class="sxs-lookup"><span data-stu-id="ef547-136">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ef547-137">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="ef547-137">Parent Elements</span></span>  
  
|<span data-ttu-id="ef547-138">Öğe</span><span class="sxs-lookup"><span data-stu-id="ef547-138">Element</span></span>|<span data-ttu-id="ef547-139">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ef547-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef547-140">\<Ekle ></span><span class="sxs-lookup"><span data-stu-id="ef547-140">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="ef547-141">Belirtilen güvenlik belirteci işleyicisi belirteci işleyicisi koleksiyona ekler.</span><span class="sxs-lookup"><span data-stu-id="ef547-141">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef547-142">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ef547-142">Remarks</span></span>  
 <span data-ttu-id="ef547-143">`<samlSecurityTokenRequirement>` Öğesi tarafından temsil edilen <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> sınıfı nesne modelinde ve yapılandırmak için kullanılan `SamlSecurityTokenRequirement` özelliği bir <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> veya <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="ef547-143">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef547-144">Örnek</span><span class="sxs-lookup"><span data-stu-id="ef547-144">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement issuerCertificateValidationMode="PeerOrChainTrust"  
                                  issuerCertificateRevocationMode="Online"  
                                  issuerCertificateTrustedStoreLocation="LocalMachine"  
                                  mapToWindows="false">  
  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```
