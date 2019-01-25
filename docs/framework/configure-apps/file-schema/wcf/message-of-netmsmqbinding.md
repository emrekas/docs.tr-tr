---
title: '&lt;netMsmqBinding&gt; &lt;iletisi&gt;'
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: b636a22fe7c6bcfae5b8f81c1566ea39c9f8ced5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54683748"
---
# <a name="ltmessagegt-of-ltnetmsmqbindinggt"></a><span data-ttu-id="99846-102">&lt;netMsmqBinding&gt; &lt;iletisi&gt;</span><span class="sxs-lookup"><span data-stu-id="99846-102">&lt;message&gt; of &lt;netMsmqBinding&gt;</span></span>
<span data-ttu-id="99846-103">SOAP ileti güvenlik ayarları bu tanımlar `netMsmqBinding` bağlama.</span><span class="sxs-lookup"><span data-stu-id="99846-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>  
  
 <span data-ttu-id="99846-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="99846-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="99846-105">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="99846-105">\<bindings></span></span>  
<span data-ttu-id="99846-106">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="99846-106">\<netMsmqBinding></span></span>  
<span data-ttu-id="99846-107">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="99846-107">\<binding></span></span>  
<span data-ttu-id="99846-108">\<Güvenlik ></span><span class="sxs-lookup"><span data-stu-id="99846-108">\<security></span></span>  
<span data-ttu-id="99846-109">\<İleti ></span><span class="sxs-lookup"><span data-stu-id="99846-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99846-110">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="99846-110">Syntax</span></span>  
  
```xml  
<netMsmqBinding>
  <binding>
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
    </security>
  </binding>
</netMsmqBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99846-111">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="99846-111">Attributes and Elements</span></span>  
 <span data-ttu-id="99846-112">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="99846-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99846-113">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="99846-113">Attributes</span></span>  
  
|<span data-ttu-id="99846-114">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="99846-114">Attribute</span></span>|<span data-ttu-id="99846-115">Açıklama</span><span class="sxs-lookup"><span data-stu-id="99846-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="99846-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="99846-116">algorithmSuite</span></span>|<span data-ttu-id="99846-117">İletinin MSMQ taşıma gönderilen iletiler için ileti tabanlı güvenlik elde etmek için kullanılan şifreleme ve anahtar-wrap algoritmaları ayarlar.</span><span class="sxs-lookup"><span data-stu-id="99846-117">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="99846-118">Varsayılan değer `Aes256` şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="99846-118">The default value is `Aes256`.</span></span> <span data-ttu-id="99846-119">Bu öznitelik türünde <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="99846-119">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|  
|<span data-ttu-id="99846-120">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="99846-120">clientCredentialType</span></span>|<span data-ttu-id="99846-121">MSMQ taşıma gönderilen iletiler için istemci kimlik doğrulaması yapılırken kullanılacak kimlik bilgisi türünü belirtir.</span><span class="sxs-lookup"><span data-stu-id="99846-121">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="99846-122">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="99846-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="99846-123">-Yok: Bu, anonim istemcilerle etkileşime geçmek bir hizmet sağlar.</span><span class="sxs-lookup"><span data-stu-id="99846-123">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="99846-124">Hizmet ya da istemci kimlik bilgileri gerektirir.</span><span class="sxs-lookup"><span data-stu-id="99846-124">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="99846-125">-   Windows: Bu, SOAP değişimleri, Windows kimlik bilgisi kimliği doğrulanmış bağlamı altında olmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="99846-125">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="99846-126">Bu, her zaman Kerberos tabanlı kimlik doğrulaması gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="99846-126">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="99846-127">-UserName: Bu hizmet gerektirecek şekilde sağlar, istemci kimlik doğrulaması kullanarak bir kullanıcı adı kimlik bilgisi.</span><span class="sxs-lookup"><span data-stu-id="99846-127">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="99846-128">Kimlik bilgisi bu durumda kullanarak belirtilmesi gerekiyor `clientCredentials` davranışı **dikkatli olun:**  Windows Communication Foundation (WCF), bir parola özeti gönderme veya parola ve ileti güvenliği için bu anahtarları kullanarak anahtarlar türetme desteklemez.</span><span class="sxs-lookup"><span data-stu-id="99846-128">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="99846-129">Bu nedenle, WCF exchange kullanıcı adı kimlik bilgileri kullanılırken sağlandığını zorlar.</span><span class="sxs-lookup"><span data-stu-id="99846-129">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="99846-130">Bu mod, hizmet sertifikası kullanarak istemci tarafı belirtilmesini gerektirir `clientCredential` davranışı ve `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="99846-130">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="99846-131">-Sertifikası: Bu hizmet gerektirecek şekilde sağlar, istemci kimlik doğrulaması kullanarak bir sertifika.</span><span class="sxs-lookup"><span data-stu-id="99846-131">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="99846-132">İstemci kimlik bilgisi bu durumda kullanarak belirtilmesi gerekiyor `clientCredentials` davranışı.</span><span class="sxs-lookup"><span data-stu-id="99846-132">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="99846-133">Hizmet kimlik bilgisi bu durumda kullanarak belirtilmesi gerekiyor `clientCredentials` belirterek davranışı `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="99846-133">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="99846-134">-CardSpace: Bu hizmet gerektirecek şekilde sağlar, istemci kimlik doğrulaması kullanarak bir CardSpace.</span><span class="sxs-lookup"><span data-stu-id="99846-134">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="99846-135">`serviceCertiifcate` İçinde sağlanmalıdır `clientCredential` davranışı.</span><span class="sxs-lookup"><span data-stu-id="99846-135">The `serviceCertiifcate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="99846-136">Varsayılan değer `Windows` şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="99846-136">The default value is `Windows`.</span></span> <span data-ttu-id="99846-137">Bu öznitelik türünde <xref:System.ServiceModel.MessageCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="99846-137">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99846-138">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="99846-138">Child Elements</span></span>  
 <span data-ttu-id="99846-139">Hiçbiri</span><span class="sxs-lookup"><span data-stu-id="99846-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99846-140">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="99846-140">Parent Elements</span></span>  
  
|<span data-ttu-id="99846-141">Öğe</span><span class="sxs-lookup"><span data-stu-id="99846-141">Element</span></span>|<span data-ttu-id="99846-142">Açıklama</span><span class="sxs-lookup"><span data-stu-id="99846-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99846-143">\<Güvenlik ></span><span class="sxs-lookup"><span data-stu-id="99846-143">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="99846-144">Bir bağlama için güvenlik ayarlarını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="99846-144">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="99846-145">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="99846-145">See also</span></span>
- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [<span data-ttu-id="99846-146">WCF'de Kuyruklar</span><span class="sxs-lookup"><span data-stu-id="99846-146">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="99846-147">Hizmet ve İstemcileri Güvenli Hale Getirme</span><span class="sxs-lookup"><span data-stu-id="99846-147">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="99846-148">Bağlamalar</span><span class="sxs-lookup"><span data-stu-id="99846-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="99846-149">Sistem Tarafından Sağlanan Bağlamaları Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="99846-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="99846-150">Hizmetler ve İstemcileri Yapılandırmak için Bağlamaları Kullanma</span><span class="sxs-lookup"><span data-stu-id="99846-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="99846-151">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="99846-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
