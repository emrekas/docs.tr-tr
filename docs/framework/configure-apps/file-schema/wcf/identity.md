---
title: <identity>
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: 262ac9be6d5ce6466cf9aff33c0c2791c0e149dd
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/23/2019
ms.locfileid: "69988378"
---
# <a name="identity"></a><span data-ttu-id="0bd5a-101">\<kimlik ></span><span class="sxs-lookup"><span data-stu-id="0bd5a-101">\<identity></span></span>
<span data-ttu-id="0bd5a-102">Identity öğesi, bir istemci geliştiricisinin, hizmetin beklenen kimliği olan tasarım zamanında belirtmesini sağlar.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-102">The identity element allows a client developer to specify at design time the expected identity of the service.</span></span> <span data-ttu-id="0bd5a-103">İstemci ve hizmet arasındaki el sıkışma işleminde, Windows Communication Foundation (WCF) altyapısı, beklenen hizmetin kimliğinin bu öğenin değerleriyle eşleştiğinden emin olur ve bu nedenle kimlik doğrulaması yapılabilir.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-103">In the handshake process between the client and service, the Windows Communication Foundation (WCF) infrastructure will ensure that the identity of the expected service matches the values of this element, and thus can be authenticated.</span></span> <span data-ttu-id="0bd5a-104">Daha fazla bilgi için bkz. [hizmet kimliği ve kimlik doğrulaması](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="0bd5a-104">For more information, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="0bd5a-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0bd5a-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="0bd5a-106">\<İstemci ></span><span class="sxs-lookup"><span data-stu-id="0bd5a-106">\<client></span></span>  
<span data-ttu-id="0bd5a-107">\<uç nokta ></span><span class="sxs-lookup"><span data-stu-id="0bd5a-107">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bd5a-108">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="0bd5a-108">Syntax</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="String" />
  <certificateReference findValue="String"
                        isChainIncluded="Boolean"
                        storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                        storeLocation="LocalMachine/CurrentUser"
                        X509FindType="Enumeration" />
  <dns value="String" />
  <rsa value="String" />
  <servicePrincipalName value="String" />
  <userPrincipalName value="String" />
</identity>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0bd5a-109">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="0bd5a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0bd5a-110">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0bd5a-111">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="0bd5a-111">Attributes</span></span>  
 <span data-ttu-id="0bd5a-112">Yok.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0bd5a-113">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="0bd5a-113">Child Elements</span></span>  
  
|<span data-ttu-id="0bd5a-114">Öğe</span><span class="sxs-lookup"><span data-stu-id="0bd5a-114">Element</span></span>|<span data-ttu-id="0bd5a-115">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0bd5a-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0bd5a-116">sertifika</span><span class="sxs-lookup"><span data-stu-id="0bd5a-116">certificate</span></span>|<span data-ttu-id="0bd5a-117">X. 509.440 sertifikasının ayarlarını belirtir.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-117">Specifies settings of an X.509 certificate.</span></span> <span data-ttu-id="0bd5a-118">Bu öğe türündedir <xref:System.ServiceModel.Configuration.CertificateElement>.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-118">This element is of type <xref:System.ServiceModel.Configuration.CertificateElement>.</span></span> <span data-ttu-id="0bd5a-119">Bu, bu sertifika `encodedValue` tarafından kodlanan değeri belirten String olan bir özniteliği içerir.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-119">It contains an attribute `encodedValue` that is a string, which specifies the value encoded by this certificate.</span></span>|  
|<span data-ttu-id="0bd5a-120">certificateReference</span><span class="sxs-lookup"><span data-stu-id="0bd5a-120">certificateReference</span></span>|<span data-ttu-id="0bd5a-121">X. 509.440 sertifika doğrulamasının ayarlarını belirtir.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-121">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="0bd5a-122">Bu öğe türündedir <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-122">This element is of type <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span></span>|  
|<span data-ttu-id="0bd5a-123">dns</span><span class="sxs-lookup"><span data-stu-id="0bd5a-123">dns</span></span>|<span data-ttu-id="0bd5a-124">Bir hizmetin kimliğini doğrulamak için kullanılan X. 509.440 sertifikasının DNS 'sini belirtir.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-124">Specifies the DNS of an X.509 certificate used to authenticate a service.</span></span> <span data-ttu-id="0bd5a-125">Bu öğe, bir dize `value` olan ve gerçek kimliği içeren bir özniteliği içerir.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-125">This element contains an attribute `value` that is a string, and contains the actual identity.</span></span>|  
|<span data-ttu-id="0bd5a-126">rsa</span><span class="sxs-lookup"><span data-stu-id="0bd5a-126">rsa</span></span>|<span data-ttu-id="0bd5a-127">Bir istemciye bir hizmetin kimliğini doğrulamak için kullanılan X. 509.440 sertifikasının RSA alanının değerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-127">Specifies the value of the RSA field of an X.509 certificate used to authenticate a service to a client.</span></span> <span data-ttu-id="0bd5a-128">Bu öğe, bir dize `value` olan ve gerçek kimliği içeren bir özniteliği içerir</span><span class="sxs-lookup"><span data-stu-id="0bd5a-128">This element contains an attribute `value` that is a string, and contains the actual identity</span></span>|  
|<span data-ttu-id="0bd5a-129">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="0bd5a-129">servicePrincipalName</span></span>|<span data-ttu-id="0bd5a-130">Bir hizmetin bir örneğini benzersiz bir şekilde tanımlamak için bir istemci tarafından kullanılan asıl ad olan bir sunucu asıl adı (SPN) kimliğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-130">Specifies a server principal name (SPN) identity, which is the principal name used by a client to uniquely identify an instance of a service.</span></span> <span data-ttu-id="0bd5a-131">Bu öğe, bir dize `value` olan ve asıl asıl adı içeren bir özniteliği içerir.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-131">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="0bd5a-132">Bu öğe türündedir <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-132">This element is of type <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span></span>|  
|<span data-ttu-id="0bd5a-133">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="0bd5a-133">userPrincipalName</span></span>|<span data-ttu-id="0bd5a-134">Bir ağdaki kullanıcının oturum açma adı türü olan bir Kullanıcı asıl adı (UPN) kimliğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-134">Specifies a user principal name (UPN) identity, which is the logon name type of a user on a network.</span></span> <span data-ttu-id="0bd5a-135">Kullanıcı asıl adı, Active Directory '\@de kullanılan Kullanıcı nesne adından ve ardından genellikle etki alanı adı sistemi üst etki alanına sahip.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-135">The user principal name consists of the user object name used in Active Directory, followed by the at symbol (\@) and then, typically, the Domain Name System parent domain.</span></span> <span data-ttu-id="0bd5a-136">Örneğin, Fabrikam.com etki alanı ağacındaki Jeff, Kullanıcı asıl adına [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com)sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-136">For example, Jeff in the Fabrikam.com domain tree might have the user principal name [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).</span></span>  <span data-ttu-id="0bd5a-137">Bu öğe, bir dize `value` olan ve asıl asıl adı içeren bir özniteliği içerir.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-137">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="0bd5a-138">Bu öğe türündedir <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-138">This element is of type <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0bd5a-139">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="0bd5a-139">Parent Elements</span></span>  
  
|<span data-ttu-id="0bd5a-140">Öğe</span><span class="sxs-lookup"><span data-stu-id="0bd5a-140">Element</span></span>|<span data-ttu-id="0bd5a-141">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0bd5a-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0bd5a-142">\<Özel ></span><span class="sxs-lookup"><span data-stu-id="0bd5a-142">\<custom></span></span>](custom.md)|<span data-ttu-id="0bd5a-143">NetPeerTcpBinding için özel bir eş çözümleyici belirtir.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-143">Specifies a custom peer resolver for a netPeerTcpBinding.</span></span>|  
|[<span data-ttu-id="0bd5a-144">\<uç nokta ></span><span class="sxs-lookup"><span data-stu-id="0bd5a-144">\<endpoint></span></span>](endpoint-element.md)|<span data-ttu-id="0bd5a-145">Hizmet uç noktalarını yapılandırır.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-145">Configures service endpoints.</span></span>|  
|[<span data-ttu-id="0bd5a-146">\<\<istemci > uç noktası ></span><span class="sxs-lookup"><span data-stu-id="0bd5a-146">\<endpoint> of \<client></span></span>](endpoint-of-client.md)|<span data-ttu-id="0bd5a-147">Kanal uç noktalarını yapılandırır.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-147">Configures channel endpoints.</span></span>|  
|[<span data-ttu-id="0bd5a-148">\<veren ></span><span class="sxs-lookup"><span data-stu-id="0bd5a-148">\<issuer></span></span>](issuer.md)|<span data-ttu-id="0bd5a-149">Federasyon Hizmeti için güvenlik belirteci hizmetini (STS) belirtir.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-149">Specifies the Security Token Service (STS) for the federated service.</span></span>|  
|[<span data-ttu-id="0bd5a-150">\<IssuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="0bd5a-150">\<issuerMetadata></span></span>](issuermetadata.md)|<span data-ttu-id="0bd5a-151">Federasyon Hizmeti 'nin güvenlik belirteci hizmeti (STS) için meta veri uç noktasını belirtir.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-151">Specifies the metadata endpoint for the Security Token Service (STS) of a federated service.</span></span>|  
|[<span data-ttu-id="0bd5a-152">\<IssuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="0bd5a-152">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="0bd5a-153">Özel bağlamadaki verilen belirtecin parametrelerini tanımlar.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-153">Defines parameters for an issued token in a custom binding.</span></span>|  
|[<span data-ttu-id="0bd5a-154">\<LocalIssuer ></span><span class="sxs-lookup"><span data-stu-id="0bd5a-154">\<localIssuer></span></span>](localissuer.md)|<span data-ttu-id="0bd5a-155">Yerel bir güvenlik belirteci hizmetini (STS) belirtir.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-155">Specifies a local Security Token Service (STS).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0bd5a-156">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="0bd5a-156">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- [<span data-ttu-id="0bd5a-157">Kimlik Doğrulama ile Hizmet Kimliği</span><span class="sxs-lookup"><span data-stu-id="0bd5a-157">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="0bd5a-158">Noktalarının Adresler, bağlamalar ve sözleşmeler</span><span class="sxs-lookup"><span data-stu-id="0bd5a-158">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
