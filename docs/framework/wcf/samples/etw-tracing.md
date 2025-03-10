---
title: ETW İzleme
ms.date: 03/30/2017
ms.assetid: ac99a063-e2d2-40cc-b659-d23c2f783f92
ms.openlocfilehash: c484e3438ad3512bd6186297f3edf8068a60795e
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044999"
---
# <a name="etw-tracing"></a>ETW İzleme
Bu örnek, `ETWTraceListener` Windows için olay izleme (ETW) ve bu örnekle birlikte sunulan uçtan uca (e2e) izlemenin nasıl uygulanacağını gösterir. Örnek, [Başlarken](../../../../docs/framework/wcf/samples/getting-started-sample.md) ' i temel alır ve ETW izleme içerir.  
  
> [!NOTE]
> Bu örneğe ilişkin Kurulum yordamı ve derleme yönergeleri bu konunun sonunda bulunur.  
  
 Bu örnek, [izleme ve Ileti günlüğe kaydetme](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md)hakkında bilgi sahibi olduğunuzu varsayar.  
  
 <xref:System.Diagnostics> İzleme modelindeki her izleme kaynağı, verilerin nerede ve nasıl izlendiğinizi tespit eden birden fazla izleme dinleyicilerine sahip olabilir. Dinleyici türü, izleme verilerinin günlüğe kaydedildiği biçimi tanımlar. Aşağıdaki kod örneği, bir dinleyicinin yapılandırmaya nasıl ekleneceğini gösterir.  
  
```xml  
<system.diagnostics>  
    <sources>  
        <source name="System.ServiceModel"   
             switchValue="Verbose,ActivityTracing"  
             propagateActivity="true">  
            <listeners>  
                <add type=  
                   "System.Diagnostics.DefaultTraceListener"  
                   name="Default">  
                   <filter type="" />  
                </add>  
                <add name="ETW">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
    </sources>  
    <sharedListeners>  
        <add type=  
            "Microsoft.ServiceModel.Samples.EtwTraceListener, ETWTraceListener"  
            name="ETW" traceOutputOptions="Timestamp">  
            <filter type="" />  
       </add>  
    </sharedListeners>  
</system.diagnostics>  
```  
  
 Bu dinleyiciyi kullanmadan önce, bir ETW Izleme oturumunun başlatılmış olması gerekir. Bu oturum, Logman. exe veya tracelog. exe kullanılarak başlatılabilir. Bu örneğe eklenen bir SetupETW. bat dosyası, oturumu kapatmak ve günlük dosyasını tamamlamak için bir CleanupETW. bat dosyası ile birlikte ETW Izleme oturumunu ayarlayabilmeniz için eklenmiştir.  
  
