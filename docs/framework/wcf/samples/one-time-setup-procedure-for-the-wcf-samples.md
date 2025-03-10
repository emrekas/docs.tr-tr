---
title: Windows Communication Foundation Örnekleri için Bir Kerelik Kurulum Prosedürü
ms.date: 03/30/2017
ms.assetid: a5848ffd-3eb5-432d-812e-bd948ccb6bca
ms.openlocfilehash: 4fe77455c26393455c66c24c74691a335ad8cb1b
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/27/2019
ms.locfileid: "70039176"
---
# <a name="one-time-setup-procedure-for-the-windows-communication-foundation-samples"></a>Windows Communication Foundation Örnekleri için Bir Kerelik Kurulum Prosedürü

Windows Communication Foundation (WCF) örneklerinin çoğu Internet Information Services (IIS) içinde barındırılır ve ortak bir sanal dizinden çalıştırılır. Bu tek seferlik kurulum yordamı, disk üzerinde bir klasör oluşturur; Ayrıca, **servicemodelsamples**adlı IIS 'ye bir sanal dizin ekler.

**Servicemodelsamples** sanal DIZINI, IIS tarafından barındırılan bir hizmeti kullanan tüm örnekleri oluşturmak ve çalıştırmak için kullanılır. Bu, örnekleri çalıştırmak için gereken tek sanal dizindir. Örnek oluşturmak, bu sanal dizinde önceden dağıtılan tüm hizmetleri değiştirecek; Bu sanal dizinde yalnızca en son oluşturulan örnek dağıtılır ve kullanılabilir.

> [!NOTE]
> Tüm komutları bir yerel yönetici hesabı altında çalıştırmalısınız. Windows 7, [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)]veya Windows Server 2008 R2 kullanıyorsanız, komut istemi ' ni yükseltilmiş ayrıcalıklarla da çalıştırmalısınız. Bunu yapmak için, komut istemi simgesine sağ tıklayın ve ardından **yönetici olarak çalıştır**' a tıklayın. Bu konudaki tüm komutların, uygun yol ayarlarına sahip bir komut isteminde çalıştırılması gerekir.  Bunu sağlamanın en kolay yolu Visual Studio komut Istemi ' ni kullanmaktır. Bu istemi açmak için **Başlat**' a tıklayın, **tüm programlar**' ı seçin, **Visual Studio 2010**' ye kaydırın, **Visual Studio Araçları**' i seçin, **Visual Studio komut istemi (2010)** öğesini sağ tıklatın ve ardından **yönetici olarak Çalıştır ' ı tıklatın** . Visual Studio Express sürümlerinden biri yüklüyse, bu komut istemi kullanılamaz ve sistem yoluna "C:\Windows\Microsoft.Net\Framework\v4.0" eklemeniz gerekir.

### <a name="one-time-setup-procedure-for-wcf-samples"></a>WCF örnekleri için bir kerelik Kurulum yordamı

1. ASP.NET ayarlandığından emin olun. ASP.NET ayarlama hakkında daha fazla bilgi için bkz. [Internet Information Service barındırma yönergeleri](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md).

2. [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] ' Nin yüklü olduğundan emin olun. V 4.0 (veya üzeri) için şu dizinde arama yapın: **\Windows\microsoft.NET\Framework**

