---
title: Hata İşleme ve Bildirme Denetimini Genişletme
ms.date: 03/30/2017
ms.assetid: 45f996a7-fa00-45cb-9d6f-b368f5778aaa
ms.openlocfilehash: 09216d8b0ff58ac90a0fd6183f43fd2ccf82ad52
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/27/2019
ms.locfileid: "70039674"
---
# <a name="extending-control-over-error-handling-and-reporting"></a>Hata İşleme ve Bildirme Denetimini Genişletme
Bu örnek, <xref:System.ServiceModel.Dispatcher.IErrorHandler> arabirimi kullanarak bir Windows Communication Foundation (WCF) hizmetinde hata işleme ve hata raporlama üzerinde denetimin nasıl genişletileceğini gösterir. Örnek, hataları işlemek için hizmete eklenen bazı ek kod ile [çalışmaya](../../../../docs/framework/wcf/samples/getting-started-sample.md) başlama konusunda temel alır. İstemci birkaç hata koşulu zorlar. Hizmet hataları karşılar ve bunları bir dosyada günlüğe kaydeder.  
  
> [!NOTE]
> Bu örneğe ilişkin Kurulum yordamı ve derleme yönergeleri bu konunun sonunda bulunur.  
  
 Hizmetler hataları ele geçirebilir, işleme gerçekleştirebilir ve <xref:System.ServiceModel.Dispatcher.IErrorHandler> arabirim kullanarak hataların nasıl raporlanacağı etkisini etkileyebilir. Arabirimin uygulanıuygulanabilen iki yöntemi vardır: <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> ve. <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A> <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> Yöntemi, bir özel duruma yanıt olarak oluşturulan bir hata iletisini eklemenize, değiştirmenize veya gizlemesine olanak sağlar. <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A> Yöntemi hata işlemenin hata durumunda gerçekleşmesini sağlar ve ek hata işlemenin çalıştırılıp çalıştırılmadığını denetler.  
  
 Bu örnekte, `CalculatorErrorHandler` türü <xref:System.ServiceModel.Dispatcher.IErrorHandler> arabirimini uygular. İçinde  
  
 <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A>yöntemi, `CalculatorErrorHandler` c:\logs. içindeki Error. txt metin dosyasına hata günlüğü yazar. Örneğin hatayı günlüğe kaydettiğine ve bunu göstermez ve istemciye geri raporlanmasını sağlar.  
  
```  
public class CalculatorErrorHandler : IErrorHandler  
{  
        // Provide a fault. The Message fault parameter can be replaced, or set to  
        // null to suppress reporting a fault.  
  
        public void ProvideFault(Exception error, MessageVersion version, ref Message fault)  
        {  
        }  
  
        // HandleError. Log an error, then allow the error to be handled as usual.  
        // Return true if the error is considered as already handled  
  
        public bool HandleError(Exception error)  
        {  
            using (TextWriter tw = File.AppendText(@"c:\logs\error.txt"))  
            {  
                if (error != null)  
                {  
                    tw.WriteLine("Exception: " + error.GetType().Name + " - " + error.Message);  
                }  
                tw.Close();  
            }  
            return true;  
        }  
    }  
```  
  
 Bir hizmet ile bir hata işleyicisini kaydetme mekanizması olarak mevcuttur.`ErrorBehaviorAttribute` Bu öznitelik tek bir tür parametresi alır. Bu tür <xref:System.ServiceModel.Dispatcher.IErrorHandler> arabirimini uygulamalıdır ve genel, boş bir oluşturucuya sahip olmalıdır. Özniteliği daha sonra bu hata işleyicisi türünün bir örneğini başlatır ve hizmete kurar. Bunu, <xref:System.ServiceModel.Description.IServiceBehavior> arabirimini uygulayarak ve sonra hata işleyicisinin örneklerine eklemek için <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A> yöntemini kullanarak yapar.  
  
