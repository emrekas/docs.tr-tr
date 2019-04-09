---
title: Windows İstemcisi ile İleti Güvenliği
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 01e7d0b8-10f9-45c3-a4c5-53d44dc61eb8
ms.openlocfilehash: 794a3d8e118cadd2a2752e1bbf85ef930deb2f27
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138651"
---
# <a name="message-security-with-a-windows-client"></a><span data-ttu-id="40a88-102">Windows İstemcisi ile İleti Güvenliği</span><span class="sxs-lookup"><span data-stu-id="40a88-102">Message Security with a Windows Client</span></span>
<span data-ttu-id="40a88-103">Bu senaryo, bir Windows Communication Foundation (WCF) istemci ve sunucu güvenli ileti güvenlik modunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="40a88-103">This scenario shows a Windows Communication Foundation (WCF) client and server secured by message security mode.</span></span> <span data-ttu-id="40a88-104">İstemci ve hizmet Windows kimlik bilgilerini kullanarak kimlik doğrulaması yapılır.</span><span class="sxs-lookup"><span data-stu-id="40a88-104">The client and service are authenticated using Windows credentials.</span></span>  
  
 <span data-ttu-id="40a88-105">![İleti güvenliği Windows İstemcisi ile](../../../../docs/framework/wcf/feature-details/media/1c8618d4-0005-4022-beb6-32fd087a8c3c.gif "1c8618d4-0005-4022-beb6-32fd087a8c3c")</span><span class="sxs-lookup"><span data-stu-id="40a88-105">![Message security with a Windows client](../../../../docs/framework/wcf/feature-details/media/1c8618d4-0005-4022-beb6-32fd087a8c3c.gif "1c8618d4-0005-4022-beb6-32fd087a8c3c")</span></span>  
  
|<span data-ttu-id="40a88-106">Özelliği</span><span class="sxs-lookup"><span data-stu-id="40a88-106">Characteristic</span></span>|<span data-ttu-id="40a88-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="40a88-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="40a88-108">Güvenlik modu</span><span class="sxs-lookup"><span data-stu-id="40a88-108">Security Mode</span></span>|<span data-ttu-id="40a88-109">İleti</span><span class="sxs-lookup"><span data-stu-id="40a88-109">Message</span></span>|  
|<span data-ttu-id="40a88-110">Birlikte Çalışabilirlik</span><span class="sxs-lookup"><span data-stu-id="40a88-110">Interoperability</span></span>|<span data-ttu-id="40a88-111">Yalnızca WCF</span><span class="sxs-lookup"><span data-stu-id="40a88-111">WCF Only</span></span>|  
|<span data-ttu-id="40a88-112">Kimlik doğrulaması (sunucu)</span><span class="sxs-lookup"><span data-stu-id="40a88-112">Authentication (Server)</span></span>|<span data-ttu-id="40a88-113">İstemci ve sunucu, karşılıklı kimlik doğrulaması</span><span class="sxs-lookup"><span data-stu-id="40a88-113">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="40a88-114">Kimlik doğrulaması (istemci)</span><span class="sxs-lookup"><span data-stu-id="40a88-114">Authentication (Client)</span></span>|<span data-ttu-id="40a88-115">İstemci ve sunucu, karşılıklı kimlik doğrulaması</span><span class="sxs-lookup"><span data-stu-id="40a88-115">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="40a88-116">Bütünlüğü</span><span class="sxs-lookup"><span data-stu-id="40a88-116">Integrity</span></span>|<span data-ttu-id="40a88-117">Evet, paylaşılan bir güvenlik bağlamı kullanma</span><span class="sxs-lookup"><span data-stu-id="40a88-117">Yes, using shared security context</span></span>|  
|<span data-ttu-id="40a88-118">Gizliliği</span><span class="sxs-lookup"><span data-stu-id="40a88-118">Confidentiality</span></span>|<span data-ttu-id="40a88-119">Evet, paylaşılan bir güvenlik bağlamı kullanma</span><span class="sxs-lookup"><span data-stu-id="40a88-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="40a88-120">Taşıma</span><span class="sxs-lookup"><span data-stu-id="40a88-120">Transport</span></span>|<span data-ttu-id="40a88-121">NET. TCP</span><span class="sxs-lookup"><span data-stu-id="40a88-121">NET.TCP</span></span>|  
|<span data-ttu-id="40a88-122">Bağlama</span><span class="sxs-lookup"><span data-stu-id="40a88-122">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="40a88-123">Hizmet</span><span class="sxs-lookup"><span data-stu-id="40a88-123">Service</span></span>  
 <span data-ttu-id="40a88-124">Aşağıdaki kod ve yapılandırma, bağımsız olarak çalışmaya yöneliktir.</span><span class="sxs-lookup"><span data-stu-id="40a88-124">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="40a88-125">Aşağıdakilerden birini yapın:</span><span class="sxs-lookup"><span data-stu-id="40a88-125">Do one of the following:</span></span>  
  
