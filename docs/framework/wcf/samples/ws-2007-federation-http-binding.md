---
title: WS 2007 Federasyon HTTP Bağlama
ms.date: 03/30/2017
ms.assetid: 91c1b477-a96e-4bf5-9330-5e9312113371
ms.openlocfilehash: 0a01cd3790e17f532b2f6405f83c9507ecc2f6fd
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/27/2019
ms.locfileid: "70038526"
---
# <a name="ws-2007-federation-http-binding"></a>WS 2007 Federasyon HTTP Bağlama
Bu örnek <xref:System.ServiceModel.WS2007FederationHttpBinding>, WS-Trust belirtiminin 1,3 sürümünü destekleyen federe senaryolar oluşturmak için kullanabileceğiniz standart bir bağlamanın kullanımını gösterir.  
  
> [!NOTE]
> Bu örneğe ilişkin Kurulum yordamı ve derleme yönergeleri bu konunun sonunda bulunur.  
  
 Örnek, konsol tabanlı bir istemci programından (Client. exe), konsol tabanlı bir güvenlik belirteci hizmeti programından (SecurityTokenService. exe) ve konsol tabanlı bir hizmet programından (Service. exe) oluşur. Hizmet, istek/yanıt iletişim modelini tanımlayan bir sözleşme uygular. Sözleşme, matematik `ICalculator` işlemlerini (`Add`, `Subtract` `Multiply`, ve`Divide`) sunan arabirim tarafından tanımlanır. İstemci, güvenlik belirteci hizmetinden (STS) bir güvenlik belirteci alır ve belirli bir matematik işlemi için hizmete zaman uyumlu istekler sağlar. Hizmet daha sonra sonuçla yanıt verir. İstemci etkinliği konsol penceresinde görünür.  
  
 Örnek, `ICalculator` sözleşmenin `ws2007FederationHttpBinding` öğesini kullanarak kullanılabilir hale getirir. İstemci üzerindeki bu bağlamanın yapılandırması aşağıdaki kodda gösterilmiştir.  
  
```xml  
<bindings>  
  <ws2007FederationHttpBinding>  
    <binding name="ServiceFed" >  
      <security mode ="Message">  
        <message issuedKeyType ="SymmetricKey"  
                 issuedTokenType ="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1" >  
          <!-- Endpoint address and binding for Security Token Service -->  
          <issuer address ="http://localhost:8000/sts/windows"   
                  binding ="ws2007HttpBinding" />                
        </message>  
      </security>  
    </binding>  
  </ws2007FederationHttpBinding>  
</bindings>  
```  
  
 Güvenlik >, değerhangigüvenlikmodununkullanılmasıgerektiğinibelirtir.`security` [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md) Bu örnekte, `message` güvenlik [ >\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md)içinde [ \<ileti >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) belirtilmesinin nedeni olan güvenlik kullanılır. `ICalculator` [İleti >\<](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) [ veren>öğesi,istemcininhizmettekimlikdoğrulamasıyapabilmesiiçinistemciye\<](../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md) bir güvenlik belirteci veren STS 'nin adresini ve bağlamayı belirtir.  
  
 Hizmette Bu bağlamanın yapılandırması aşağıdaki kodda gösterilmiştir.  
  
