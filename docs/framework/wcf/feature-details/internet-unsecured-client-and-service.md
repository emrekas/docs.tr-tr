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
# <a name="internet-unsecured-client-and-service"></a>İnternet Güvenli Olmayan Hizmet ve İstemci
Aşağıdaki çizimde, bir genel, güvenli olmayan Windows Communication Foundation (WCF) istemci ve hizmet örneği gösterilmektedir:  
  
 ![Güvenli olmayan bir Internet senaryoyu gösteren ekran görüntüsü](./media/internet-unsecured-client-and-service/public-unsecured-internet.gif)  
  
|Özelliği|Açıklama|  
|--------------------|-----------------|  
|Güvenlik modu|None|  
|Taşıma|HTTP|  
|Bağlama|<xref:System.ServiceModel.BasicHttpBinding> kodda veya [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) yapılandırma öğesi.|  
|Birlikte Çalışabilirlik|Mevcut Web hizmeti istemcileri ve Hizmetleri ile|  
|Kimlik doğrulaması|None|  
|Bütünlüğü|None|  
|Gizliliği|None|  
  
## <a name="service"></a>Hizmet  
 Aşağıdaki kod ve yapılandırma, bağımsız olarak çalışmaya yöneliktir. Aşağıdakilerden birini yapın:  
  
- Kod ile yapılandırma kullanarak tek başına bir hizmet oluşturun.  
  
- Sağlanan Yapılandırması'nı kullanarak bir hizmet oluşturma, ancak tüm uç noktalar tanımlamaz.  
  
### <a name="code"></a>Kod  
 Aşağıdaki kod, bir uç nokta ile herhangi bir güvenliğin oluşturma işlemini gösterir. Varsayılan olarak, <xref:System.ServiceModel.BasicHttpBinding> sahip ayarlamak kullanılan güvenlik modunu <xref:System.ServiceModel.BasicHttpSecurityMode.None>.  
  
 [!code-csharp[C_UnsecuredService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#1)]
 [!code-vb[C_UnsecuredService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#1)]  
  
### <a name="service-configuration"></a>Hizmet yapılandırması  
 Aşağıdaki kod, yapılandırma kullanarak aynı uç noktasını ayarlar.  
  
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
  
## <a name="client"></a>İstemci  
 Aşağıdaki kod ve yapılandırma, bağımsız olarak çalışmaya yöneliktir. Aşağıdakilerden birini yapın:  
  
- Bir tek başına istemci kodu (ve istemci kodu) kullanarak oluşturun.  
  
- Herhangi bir uç nokta adresi tanımlamıyor bir istemci oluşturun. Bunun yerine, yapılandırma adı bağımsız değişkeni olarak alan İstemci Oluşturucu kullanın. Örneğin:  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a>Kod  
 Aşağıdaki kod güvenli olmayan bir uç noktaya erişen temel bir WCF istemcisi gösterir.  
  
 [!code-csharp[C_UnsecuredClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#1)]
 [!code-vb[C_UnsecuredClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#1)]  
  
### <a name="client-configuration"></a>İstemci Yapılandırması  
 Aşağıdaki kod, istemciyi yapılandırır.  
  
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
  
## <a name="see-also"></a>Ayrıca bkz.

- [Ortak Güvenlik Senaryoları](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)
- [Güvenliğe Genel Bakış](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Windows Server AppFabric için güvenlik modeli](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
