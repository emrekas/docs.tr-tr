---
title: <security> , <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
ms.openlocfilehash: f2750036aa4d3fbe41062ad041e50ff3a4be32b5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283978"
---
# <a name="security-of-nethttpbinding"></a><span data-ttu-id="b134c-102">\<Güvenlik >, \<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="b134c-102">\<security> of \<netHttpBinding></span></span>

<span data-ttu-id="b134c-103">Güvenlik yeteneklerini tanımlar [ \<basicHttpBinding >](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="b134c-103">Defines the security capabilities of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>

<span data-ttu-id="b134c-104">\<sistemi. ServiceModel > \\</span><span class="sxs-lookup"><span data-stu-id="b134c-104">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="b134c-105">\<bağlamaları > \\</span><span class="sxs-lookup"><span data-stu-id="b134c-105">\<bindings>\\</span></span>
<span data-ttu-id="b134c-106">\<netHttpBinding > \\</span><span class="sxs-lookup"><span data-stu-id="b134c-106">\<netHttpBinding>\\</span></span>
<span data-ttu-id="b134c-107">\<bağlama > \\</span><span class="sxs-lookup"><span data-stu-id="b134c-107">\<binding>\\</span></span>
<span data-ttu-id="b134c-108">\<Güvenlik ></span><span class="sxs-lookup"><span data-stu-id="b134c-108">\<security></span></span>

## <a name="syntax"></a><span data-ttu-id="b134c-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="b134c-109">Syntax</span></span>

```xml
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b134c-110">Öznitelikler ve öğeler</span><span class="sxs-lookup"><span data-stu-id="b134c-110">Attributes and elements</span></span>

<span data-ttu-id="b134c-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="b134c-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b134c-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="b134c-112">Attributes</span></span>

|<span data-ttu-id="b134c-113">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="b134c-113">Attribute</span></span>|<span data-ttu-id="b134c-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b134c-114">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="b134c-115">mod</span><span class="sxs-lookup"><span data-stu-id="b134c-115">mode</span></span>|<span data-ttu-id="b134c-116">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="b134c-116">Optional.</span></span> <span data-ttu-id="b134c-117">Kullanılan güvenlik türünü belirtir.</span><span class="sxs-lookup"><span data-stu-id="b134c-117">Specifies the type of security that is used.</span></span> <span data-ttu-id="b134c-118">Varsayılan, `None` değeridir.</span><span class="sxs-lookup"><span data-stu-id="b134c-118">The default is `None`.</span></span> <span data-ttu-id="b134c-119">Bu öznitelik türünde <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="b134c-119">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|

## <a name="mode-attribute"></a><span data-ttu-id="b134c-120">mod özniteliği</span><span class="sxs-lookup"><span data-stu-id="b134c-120">mode attribute</span></span>

|<span data-ttu-id="b134c-121">Değer</span><span class="sxs-lookup"><span data-stu-id="b134c-121">Value</span></span>|<span data-ttu-id="b134c-122">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b134c-122">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="b134c-123">Hiçbiri</span><span class="sxs-lookup"><span data-stu-id="b134c-123">None</span></span>|<span data-ttu-id="b134c-124">-Sıradaki iletiler, aktarım sırasında sağlanmaz.</span><span class="sxs-lookup"><span data-stu-id="b134c-124">-   Messages are not secured during transfer.</span></span>|
|<span data-ttu-id="b134c-125">Taşıma</span><span class="sxs-lookup"><span data-stu-id="b134c-125">Transport</span></span>|<span data-ttu-id="b134c-126">HTTPS aktarımı kullanarak güvenliği sağlanır.</span><span class="sxs-lookup"><span data-stu-id="b134c-126">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="b134c-127">SOAP iletilerini HTTPS kullanılarak güvenli hale getirilir.</span><span class="sxs-lookup"><span data-stu-id="b134c-127">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="b134c-128">Hizmet, hizmetin X.509 sertifikası kullanarak istemci kimlik doğrulaması yapılır.</span><span class="sxs-lookup"><span data-stu-id="b134c-128">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="b134c-129">İstemci tarafından sağlanan ClientCredentialType kullanarak kimlik doğrulaması yapılır.</span><span class="sxs-lookup"><span data-stu-id="b134c-129">The client is authenticated using the ClientCredentialType supplied.</span></span>|
|<span data-ttu-id="b134c-130">İleti</span><span class="sxs-lookup"><span data-stu-id="b134c-130">Message</span></span>|<span data-ttu-id="b134c-131">SOAP ileti güveliği kullanarak güvenliği sağlanır.</span><span class="sxs-lookup"><span data-stu-id="b134c-131">Security is provided using SOAP message security.</span></span> <span data-ttu-id="b134c-132">Varsayılan olarak, gövde imzalı ve şifrelenir.</span><span class="sxs-lookup"><span data-stu-id="b134c-132">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="b134c-133">Bu bağlama için sistem sunucu sertifikası istemciyi bant dışından sağlanmasını gerektirir.</span><span class="sxs-lookup"><span data-stu-id="b134c-133">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="b134c-134">Yalnızca geçerli `ClientCredentialType` Bu bağlama için `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="b134c-134">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|
|<span data-ttu-id="b134c-135">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="b134c-135">TransportWithMessageCredential</span></span>|<span data-ttu-id="b134c-136">Bütünlüğü, gizliliği ve sunucu kimlik doğrulaması ile Aktarım güvenliği sağlanır.</span><span class="sxs-lookup"><span data-stu-id="b134c-136">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="b134c-137">İstemci kimlik doğrulaması yoluyla SOAP ileti güvenliği sağlanır.</span><span class="sxs-lookup"><span data-stu-id="b134c-137">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="b134c-138">Bu mod, kullanıcının kullanıcı adı/parola kullanarak kimlik doğrulaması ve ileti aktarım güvenliğini sağlamak için var olan bir HTTP dağıtım olduğunda geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="b134c-138">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|
|<span data-ttu-id="b134c-139">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="b134c-139">TransportCredentialOnly</span></span>|<span data-ttu-id="b134c-140">Bu mod, ileti bütünlüğü ve gizliliği sağlamaz.</span><span class="sxs-lookup"><span data-stu-id="b134c-140">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="b134c-141">Bu, http tabanlı istemci kimlik doğrulaması sağlar.</span><span class="sxs-lookup"><span data-stu-id="b134c-141">It provides http-based client authentication.</span></span> <span data-ttu-id="b134c-142">Bu mod, dikkatli kullanılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="b134c-142">This mode should be used with caution.</span></span> <span data-ttu-id="b134c-143">Burada aktarım güvenliği (IPSec gibi) diğer yollarla sağlanmaktadır ve yalnızca istemci kimlik doğrulaması WCF altyapısı tarafından sağlanan ortamlarda kullanılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="b134c-143">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="b134c-144">Alt öğeleri</span><span class="sxs-lookup"><span data-stu-id="b134c-144">Child elements</span></span>

|<span data-ttu-id="b134c-145">Öğe</span><span class="sxs-lookup"><span data-stu-id="b134c-145">Element</span></span>|<span data-ttu-id="b134c-146">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b134c-146">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b134c-147">\<taşıma ></span><span class="sxs-lookup"><span data-stu-id="b134c-147">\<transport></span></span>](transport-of-nethttpbinding.md)|<span data-ttu-id="b134c-148">Temel HTTP hizmeti için taşıma güvenlik ayarlarını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="b134c-148">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="b134c-149">Bu öğe için karşılık gelen <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="b134c-149">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|
|[<span data-ttu-id="b134c-150">\<İleti ></span><span class="sxs-lookup"><span data-stu-id="b134c-150">\<message></span></span>](message-of-nethttpbinding.md)|<span data-ttu-id="b134c-151">Temel HTTP hizmeti için ileti güvenlik ayarlarını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="b134c-151">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="b134c-152">Bu öğe için karşılık gelen <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="b134c-152">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b134c-153">Üst öğeler</span><span class="sxs-lookup"><span data-stu-id="b134c-153">Parent elements</span></span>

