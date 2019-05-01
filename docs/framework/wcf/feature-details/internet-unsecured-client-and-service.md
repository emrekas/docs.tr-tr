---
title: İnternet Güvenli Olmayan Hizmet ve İstemci
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 97a10d79-3e7d-4bd1-9a99-fd9807fd70bc
ms.openlocfilehash: ca6b028ef20095d6faeb125151772eedf1500fa0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62038733"
---
# <a name="internet-unsecured-client-and-service"></a><span data-ttu-id="6c064-102">İnternet Güvenli Olmayan Hizmet ve İstemci</span><span class="sxs-lookup"><span data-stu-id="6c064-102">Internet Unsecured Client and Service</span></span>
<span data-ttu-id="6c064-103">Aşağıdaki çizimde, bir genel, güvenli olmayan Windows Communication Foundation (WCF) istemci ve hizmet örneği gösterilmektedir:</span><span class="sxs-lookup"><span data-stu-id="6c064-103">The following illustration shows an example of a public, unsecured Windows Communication Foundation (WCF) client and service:</span></span>  
  
 ![Güvenli olmayan bir Internet senaryoyu gösteren ekran görüntüsü](./media/internet-unsecured-client-and-service/public-unsecured-internet.gif)  
  
|<span data-ttu-id="6c064-105">Özelliği</span><span class="sxs-lookup"><span data-stu-id="6c064-105">Characteristic</span></span>|<span data-ttu-id="6c064-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6c064-106">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="6c064-107">Güvenlik modu</span><span class="sxs-lookup"><span data-stu-id="6c064-107">Security Mode</span></span>|<span data-ttu-id="6c064-108">None</span><span class="sxs-lookup"><span data-stu-id="6c064-108">None</span></span>|  
|<span data-ttu-id="6c064-109">Taşıma</span><span class="sxs-lookup"><span data-stu-id="6c064-109">Transport</span></span>|<span data-ttu-id="6c064-110">HTTP</span><span class="sxs-lookup"><span data-stu-id="6c064-110">HTTP</span></span>|  
|<span data-ttu-id="6c064-111">Bağlama</span><span class="sxs-lookup"><span data-stu-id="6c064-111">Binding</span></span>|<span data-ttu-id="6c064-112"><xref:System.ServiceModel.BasicHttpBinding> kodda veya [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) yapılandırma öğesi.</span><span class="sxs-lookup"><span data-stu-id="6c064-112"><xref:System.ServiceModel.BasicHttpBinding> in code, or the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) element in configuration.</span></span>|  
|<span data-ttu-id="6c064-113">Birlikte Çalışabilirlik</span><span class="sxs-lookup"><span data-stu-id="6c064-113">Interoperability</span></span>|<span data-ttu-id="6c064-114">Mevcut Web hizmeti istemcileri ve Hizmetleri ile</span><span class="sxs-lookup"><span data-stu-id="6c064-114">With existing Web service clients and services</span></span>|  
|<span data-ttu-id="6c064-115">Kimlik doğrulaması</span><span class="sxs-lookup"><span data-stu-id="6c064-115">Authentication</span></span>|<span data-ttu-id="6c064-116">None</span><span class="sxs-lookup"><span data-stu-id="6c064-116">None</span></span>|  
|<span data-ttu-id="6c064-117">Bütünlüğü</span><span class="sxs-lookup"><span data-stu-id="6c064-117">Integrity</span></span>|<span data-ttu-id="6c064-118">None</span><span class="sxs-lookup"><span data-stu-id="6c064-118">None</span></span>|  
|<span data-ttu-id="6c064-119">Gizliliği</span><span class="sxs-lookup"><span data-stu-id="6c064-119">Confidentiality</span></span>|<span data-ttu-id="6c064-120">None</span><span class="sxs-lookup"><span data-stu-id="6c064-120">None</span></span>|  
  
## <a name="service"></a><span data-ttu-id="6c064-121">Hizmet</span><span class="sxs-lookup"><span data-stu-id="6c064-121">Service</span></span>  
 <span data-ttu-id="6c064-122">Aşağıdaki kod ve yapılandırma, bağımsız olarak çalışmaya yöneliktir.</span><span class="sxs-lookup"><span data-stu-id="6c064-122">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="6c064-123">Aşağıdakilerden birini yapın:</span><span class="sxs-lookup"><span data-stu-id="6c064-123">Do one of the following:</span></span>  
  