3. Visual Studio 2012 yüklü değilse ve işletim sisteminiz Windows Server 2008 SP2 veya üstü değilse, [düzeltme 251798](https://go.microsoft.com/fwlink/?LinkId=184693)' i yükleme.

4. Aşağıdaki komutları çalıştırın. Bu komutların neden çalıştırılması gereken hakkında daha fazla bilgi için bkz. [IIS barındırılan hizmeti başarısız oluyor](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752252(v=vs.90)).

    > [!WARNING]
    > IIS yeniden yüklenirse, aşağıdaki komutların yeniden çalıştırılması gerekir.

    ```
    "%WINDIR%\Microsoft.Net\Framework\v4.0.30319\aspnet_regiis" –i –enable
    "%WINDIR%\Microsoft.Net\Framework\v4.0.30319\ServiceModelReg.exe" -r
    ```

    > [!WARNING]
    > Komutu `aspnet_regiis –i –enable` çalıştırmak varsayılan uygulama havuzunun kullanımını kullanarak [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], aynı bilgisayardaki diğer uygulamalar için uyumsuzluk sorunları oluşturabilecek hale getirir.

5. Örnekler tarafından kullanılan bağlantı noktalarını etkinleştirmeye yönelik [güvenlik duvarı yönergelerini](../../../../docs/framework/wcf/samples/firewall-instructions.md) izleyin.

6. Aşağıdaki varsayılan dizini denetle: \<InstallDrive >: **\Wf_wcf_samples**. Örnekler daha önce yüklenmişse, bu varsayılan dizindir.

7. Örnekler yüklü değilse, bunları [Visual C# ](https://go.microsoft.com/fwlink/?LinkId=190939) veya [Visual Basic](https://go.microsoft.com/fwlink/?LinkID=193373)için örnek indirme konumundan yükleyin.

8. Örnekleri yükledikten sonra şuraya gidin: \<InstallDrive >: **\Wf_wcf_samples\wcf\setup\\**

9. **Setupvroot. bat** toplu iş dosyasını çalıştırın. Aşağıdaki adımlar gerçekleştirilir:

    - ServiceModelSamples adlı IIS 'de bir sanal dizin oluşturulur.

    - %SystemDrive%\Inetpub\wwwroot\ServiceModelSamples ve%SystemDrive%\Inetpub\wwwroot\ServiceModelSamples\bin. adlı yeni disk dizinleri oluşturulur

    Bu dizinleri el ile ayarlamayı tercih ediyorsanız, [sanal dizin kurulum yönergelerine](../../../../docs/framework/wcf/samples/virtual-directory-setup-instructions.md)bakın. Bu adımda yapılan tüm değişiklikleri dönmek için, örnekleri kullanmayı bitirdikten sonra Cleanupvroot. bat dosyasını çalıştırın.

    > [!NOTE]
    > Bu yordam, Cleanupvroot. bat çalıştırılmadığı müddetçe bir bilgisayarda yalnızca bir kez gerçekleştirilmelidir.

10. %Systemdrive%\ınetpub\wwwroot için, örnekleri ve ağ hizmeti kullanıcısını oluşturduğunuz hesaba yönelik değiştirme izni vermelisiniz. Derlenirken, Web 'de barındırılan bazı örnekler derlenmiş ikilileri önceden belirtilen konuma kopyalamaya çalışabilir ve uygun izinleri ayarlanmamışsa, derleme kesilir. Alternatif olarak, izinleri oldukları gibi bırakabilir ve SDK komut istemi veya Visual Studio komut Istemi 'ni (2012) yönetici olarak çalıştırabilir ya da Visual Studio 2012 ' de aynı zamanda yönetici olarak da çalıştırabilirsiniz.

    > [!NOTE]
    > Bu adım tamamlanmazsa, derleme sırasında IIS 'de barındırılan tüm örnekler başarısız olur. İzinleri doğru şekilde ayarlamış olduğunuzdan emin olun veya hem SDK komut istemi 'ni hem de Visual Studio komut Istemi 'ni (2012) yönetici olarak çalıştırın.

11. Bilgisayarda C:\logs dizini oluşturun; bazı örnekler bekleniyor olabilir. Uygun hesabın bu klasöre verilen yazma erişimi olduğundan emin olun. Windows 7, [!INCLUDE[wv](../../../../includes/wv-md.md)]ve Windows Server 2008 R2 için bu hesap, **ağ hizmetidir**. İçin [!INCLUDE[lserver](../../../../includes/lserver-md.md)], bu hesap NT Authority\Network Service ' dir. [!INCLUDE[wxp](../../../../includes/wxp-md.md)] Ve[!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]için, bu hesap ASPNET ' dir.

12. Setupcerttool. bat dosyasını çalıştırın. Bu dosya \<InstallPath > \wf_wcf_samples\wcf\setup\ klasöründe bulunur.  Bu betik aşağıdaki görevleri gerçekleştirir:

    - FindPrivateKey aracını oluşturun.

    - %ProgramFiles%\ServiceModelSampleTools. adlı bir dizin oluşturun

    - Yeni FindPrivateKey aracını bu dizine kopyalayın.

    Bu araç, sertifikaları kullanan ve IIS 'de barındırılan örnekler için gereklidir.

    > [!NOTE]
    > Güvenlik nedeniyle, örnekleri ile işiniz bittiğinde Cleanupvroot. bat adlı toplu iş dosyasını çalıştırarak yukarıdaki Kurulum adımlarında verilen sanal dizin tanımını ve izinleri kaldırmayı unutmayın.

13. Şirket içinde barındırılan (IIS 'de barındırılmayan) örnekler, dinlemek üzere bilgisayarda HTTP adreslerini kaydetmek için izin gerektirir. Bir HTTP ad alanı ayırması için izin, örneği çalıştırmak için kullanılan kullanıcı hesabından gelir. Varsayılan olarak, yönetici hesaplarının herhangi bir HTTP adresini kaydetme izni vardır. Yönetici olmayan hesaplara, örnekler tarafından kullanılan HTTP ad alanları için izin verilmesi gerekir. Ad alanı ayırmalarını yapılandırma hakkında daha fazla bilgi için bkz. [http ve https yapılandırma](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).

14. Bazı örnekler Message Queuing gerektirir. Yükleme yönergeleri için bkz. [Message Queuing (MSMQ) yükleme](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md) .

    > [!NOTE]
    > Message Queuing gerektiren örnekleri çalıştırmadan önce MSMQ hizmetini başlattığınızdan emin olun.

15. Bazı örnekler için sertifikalar gerekir. Bkz. [Internet Information Services (IIS) sunucu sertifikası yükleme yönergeleri](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).