```  
// This attribute can be used to install a custom error handler for a service.  
public class ErrorBehaviorAttribute : Attribute, IServiceBehavior  
{  
    Type errorHandlerType;  
  
    public ErrorBehaviorAttribute(Type errorHandlerType)  
    {  
        this.errorHandlerType = errorHandlerType;  
    }  
  
    void IServiceBehavior.Validate(ServiceDescription description, ServiceHostBase serviceHostBase)  
    {  
    }  
  
    void IServiceBehavior.AddBindingParameters(ServiceDescription description, ServiceHostBase serviceHostBase, System.Collections.ObjectModel.Collection<ServiceEndpoint> endpoints, BindingParameterCollection parameters)  
    {  
    }  
  
    void IServiceBehavior.ApplyDispatchBehavior(ServiceDescription description, ServiceHostBase serviceHostBase)  
    {  
        IErrorHandler errorHandler;  
  
        try  
        {  
            errorHandler = (IErrorHandler)Activator.CreateInstance(errorHandlerType);  
        }  
        catch (MissingMethodException e)  
        {  
            throw new ArgumentException("The errorHandlerType specified in the ErrorBehaviorAttribute constructor must have a public empty constructor.", e);  
        }  
        catch (InvalidCastException e)  
        {  
            throw new ArgumentException("The errorHandlerType specified in the ErrorBehaviorAttribute constructor must implement System.ServiceModel.Dispatcher.IErrorHandler.", e);  
        }  
  
        foreach (ChannelDispatcherBase channelDispatcherBase in serviceHostBase.ChannelDispatchers)  
        {  
            ChannelDispatcher channelDispatcher = channelDispatcherBase as ChannelDispatcher;  
            channelDispatcher.ErrorHandlers.Add(errorHandler);  
        }                                                  
    }  
}  
```  
  
 Örnek, bir Hesaplayıcı hizmeti uygular. İstemci, geçersiz değerlere sahip parametreler sağlayarak hizmette iki hatanın oluşmasına neden olur. , `CalculatorErrorHandler` Hataları yerel <xref:System.ServiceModel.Dispatcher.IErrorHandler> bir dosyaya kaydetmek için arabirimini kullanır ve ardından istemciye geri bildirilmelerini sağlar. İstemci, sıfıra bölme ve bağımsız değişken olmayan bir koşula zorlar.  
  
```  
try  
{  
    Console.WriteLine("Forcing an error in Divide");  
    // Call the Divide service operation - trigger a divide by 0 error.  
    value1 = 22;  
    value2 = 0;  
    result = proxy.Divide(value1, value2);  
    Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
}  
catch (FaultException e)  
{  
    Console.WriteLine("FaultException: " + e.GetType().Name + " - " + e.Message);  
}  
catch (Exception e)  
{  
    Console.WriteLine("Exception: " + e.GetType().Name + " - " + e.Message);  
}  
```  
  
 Örneği çalıştırdığınızda, işlem istekleri ve yanıtları istemci konsol penceresinde görüntülenir. Sıfıra göre bölme ve bağımsız değişken dışı koşulların hata olarak raporlanmakta olduğunu görürsünüz. İstemcisini kapatmak için istemci penceresinde ENTER tuşuna basın.  
  
```  
Add(15,3) = 18  
Subtract(145,76) = 69  
Multiply(9,81) = 729  
Forcing an error in Divide  
FaultException: FaultException - Invalid Argument: The second argument must not be zero.  
Forcing an error in Factorial  
FaultException: FaultException - Invalid Argument: The argument must be greater than zero.  
  
Press <ENTER> to terminate client.  
```  
  
 C:\logs\errors.txt dosyası, hizmet tarafından karşılaşılan hatalar hakkında günlüğe kaydedilen bilgileri içerir. Hizmetin dizine yazabilmesi için hizmetin çalıştığı işlemin (genellikle ASP.NET veya ağ hizmeti), dizine yazma iznine sahip olduğundan emin olun.  
  
```  
Fault: Reason = Invalid Argument: The second argument must not be zero.  
Fault: Reason = Invalid Argument: The argument must be greater than zero.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Örneği ayarlamak, derlemek ve çalıştırmak için  
  
1. [Windows Communication Foundation Örnekleri Için tek seferlik Kurulum yordamını](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)gerçekleştirdiğinizden emin olun.  
  
2. Çözümü derlemek için [Windows Communication Foundation örnekleri oluşturma](../../../../docs/framework/wcf/samples/building-the-samples.md)bölümündeki yönergeleri izleyin.  
  
3. Error. txt dosyası için c:\logs. dizinini oluşturduğunuzdan emin olun. Veya ' de `CalculatorErrorHandler.HandleError`kullanılan dosya adını değiştirebilirsiniz.  
  
4. Örneği tek veya bir çapraz makine yapılandırmasında çalıştırmak için [Windows Communication Foundation Örnekleri çalıştırma](../../../../docs/framework/wcf/samples/running-the-samples.md)bölümündeki yönergeleri izleyin.  
  
> [!IMPORTANT]
> Örnekler makinenizde zaten yüklü olabilir. Devam etmeden önce aşağıdaki (varsayılan) dizini denetleyin.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Bu dizin yoksa, tüm Windows Communication Foundation (WCF) ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri indirmek için [Windows Communication Foundation (WCF) ve Windows Workflow Foundation (WF) örneklerine .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) ' e gidin. Bu örnek, aşağıdaki dizinde bulunur.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\ErrorHandling`  
