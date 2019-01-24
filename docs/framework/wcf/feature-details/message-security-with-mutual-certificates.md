---
title: Karşılıklı Sertifikalar ile İleti Güvenliği
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 99d7a528-7ae4-4d39-a0f9-3066ea237de0
ms.openlocfilehash: 51795007b906a6eb71e5e03b4afef2fc83328b28
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54593348"
---
# <a name="message-security-with-mutual-certificates"></a><span data-ttu-id="aec01-102">Karşılıklı Sertifikalar ile İleti Güvenliği</span><span class="sxs-lookup"><span data-stu-id="aec01-102">Message Security with Mutual Certificates</span></span>
<span data-ttu-id="aec01-103">Aşağıdaki senaryoda, bir Windows Communication Foundation (WCF) hizmeti ve istemcisine ileti güvenlik modunu kullanarak güvenli gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="aec01-103">The following scenario shows a Windows Communication Foundation (WCF) service and client secured using message security mode.</span></span> <span data-ttu-id="aec01-104">Hizmet ve istemci sertifikaları ile doğrulanır.</span><span class="sxs-lookup"><span data-stu-id="aec01-104">The client and the service are authenticated with certificates.</span></span>  
  
 <span data-ttu-id="aec01-105">X.509 Sertifika belirteci profiliyle WS-güvenlik kullandığından bu birlikte çalışabilen bir senaryodur.</span><span class="sxs-lookup"><span data-stu-id="aec01-105">This scenario is interoperable because it uses WS-Security with the X.509 certificate token profile.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aec01-106">Bu senaryo, hizmet sertifikasının anlaşma gerçekleştirmez.</span><span class="sxs-lookup"><span data-stu-id="aec01-106">This scenario does not perform negotiation of the service certificate.</span></span> <span data-ttu-id="aec01-107">Hizmet sertifikası, öncesinde herhangi bir iletişim istemciye sağlanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="aec01-107">The service certificate must be provided to the client in advance of any communication.</span></span> <span data-ttu-id="aec01-108">Sunucu sertifikası uygulamayla birlikte dağıtılmış veya bir bant dışı iletişimi sağlanan.</span><span class="sxs-lookup"><span data-stu-id="aec01-108">The server certificate can be distributed with the application or provided in an out-of-band communication.</span></span>  
  
 <span data-ttu-id="aec01-109">![Karşılıklı sertifikalar ile güvenlik iletisi](../../../../docs/framework/wcf/feature-details/media/f4157312-b17c-416c-a5ee-fa7b54db211b.gif "f4157312-b17c-416c-a5ee-fa7b54db211b")</span><span class="sxs-lookup"><span data-stu-id="aec01-109">![Message security with mutual certificates](../../../../docs/framework/wcf/feature-details/media/f4157312-b17c-416c-a5ee-fa7b54db211b.gif "f4157312-b17c-416c-a5ee-fa7b54db211b")</span></span>  
  
|<span data-ttu-id="aec01-110">Özelliği</span><span class="sxs-lookup"><span data-stu-id="aec01-110">Characteristic</span></span>|<span data-ttu-id="aec01-111">Açıklama</span><span class="sxs-lookup"><span data-stu-id="aec01-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="aec01-112">Güvenlik modu</span><span class="sxs-lookup"><span data-stu-id="aec01-112">Security Mode</span></span>|<span data-ttu-id="aec01-113">İleti</span><span class="sxs-lookup"><span data-stu-id="aec01-113">Message</span></span>|  
|<span data-ttu-id="aec01-114">Birlikte Çalışabilirlik</span><span class="sxs-lookup"><span data-stu-id="aec01-114">Interoperability</span></span>|<span data-ttu-id="aec01-115">Evet, WS-Security, X.509 Sertifika belirteci profili uyumlu istemcileri ve Hizmetleri.</span><span class="sxs-lookup"><span data-stu-id="aec01-115">Yes, with WS-Security and X.509 certificate token profile compatible clients and services.</span></span>|  
|<span data-ttu-id="aec01-116">Kimlik doğrulaması</span><span class="sxs-lookup"><span data-stu-id="aec01-116">Authentication</span></span>|<span data-ttu-id="aec01-117">İstemci ve sunucu, karşılıklı kimlik doğrulaması.</span><span class="sxs-lookup"><span data-stu-id="aec01-117">Mutual authentication of the server and client.</span></span>|  
|<span data-ttu-id="aec01-118">Bütünlüğü</span><span class="sxs-lookup"><span data-stu-id="aec01-118">Integrity</span></span>|<span data-ttu-id="aec01-119">Evet</span><span class="sxs-lookup"><span data-stu-id="aec01-119">Yes</span></span>|  
|<span data-ttu-id="aec01-120">Gizliliği</span><span class="sxs-lookup"><span data-stu-id="aec01-120">Confidentiality</span></span>|<span data-ttu-id="aec01-121">Evet</span><span class="sxs-lookup"><span data-stu-id="aec01-121">Yes</span></span>|  
|<span data-ttu-id="aec01-122">Taşıma</span><span class="sxs-lookup"><span data-stu-id="aec01-122">Transport</span></span>|<span data-ttu-id="aec01-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="aec01-123">HTTP</span></span>|  
|<span data-ttu-id="aec01-124">Bağlama</span><span class="sxs-lookup"><span data-stu-id="aec01-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="aec01-125">Hizmet</span><span class="sxs-lookup"><span data-stu-id="aec01-125">Service</span></span>  
 <span data-ttu-id="aec01-126">Aşağıdaki kod ve yapılandırma, bağımsız olarak çalışmaya yöneliktir.</span><span class="sxs-lookup"><span data-stu-id="aec01-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="aec01-127">Aşağıdakilerden birini yapın:</span><span class="sxs-lookup"><span data-stu-id="aec01-127">Do one of the following:</span></span>  
  
