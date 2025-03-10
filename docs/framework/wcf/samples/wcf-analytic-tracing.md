---
title: WCF Analiz İzleme
ms.date: 03/30/2017
ms.assetid: 6029c7c7-3515-4d36-9d43-13e8f4971790
ms.openlocfilehash: ba4f1778059f7b960eebd42822048fa031e6961e
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044541"
---
# <a name="wcf-analytic-tracing"></a>WCF Analiz İzleme
Bu örnek, ' de [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]Windows Communication Foundation (WCF) tarafından ETW 'ye yazma işlemleri için kendi izleme olaylarınızın akışa nasıl ekleneceğini gösterir. Analitik izlemeler, yüksek performans cezası ödemeksizin hizmetlerinizin görünürlüğünü daha kolay hale getirmek için tasarlanmıştır. Bu örnek, <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> WCF hizmetleriyle tümleştirilen olayları yazmak için API 'lerinin nasıl kullanılacağını gösterir.  
  
 <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> API 'ler hakkında daha fazla bilgi için bkz <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>.  
  
 Windows 'da olay izleme hakkında daha fazla bilgi edinmek için bkz. [ETW Ile hata ayıklamayı ve performans ayarlamayı geliştirme](https://go.microsoft.com/fwlink/?LinkId=166488).  
  