|<span data-ttu-id="b134c-154">Öğe</span><span class="sxs-lookup"><span data-stu-id="b134c-154">Element</span></span>|<span data-ttu-id="b134c-155">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b134c-155">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="b134c-156">bağlama</span><span class="sxs-lookup"><span data-stu-id="b134c-156">binding</span></span>|<span data-ttu-id="b134c-157">Bağlama öğesi [ \<basicHttpBinding >](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="b134c-157">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|

## <a name="remarks"></a><span data-ttu-id="b134c-158">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="b134c-158">Remarks</span></span>

 <span data-ttu-id="b134c-159">Varsayılan olarak, SOAP ileti güvenli olmadığından ve istemci kimliği doğrulanmamış.</span><span class="sxs-lookup"><span data-stu-id="b134c-159">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="b134c-160">Bu öğe için ek güvenlik ayarları yapılandırmanızı sağlar `netHttpBinding` öğesi.</span><span class="sxs-lookup"><span data-stu-id="b134c-160">This element enables you to configure additional security settings for the `netHttpBinding` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="b134c-161">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="b134c-161">See also</span></span>

- <xref:System.ServiceModel.NetHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>  
- [<span data-ttu-id="b134c-162">Hizmet ve İstemcileri Güvenli Hale Getirme</span><span class="sxs-lookup"><span data-stu-id="b134c-162">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="b134c-163">Kimlik Bilgisi Türü Seçme</span><span class="sxs-lookup"><span data-stu-id="b134c-163">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="b134c-164">Bağlamalar</span><span class="sxs-lookup"><span data-stu-id="b134c-164">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b134c-165">Sistem Tarafından Sağlanan Bağlamaları Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="b134c-165">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b134c-166">Hizmetler ve İstemcileri Yapılandırmak için Bağlamaları Kullanma</span><span class="sxs-lookup"><span data-stu-id="b134c-166">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="b134c-167">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="b134c-167">\<binding></span></span>](../../../misc/binding.md)