-   <span data-ttu-id="aec01-128">Kod ile yapılandırma kullanarak tek başına bir hizmet oluşturun.</span><span class="sxs-lookup"><span data-stu-id="aec01-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="aec01-129">Sağlanan Yapılandırması'nı kullanarak bir hizmet oluşturma, ancak tüm uç noktalar tanımlamaz.</span><span class="sxs-lookup"><span data-stu-id="aec01-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="aec01-130">Kod</span><span class="sxs-lookup"><span data-stu-id="aec01-130">Code</span></span>  
 <span data-ttu-id="aec01-131">Aşağıdaki kodun gösterdiği ileti güvenliği kullanan bir hizmet uç noktası oluşturur.</span><span class="sxs-lookup"><span data-stu-id="aec01-131">The following code shows creates a service endpoint that uses message security.</span></span> <span data-ttu-id="aec01-132">Hizmete kendi kimliğini doğrulamak için bir sertifika gerektirir.</span><span class="sxs-lookup"><span data-stu-id="aec01-132">The service requires a certificate to authenticate itself.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#13)]
 [!code-vb[C_SecurityScenarios#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#13)]  
  
### <a name="configuration"></a><span data-ttu-id="aec01-133">Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="aec01-133">Configuration</span></span>  
 <span data-ttu-id="aec01-134">Aşağıdaki yapılandırmayı kod yerine aynı hizmet oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="aec01-134">The following configuration can be used instead of the code to create the same service.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="serviceCredentialBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"   
                                storeLocation="LocalMachine"  
                                storeName="My"   
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="serviceCredentialBehavior"   
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="InteropCertificateBinding"  
                  name="WSHttpBinding_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="InteropCertificateBinding">  
          <security mode="Message">  
            <message clientCredentialType="Certificate"  
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="aec01-135">İstemci</span><span class="sxs-lookup"><span data-stu-id="aec01-135">Client</span></span>  
 <span data-ttu-id="aec01-136">Aşağıdaki kod ve yapılandırma, bağımsız olarak çalışmaya yöneliktir.</span><span class="sxs-lookup"><span data-stu-id="aec01-136">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="aec01-137">Aşağıdakilerden birini yapın:</span><span class="sxs-lookup"><span data-stu-id="aec01-137">Do one of the following:</span></span>  
  
-   <span data-ttu-id="aec01-138">Bir tek başına istemci kodu (ve istemci kodu) kullanarak oluşturun.</span><span class="sxs-lookup"><span data-stu-id="aec01-138">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="aec01-139">Herhangi bir uç nokta adresi tanımlamıyor bir istemci oluşturun.</span><span class="sxs-lookup"><span data-stu-id="aec01-139">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="aec01-140">Bunun yerine, yapılandırma adı bağımsız değişkeni olarak alan İstemci Oluşturucu kullanın.</span><span class="sxs-lookup"><span data-stu-id="aec01-140">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="aec01-141">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="aec01-141">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="aec01-142">Kod</span><span class="sxs-lookup"><span data-stu-id="aec01-142">Code</span></span>  
 <span data-ttu-id="aec01-143">Aşağıdaki kod, istemci oluşturur.</span><span class="sxs-lookup"><span data-stu-id="aec01-143">The following code creates the client.</span></span> <span data-ttu-id="aec01-144">İleti güvenlik modunu ayarlanır ve istemci kimlik bilgisi türü için sertifika ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="aec01-144">The security mode is set to Message, and the client credential type is set to Certificate.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#20)]
 [!code-vb[C_SecurityScenarios#20](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#20)]  
  
### <a name="configuration"></a><span data-ttu-id="aec01-145">Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="aec01-145">Configuration</span></span>  
 <span data-ttu-id="aec01-146">İstemciyi yapılandırır.</span><span class="sxs-lookup"><span data-stu-id="aec01-146">The following configures the client.</span></span> <span data-ttu-id="aec01-147">Bir istemci sertifikası kullanılarak belirtilmelidir [ \<clientCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span><span class="sxs-lookup"><span data-stu-id="aec01-147">A client certificate must be specified using the [\<clientCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span></span> <span data-ttu-id="aec01-148">Ayrıca, hizmet sertifikası kullanılarak belirtilir [ \<defaultCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md).</span><span class="sxs-lookup"><span data-stu-id="aec01-148">Also, the service certificate is specified using the [\<defaultCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientCredentialsBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="Cohowinery.com"   
                 storeLocation="CurrentUser"  
                 storeName="My"  
                 x509FindType="FindBySubjectName" />  
            <serviceCertificate>  
              <defaultCertificate findValue="Contoso.com"   
                                  storeLocation="CurrentUser"  
                                  storeName="TrustedPeople"  
                                  x509FindType="FindBySubjectName" />  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Certificate"   
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"   
                behaviorConfiguration="ClientCredentialsBehavior"  
                binding="wsHttpBinding"   
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <certificate encodedValue="Encoded_Value_Not_Shown" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="aec01-149">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="aec01-149">See also</span></span>
- [<span data-ttu-id="aec01-150">Güvenliğe Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="aec01-150">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="aec01-151">Windows Server AppFabric için güvenlik modeli</span><span class="sxs-lookup"><span data-stu-id="aec01-151">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
- [<span data-ttu-id="aec01-152">Nasıl yapılır: Oluşturma ve geçici sertifikalar WCF'de aktarım güvenliği için geliştirme sırasında yükleme</span><span class="sxs-lookup"><span data-stu-id="aec01-152">How to: Create and Install Temporary Certificates in WCF for Transport Security During Development</span></span>](https://go.microsoft.com/fwlink/?LinkId=244264)
