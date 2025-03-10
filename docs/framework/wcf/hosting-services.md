---
title: Barındırma Hizmetleri
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF]
ms.assetid: 192be927-6be2-4fda-98f0-e513c4881acc
ms.openlocfilehash: b1a0a07876e9cc111e8c5eef56f208d7bf2cb49f
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2019
ms.locfileid: "67487706"
---
# <a name="hosting-services"></a>Barındırma Hizmetleri
Etkin duruma gelmesi bir hizmet oluşturup kendi bağlam ve yaşam süresini denetleyen bir çalışma zamanı ortamında barındırılması gerekir. Windows Communication Foundation (WCF) hizmetlerini destekleyen yönetilen kodu herhangi bir Windows işlem içinde çalıştırmak için tasarlanmıştır.  
  
 WCF hizmet odaklı uygulamalar oluşturmak için birleştirilmiş programlama modeli sağlar. Bu programlama modeli, tutarlı kalır ve hizmetin dağıtıldığı çalışma zamanı ortamının bağımsızdır. Uygulamada, bu kod hizmetleriniz için aynı ne olursa olsun barındırma seçeneği benzer olduğunu anlamına gelir.  
  
 Bu barındırma seçenekleri aralığı gibi bir çalışan işleminin içinde çalışan bir Windows hizmeti Internet Information Services (IIS) tarafından veya Windows İşlem Etkinleştirme Hizmeti (WAS) tarafından yönetilen çalışmasını server ortamları için bir konsol uygulaması içinde. Geliştiriciler hizmet dağıtım gereksinimleri karşılayan bir barındırma ortamı seçin. Bu gereksinimleri, üzerinde uygulama dağıtılır, platformu üzerinde gereken iletileri gönderip, taşıma veya işlem geri dönüştürme ve yeterli kullanılabilir olmasını sağlamak için gerekli diğer işlem yönetimi türü veya bazı birisinden türetin diğer yönetim veya Güvenilirlik gereksinimleri. Sonraki bölümde, barındırma seçenekleri hakkında bilgi ve yönergeler sağlar.  
  
## <a name="hosting-options"></a>Barındırma seçenekleri  
  
#### <a name="self-hosting-in-a-managed-application"></a>Kendi kendine yönetilen bir uygulamada barındırma  
 WCF hizmetleri, yönetilen bir uygulamada barındırılabilir. Dağıtmak için en az bir altyapı gerektiğinden bu en esnek bir seçenektir. Hizmet içinde yönetilen bir uygulama kodu için kod ekleme ve oluşturma ve bir örneğini açın <xref:System.ServiceModel.ServiceHost> hizmet kullanılabilir hale getirmek için. Daha fazla bilgi için [nasıl yapılır: Yönetilen bir uygulamada bir WCF Hizmeti barındırma](../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md).  
  
 Bu seçenek, iki yaygın senaryolara olanak sağlar: Konsol uygulamaları ve Windows Presentation Foundation (WPF) veya Windows Forms (WinForms) göre gibi zengin istemci uygulamalarının içinde çalışan WCF hizmetleri. Bir konsol uygulaması içinde bir WCF Hizmeti barındırma uygulama geliştirme aşamasında genellikle yararlı olur. Bu bunları hata ayıklamak kolay, uygulama içinde neler olup bittiğine bulmak için izleme bilgilerini almak kolay ve bunları yeni konumlara kopyalayarak yerleri daha kolay hale getirir. Bu barındırma seçeneği ayrıca, dış dünya ile iletişim kurmak için WPF ve WinForms uygulamaları gibi zengin istemci uygulamaları için kolaylaştırır. Örneğin, WPF için kullanıcı arabirimi kullanan ve ayrıca diğer istemcilerin kendisine bağlanıp bilgi paylaşmak bir WCF hizmetini barındıran bir eşler arası işbirliği istemci.  
  