## <a name="disposing-eventprovider"></a>EventProvider elden atılıyor  
 Bu örnek, uygulayan <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType> <xref:System.IDisposable?displayProperty=nameWithType>sınıfını kullanır. Bir WCF hizmeti için izlemeyi uygularken, hizmetin kullanım ömrü boyunca kaynaklarını kullanabilmeniz <xref:System.Diagnostics.Eventing.EventProvider>olasıdır. Bu nedenle ve okunabilirlik için bu örnek sarmalanmamış <xref:System.Diagnostics.Eventing.EventProvider>hiçbir şekilde yok. Bazı nedenlerle hizmetinizin izleme için farklı gereksinimleri varsa ve bu kaynağı atlamazsanız, bu örneği yönetilmeyen kaynakların elden atılamamasının en iyi uygulamalarına uygun olarak değiştirmeniz gerekir. Yönetilmeyen kaynakları elden atma hakkında daha fazla bilgi için bkz. [Dispose yöntemi uygulama](https://go.microsoft.com/fwlink/?LinkId=166436).  
  
## <a name="self-hosting-vs-web-hosting"></a>Kendi kendine barındırma ile Web barındırma  
 Web 'de barındırılan hizmetlerde, WCF 'nin analitik izlemeleri, izlemeleri yayan hizmeti belirlemek için kullanılan "HostReference" adlı bir alan sağlar. Genişletilebilir kullanıcı izlemeleri bu modele katılabilir ve bu örnekte bunu gerçekleştirmek için en iyi yöntemler gösterilmektedir. Sonuçta ortaya çıkan dizedeki Kanal '&#124;' karakteri göründüğünde bir Web ana bilgisayar başvurusunun biçimi aşağıdakilerden biri olabilir:  
  
- Uygulama kökte değilse.  
  
     \<SiteName >\<ApplicationVirtualPath >&#124;\<ServiceVirtualPath >&#124;\<ServiceName >  
  
- Uygulama kökde ise.  
  
     \<SiteName >&#124;\<ServiceVirtualPath >&#124;\<ServiceName >  
  
 Self-hosted Hizmetleri için, WCF 'nin analitik izlemeleri "HostReference" alanını doldurmamaktadır. Bu `WCFUserEventProvider` örnekteki sınıf, kendi kendine barındırılan bir hizmet tarafından kullanıldığında tutarlı bir şekilde davranır.  
  
## <a name="custom-event-details"></a>Özel olay ayrıntıları  
 WCF 'nin ETW olay sağlayıcısı bildirimi, WCF hizmeti yazarları tarafından hizmet kodu içinden yayınlanarak tasarlanan üç olay tanımlar. Aşağıdaki tabloda, üç olay dökümü gösterilmektedir.  
  
|Olay|Açıklama|Olay Kimliği|  
|-----------|-----------------|--------------|  
|UserDefinedInformationEventOccurred|Bu olayı, hizmetinize bir sorun olmayan bir not oluştuğunda ortaya çıkar. Örneğin, bir veritabanına başarıyla çağrı yaptıktan sonra bir olay yayabilirsiniz.|301|  
|Userdefinedwarninggerçekleşti|Bu olayı, gelecekte hata oluşmasına neden olabilecek bir sorun oluştuğunda göster. Örneğin, bir veritabanına yapılan çağrı başarısız olduğunda ancak gereksiz bir veri deposuna geri dönerek kurtarılamadığında bir uyarı olayı oluşturabilirsiniz.|302|  
|UserDefinedErrorOccurred|Hizmetiniz beklendiği gibi davranamazsa bu olayı gösterin. Örneğin, bir veritabanına yapılan çağrı başarısız olursa ve verileri başka bir yerden alamadıysanız bir olay oluşturabilirsiniz.|303|  
  
#### <a name="to-use-this-sample"></a>Bu örneği kullanmak için  
  
1. Visual Studio 2012 kullanarak Wcfanaltictracingextensibility. sln çözüm dosyasını açın.  
  
2. Çözümü derlemek için CTRL + SHIFT + B tuşlarına basın.  
  
3. Çözümü çalıştırmak için CTRL + F5 tuşlarına basın.  
  
     Web tarayıcısında, **Hesaplayıcı. svc**' ye tıklayın. Hizmet için WSDL belgesinin URI 'SI tarayıcıda görünmelidir. Bu URI 'yi kopyalayın.  
  
4. WCF test istemcisini (WcfTestClient. exe) çalıştırın.  
  
     WCF Test istemcisi (WcfTestClient. exe) konumunda `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`bulunur. Varsayılan Visual Studio 2012 install dir `C:\Program Files\Microsoft Visual Studio 10.0`.  
  
5. WCF Test istemcisi içinde **Dosya**' yı ve ardından **Hizmet Ekle**' yi seçerek hizmeti ekleyin.  
  
     Giriş kutusuna uç nokta adresini ekleyin.  
  
6. İletişim kutusunu kapatmak için **Tamam** ' ı tıklatın.  
  
     Icalsoltor hizmeti, sol bölmede **hizmet projelerim**altında eklenir.  
  
7. Olay Görüntüleyici uygulamasını açın.  
  
     Hizmeti çağırmadan önce Olay Görüntüleyicisi başlatın ve olay günlüğünün WCF hizmetinden yayılan izleme olaylarını dinlediğinden emin olun.  
  
8. **Başlat** menüsünde, **Yönetim Araçları**' nı seçin ve ardından **Olay Görüntüleyicisi**. **Analitik** ve **hata ayıklama** günlüklerini etkinleştirin.  
  
9. Olay Görüntüleyicisi ' deki ağaç görünümünde **Olay Görüntüleyicisi**, **uygulamalar ve hizmetler günlükleri**, **Microsoft**, **Windows**ve ardından **uygulama sunucusu-uygulamalar**' a gidin. **Uygulama sunucusu-uygulamalar**' a sağ tıklayın, **Görünüm**' ü seçin ve ardından **analitik ve hata ayıklama günlüklerini görüntüleyin**.  
  
     **Analitik ve hata ayıklama günlüklerini göster** seçeneğinin işaretli olduğundan emin olun. **Analitik** günlüğü etkinleştirin.  
  
     Olay Görüntüleyicisi 'daki ağaç görünümünde **Olay Görüntüleyicisi**, **uygulama ve hizmet günlükleri**, **Microsoft**, **Windows**, **uygulama sunucusu-uygulamalar**ve ardından **analitik**' e gidin. **Analitik** öğesine sağ tıklayın ve **günlüğü etkinleştir**' i seçin.  
  
10. WCF test Istemcisini kullanarak hizmeti test edin.  
  
    1. WCF test Istemcisinde, Icalbir hizmet düğümü altında **Add ()** öğesine çift tıklayın.  
  
         **Add ()** yöntemi sağ bölmede iki parametre ile görünür.  
  
    2. İkinci parametre için ilk parametre olarak 2 yazın ve 3.  
  
    3. Yöntemi çağırmak için **çağır** ' a tıklayın.  
  
11. Zaten açtığınız **Olay Görüntüleyicisi** penceresine gidin. **Olay Görüntüleyicisi**, **uygulama ve hizmet günlükleri**, **Microsoft**, **Windows**, **uygulama sunucusu-uygulamalar**' a gidin.  
  
12. **Analitik** düğümüne sağ tıklayın ve **Yenile**' yi seçin.  
  
     Olaylar sağ bölmede görüntülenir.  
  
13. KIMLIĞI 303 olan olayı bulun ve çift tıklayarak içeriği açın ve içeriğini inceleyin.  
  
     Bu olay, icalbir hizmet `Add()` yöntemi tarafından yayılmıştı ve "2 + 3 = 5" değerine eşit bir yüke sahip.  
  
#### <a name="to-clean-up-optional"></a>Temizlemek için (Isteğe bağlı)  
  
1. **Olay Görüntüleyicisi**açın.  
  
2. **Olay Görüntüleyicisi**, **uygulama ve hizmet günlükleri**, **Microsoft**, **Windows**ve sonra **uygulama-sunucu uygulamaları**' na gidin. **Analitik** öğesine sağ tıklayın ve **günlüğü devre dışı bırak**' ı seçin.  
  
3. **Olay Görüntüleyicisi**, **uygulama ve hizmet günlükleri**, **Microsoft**, **Windows**, **uygulama-sunucu-uygulamalar**ve ardından **analitik**' e gidin. **Analitik** öğesine sağ tıklayın ve **Günlüğü Temizle**' yi seçin.  
  
4. Olayları temizlemek için **Temizle** ' ye tıklayın.  
  
## <a name="known-issue"></a>Bilinen sorun  
 **Olay Görüntüleyicisi** IÇINDE, ETW olaylarının kodunu çözemediği bilinen bir sorun vardır. Şöyle bir hata iletisi görebilirsiniz: "Kaynak Microsoft-Windows- \<Application Server 'dan > olay kimliği kimliği için açıklama-uygulamalar bulunamıyor. Bu olayı başlatan bileşen yerel bilgisayarınızda yüklü değil veya yükleme bozuk. Bileşeni yerel bilgisayara yükleyebilir veya onarabilirsiniz. " Bu hatayla karşılaşırsanız, **Eylemler** menüsünden **Yenile** ' yi seçin. Olay daha sonra doğru şekilde kod çözmelidir.  
  
> [!IMPORTANT]
> Örnekler bilgisayarınızda zaten yüklü olabilir. Devam etmeden önce aşağıdaki (varsayılan) dizini denetleyin.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Bu dizin yoksa, tüm Windows Communication Foundation (WCF) ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri indirmek için [Windows Communication Foundation (WCF) ve Windows Workflow Foundation (WF) örneklerine .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) ' e gidin. Bu örnek, aşağıdaki dizinde bulunur.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTrace`  
  
## <a name="see-also"></a>Ayrıca bkz.

- [AppFabric Izleme örnekleri](https://go.microsoft.com/fwlink/?LinkId=193959)
