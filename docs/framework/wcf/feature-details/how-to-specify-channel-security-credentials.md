---
title: 'Nasıl yapılır: Kanal güvenliği kimlik bilgilerini belirtin'
ms.date: 03/30/2017
ms.assetid: f8e03f47-9c4f-4dd5-8f85-429e6d876119
ms.openlocfilehash: dac85a31a3194af3dff8a14461591d0f1a97399f
ms.sourcegitcommit: d9a0071d0fd490ae006c816f78a563b9946e269a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55066204"
---
# <a name="how-to-specify-channel-security-credentials"></a>Nasıl yapılır: Kanal güvenliği kimlik bilgilerini belirtin
Windows Communication Foundation (WCF) hizmet bilinen adını COM uygulamaları, WCF hizmetlerini çağırmak sağlar. Çoğu WCF hizmetleri, istemci kimlik doğrulaması ve yetkilendirme kimlik bilgilerini belirtmenizi gerektirir. Bir WCF hizmeti bir WCF istemciden çağrılırken, yönetilen kodda ya da bir uygulama yapılandırma dosyasında bu kimlik bilgileri belirtebilirsiniz. Bir WCF hizmeti bir COM uygulamasından çağrılırken kullanabileceğiniz <xref:System.ServiceModel.ComIntegration.IChannelCredentials> kimlik bilgilerini belirtmek için arabirim. Bu konuda kullanarak kimlik bilgilerini belirtmek için çeşitli yollar ortaya konacaktır <xref:System.ServiceModel.ComIntegration.IChannelCredentials> arabirimi.  
  
> [!NOTE]
>  <xref:System.ServiceModel.ComIntegration.IChannelCredentials> IDispatch tabanlı bir arabirim ve Visual Studio ortamında IntelliSense işlevselliği almazsınız.  
  
 Bu makalede tanımlanan WCF hizmetini kullanacak olan [ileti güvenliği örneği](../../../../docs/framework/wcf/samples/message-security-sample.md).  
  
### <a name="to-specify-a-client-certificate"></a>Bir istemci sertifikasını belirtmek için  
  
1.  Setup.bat dosyasının ileti güvenliği dizininde oluşturun ve gereken test sertifikaları yüklemek için çalıştırın.  
  
2.  İleti güvenliği projeyi açın.  
  
3.  Ekleme `[ServiceBehavior(Namespace="http://Microsoft.ServiceModel.Samples")]` için `ICalculator` arabirim tanımı.  
  
4.  Ekleme `bindingNamespace="http://Microsoft.ServiceModel.Samples"` hizmeti için App.config dosyasındaki endpoint etikete.  
  
5.  İleti güvenliği örneği oluşturun ve Service.exe çalıştırın. Internet Explorer'ı kullanın ve hizmetin URI için Gözat (http://localhost:8000/ServiceModelSamples/Service) hizmetinin çalıştığından emin olmak için.  
  
6.  Visual Basic 6.0 açın ve yeni bir standart .exe dosyası oluşturun. Forma bir düğme ekleyin ve aşağıdaki kodu için tıklama işleyicisi eklemek için Ekle düğmesine çift tıklayın:  
  
    ```  
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
        monString = monString + ", binding=BasicHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
        Set monikerProxy = GetObject(monString)  
  
        'Set the Service Certificate.  
     monikerProxy.ChannelCredentials.SetServiceCertificateAuthentication "CurrentUser", "NoCheck", "PeerOrChainTrust"  
    monikerProxy.ChannelCredentials.SetDefaultServiceCertificateFromStore "CurrentUser", "TrustedPeople", "FindBySubjectName", "localhost"  
  
        'Set the Client Certificate.  
        monikerProxy.ChannelCredentials.SetClientCertificateFromStoreByName "CN=client.com", "CurrentUser", "My"  
        MsgBox monikerProxy.Add(3, 4)  
    ```  
  
7.  Visual Basic uygulamasını çalıştırın ve sonuçları doğrulayın.  
  
     Visual Basic uygulamasını çağırma Ekle (3, 4) öğesinden sonuç içeren bir ileti kutusu görüntüler. <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromFile%28System.String%2CSystem.String%2CSystem.String%29> veya <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStoreByName%28System.String%2CSystem.String%2CSystem.String%29> yerine de kullanılabilir <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStore%28System.String%2CSystem.String%2CSystem.String%2CSystem.Object%29> istemci sertifikasını ayarlamak için:  
  
    ```  
    monikerProxy.ChannelCredentials.SetClientCertificateFromFile "C:\MyClientCert.pfx", "password", "DefaultKeySet"  
    ```  
  
