---
title: <security> / <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
ms.openlocfilehash: 68d3aa4da793e0338c2b0b704335bafce7cc3e31
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670409"
---
# <a name="security-of-wshttpbinding"></a><span data-ttu-id="7cb86-102">\<Güvenlik >, \<wsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="7cb86-102">\<security> of \<wsHttpBinding></span></span>
<span data-ttu-id="7cb86-103">Güvenlik özelliklerini gösteren [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="7cb86-103">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="7cb86-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7cb86-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7cb86-105">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="7cb86-105">\<bindings></span></span>  
<span data-ttu-id="7cb86-106">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="7cb86-106">\<wsHttpBinding></span></span>  
<span data-ttu-id="7cb86-107">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="7cb86-107">\<binding></span></span>  
<span data-ttu-id="7cb86-108">\<Güvenlik ></span><span class="sxs-lookup"><span data-stu-id="7cb86-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cb86-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="7cb86-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithMessageCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="String"
             defaultClientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             defaultProxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             defaultRealm="String" />
  <message clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           establishSecurityContext="Boolean"
           negotiateServiceCredential="Boolean" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7cb86-110">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="7cb86-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7cb86-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="7cb86-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7cb86-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="7cb86-112">Attributes</span></span>  
  
|<span data-ttu-id="7cb86-113">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="7cb86-113">Attribute</span></span>|<span data-ttu-id="7cb86-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="7cb86-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7cb86-115">mod</span><span class="sxs-lookup"><span data-stu-id="7cb86-115">mode</span></span>|<span data-ttu-id="7cb86-116">-İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="7cb86-116">-   Optional.</span></span> <span data-ttu-id="7cb86-117">Uygulanan güvenlik türünü belirtir.</span><span class="sxs-lookup"><span data-stu-id="7cb86-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="7cb86-118">Varsayılan, `Message` değeridir.</span><span class="sxs-lookup"><span data-stu-id="7cb86-118">The default is `Message`.</span></span><br /><span data-ttu-id="7cb86-119">-Bu öznitelik türünde <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="7cb86-119">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="7cb86-120">mod özniteliği</span><span class="sxs-lookup"><span data-stu-id="7cb86-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="7cb86-121">Değer</span><span class="sxs-lookup"><span data-stu-id="7cb86-121">Value</span></span>|<span data-ttu-id="7cb86-122">Açıklama</span><span class="sxs-lookup"><span data-stu-id="7cb86-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7cb86-123">Yok.</span><span class="sxs-lookup"><span data-stu-id="7cb86-123">None</span></span>|<span data-ttu-id="7cb86-124">Güvenlik devre dışı bırakıldı.</span><span class="sxs-lookup"><span data-stu-id="7cb86-124">Security is disabled.</span></span>|  
|<span data-ttu-id="7cb86-125">Taşıma</span><span class="sxs-lookup"><span data-stu-id="7cb86-125">Transport</span></span>|<span data-ttu-id="7cb86-126">HTTPS kullanarak güvenliği sağlanır.</span><span class="sxs-lookup"><span data-stu-id="7cb86-126">Security is provided using HTTPS.</span></span> <span data-ttu-id="7cb86-127">Hizmet SSL sertifikaları ile yapılandırılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="7cb86-127">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="7cb86-128">İleti tamamen HTTPS kullanan güvenli ve hizmetin SSL sertifikası kullanarak istemci tarafından doğrulanır.</span><span class="sxs-lookup"><span data-stu-id="7cb86-128">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="7cb86-129">İstemci kimlik doğrulaması aracılığıyla denetlenir `ClientCredentials` özniteliği.</span><span class="sxs-lookup"><span data-stu-id="7cb86-129">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="7cb86-130">' ın [ \<aktarım >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="7cb86-130">of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="7cb86-131">İleti</span><span class="sxs-lookup"><span data-stu-id="7cb86-131">Message</span></span>|<span data-ttu-id="7cb86-132">SOAP ileti güveliği kullanarak güvenliği sağlanır.</span><span class="sxs-lookup"><span data-stu-id="7cb86-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="7cb86-133">Varsayılan olarak, SOAP gövdesi şifreli ve imza var.</span><span class="sxs-lookup"><span data-stu-id="7cb86-133">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="7cb86-134">Çeşitli hizmet kimlik bilgilerini kullanmak için algoritma paketini olan bant dışı istemci kullanılabilir olup gibi özellikler, bu mod sunar ve ileti gövdesi Security.Message özelliği uygulamak için koruma düzeyini.</span><span class="sxs-lookup"><span data-stu-id="7cb86-134">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="7cb86-135">İstemci kimlik doğrulaması, oturum başına bir kez gerçekleştirilir ve kimlik doğrulama sonuçlarını oturum süresi boyunca önbelleğe alınır.</span><span class="sxs-lookup"><span data-stu-id="7cb86-135">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="7cb86-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="7cb86-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="7cb86-137">Bu modda, HTTPS kimlik doğrulaması bütünlüğü ve gizliliği sağlar ve istemci kimlik doğrulaması SOAP ileti güvenliği sağlar.</span><span class="sxs-lookup"><span data-stu-id="7cb86-137">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="7cb86-138">Varsayılan olarak, istemci kimlik doğrulaması, oturum başına bir kez gerçekleştirilir ve kimlik doğrulama sonuçlarını oturum süresi boyunca önbelleğe alınır.</span><span class="sxs-lookup"><span data-stu-id="7cb86-138">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7cb86-139">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="7cb86-139">Child Elements</span></span>  
  
|<span data-ttu-id="7cb86-140">Öğe</span><span class="sxs-lookup"><span data-stu-id="7cb86-140">Element</span></span>|<span data-ttu-id="7cb86-141">Açıklama</span><span class="sxs-lookup"><span data-stu-id="7cb86-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7cb86-142">\<taşıma ></span><span class="sxs-lookup"><span data-stu-id="7cb86-142">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)|<span data-ttu-id="7cb86-143">Taşıma güvenlik ayarlarını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="7cb86-143">Defines the transport security settings.</span></span> <span data-ttu-id="7cb86-144">Bu öğe için karşılık gelen <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> türü.</span><span class="sxs-lookup"><span data-stu-id="7cb86-144">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[<span data-ttu-id="7cb86-145">\<İleti ></span><span class="sxs-lookup"><span data-stu-id="7cb86-145">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md)|<span data-ttu-id="7cb86-146">İleti için güvenlik ayarlarını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="7cb86-146">Defines the security settings for the message.</span></span> <span data-ttu-id="7cb86-147">Bu öğe için karşılık gelen <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> türü.</span><span class="sxs-lookup"><span data-stu-id="7cb86-147">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7cb86-148">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="7cb86-148">Parent Elements</span></span>  
  
