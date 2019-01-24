---
title: '&lt;netMsmqBinding&gt; &lt;taşıma&gt;'
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: 7eac5c7a0da71e2d06929322ac5c702d83a1ea65
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597443"
---
# <a name="lttransportgt-of-ltnetmsmqbindinggt"></a><span data-ttu-id="e4960-102">&lt;netMsmqBinding&gt; &lt;taşıma&gt;</span><span class="sxs-lookup"><span data-stu-id="e4960-102">&lt;transport&gt; of &lt;netMsmqBinding&gt;</span></span>
<span data-ttu-id="e4960-103">Taşıma güvenlik ayarlarını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="e4960-103">Defines the transport security settings.</span></span>  
  
 <span data-ttu-id="e4960-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e4960-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e4960-105">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="e4960-105">\<bindings></span></span>  
<span data-ttu-id="e4960-106">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="e4960-106">\<netMsmqBinding></span></span>  
<span data-ttu-id="e4960-107">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="e4960-107">\<binding></span></span>  
<span data-ttu-id="e4960-108">\<Güvenlik ></span><span class="sxs-lookup"><span data-stu-id="e4960-108">\<security></span></span>  
<span data-ttu-id="e4960-109">\<taşıma ></span><span class="sxs-lookup"><span data-stu-id="e4960-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4960-110">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="e4960-110">Syntax</span></span>  
  