#### <a name="managed-windows-services"></a>Yönetilen Windows Hizmetleri  
 Bu barındırma seçeneği için işlem ömrü hizmetinin Hizmet Denetimi Yöneticisi (SCM) tarafından denetlenmesi (eski adıyla NT hizmeti olarak da bilinir) yönetilen bir Windows hizmeti olarak bir WCF hizmetini barındıran uygulama etki alanı (AppDomain) kaydetme oluşur. Windows Hizmetleri. Kendi kendine barındırma seçeneği gibi bazı barındırma kodu uygulamanın bir parçası yazılır, bu tür bir barındırma ortamı gerektirir. Hizmet hem de bir Windows hizmeti ve bir WCF hizmeti olarak devralmasına neden tarafından uygulanan <xref:System.ServiceProcess.ServiceBase> sınıfı olarak bir WCF Hizmeti sözleşmesi arabirimi. <xref:System.ServiceModel.ServiceHost> Ardından oluşturulur ve açık bir geçersiz kılınan içinde <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> yöntemi ve içinde bir geçersiz kılınan kapalı <xref:System.ServiceProcess.ServiceBase.OnStop> yöntemi. Devralınan bir yükleyici sınıfı <xref:System.Configuration.Install.Installer> Installutil.exe aracı tarafından bir Windows hizmeti olarak yüklenecek program izin vermek için de uygulanmalıdır. Daha fazla bilgi için [nasıl yapılır: Yönetilen bir Windows hizmetinde bir WCF Hizmeti barındırma](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md). Uzun süre çalışan, IIS dışında iletisi-etkinleştirilmemiş güvenli bir ortamda barındırılan bir WCF hizmeti, barındırma seçeneği yönetilen Windows hizmeti tarafından etkin bir senaryodur. Hizmet ömrü, bunun yerine işletim sistemi tarafından denetlenir. Barındırma bu seçenek, tüm Windows sürümlerinde kullanılabilir.  
  