> [!NOTE]
>  Bu çağrı çalışmak istemci sertifikası istemciyi çalıştıran makinede güvenilir olması gerekir.  
  
> [!NOTE]
>  Bilinen ad hatalı veya hizmet kullanılamıyor durumunda çağrısı `GetObject` "Geçersiz sözdizimi." belirten bir hata döndürür Bu hata iletisini alırsanız kullandığınız ad doğru olduğundan ve hizmetin kullanılabilir olduğundan emin olun.  
  
### <a name="to-specify-user-name-and-password"></a>Kullanıcı adı ve parola belirtmek için  
  
1.  Kullanılacak hizmet App.config dosyasını değiştirmek `wsHttpBinding`. Bu, kullanıcı adı ve parola doğrulaması gereklidir:  
  
  
  
2.  Ayarlama `clientCredentialType` için kullanıcı adı:  
  
  
  
3.  Visual Basic 6.0 açın ve yeni bir standart .exe dosyası oluşturun. Forma bir düğme ekleyin ve aşağıdaki kodu için tıklama işleyicisi eklemek için Ekle düğmesine çift tıklayın:  
  
    ```  
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set monikerProxy = GetObject(monString)  
  
    monikerProxy.ChannelCredentials.SetServiceCertificateAuthentication "CurrentUser", "NoCheck", "PeerOrChainTrust"  
    monikerProxy.ChannelCredentials.SetUserNameCredential "username", "password"  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
4.  Visual Basic uygulamasını çalıştırın ve sonuçları doğrulayın. Visual Basic uygulamasını çağırma Ekle (3, 4) öğesinden sonuç içeren bir ileti kutusu görüntüler.  
  
    > [!NOTE]
    >  Bu hizmet bilinen adı belirtilen bağlama için WSHttpBinding_ICalculator değiştirildi. Ayrıca bir geçerli kullanıcı adı ve parola çağrısında sağlamanız gerektiğini unutmayın. <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetUserNameCredential%28System.String%2CSystem.String%29>.  
  
### <a name="to-specify-windows-credentials"></a>Windows kimlik bilgilerini belirtmek için  
  
1.  Ayarlama `clientCredentialType` hizmet App.config dosyasında Windows için:  
  
  
  
2.  Visual Basic 6.0 açın ve yeni bir standart .exe dosyası oluşturun. Forma bir düğme ekleyin ve aşağıdaki kodu için tıklama işleyicisi eklemek için Ekle düğmesine çift tıklayın:  
  
    ```  
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", upnidentity=domain\userID"  
  
    Set monikerProxy = GetObject(monString)  
     monikerProxy.ChannelCredentials.SetWindowsCredential "domain", "userID", "password", 1, True  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
3.  Visual Basic uygulamasını çalıştırın ve sonuçları doğrulayın. Visual Basic uygulamasını çağırma Ekle (3, 4) öğesinden sonuç içeren bir ileti kutusu görüntüler.  
  
    > [!NOTE]
    >  "Etki alanı", "userID" ve "password" geçerli değerlerle değiştirmeniz gerekir.  
  
### <a name="to-specify-an-issue-token"></a>Bir sorun belirteci belirtmek için  
  
1.  Sorun belirteçleri yalnızca Birleşik güvenliği kullanan uygulamalar için kullanılır. Birleşik güvenliği hakkında daha fazla bilgi için bkz: [Federasyon ve verilen belirteçler](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md) ve [Federasyon örneği](../../../../docs/framework/wcf/samples/federation-sample.md).  
  
     Aşağıdaki Visual Basic kod örneği nasıl çağrılacağını gösterir <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29> yöntemi:  
  
    ```  
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/SomeService/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://SomeService.Samples"  
        monString = monString + ", binding=WSHttpBinding_ISomeContract, bindingNamespace=http://SomeService.Samples"  
  
        Set monikerProxy = GetObject(monString)  
    monikerProxy.SetIssuedToken("http://somemachine/sts", "bindingType", "binding")  
    ```  
  
     Bu yöntem için parametreler hakkında daha fazla bilgi için bkz. <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>.  
  
## <a name="see-also"></a>Ayrıca bkz.
- [Federasyon](../../../../docs/framework/wcf/feature-details/federation.md)
- [Nasıl yapılır: Federe bir hizmette kimlik bilgilerini yapılandırma](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [Nasıl yapılır: Federe istemci oluşturma](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [İleti Güvenliği](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)
- [Bağlamalar ve Güvenlik](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)