```xml  
<netMsmqBinding>
  <binding>
    <security>
      <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    </security>
  </binding>
</netMsmqBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4960-111">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="e4960-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e4960-112">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="e4960-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4960-113">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="e4960-113">Attributes</span></span>  
  
|<span data-ttu-id="e4960-114">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="e4960-114">Attribute</span></span>|<span data-ttu-id="e4960-115">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e4960-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e4960-116">msmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="e4960-116">msmqAuthenticationMode</span></span>|<span data-ttu-id="e4960-117">İletinin MSMQ taşıma tarafından nasıl doğrulacağını belirtir.</span><span class="sxs-lookup"><span data-stu-id="e4960-117">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="e4960-118">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="e4960-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e4960-119">-Yok: Kimlik doğrulaması yok.</span><span class="sxs-lookup"><span data-stu-id="e4960-119">-   None: No authentication.</span></span><br /><span data-ttu-id="e4960-120">-   WindowsDomain: İletiyle ilişkili güvenlik kimliği için X.509 sertifikası almak için Active Directory kimlik doğrulama mekanizması kullanır.</span><span class="sxs-lookup"><span data-stu-id="e4960-120">-   WindowsDomain: The authentication mechanism uses Active Directory to retrieve the X.509 certificate for the security identifier associated with the message.</span></span> <span data-ttu-id="e4960-121">Bu, ardından kullanıcı emin olmak için ACL kuyruğun sıra için yazma iznine sahip olmadığını denetlemek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="e4960-121">This is then used to check the ACL of the queue to ensure the user has write permission for the queue.</span></span><br /><span data-ttu-id="e4960-122">-Sertifikası: Kanal sertifikayı sertifika deposundan alır.</span><span class="sxs-lookup"><span data-stu-id="e4960-122">-   Certificate: The channel retrieves the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="e4960-123">Varsayılan, `WindowsDomain` değeridir.</span><span class="sxs-lookup"><span data-stu-id="e4960-123">The default is `WindowsDomain`.</span></span><br /><br /> <span data-ttu-id="e4960-124">Bu öznitelik ayarlanırsa `None`, `msmqProtectionLevel` özniteliği de ayarlanması gerekir `None`.</span><span class="sxs-lookup"><span data-stu-id="e4960-124">If this attribute is set to `None`, the `msmqProtectionLevel` attribute must also be set to `None`.</span></span> <span data-ttu-id="e4960-125">Bu öznitelik türünde <xref:System.ServiceModel.MsmqAuthenticationMode></span><span class="sxs-lookup"><span data-stu-id="e4960-125">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode></span></span>|  
|<span data-ttu-id="e4960-126">msmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="e4960-126">msmqEncryptionAlgorithm</span></span>|<span data-ttu-id="e4960-127">Etkin ileti şifreleme için iletileri ileti sıra yöneticileri arasında transfer ederken kullanılan algoritmayı belirtir.</span><span class="sxs-lookup"><span data-stu-id="e4960-127">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="e4960-128">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="e4960-128">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e4960-129">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="e4960-129">-   RC4Stream</span></span><br /><span data-ttu-id="e4960-130">-AES</span><span class="sxs-lookup"><span data-stu-id="e4960-130">-   AES</span></span><br /><span data-ttu-id="e4960-131">-Varsayılan değer `RC4Stream`.</span><span class="sxs-lookup"><span data-stu-id="e4960-131">-   The default value is `RC4Stream`.</span></span> <span data-ttu-id="e4960-132">Bu öznitelik türünde <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="e4960-132">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|<span data-ttu-id="e4960-133">msmqProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="e4960-133">msmqProtectionLevel</span></span>|<span data-ttu-id="e4960-134">MSMQ taşıma düzeyinde güvenli şekilde iletileri belirtir.</span><span class="sxs-lookup"><span data-stu-id="e4960-134">Specifies the way messages are secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="e4960-135">İleti bütünlüğü hem takası ileti bütünlüğü çalışırken işaretini ve şifreleme sağlar şifreleme sağlar.</span><span class="sxs-lookup"><span data-stu-id="e4960-135">Encryption ensures message integrity, while sign and encrypt ensures both message integrity and non-repudiation.</span></span> <span data-ttu-id="e4960-136">Diğer bir deyişle, ileti gönderen gerçekten geldi ve gönderen kim kendisinin kendisinin olduğunu söylüyor.</span><span class="sxs-lookup"><span data-stu-id="e4960-136">That is, the message indeed came from the sender and the sender is who he says he is.</span></span> <span data-ttu-id="e4960-137">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="e4960-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e4960-138">-Yok: Koruma yok.</span><span class="sxs-lookup"><span data-stu-id="e4960-138">-   None: No protection.</span></span><br /><span data-ttu-id="e4960-139">-Oturum: İmzalı iletiler.</span><span class="sxs-lookup"><span data-stu-id="e4960-139">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="e4960-140">-   EncryptAndSign: İletileri şifrelenir ve imzalanmış.</span><span class="sxs-lookup"><span data-stu-id="e4960-140">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><span data-ttu-id="e4960-141">-Varsayılan `Sign`.</span><span class="sxs-lookup"><span data-stu-id="e4960-141">-   The default is `Sign`.</span></span>|  
|<span data-ttu-id="e4960-142">msmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="e4960-142">msmqSecureHashAlgorithm</span></span>|<span data-ttu-id="e4960-143">İleti özeti bilgi işlem için kullanılan karma algoritmasını belirtir.</span><span class="sxs-lookup"><span data-stu-id="e4960-143">Specifies the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="e4960-144">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="e4960-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e4960-145">-MD5</span><span class="sxs-lookup"><span data-stu-id="e4960-145">-   MD5</span></span><br /><span data-ttu-id="e4960-146">-   SHA1</span><span class="sxs-lookup"><span data-stu-id="e4960-146">-   SHA1</span></span><br /><span data-ttu-id="e4960-147">-   SHA256</span><span class="sxs-lookup"><span data-stu-id="e4960-147">-   SHA256</span></span><br /><span data-ttu-id="e4960-148">-   SHA512</span><span class="sxs-lookup"><span data-stu-id="e4960-148">-   SHA512</span></span><br /><br /> <span data-ttu-id="e4960-149">Varsayılan, `SHA1` değeridir.</span><span class="sxs-lookup"><span data-stu-id="e4960-149">The default is `SHA1`.</span></span> <span data-ttu-id="e4960-150">Bu öznitelik türünde <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="e4960-150">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e4960-151">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="e4960-151">Child Elements</span></span>  
 <span data-ttu-id="e4960-152">Hiçbiri</span><span class="sxs-lookup"><span data-stu-id="e4960-152">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e4960-153">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="e4960-153">Parent Elements</span></span>  
  
|<span data-ttu-id="e4960-154">Öğe</span><span class="sxs-lookup"><span data-stu-id="e4960-154">Element</span></span>|<span data-ttu-id="e4960-155">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e4960-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e4960-156">\<Güvenlik ></span><span class="sxs-lookup"><span data-stu-id="e4960-156">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="e4960-157">Sıraya alınan taşımalar için taşıma güvenlik ayarlarını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="e4960-157">Defines the transport security settings for queued transports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e4960-158">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="e4960-158">See also</span></span>
- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="e4960-159">WCF'de Kuyruklar</span><span class="sxs-lookup"><span data-stu-id="e4960-159">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="e4960-160">Hizmet ve İstemcileri Güvenli Hale Getirme</span><span class="sxs-lookup"><span data-stu-id="e4960-160">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e4960-161">Bağlamalar</span><span class="sxs-lookup"><span data-stu-id="e4960-161">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="e4960-162">Sistem Tarafından Sağlanan Bağlamaları Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="e4960-162">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e4960-163">Hizmetler ve İstemcileri Yapılandırmak için Bağlamaları Kullanma</span><span class="sxs-lookup"><span data-stu-id="e4960-163">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="e4960-164">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="e4960-164">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
