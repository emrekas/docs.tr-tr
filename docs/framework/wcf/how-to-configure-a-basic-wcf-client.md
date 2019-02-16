---
title: 'Nasıl yapılır: Temel Windows Communication Foundation istemcisi yapılandırma'
ms.date: 09/14/2018
helpviewer_keywords:
- WCF clients [WCF], configuring
ms.assetid: d067b86d-afb0-47bf-94f6-45180a3d8d78
ms.openlocfilehash: 18acec48b2af78877f99335da38ccb0ae8942824
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/16/2019
ms.locfileid: "56332331"
---
# <a name="how-to-configure-a-basic-windows-communication-foundation-client"></a>Nasıl yapılır: Temel Windows Communication Foundation istemcisi yapılandırma

Beşinci altı görev temel Windows Communication Foundation (WCF) uygulaması oluşturmak için gereken budur. Tüm altı görevleri genel bakış için bkz. [başlangıç Öğreticisi](../../../docs/framework/wcf/getting-started-tutorial.md) konu.

Bu konuda ele alınmıştır kullanılarak oluşturulan istemci yapılandırma dosyası **hizmet Başvurusu Ekle** Visual Studio işlevselliğini veya [ServiceModel meta veri yardımcı Programracı (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). İstemci yapılandırması, istemcinin hizmete erişmek için kullandığı uç noktası belirtme oluşur. Bir uç nokta bir adresi, bağlama ve bir sözleşme vardır ve her birinin istemci yapılandırma sürecinde belirtilmelidir.

## <a name="configure-a-windows-communication-foundation-client"></a>Bir Windows Communication Foundation istemcisi yapılandırma

GettingStartedClient projeden oluşturulan yapılandırma dosyası (App.config) açın. Aşağıdaki örnek, oluşturulan yapılandırma dosyasının bir görünümüdür. Altında [ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) bölümünde, bulma [ \<uç noktası >](../configure-apps/file-schema/wcf/endpoint-element.md) öğesi.

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
        <startup>
          <!-- specifies the version of WCF to use-->
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5,Profile=Client" />
        </startup>
        <system.serviceModel>
            <bindings>
                <!-- Uses wsHttpBinding-->
                <wsHttpBinding>
                    <binding name="WSHttpBinding_ICalculator" />
                </wsHttpBinding>
            </bindings>
            <client>
                <!-- specifies the endpoint to use when calling the service -->
                <endpoint address="http://localhost:8000/ServiceModelSamples/Service/CalculatorService"
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">
                    <identity>
                        <userPrincipalName value="migree@redmond.corp.microsoft.com" />
                    </identity>
                </endpoint>
            </client>
        </system.serviceModel>
    </configuration>
```

Bu örnekte istemci şu adresten bulunduğu hizmete erişmek için kullandığı uç nokta yapılandırır: `http://localhost:8000/ServiceModelSamples/Service/CalculatorService`.

Uç nokta öğesini belirten `ServiceReference1.ICalculator` hizmet sözleşmesi WCF istemci ve hizmet arasındaki iletişim için kullanılır. WCF kanalı sistem tarafından sağlanan ile yapılandırılmış <xref:System.ServiceModel.WSHttpBinding>. Bu sözleşme kullanılarak oluşturulmuş **hizmet Başvurusu Ekle** Visual Studio'da. Bu temelde GettingStartedLib projede tanımlanan sözleşme bir kopyasıdır. <xref:System.ServiceModel.WSHttpBinding> Bağlama HTTP taşıma, birlikte çalışabilen güvenlik ve diğer yapılandırma ayrıntılarını belirtir.

Bu yapılandırma ile oluşturulan istemciyi kullanma hakkında daha fazla bilgi için bkz. [nasıl yapılır: Bir istemci kullanın](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [Nasıl yapılır: WCF istemci kullanma](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Hizmetler ve İstemcileri Yapılandırmak için Bağlamaları Kullanma](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [ServiceModel Meta Veri Yardımcı Programı Aracı (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Nasıl yapılır: Bir istemci oluşturma](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [Başlarken](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [Kendini Barındırma](../../../docs/framework/wcf/samples/self-host.md)