|<span data-ttu-id="7cb86-149">Öğe</span><span class="sxs-lookup"><span data-stu-id="7cb86-149">Element</span></span>|<span data-ttu-id="7cb86-150">Açıklama</span><span class="sxs-lookup"><span data-stu-id="7cb86-150">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7cb86-151">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="7cb86-151">\<wsHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|<span data-ttu-id="7cb86-152">HTTP taşıma uygulamalar için güvenli bir bağlama.</span><span class="sxs-lookup"><span data-stu-id="7cb86-152">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7cb86-153">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="7cb86-153">Remarks</span></span>  
 <span data-ttu-id="7cb86-154">WSHttpBinding sınıfı WS - uygulama hizmetleri ile birlikte çalışabilirlik için tasarlanmış \* belirtimleri.</span><span class="sxs-lookup"><span data-stu-id="7cb86-154">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="7cb86-155">Bu bağlama için Aktarım güvenliği HTTP veya HTTPS üzerinden Güvenli Yuva Katmanı (SSL) olan.</span><span class="sxs-lookup"><span data-stu-id="7cb86-155">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cb86-156">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="7cb86-156">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- [<span data-ttu-id="7cb86-157">Hizmet ve İstemcileri Güvenli Hale Getirme</span><span class="sxs-lookup"><span data-stu-id="7cb86-157">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7cb86-158">Bağlamalar</span><span class="sxs-lookup"><span data-stu-id="7cb86-158">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="7cb86-159">Sistem Tarafından Sağlanan Bağlamaları Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="7cb86-159">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7cb86-160">Hizmetler ve İstemcileri Yapılandırmak için Bağlamaları Kullanma</span><span class="sxs-lookup"><span data-stu-id="7cb86-160">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="7cb86-161">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="7cb86-161">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
