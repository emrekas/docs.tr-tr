---
title: Özel Bağlama Kesinliği
ms.date: 03/30/2017
ms.assetid: 6e13bf96-5de0-4476-b646-5f150774418d
ms.openlocfilehash: c0f72c8216492b48de8c863dc35880d3c0034ef2
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/27/2019
ms.locfileid: "70045660"
---
# <a name="custom-binding-imperative"></a>Özel Bağlama Kesinliği
Örnek, bir yapılandırma dosyası veya Windows Communication Foundation (WCF) tarafından oluşturulan bir istemci kullanılmadan özel bağlamaları tanımlamak ve kullanmak için, zorunlu kodun nasıl yazılacağını gösterir. Bu örnek, güvenilir bir HTTP tabanlı bağlama oluşturmak için HTTP taşıması ve güvenilir oturum kanalı tarafından belirtilen özellikleri birleştirir. Bu örnek, bir Hesaplayıcı hizmeti uygulayan [kullanmaya](../../../../docs/framework/wcf/samples/getting-started-sample.md) Başlarken hizmetini temel alır.  
  
> [!NOTE]
> Bu örneğe ilişkin Kurulum yordamı ve derleme yönergeleri bu konunun sonunda bulunur.  
  
 Hem istemcide hem de hizmette, iki bağlama öğesi (güvenilir oturum ve HTTP) içeren özel bir bağlama oluşturulur:  

```csharp
ReliableSessionBindingElement reliableSession = new ReliableSessionBindingElement();  
reliableSession.Ordered = true;  
  
HttpTransportBindingElement httpTransport = new HttpTransportBindingElement();  
httpTransport.AuthenticationScheme = System.Net.AuthenticationSchemes.Anonymous;  
httpTransport.HostNameComparisonMode = HostNameComparisonMode.StrongWildcard;  
  
CustomBinding binding = new CustomBinding(reliableSession, httpTransport);  
```
  
 Hizmette, ServiceHost öğesine bir uç nokta eklenerek bağlama kullanılır:  

```csharp
serviceHost.AddServiceEndpoint(typeof(ICalculator), binding, "");  
```

 İstemci üzerinde, bağlama bir <xref:System.ServiceModel.ChannelFactory> hizmeti tarafından hizmete bir kanal oluşturmak için kullanılır:  

```csharp
EndpointAddress address = new EndpointAddress("http://localhost:8000/servicemodelsamples/service");  
ChannelFactory<ICalculator> channelFactory = new ChannelFactory<ICalculator>(binding, address);  
ICalculator channel = channelFactory.CreateChannel();  
```

 Bu kanal daha sonra hizmetle etkileşimde bulunmak için kullanılır:  

```csharp
// Call the Add service operation.  
double value1 = 100.00D;  
double value2 = 15.99D;  
double result = channel.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
```

 Örneği çalıştırdığınızda, işlem istekleri ve yanıtları istemci konsol penceresinde görüntülenir. İstemcisini kapatmak için istemci penceresinde ENTER tuşuna basın.  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Örneği ayarlamak, derlemek ve çalıştırmak için  
  
1. [Windows Communication Foundation Örnekleri Için tek seferlik Kurulum yordamını](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)gerçekleştirdiğinizden emin olun.  
  
2. Çözümün C# veya Visual Basic .NET sürümünü oluşturmak Için [Windows Communication Foundation örnekleri oluşturma](../../../../docs/framework/wcf/samples/building-the-samples.md)konusundaki yönergeleri izleyin.  
  
3. Örneği tek veya bir çapraz makine yapılandırmasında çalıştırmak için [Windows Communication Foundation Örnekleri çalıştırma](../../../../docs/framework/wcf/samples/running-the-samples.md)bölümündeki yönergeleri izleyin.  
  
> [!IMPORTANT]
> Örnekler makinenizde zaten yüklü olabilir. Devam etmeden önce aşağıdaki (varsayılan) dizini denetleyin.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Bu dizin yoksa, tüm Windows Communication Foundation (WCF) ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri indirmek için [Windows Communication Foundation (WCF) ve Windows Workflow Foundation (WF) örneklerine .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) ' e gidin. Bu örnek, aşağıdaki dizinde bulunur.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\Custom\Imperative`  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Özel bağlama örnekleri](custom-binding.md)
