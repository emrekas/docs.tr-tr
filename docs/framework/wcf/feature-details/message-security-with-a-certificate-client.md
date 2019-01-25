---
title: Sertifika İstemcisi ile İleti Güvenliği
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 99770573-c815-4428-a38c-e4335c8bd7ce
ms.openlocfilehash: a027577f5118f9a5b2f3eeaa29ddfde20851a8f2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54530859"
---
# <a name="message-security-with-a-certificate-client"></a><span data-ttu-id="6be73-102">Sertifika İstemcisi ile İleti Güvenliği</span><span class="sxs-lookup"><span data-stu-id="6be73-102">Message Security with a Certificate Client</span></span>
<span data-ttu-id="6be73-103">Aşağıdaki senaryoda, bir Windows Communication Foundation (WCF) istemci ve hizmet ileti güvenlik modunu kullanarak güvenli gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="6be73-103">The following scenario shows a Windows Communication Foundation (WCF) client and service secured using message security mode.</span></span> <span data-ttu-id="6be73-104">Hem istemci hem de hizmet sertifikaları ile doğrulanır.</span><span class="sxs-lookup"><span data-stu-id="6be73-104">Both the client and the service are authenticated with certificates.</span></span> <span data-ttu-id="6be73-105">Daha fazla bilgi için [dağıtılmış uygulama güvenliği](../../../../docs/framework/wcf/feature-details/distributed-application-security.md).</span><span class="sxs-lookup"><span data-stu-id="6be73-105">For more information, see [Distributed Application Security](../../../../docs/framework/wcf/feature-details/distributed-application-security.md).</span></span>  
  
 <span data-ttu-id="6be73-106">Örnek bir uygulama için bkz: [ileti güvenliği sertifikası](../../../../docs/framework/wcf/samples/message-security-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="6be73-106">For a sample application, see [Message Security Certificate](../../../../docs/framework/wcf/samples/message-security-certificate.md).</span></span>  
  
 <span data-ttu-id="6be73-107">![İstemci sertifikası ile](../../../../docs/framework/wcf/feature-details/media/clientwithcertificate.gif "ClientWithCertificate")</span><span class="sxs-lookup"><span data-stu-id="6be73-107">![Client with certificate](../../../../docs/framework/wcf/feature-details/media/clientwithcertificate.gif "ClientWithCertificate")</span></span>  
  
|<span data-ttu-id="6be73-108">Özelliği</span><span class="sxs-lookup"><span data-stu-id="6be73-108">Characteristic</span></span>|<span data-ttu-id="6be73-109">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6be73-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="6be73-110">Güvenlik modu</span><span class="sxs-lookup"><span data-stu-id="6be73-110">Security Mode</span></span>|<span data-ttu-id="6be73-111">İleti</span><span class="sxs-lookup"><span data-stu-id="6be73-111">Message</span></span>|  
|<span data-ttu-id="6be73-112">Birlikte Çalışabilirlik</span><span class="sxs-lookup"><span data-stu-id="6be73-112">Interoperability</span></span>|<span data-ttu-id="6be73-113">Yalnızca WCF</span><span class="sxs-lookup"><span data-stu-id="6be73-113">WCF only</span></span>|  
|<span data-ttu-id="6be73-114">Kimlik doğrulaması (sunucu)</span><span class="sxs-lookup"><span data-stu-id="6be73-114">Authentication (Server)</span></span>|<span data-ttu-id="6be73-115">Hizmet sertifikası kullanarak</span><span class="sxs-lookup"><span data-stu-id="6be73-115">Using service certificate</span></span>|  
|<span data-ttu-id="6be73-116">Kimlik doğrulaması (istemci)</span><span class="sxs-lookup"><span data-stu-id="6be73-116">Authentication (Client)</span></span>|<span data-ttu-id="6be73-117">İstemci sertifikası kullanarak</span><span class="sxs-lookup"><span data-stu-id="6be73-117">Using client certificate</span></span>|  
|<span data-ttu-id="6be73-118">Bütünlüğü</span><span class="sxs-lookup"><span data-stu-id="6be73-118">Integrity</span></span>|<span data-ttu-id="6be73-119">Evet</span><span class="sxs-lookup"><span data-stu-id="6be73-119">Yes</span></span>|  
|<span data-ttu-id="6be73-120">Gizliliği</span><span class="sxs-lookup"><span data-stu-id="6be73-120">Confidentiality</span></span>|<span data-ttu-id="6be73-121">Evet</span><span class="sxs-lookup"><span data-stu-id="6be73-121">Yes</span></span>|  
|<span data-ttu-id="6be73-122">Taşıma</span><span class="sxs-lookup"><span data-stu-id="6be73-122">Transport</span></span>|<span data-ttu-id="6be73-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="6be73-123">HTTP</span></span>|  
|<span data-ttu-id="6be73-124">Bağlama</span><span class="sxs-lookup"><span data-stu-id="6be73-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="6be73-125">Hizmet</span><span class="sxs-lookup"><span data-stu-id="6be73-125">Service</span></span>  
 <span data-ttu-id="6be73-126">Aşağıdaki kod ve yapılandırma, bağımsız olarak çalışmaya yöneliktir.</span><span class="sxs-lookup"><span data-stu-id="6be73-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="6be73-127">Aşağıdakilerden birini yapın:</span><span class="sxs-lookup"><span data-stu-id="6be73-127">Do one of the following:</span></span>  
  
-   <span data-ttu-id="6be73-128">Kod ile yapılandırma kullanarak tek başına bir hizmet oluşturun.</span><span class="sxs-lookup"><span data-stu-id="6be73-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="6be73-129">Sağlanan Yapılandırması'nı kullanarak bir hizmet oluşturma, ancak tüm uç noktalar tanımlamaz.</span><span class="sxs-lookup"><span data-stu-id="6be73-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6be73-130">Kod</span><span class="sxs-lookup"><span data-stu-id="6be73-130">Code</span></span>  
 <span data-ttu-id="6be73-131">Aşağıdaki kod, güvenli bir bağlam'kurmak için ileti güvenliği kullanan bir hizmet uç noktası oluşturma gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="6be73-131">The following code shows how to create a service endpoint that uses message security to establish a secure context.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#10)]
 [!code-vb[C_SecurityScenarios#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#10)]  
  
### <a name="configuration"></a><span data-ttu-id="6be73-132">Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="6be73-132">Configuration</span></span>  
 <span data-ttu-id="6be73-133">Aşağıdaki yapılandırmayı kod yerine kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="6be73-133">The following configuration can be used instead of the code.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"  
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="ServiceCredentialsBehavior"   
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="MessageAndCerficiateClient"   
                  name="SecuredByClientCertificate"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator">  
          <security mode="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="6be73-134">İstemci</span><span class="sxs-lookup"><span data-stu-id="6be73-134">Client</span></span>  
 <span data-ttu-id="6be73-135">Aşağıdaki kod ve yapılandırma, bağımsız olarak çalışmaya yöneliktir.</span><span class="sxs-lookup"><span data-stu-id="6be73-135">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="6be73-136">Aşağıdakilerden birini yapın:</span><span class="sxs-lookup"><span data-stu-id="6be73-136">Do one of the following:</span></span>  
  
-   <span data-ttu-id="6be73-137">Bir tek başına istemci kodu (ve istemci kodu) kullanarak oluşturun.</span><span class="sxs-lookup"><span data-stu-id="6be73-137">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="6be73-138">Herhangi bir uç nokta adresi tanımlamıyor bir istemci oluşturun.</span><span class="sxs-lookup"><span data-stu-id="6be73-138">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="6be73-139">Bunun yerine, yapılandırma adı bağımsız değişkeni olarak alan İstemci Oluşturucu kullanın.</span><span class="sxs-lookup"><span data-stu-id="6be73-139">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="6be73-140">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="6be73-140">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="6be73-141">Kod</span><span class="sxs-lookup"><span data-stu-id="6be73-141">Code</span></span>  
 <span data-ttu-id="6be73-142">Aşağıdaki kod, istemci oluşturur.</span><span class="sxs-lookup"><span data-stu-id="6be73-142">The following code creates the client.</span></span> <span data-ttu-id="6be73-143">İleti modu güvenlik bağlamadır ve istemci kimlik bilgisi türü `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="6be73-143">The binding is to message mode security, and the client credential type is set to `Certificate`.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#17](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#17)]
 [!code-vb[C_SecurityScenarios#17](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#17)]  
  
### <a name="configuration"></a><span data-ttu-id="6be73-144">Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="6be73-144">Configuration</span></span>  
 <span data-ttu-id="6be73-145">Aşağıdaki yapılandırma, bir uç nokta davranışı'nı kullanarak istemci sertifikasını belirtir.</span><span class="sxs-lookup"><span data-stu-id="6be73-145">The following configuration specifies the client certificate using an endpoint behavior.</span></span> <span data-ttu-id="6be73-146">Sertifikalar hakkında daha fazla bilgi için bkz. [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="6be73-146">For more information about certificates, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span> <span data-ttu-id="6be73-147">Ayrıca kodda bir <`identity`> öğesini bir etki alanı adı sistemi (DNS), beklenen sunucu kimliğini belirtin.</span><span class="sxs-lookup"><span data-stu-id="6be73-147">The code also uses an <`identity`> element to specify a Domain Name System (DNS) of the expected server identity.</span></span> <span data-ttu-id="6be73-148">Kimlik hakkında daha fazla bilgi için bkz: [kimlik doğrulama ile hizmet kimliği](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="6be73-148">For more information about identity, see [Service Identity and Authentication](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="endpointCredentialsBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="Cohowinery.com"   
               storeLocation="LocalMachine"  
              x509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"   
                behaviorConfiguration="endpointCredentialsBehavior"  
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value="Contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6be73-149">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="6be73-149">See also</span></span>
- [<span data-ttu-id="6be73-150">Güvenliğe Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="6be73-150">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="6be73-151">Kimlik Doğrulama ile Hizmet Kimliği</span><span class="sxs-lookup"><span data-stu-id="6be73-151">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="6be73-152">Sertifikalarla Çalışma</span><span class="sxs-lookup"><span data-stu-id="6be73-152">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="6be73-153">Windows Server AppFabric için güvenlik modeli</span><span class="sxs-lookup"><span data-stu-id="6be73-153">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
