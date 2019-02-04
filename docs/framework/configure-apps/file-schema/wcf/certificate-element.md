---
title: <certificate> Öğesi
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: f0cec2ad0e7747ddbc0ef566b4e8cbc7f8795b02
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2019
ms.locfileid: "55675393"
---
# <a name="certificate-element"></a><span data-ttu-id="cb7b9-102">\<Sertifika > öğesi</span><span class="sxs-lookup"><span data-stu-id="cb7b9-102">\<certificate> Element</span></span>
<span data-ttu-id="cb7b9-103">İmzalama ve eşler arası istemcileri için iletileri şifrelemek için bir X.509 sertifikasını belirtir.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="cb7b9-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cb7b9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="cb7b9-105">\<davranışlar ></span><span class="sxs-lookup"><span data-stu-id="cb7b9-105">\<behaviors></span></span>  
<span data-ttu-id="cb7b9-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="cb7b9-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="cb7b9-107">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="cb7b9-107">\<behavior></span></span>  
<span data-ttu-id="cb7b9-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="cb7b9-108">\<clientCredentials></span></span>  
<span data-ttu-id="cb7b9-109">\<Eş ></span><span class="sxs-lookup"><span data-stu-id="cb7b9-109">\<peer></span></span>  
<span data-ttu-id="cb7b9-110">\<Sertifika ></span><span class="sxs-lookup"><span data-stu-id="cb7b9-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb7b9-111">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="cb7b9-111">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb7b9-112">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="cb7b9-112">Attributes and Elements</span></span>  
 <span data-ttu-id="cb7b9-113">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb7b9-114">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="cb7b9-114">Attributes</span></span>  
  
|<span data-ttu-id="cb7b9-115">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="cb7b9-115">Attribute</span></span>|<span data-ttu-id="cb7b9-116">Açıklama</span><span class="sxs-lookup"><span data-stu-id="cb7b9-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="cb7b9-117">X.509 sertifika deposunda aranacak değeri içeren bir dize.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="cb7b9-118">Özniteliğinde bulunan türü belirtilen gereksinimleri karşılaması gerekir `x509FindType`.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-118">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="cb7b9-119">Varsayılan değer boş bir dizedir.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="cb7b9-120">Eşin sertifikasını doğrulamak için istemcinin kullandığı X.509 Sertifika deposunun konumunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-120">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="cb7b9-121">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="cb7b9-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="cb7b9-122">-LocalMachine: yerel makineye atanmış sertifika deposu.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="cb7b9-123">-CurrentUser: geçerli kullanıcıya atanmış sertifika deposu.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="cb7b9-124">LocalMachine varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="cb7b9-125">Açılacak X.509 Sertifika deposunun adını belirtir.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="cb7b9-126">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="cb7b9-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="cb7b9-127">-Adres Defteri: Diğer kullanıcılar için sertifika deposu.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="cb7b9-128">-AuthRoot: Üçüncü taraf sertifika yetkilileri (CA'lar) için sertifika deposu.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-128">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="cb7b9-129">-CertificateAuthority: Ara Sertifika yetkilileri (CA'lar) için sertifika deposu.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-129">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="cb7b9-130">-İzin verilmedi: İptal edilen sertifikalar için sertifika deposu.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="cb7b9-131">-My: Kişisel Sertifikalar için sertifika deposu.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="cb7b9-132">-Kök: Güvenilen kök sertifika yetkilileri (CA'lar) için sertifika deposu.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-132">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="cb7b9-133">-TrustedPeople: Sertifika deposu-doğrudan güvenilen kişiler ve kaynaklar.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-133">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="cb7b9-134">-TrustedPublisher: Doğrudan Güvenilen Yayımcılar sertifika deposu.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-134">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="cb7b9-135">Varsayılan değer benim.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="cb7b9-136">Yürütülecek X.509 arama türünü tanımlar.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="cb7b9-137">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="cb7b9-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="cb7b9-138">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="cb7b9-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="cb7b9-139">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="cb7b9-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="cb7b9-140">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="cb7b9-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="cb7b9-141">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="cb7b9-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="cb7b9-142">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="cb7b9-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="cb7b9-143">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="cb7b9-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="cb7b9-144">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="cb7b9-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="cb7b9-145">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="cb7b9-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="cb7b9-146">-   FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="cb7b9-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="cb7b9-147">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="cb7b9-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="cb7b9-148">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="cb7b9-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="cb7b9-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="cb7b9-149">-   FindByExtension</span></span><br /><span data-ttu-id="cb7b9-150">-   FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="cb7b9-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="cb7b9-151">-FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="cb7b9-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="cb7b9-152">Bulunan tür `findValue` öznitelik belirtilen gereksinimleri karşılaması gerekir `X509FindType`.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="cb7b9-153">FindBySubjectDistinguishedName varsayılan değerdir.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cb7b9-154">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="cb7b9-154">Child Elements</span></span>  
 <span data-ttu-id="cb7b9-155">Yok.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cb7b9-156">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="cb7b9-156">Parent Elements</span></span>  
  
|<span data-ttu-id="cb7b9-157">Öğe</span><span class="sxs-lookup"><span data-stu-id="cb7b9-157">Element</span></span>|<span data-ttu-id="cb7b9-158">Açıklama</span><span class="sxs-lookup"><span data-stu-id="cb7b9-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cb7b9-159">\<Eş ></span><span class="sxs-lookup"><span data-stu-id="cb7b9-159">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="cb7b9-160">Eşler arası istemcilerin kimlik doğrulaması için kullanılan kimlik bilgilerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-160">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb7b9-161">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="cb7b9-161">Remarks</span></span>  
 <span data-ttu-id="cb7b9-162">Bu yapılandırma öğesi içinde Eş Ağ Komşuları kimlik doğrulaması için kullanılan bir X509Certificate2 örneği içerir.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-162">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="cb7b9-163">Eşler arası programlama hakkında daha fazla bilgi için bkz. [eşler arası ağ](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="cb7b9-163">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb7b9-164">Örnek</span><span class="sxs-lookup"><span data-stu-id="cb7b9-164">Example</span></span>  
 <span data-ttu-id="cb7b9-165">Aşağıdaki kod, bir eşler arası senaryosunda kullanılan sertifikanın nasıl belirtir.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-165">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="cb7b9-166">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="cb7b9-166">See also</span></span>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [<span data-ttu-id="cb7b9-167">Sertifikalarla Çalışma</span><span class="sxs-lookup"><span data-stu-id="cb7b9-167">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="cb7b9-168">Eşler Arası Ağ</span><span class="sxs-lookup"><span data-stu-id="cb7b9-168">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="cb7b9-169">[Eş kanal ileti kimlik doğrulaması](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="cb7b9-169">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="cb7b9-170">[Eş kanal özel kimlik doğrulama](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="cb7b9-170">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="cb7b9-171">Eş Kanalı Uygulamalarını Güvenli Hale Getirme</span><span class="sxs-lookup"><span data-stu-id="cb7b9-171">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