-   <span data-ttu-id="40a88-126">Kod ile yapılandırma kullanarak tek başına bir hizmet oluşturun.</span><span class="sxs-lookup"><span data-stu-id="40a88-126">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="40a88-127">Sağlanan Yapılandırması'nı kullanarak bir hizmet oluşturma, ancak tüm uç noktalar tanımlamaz.</span><span class="sxs-lookup"><span data-stu-id="40a88-127">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="40a88-128">Kod</span><span class="sxs-lookup"><span data-stu-id="40a88-128">Code</span></span>  
 <span data-ttu-id="40a88-129">Aşağıdaki kod, ileti güvenliği Windows makine ile güvenli bir bağlam kurmak için kullandığı bir hizmet uç noktası oluşturma işlemini gösterir.</span><span class="sxs-lookup"><span data-stu-id="40a88-129">The following code shows how to create a service endpoint that uses message security to establish a secure context with a Windows machine.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#11)]
 [!code-vb[C_SecurityScenarios#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#11)]  
  
### <a name="configuration"></a><span data-ttu-id="40a88-130">Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="40a88-130">Configuration</span></span>  
 <span data-ttu-id="40a88-131">Aşağıdaki yapılandırmayı kod yerine barındırılan hizmeti kurmak için kullanılabilir:</span><span class="sxs-lookup"><span data-stu-id="40a88-131">The following configuration can be used instead of the code to set up the service:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration=""  
               name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"  
                  binding="netTcpBinding"  
                  bindingConfiguration="Windows"  
                  name="WindowsOverMessage"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="Windows">  
          <security mode="Message">  
            <message clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="40a88-132">İstemci</span><span class="sxs-lookup"><span data-stu-id="40a88-132">Client</span></span>  
 <span data-ttu-id="40a88-133">Aşağıdaki kod ve yapılandırma, bağımsız olarak çalışmaya yöneliktir.</span><span class="sxs-lookup"><span data-stu-id="40a88-133">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="40a88-134">Aşağıdakilerden birini yapın:</span><span class="sxs-lookup"><span data-stu-id="40a88-134">Do one of the following:</span></span>  
  
-   <span data-ttu-id="40a88-135">Bir tek başına istemci kodu (ve istemci kodu) kullanarak oluşturun.</span><span class="sxs-lookup"><span data-stu-id="40a88-135">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="40a88-136">Herhangi bir uç nokta adresi tanımlamıyor bir istemci oluşturun.</span><span class="sxs-lookup"><span data-stu-id="40a88-136">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="40a88-137">Bunun yerine, yapılandırma adı bağımsız değişkeni olarak alan İstemci Oluşturucu kullanın.</span><span class="sxs-lookup"><span data-stu-id="40a88-137">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="40a88-138">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="40a88-138">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="40a88-139">Kod</span><span class="sxs-lookup"><span data-stu-id="40a88-139">Code</span></span>  
 <span data-ttu-id="40a88-140">Aşağıdaki kod, bir istemci oluşturur.</span><span class="sxs-lookup"><span data-stu-id="40a88-140">The following code creates a client.</span></span> <span data-ttu-id="40a88-141">İleti modu güvenlik bağlamadır ve istemci kimlik bilgisi türü `Windows`.</span><span class="sxs-lookup"><span data-stu-id="40a88-141">The binding is to Message mode security, and the client credential type is set to `Windows`.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#18](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#18)]
 [!code-vb[C_SecurityScenarios#18](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#18)]  
  
### <a name="configuration"></a><span data-ttu-id="40a88-142">Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="40a88-142">Configuration</span></span>  
 <span data-ttu-id="40a88-143">Aşağıdaki yapılandırma, istemci özelliklerini ayarlamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="40a88-143">The following configuration is used to set the client properties.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
         <security mode="Message">  
            <message clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://machineName:8008/Calculator"   
                binding="netTcpBinding"  
                bindingConfiguration="NetTcpBinding_ICalculator"  
                contract="ICalculator"  
                name="NetTcpBinding_ICalculator">          
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="40a88-144">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="40a88-144">See also</span></span>

- [<span data-ttu-id="40a88-145">Güvenlik Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="40a88-145">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="40a88-146">Windows Server AppFabric için güvenlik modeli</span><span class="sxs-lookup"><span data-stu-id="40a88-146">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