#### <a name="internet-information-services-iis"></a>Internet Information Services (IIS)  
 Barındırma seçeneği IIS, ASP.NET ile tümleşiktir ve işlem geri dönüştürme, boşta kapatma, sistem durumu izleme işlemi ve ileti tabanlı etkinleştirme gibi teknolojiler teklif özelliklerini kullanır. Üzerinde [!INCLUDE[wxp](../../../includes/wxp-md.md)] ve [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] işletim sistemleri, bu, yüksek oranda kullanılabilir ve yüksek oranda ölçeklenebilir olması gereken bir Web hizmeti uygulamalarını barındırmak için tercih edilen çözümüdür. IIS ayrıca müşterilere bir kurumsal sınıf server ürün beklediğiniz tümleşik yönetilebilirlik sunar. Bu barındırma seçeneği IIS düzgün şekilde yapılandırılmasını gerektirir, ancak uygulamanın bir parçası herhangi bir barındırma kod yazılmasını gerektirmez. Bir WCF hizmeti için barındırma IIS yapılandırma hakkında daha fazla bilgi için bkz: [nasıl yapılır: IIS'de WCF Hizmeti barındırma](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
 IIS tarafından barındırılan hizmetleri yalnızca HTTP aktarımı kullanabileceğinizi unutmayın. IIS 5.1, uygulanması bazı sınırlamalar tanıttı [!INCLUDE[wxp](../../../includes/wxp-md.md)]. Bir WCF hizmeti için IIS 5.1 tarafından sağlanan ileti tabanlı etkinleştirme [!INCLUDE[wxp](../../../includes/wxp-md.md)] herhangi diğer kendini barındıran WCF hizmetinde aynı bilgisayarda iletişim kurmak için 80 numaralı bağlantı noktasını kullanmasını engeller. WCF hizmetleri aynı AppDomain/uygulama havuzu/çalışan işleminde IIS 6.0 tarafından üzerinde barındırıldığında diğer uygulamaları çalıştırabilir [!INCLUDE[ws2003](../../../includes/ws2003-md.md)]. Ancak çekirdek modu HTTP yığınını (HTTP.sys) kullandığından WCF hem de IIS 6.0, IIS 6.0 80 numaralı bağlantı noktası IIS 5.1 aksine aynı makine üzerinde çalışan diğer şirket içinde barındırılan WCF hizmetleri paylaşabilirsiniz.  
  
#### <a name="windows-process-activation-service-was"></a>Windows İşlem Etkinleştirme Hizmeti (WAS)  
 Windows İşlem Etkinleştirme Hizmeti (WAS) olduğu için yeni işlem etkinleştirme mekanizması [!INCLUDE[lserver](../../../includes/lserver-md.md)] , ayrıca üzerinde kullanılabilir [!INCLUDE[wv](../../../includes/wv-md.md)]. Tanıdık IIS 6.0 işlem modeli (uygulama havuzları ve işlem ileti tabanlı etkinleştirme) korur ve özellikleri (örneğin, hızlı hata koruması, sistem durumu izleme ve geri dönüştürme), ancak barındırma etkinleştirme işleminden HTTP üzerindeki bağımlılığı kaldırır Mimari. IIS 7.0 WAS HTTP üzerinden ileti tabanlı etkinleştirme gerçekleştirmek için kullanır. Ek WCF bileşenler de ileti tabanlı etkinleştirme, WCF destekleyen diğer protokolleri üzerinden, TCP MSMQ ve adlandırılmış kanallar gibi sağlamak üzere WAS takın. Bu işlem geri dönüşümü gibi IIS özellikleri hızlı kullanmak için iletişim protokolleri kullanan uygulamalar, koruma ve yalnızca HTTP tabanlı uygulamalarda kullanılabilen ortak yapılandırma sistemi başarısız sağlar.  
  
 Bu barındırma seçeneği gerektirir, olması düzgün şekilde yapılandırıldı, ancak uygulamanın bir parçası herhangi bir barındırma kod yazmanızı gerektirmez. Yapılandırma hakkında daha fazla bilgi barındırma için bkz: [nasıl yapılır: Was'ta WCF Hizmeti barındırma](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).  
  
## <a name="choosing-a-hosting-environment"></a>Bir barındırma ortamı seçme  
 Aşağıdaki tabloda bazı temel avantajları ve barındırma seçenekleri her biriyle ilişkili senaryoları özetlenmiştir.  
  
|Barındırma ortamı|Yaygın senaryolar|Temel avantajlar ve sınırlamalar|  
|-------------------------|----------------------|----------------------------------|  
|Yönetilen uygulama ("şirket içinde barındırılan")|-Konsol uygulamaları geliştirme sırasında kullanılır.<br />-Zengin WinForm ve WPF istemci uygulama hizmetlerine erişme.|-Esnek.<br />-Kolayca dağıtın.<br />-Olmayan hizmetler için Kurumsal çözümü.|  
|Windows Hizmetleri (eski adıyla NT Hizmetleri da bilinir)|IIS dışında barındırılan uzun süreli WCF hizmeti.|-İleti etkinleştirilmemiş olan işletim sistemi tarafından denetlenen hizmet işlem yaşam süresi.<br />-Tüm Windows sürümleri tarafından desteklenir.<br />-Güvenli bir ortam.|  
|IIS 5.1, IIS 6.0|-Bir WCF Hizmeti yan yana ASP.NET içeriği ile HTTP protokolünü kullanarak Internet'te çalışıyor.|-İşlem geri dönüştürme.<br />-Boşta kapatın.<br />-Sistem durumu izleme işlemi.<br />-İleti tabanlı etkinleştirme.<br />-Yalnızca HTTP.|  
|Windows İşlem Etkinleştirme Hizmeti (WAS)|-IIS çeşitli aktarım protokolünü kullanarak Internet'te yüklemeden bir WCF hizmeti çalışıyor.|-IIS gerekli değildir.<br />-İşlem geri dönüştürme.<br />-Boşta kapatın.<br />-Sistem durumu izleme işlemi.<br />-İleti tabanlı etkinleştirme.<br />-HTTP, TCP veya adlandırılmış kanallar ve MSMQ ile çalışır.|  
|IIS 7.0|-Bir WCF hizmetini ASP.NET içeriği ile çalışıyor.<br />-Çeşitli aktarım protokolünü kullanarak Internet'te bir WCF hizmeti çalışıyor.|-Avantajları OLUŞTU.<br />-ASP.NET ve IIS içeriği ile tümleşiktir.|  
  
 Bir barındırma ortamı seçimi Windows üzerinde dağıtıldığı, iletileri ve işlem ve uygulama gerektiriyorsa, etki alanı geri dönüştürme türünü göndermek için gerektirir taşımalar sürümüne bağlıdır. Aşağıdaki tabloda bu gereksinimlere ilgili verileri özetler.  
  
|Barındırma ortamı|Platform kullanılabilirlik|Desteklenen aktarmalar|İşlem ve AppDomain geri dönüştürülüyor|  
|-------------------------|---------------------------|--------------------------|-------------------------------------|  
|Yönetilen uygulamaların ("şirket içinde barındırılan")|[!INCLUDE[wxp](../../../includes/wxp-md.md)], [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], [!INCLUDE[wv](../../../includes/wv-md.md)],<br /><br /> [!INCLUDE[lserver](../../../includes/lserver-md.md)]|HTTP<br /><br /> NET.TCP,<br /><br /> NET.pipe,<br /><br /> net.msmq|Hayır|  
|Windows Hizmetleri (eski adıyla NT Hizmetleri da bilinir)|[!INCLUDE[wxp](../../../includes/wxp-md.md)], [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], [!INCLUDE[wv](../../../includes/wv-md.md)],<br /><br /> [!INCLUDE[lserver](../../../includes/lserver-md.md)]|HTTP<br /><br /> NET.TCP,<br /><br /> NET.pipe,<br /><br /> net.msmq|Hayır|  
|IIS 5.1|[!INCLUDE[wxp](../../../includes/wxp-md.md)]|HTTP|Evet|  
|IIS 6.0|[!INCLUDE[ws2003](../../../includes/ws2003-md.md)]|HTTP|Evet|  
|Windows İşlem Etkinleştirme Hizmeti (WAS)|[!INCLUDE[wv](../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../includes/lserver-md.md)]|HTTP<br /><br /> NET.TCP,<br /><br /> NET.pipe,<br /><br /> net.msmq|Evet|  
  
 Bir hizmeti ya da herhangi bir uzantı bir güvenilmeyen konak ödün güvenlikten çalıştıran dikkat etmeniz önemlidir. Ayrıca, açılırken unutmayın bir <xref:System.ServiceModel.ServiceHost> kimliğe bürünme altında kullanıcı kapalı, örneğin önbelleğe alarak kaydedildiğini değil bir uygulama sağlamalıdır <xref:System.Security.Principal.WindowsIdentity> kullanıcının.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Sistem Gereksinimleri](../../../docs/framework/wcf/wcf-system-requirements.md)
- [Temel Programlama Yaşam Döngüsü](../../../docs/framework/wcf/basic-programming-lifecycle.md)
- [Hizmet Anlaşmalarını Uygulama](../../../docs/framework/wcf/implementing-service-contracts.md)
- [Nasıl yapılır: IIS'de WCF Hizmeti barındırma](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)
- [Nasıl yapılır: Was'ta WCF Hizmeti barındırma](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md)
- [Nasıl yapılır: Yönetilen bir Windows hizmetinde bir WCF Hizmeti barındırma](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md)
- [Nasıl yapılır: Yönetilen bir uygulamada bir WCF Hizmeti barındırma](../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)