> [!NOTE]
> Bu örneğe ilişkin Kurulum yordamı ve derleme yönergeleri bu konunun sonunda bulunur. Bu araçlar hakkında daha fazla bilgi için bkz.<https://go.microsoft.com/fwlink/?LinkId=56580>  
  
 ETWTraceListener kullanılırken izlemeler ikili. etl dosyalarında günlüğe kaydedilir. ServiceModel izleme açık olduğunda, oluşturulan tüm izlemeler aynı dosyada görünür. . Etl ve. svclog dosyalarını görüntülemek için [hizmet Izleme Görüntüleyicisi aracı 'nı (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) kullanın. Görüntüleyici, bir iletiyi kaynağından hedefine ve tüketim noktasına izlemeyi olanaklı kılan sistemin uçtan uca bir görünümünü oluşturur.  
  
 ETW Izleme dinleyicisi döngüsel günlüğe yazmayı destekler. Bu özelliği etkinleştirmek için **Başlat**, **Çalıştır** ve yazın `cmd` ' a giderek bir komut konsolu başlatın. Aşağıdaki komutta, `<logfilename>` parametresini günlük dosyanızın adıyla değiştirin.  
  
```  
logman create trace Wcf -o <logfilename> -p "{411a0819-c24b-428c-83e2-26b41091702e}" -f bincirc -max 1000  
```  
  
 `-f` Ve`-max` anahtarları isteğe bağlıdır. İkili dairesel biçimi ve en fazla 1000MB günlük boyutunu belirtir. `-p` Anahtar, izleme sağlayıcısını belirtmek için kullanılır. Örneğimizde, `"{411a0819-c24b-428c-83e2-26b41091702e}"` "XML ETW örnek sağlayıcısı" için GUID kullanılır.  
  
 Oturumu başlatmak için aşağıdaki komutu yazın.  
  
```  
Logman start Wcf  
```  
  
 Günlüğe kaydetmeyi bitirdikten sonra, aşağıdaki komutla oturumu durdurabilirsiniz.  
  
```  
Logman stop Wcf  
```  
  
 Bu işlem, [hizmet Izleme Görüntüleyicisi Aracı (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) veya tracerpt dahil olmak üzere seçim aracınkiyle işleyebilmeniz gereken ikili dairesel Günlükler oluşturur.  
  
 Ayrıca, döngüsel günlük kaydı gerçekleştirmek üzere alternatif bir dinleyici hakkında daha fazla bilgi için [dairesel izleme](../../../../docs/framework/wcf/samples/circular-tracing.md) örneğini inceleyebilirsiniz.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Örneği ayarlamak, derlemek ve çalıştırmak için  
  
1. [Windows Communication Foundation Örnekleri Için tek seferlik Kurulum yordamını](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)gerçekleştirdiğinizden emin olun.  
  
2. Çözümü derlemek için [Windows Communication Foundation örnekleri oluşturma](../../../../docs/framework/wcf/samples/building-the-samples.md)bölümündeki yönergeleri izleyin.  
  
    > [!NOTE]
    > RegisterProvider. bat, SetupETW. bat ve CleanupETW. bat komutlarını kullanmak için bir yerel yönetici hesabı altında çalıştırmanız gerekir. Veya daha sonra kullanıyorsanız [!INCLUDE[wv](../../../../includes/wv-md.md)] , komut istemi ' ni yükseltilmiş ayrıcalıklarla çalıştırmanız gerekir. Bunu yapmak için, komut istemi simgesine sağ tıklayın ve ardından **yönetici olarak çalıştır**' a tıklayın.  
  
3. Örneği çalıştırmadan önce, istemci ve sunucuda RegisterProvider. bat dosyasını çalıştırın. Bu, hizmet Izleme Görüntüleyicisi tarafından okunabilen izlemeler üretmek için elde edilen ETWTracingSampleLog. etl dosyasını ayarlar. Bu dosya C:\logs klasöründe bulunabilir. Bu klasör yoksa, oluşturulması veya bir izleme üretilmemelidir. Ardından, ETW Izleme oturumunu başlatmak için istemci ve sunucu bilgisayarlarında SetupETW. bat dosyasını çalıştırın. SetupETW. bat dosyası CS\Client klasörü altında bulunabilir.  
  
4. Örneği tek veya bir çoklu bilgisayar yapılandırmasında çalıştırmak için [Windows Communication Foundation Örnekleri çalıştırma](../../../../docs/framework/wcf/samples/running-the-samples.md)bölümündeki yönergeleri izleyin.  
  
5. Örnek tamamlandığında, ETWTracingSampleLog. etl dosyası oluşturma işleminin tamamlanması için CleanupETW. bat dosyasını çalıştırın.  
  
6. Hizmet Izleme Görüntüleyicisi içinden ETWTracingSampleLog. etl dosyasını açın. İkili biçimli dosyayı bir. svclog dosyası olarak kaydetmeniz istenecektir.  
  
7. ETW ve ServiceModel izlemelerini görüntülemek için hizmet Izleme Görüntüleyicisi içinden yeni oluşturulan. svclog dosyasını açın.  
  
> [!IMPORTANT]
> Örnekler bilgisayarınızda zaten yüklü olabilir. Devam etmeden önce aşağıdaki (varsayılan) dizini denetleyin.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Bu dizin yoksa, tüm Windows Communication Foundation (WCF) ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri indirmek için [Windows Communication Foundation (WCF) ve Windows Workflow Foundation (WF) örneklerine .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) ' e gidin. Bu örnek, aşağıdaki dizinde bulunur.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\AnalyticTrace`  
  
## <a name="see-also"></a>Ayrıca bkz.

- [AppFabric Izleme örnekleri](https://go.microsoft.com/fwlink/?LinkId=193959)