- <span data-ttu-id="6c064-124">Kod ile yapılandırma kullanarak tek başına bir hizmet oluşturun.</span><span class="sxs-lookup"><span data-stu-id="6c064-124">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="6c064-125">Sağlanan Yapılandırması'nı kullanarak bir hizmet oluşturma, ancak tüm uç noktalar tanımlamaz.</span><span class="sxs-lookup"><span data-stu-id="6c064-125">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6c064-126">Kod</span><span class="sxs-lookup"><span data-stu-id="6c064-126">Code</span></span>  
 <span data-ttu-id="6c064-127">Aşağıdaki kod, bir uç nokta ile herhangi bir güvenliğin oluşturma işlemini gösterir.</span><span class="sxs-lookup"><span data-stu-id="6c064-127">The following code shows how to create an endpoint with no security.</span></span> <span data-ttu-id="6c064-128">Varsayılan olarak, <xref:System.ServiceModel.BasicHttpBinding> sahip ayarlamak kullanılan güvenlik modunu <xref:System.ServiceModel.BasicHttpSecurityMode.None>.</span><span class="sxs-lookup"><span data-stu-id="6c064-128">By default, the <xref:System.ServiceModel.BasicHttpBinding> has the security mode set to <xref:System.ServiceModel.BasicHttpSecurityMode.None>.</span></span>  
  
 [!code-csharp[C_UnsecuredService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#1)]
 [!code-vb[C_UnsecuredService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#1)]  
  
### <a name="service-configuration"></a><span data-ttu-id="6c064-129">Hizmet yapılandırması</span><span class="sxs-lookup"><span data-stu-id="6c064-129">Service Configuration</span></span>  
 <span data-ttu-id="6c064-130">Aşağıdaki kod, yapılandırma kullanarak aynı uç noktasını ayarlar.</span><span class="sxs-lookup"><span data-stu-id="6c064-130">The following code sets up the same endpoint using configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="basicHttpBinding"  
                  bindingConfiguration="Basic_Unsecured"   
                  name="BasicHttp_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="Basic_Unsecured" />  
      </basicHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="6c064-131">İstemci</span><span class="sxs-lookup"><span data-stu-id="6c064-131">Client</span></span>  
 <span data-ttu-id="6c064-132">Aşağıdaki kod ve yapılandırma, bağımsız olarak çalışmaya yöneliktir.</span><span class="sxs-lookup"><span data-stu-id="6c064-132">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="6c064-133">Aşağıdakilerden birini yapın:</span><span class="sxs-lookup"><span data-stu-id="6c064-133">Do one of the following:</span></span>  
  
- <span data-ttu-id="6c064-134">Bir tek başına istemci kodu (ve istemci kodu) kullanarak oluşturun.</span><span class="sxs-lookup"><span data-stu-id="6c064-134">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="6c064-135">Herhangi bir uç nokta adresi tanımlamıyor bir istemci oluşturun.</span><span class="sxs-lookup"><span data-stu-id="6c064-135">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="6c064-136">Bunun yerine, yapılandırma adı bağımsız değişkeni olarak alan İstemci Oluşturucu kullanın.</span><span class="sxs-lookup"><span data-stu-id="6c064-136">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="6c064-137">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="6c064-137">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="6c064-138">Kod</span><span class="sxs-lookup"><span data-stu-id="6c064-138">Code</span></span>  
 <span data-ttu-id="6c064-139">Aşağıdaki kod güvenli olmayan bir uç noktaya erişen temel bir WCF istemcisi gösterir.</span><span class="sxs-lookup"><span data-stu-id="6c064-139">The following code shows a basic WCF client that accesses an unsecured endpoint.</span></span>  
  
 [!code-csharp[C_UnsecuredClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#1)]
 [!code-vb[C_UnsecuredClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#1)]  
  
### <a name="client-configuration"></a><span data-ttu-id="6c064-140">İstemci Yapılandırması</span><span class="sxs-lookup"><span data-stu-id="6c064-140">Client Configuration</span></span>  
 <span data-ttu-id="6c064-141">Aşağıdaki kod, istemciyi yapılandırır.</span><span class="sxs-lookup"><span data-stu-id="6c064-141">The following code configures the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="BasicHttpBinding_ICalculator" >  
          <security mode="None">  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://localhost/Calculator/Unsecured"  
          binding="basicHttpBinding"   
          bindingConfiguration="BasicHttpBinding_ICalculator"  
          contract="ICalculator"   
          name="BasicHttpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c064-142">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="6c064-142">See also</span></span>

- [<span data-ttu-id="6c064-143">Ortak Güvenlik Senaryoları</span><span class="sxs-lookup"><span data-stu-id="6c064-143">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)
- [<span data-ttu-id="6c064-144">Güvenliğe Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="6c064-144">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="6c064-145">Windows Server AppFabric için güvenlik modeli</span><span class="sxs-lookup"><span data-stu-id="6c064-145">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