```xml  
<bindings>  
  <ws2007FederationHttpBinding>  
    <binding name="ServiceFed" >  
      <security mode ="Message">  
        <message issuedKeyType ="SymmetricKey"  
                 issuedTokenType ="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1" >  
          <!-- Metadata address for Security Token Service -->  
          <issuerMetadata address ="http://localhost:8000/sts/mex" >  
            <identity>  
              <certificateReference storeLocation ="CurrentUser"   
                                    storeName="TrustedPeople"   
                                    x509FindType ="FindBySubjectDistinguishedName"   
                                    findValue ="CN=STS" />  
            </identity>  
          </issuerMetadata>  
        </message>  
      </security>  
    </binding>  
  </ws2007FederationHttpBinding>  
</bindings>  
```  
  
 Güvenlik >, değerhangigüvenlikmodununkullanılmasıgerektiğinibelirtir.`security` [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md) Bu örnekte, `message` güvenlik [ >\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md)içinde [ \<ileti >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) belirtilmesinin nedeni olan güvenlik kullanılır. İletinin içindeki [IssuerMetadata > öğesi > STS için meta verileri almak üzere kullanılabilecek bir uç noktanın adresini ve kimliğini belirtir. \<](../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md) `ws2007FederationHttpBinding` [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md)  
  
 Hizmet davranışı aşağıdaki kodda gösterilmiştir.  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name ="ServiceBehaviour" >  
      <serviceDebug includeExceptionDetailInFaults ="true"/>  
      <serviceMetadata httpGetEnabled ="true"/>  
      <serviceCredentials>  
        <issuedTokenAuthentication>  
          <knownCertificates>  
            <add storeLocation ="LocalMachine"  
                 storeName="TrustedPeople"  
                 x509FindType="FindBySubjectDistinguishedName"  
                 findValue="CN=STS" />  
          </knownCertificates>  
        </issuedTokenAuthentication>  
        <serviceCertificate storeLocation ="LocalMachine"  
                            storeName ="My"  
                            x509FindType ="FindBySubjectDistinguishedName"  
                            findValue ="CN=localhost"/>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 [ \<IssuedTokenAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)>, hizmetin kimlik doğrulaması sırasında istemcilerin sunmalarına izin verdiği belirteçlerde kısıtlamalar belirlemesine izin verir. Bu yapılandırma, konu adı CN = STS olan bir sertifika tarafından imzalanmış belirteçlerin hizmet tarafından kabul edildiğini belirtir.  
  
 STS, standart <xref:System.ServiceModel.WS2007HttpBinding>kullanarak tek bir uç noktanın kullanılabilir olmasını sağlar. Hizmet, istemcilerden belirteç isteklerine yanıt verir. İstemcinin kimliği bir Windows hesabı kullanılarak doğrulandıysa, hizmet istemcinin kullanıcı adını bir talep olarak içeren bir belirteç yayınlar. Belirteç oluşturmanın bir parçası olarak STS, CN = STS sertifikasıyla ilişkili özel anahtarı kullanarak belirteci imzalar. Ayrıca, bir simetrik anahtar oluşturur ve CN = localhost sertifikasıyla ilişkili ortak anahtarı kullanarak şifreler. Belirteci istemciye döndürmekte sonra STS simetrik anahtarı da döndürür. İstemci verilen belirteci `ICalculator` hizmete sunar ve iletiyi bu anahtarla imzalayarak simetrik anahtarı bilir olduğunu kanıtlar.  
  
 Örneği çalıştırdığınızda, güvenlik belirteci isteği STS konsol penceresinde gösterilir. İşlemin istekleri ve yanıtları istemci ve hizmet konsolu pencereleri içinde görüntülenir. Uygulamayı kapatmak için konsol pencerelerinin herhangi birinde ENTER tuşuna basın.  

```
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714
Press <ENTER> to terminate client.
```

 Bu örneğe eklenen Setup. bat dosyası, şirket içinde barındırılan bir uygulamayı çalıştırmak için sunucuyu ve STS 'yi ilgili sertifikalarla yapılandırmanızı sağlar. Toplu iş dosyası, LocalMachine/Trustedkişileri sertifika deposunda iki sertifika oluşturur. İlk sertifika, CN = STS 'nin konu adına sahiptir ve STS tarafından, istemciye verdiği güvenlik belirteçlerini imzalamak için kullanılır. İkinci sertifika, CN = localhost konu adına sahiptir ve STS tarafından hizmetin şifresini çözebilmesi için bir anahtar şifrelemek için kullanılır.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Örneği ayarlamak, derlemek ve çalıştırmak için  
  
1. [Windows Communication Foundation Örnekleri Için tek seferlik Kurulum yordamını](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)gerçekleştirdiğinizden emin olun.  
  
2. Yönetici ayrıcalıklarına sahip bir Visual Studio Geliştirici Komut İstemi açın ve gerekli sertifikaları oluşturmak için Setup. bat dosyasını çalıştırın.  
  
 Bu toplu iş dosyası, Windows SDK dağıtılan certmgr. exe ve Makecert. exe ' yi kullanır. Ancak, bu araçları bulmak için betiği etkinleştirmek üzere Visual Studio komut istemi içinden Setup. bat dosyasını çalıştırmanız gerekir.  
  
1. Çözümün C# veya Visual Basic .NET sürümünü oluşturmak Için [Windows Communication Foundation örnekleri oluşturma](../../../../docs/framework/wcf/samples/building-the-samples.md)konusundaki yönergeleri izleyin.  
  
2. Örneği tek veya bir çoklu bilgisayar yapılandırmasında çalıştırmak için [Windows Communication Foundation Örnekleri çalıştırma](../../../../docs/framework/wcf/samples/running-the-samples.md)bölümündeki yönergeleri izleyin. Kullanıyorsanız [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)], Service. exe, Client. exe ve SecurityTokenService. exe ' yi yükseltilmiş ayrıcalıklarla çalıştırmanız gerekir (dosyalara sağ tıklayıp **yönetici olarak çalıştır**' a tıklayın).  
  
> [!IMPORTANT]
> Örnekler bilgisayarınızda zaten yüklü olabilir. Devam etmeden önce aşağıdaki (varsayılan) dizini denetleyin.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Bu dizin yoksa, tüm Windows Communication Foundation (WCF) ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri indirmek için [Windows Communication Foundation (WCF) ve Windows Workflow Foundation (WF) örneklerine .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) ' e gidin. Bu örnek, aşağıdaki dizinde bulunur.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\WS2007FederationHttp`  
