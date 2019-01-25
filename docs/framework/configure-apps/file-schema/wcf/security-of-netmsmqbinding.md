---
title: '&lt;netMsmqBinding&gt; &lt;güvenliği&gt;'
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: 71f0c10c336a9682971bc774141cb0c3bd37c092
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696392"
---
# <a name="ltsecuritygt-of-ltnetmsmqbindinggt"></a><span data-ttu-id="5ee3b-102">&lt;netMsmqBinding&gt; &lt;güvenliği&gt;</span><span class="sxs-lookup"><span data-stu-id="5ee3b-102">&lt;security&gt; of &lt;netMsmqBinding&gt;</span></span>
<span data-ttu-id="5ee3b-103">MSMQ bağlama için güvenlik ayarlarını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="5ee3b-104">Bu aktarım veya SOAP Güvenliği etkinleştirilmiş ve bu durumda, hangi kimlik doğrulama modu ve koruma düzeyleri kullanımda olup olmadığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
 <span data-ttu-id="5ee3b-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5ee3b-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="5ee3b-106">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="5ee3b-106">\<bindings></span></span>  
<span data-ttu-id="5ee3b-107">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="5ee3b-107">\<netMsmqBinding></span></span>  
<span data-ttu-id="5ee3b-108">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="5ee3b-108">\<binding></span></span>  
<span data-ttu-id="5ee3b-109">\<Güvenlik ></span><span class="sxs-lookup"><span data-stu-id="5ee3b-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ee3b-110">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="5ee3b-110">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/Both">
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
             clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ee3b-111">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="5ee3b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5ee3b-112">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ee3b-113">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="5ee3b-113">Attributes</span></span>  
  
|<span data-ttu-id="5ee3b-114">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="5ee3b-114">Attribute</span></span>|<span data-ttu-id="5ee3b-115">Açıklama</span><span class="sxs-lookup"><span data-stu-id="5ee3b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5ee3b-116">mod</span><span class="sxs-lookup"><span data-stu-id="5ee3b-116">mode</span></span>|<span data-ttu-id="5ee3b-117">Bütünlüğü, gizlilik ve kimlik doğrulama denetimleri güvenlik türünü belirtir.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-117">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="5ee3b-118">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="5ee3b-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5ee3b-119">-Yok: Bu güvenlik devre dışı bırakır.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-119">-   None: This disables security.</span></span><br /><span data-ttu-id="5ee3b-120">-Taşıma: Koruma ve kimlik doğrulaması taşıma tarafından sunulmaktadır.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-120">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="5ee3b-121">Bu ileti güvenliği iki sıra yöneticileri arasında geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-121">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="5ee3b-122">Kuyruk Yöneticisi ve uygulama arasında sunulan güvenlik yoktur.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-122">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="5ee3b-123">Msmq uygulamalara güvenlik modu bu tür işlevsel olarak eşdeğerdir.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-123">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="5ee3b-124">-İleti: Uçtan uca uygulama güvenliği belirtir.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-124">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="5ee3b-125">Aktarım katmanında sunulan güvenlik yoktur.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-125">There is no security offered at the transport layer.</span></span> <span data-ttu-id="5ee3b-126">Bu, standart diğer bağlamalar tarafından sunulan güvenlik benzer.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-126">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="5ee3b-127">-Hem: Hem aktarım hem de SOAP ileti katmanı güvenlik sunar.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-127">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="5ee3b-128">Aynı kimlik bilgisini iki düzeyde gereklidir.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-128">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="5ee3b-129">Aktarım varsayılan değerdir.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-129">The default value is Transport.</span></span> <span data-ttu-id="5ee3b-130">Bu öznitelik türünde <xref:System.ServiceModel.NetMsmqSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-130">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5ee3b-131">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="5ee3b-131">Child Elements</span></span>  
  
|<span data-ttu-id="5ee3b-132">Öğe</span><span class="sxs-lookup"><span data-stu-id="5ee3b-132">Element</span></span>|<span data-ttu-id="5ee3b-133">Açıklama</span><span class="sxs-lookup"><span data-stu-id="5ee3b-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ee3b-134">\<İleti ></span><span class="sxs-lookup"><span data-stu-id="5ee3b-134">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-netmsmqbinding.md)|<span data-ttu-id="5ee3b-135">SOAP ileti güvenlik ayarlarını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-135">Defines the SOAP message security settings.</span></span> <span data-ttu-id="5ee3b-136">Bu öğe türünde <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-136">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[<span data-ttu-id="5ee3b-137">\<taşıma ></span><span class="sxs-lookup"><span data-stu-id="5ee3b-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netmsmqbinding.md)|<span data-ttu-id="5ee3b-138">MSMQ taşıma güvenlik ayarlarını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-138">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="5ee3b-139">Bu öğe türünde <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-139">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5ee3b-140">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="5ee3b-140">Parent Elements</span></span>  
  
|<span data-ttu-id="5ee3b-141">Öğe</span><span class="sxs-lookup"><span data-stu-id="5ee3b-141">Element</span></span>|<span data-ttu-id="5ee3b-142">Açıklama</span><span class="sxs-lookup"><span data-stu-id="5ee3b-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5ee3b-143">bağlama</span><span class="sxs-lookup"><span data-stu-id="5ee3b-143">binding</span></span>|<span data-ttu-id="5ee3b-144">Bağlama öğesi [ \<netMsmqBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="5ee3b-144">The binding element of the [\<netMsmqBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ee3b-145">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-145">See also</span></span>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [<span data-ttu-id="5ee3b-146">Hizmet ve İstemcileri Güvenli Hale Getirme</span><span class="sxs-lookup"><span data-stu-id="5ee3b-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="5ee3b-147">Bağlamalar</span><span class="sxs-lookup"><span data-stu-id="5ee3b-147">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="5ee3b-148">Sistem Tarafından Sağlanan Bağlamaları Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="5ee3b-148">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5ee3b-149">Hizmetler ve İstemcileri Yapılandırmak için Bağlamaları Kullanma</span><span class="sxs-lookup"><span data-stu-id="5ee3b-149">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="5ee3b-150">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="5ee3b-150">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- [<span data-ttu-id="5ee3b-151">WCF'de Kuyruklar</span><span class="sxs-lookup"><span data-stu-id="5ee3b-151">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
