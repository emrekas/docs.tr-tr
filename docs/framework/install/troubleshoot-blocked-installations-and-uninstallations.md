---
title: Engellenen .NET Framework yükleme ve kaldırma sorunlarını giderme
ms.date: 04/18/2019
ms.custom: updateeachrelease
helpviewer_keywords:
- .NET Framework, troubleshooting blocked installations
- blocked .NET Framework installations, troubleshooting
ms.assetid: c3fdfbc1-ed99-4202-a2b0-8c4f1646385d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d96ca26ab3733999810dd48611cf10a577381f40
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2019
ms.locfileid: "67859525"
---
# <a name="troubleshoot-blocked-net-framework-installations-and-uninstallations"></a>Engellenen .NET Framework yükleme ve kaldırma sorunlarını giderme

Çalıştırdığınızda [web veya çevrimdışı yükleyiciyi](../../../docs/framework/install/guide-for-developers.md) .NET Framework 4.5 veya sonraki sürümler için .NET Framework'ün yüklemesini engelleyen veya durduran bir sorunla karşılaşabilirsiniz. Aşağıdaki tabloda, olası engelleme sorunları listelenmiş ve sorun giderme bilgilerinin bağlantıları sağlanmıştır.

Windows 8 ve üzeri, .NET Framework, işletim sisteminin bir bileşeni olan ve bağımsız olarak kaldırılamaz. .NET Framework güncelleştirmelerinin görünür **yüklü güncelleştirmeler** Denetim Masası sekmesinde **programlar ve Özellikler** uygulama. .NET Framework, .NET Framework değil önceden işletim sistemleri için görünür **Kaldır veya Değiştir bir program** sekme (veya **Program Ekle/Kaldır** sekmesinde),  **Program ve Özellikler** Denetim Masası'ndaki uygulama. .NET Framework önceden Windows sürümleri hakkında daha fazla bilgi için bkz: [sistem gereksinimleri](../../../docs/framework/get-started/system-requirements.md).

> [!IMPORTANT]
> .NET Framework 4.x sürümlerinin yerinde güncelleştirmeyi olduğundan, .NET Framework 4.x bir sistemde zaten daha sonraki bir sürümün yüklü olduğu bir önceki sürümünü yükleyemezsiniz. Örneğin, Windows 10 Fall Creators Update ile bir sistemde, .NET Framework 4.7.1 işletim sistemiyle birlikte önceden yüklenmiş olarak bu yana .NET Framework 4.6.2, yükleyemezsiniz.

Bir sistemde hangi .NET Framework sürümlerinin yüklü olduğunu belirleyebilirsiniz. Bkz: [nasıl yapılır: Hangi .NET Framework sürümlerinin yüklendiğini belirleme](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md) daha fazla bilgi için.

Bu tabloda, .NET Framework 4.5 ve 4.5.1, onun nokta sürümleri 4.5.x ifade eder ve 4.5.2, .NET Framework 4.7 ve onun nokta sürümleri 4.7.1 ve 4.7.2 4.7.x başvurur, .NET Framework 4.6 ve 4.6.1 ve 4.6.2, onun nokta sürümleri 4.6.x anlamına gelir , ve 4.8 için .NET Framework 4.8 ifade eder.

|İletiyi engelleme|Daha fazla bilgi veya bu sorunu gidermek için|  
|----------------------|--------------------------------------------------|  
|Microsoft .NET Framework ürününün kaldırılması bazı uygulamaların işlevini durdurmasına neden olabilir.|Genel olarak, kullandığınız bir uygulama .NET Framework'ün belirli bir sürümüne bağlı olabileceği için, bilgisayarınıza yüklü olan .NET Framework sürümlerinden hiçbirini kaldırmamalısınız. Daha fazla bilgi için [kullanıcılar için .NET Framework](../../../docs/framework/get-started/index.md#ForUsers) içinde *Başlarken* Kılavuzu.|  
|.NET framework 4.5.x/4.6.x/4.7.x (trk) veya sonraki bir sürümü bu bilgisayarda zaten yüklü.|Herhangi bir işlem gerekli değil.<br /><br /> Bir sistemde hangi .NET Framework sürümlerinin yüklü olduğunu saptamak için bkz: [nasıl yapılır: Hangi .NET Framework sürümlerinin yüklü olduğunu belirleme](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).|  
|.NET Framework 4.5.x/4.6.x/4.7.x/4.8 (*dil*) .NET Framework 4.5.x/4.6.x/4.7.x/4.8 gerektirir. Lütfen .NET Framework 4.5.x/4.6.x/4.7.x/4.8 İndirme Merkezi'nden yükleyin ve kurulumu yeniden çalıştırın.|Dil paketini yüklemeden önce belirtilen .NET Framework sürüm İngilizce sürümünü yüklemeniz gerekir. Daha fazla bilgi için üzerinde bölümüne bakın. [dil paketlerini yüklemek için](../../../docs/framework/install/guide-for-developers.md#to-install-language-packs) Yükleme Kılavuzu.|  
|.NET Framework 4.5.x/4.6.x/4.7.x/4.8 yükleyemezsiniz. Bilgisayarınızdaki diğer uygulamalar bu programla uyumlu değil.<br /><br /> -veya-<br /><br /> Bilgisayarınızdaki diğer uygulamalar bu programla uyumlu değil.|Bu ileti büyük olasılıkla .NET Framework'ün önizleme veya RC sürümünün yüklenmiş olmasından kaynaklanmıştır. Önizlemeyi veya RC sürümünü kaldırın ve kurulumu yeniden çalıştırın.|  
|.NET framework 4.5.x/4.6.x/4.7.x/4.8 Bu paket kullanılarak kaldırılamaz. .NET Framework 4.5.x/4.6.x/4.7.x/4.8 bilgisayarınızdan kaldırmak için Git **Denetim Masası**, seçin **programlar ve Özellikler**, seçin **yüklü güncelleştirmeleri görüntüle**seçin (KB2828152) Microsoft Windows için güncelleştirme ve ardından **kaldırma**.|Önizleme veya RC sürümlerini .NET Framework'ün kaldırın, yüklemekte olduğunuz paket değil.<br /><br /> Önizlemeyi veya RC kaldırın. Denetim Masası'ndan yayın.|  
|.NET Framework 4.5.x/4.6.x/4.7.x/4.8 kaldıramazsınız. Bilgisayarınızdaki diğer uygulamalar bu programa bağımlıdır.|Genel olarak, bir uygulama .NET Framework'ün belirli bir sürüme bağlı olabileceği için .NET Framework sürümlerinden hiçbirini bilgisayarınızdan kaldırmanız gerekir. Daha fazla bilgi için [kullanıcılar için .NET Framework](../../../docs/framework/get-started/index.md#ForUsers) içinde *Başlarken* Kılavuzu.|  
|Yeniden dağıtılabilir .NET Framework 4.5.x/4.6.x/4.7.x/4.8 Bu işletim sistemi için geçerli değildir. Lütfen işletim sisteminiz için .NET Framework 4.5.x/4.6.x/4.7.x/4.8 Microsoft Download Center'dan gelen indirin.|Desteklenmeyen bir platformda .NET Framework 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, 4.7.2 veya 4.8 yüklemeye çalıştığınız ya da tüm desteklenen işletim sistemleri için bileşenlerin bulunmadığı yükleme paketini seçtiniz. Çevrimdışı yükleyiciyi kullanarak yüklemeyi yeniden çalıştırın ([4.5.1 için](https://go.microsoft.com/fwlink/p/?LinkId=309493), [4.5.2 için](https://go.microsoft.com/fwlink/p/?LinkId=397706), [4.6 için](https://go.microsoft.com/fwlink/p/?LinkId=528233), [4.6.1 için](https://go.microsoft.com/fwlink/p/?LinkId=671744), için [ 4.6.2](https://go.microsoft.com/fwlink/p/?LinkId=780604), için [4.7](https://go.microsoft.com/fwlink/p/?LinkId=825306)), için [4.7.1](https://go.microsoft.com/fwlink/p/?LinkId=852090), için [4.7.2](https://go.microsoft.com/fwlink/p/?LinkId=863265), veya [4.8](https://go.microsoft.com/fwlink/?linkid=2088631). Daha fazla bilgi için [Yükleme Kılavuzu](../../../docs/framework/install/guide-for-developers.md) ve [sistem gereksinimleri](../../../docs/framework/get-started/system-requirements.md) desteklenen işletim sistemleri için.|  
|Güncelleştirme KB olarak karşılık gelen\<*numarası*> Bu ürünü yükleyebilmeniz için önce yüklü olması gerekir.|.NET Framework'ün yüklemesini bir KB güncelleştirmesi .NET Framework'ü yüklemeden önce yüklü olmasını gerektirir. Güncelleştirmeyi yükleyin ve sonra .NET Framework yüklemeyi yeniden başlatın.<br /><br /> Örneğin, yüklenmesini güncelleştirilmiş Windows 8.1, Windows RT 8.1, .NET Framework sürümleri ve Windows Server 2012 R2 gerektirir, karşılık gelen güncelleştirme [KB 2919355](https://support.microsoft.com/kb/2919355) yüklü olmalıdır.|  
|Bilgisayarınızda şu anda Windows Server 2008 işletim sisteminin Sunucu Çekirdeği yüklemesi çalışıyor. .NET Framework 4.5.x işletim sisteminin daha yeni bir sürümünü gerektirir. Lütfen Windows Server 2008 R2 SP1 ya da .NET Framework 4.5.x kurulumunu yeniden çalıştırın ve daha yüksek yükleyin.|.NET Framework 4.5.1 ve 4.5.2'yi Windows Server 2008 R2 SP1 veya daha sonra Sunucu Çekirdeği rolünde desteklenir. Bkz: [sistem gereksinimleri](../../../docs/framework/get-started/system-requirements.md).|  
|Bu bilgisayar üzerinde tüm kullanıcılar için bu işlemi tamamlamak üzere yeterli yetkiniz yok. Yönetici olarak çalıştırıp yeniden oturum **Kurulum**.|.NET Framework yüklemek için bilgisayarda yönetici olmanız gerekir.|  
|Önceki yükleme bilgisayarınızın yeniden başlatılmasını gerektirdiği için Kurulum devam edemiyor. Lütfen bilgisayarınızı yeniden başlatın ve Kurulumu yeniden çalıştırın.|Yeniden başlatma, tam olarak bir yüklemenin tamamlanabilmesi için bazen gereklidir. Bilgisayarınızı yeniden başlatın ve kurulumu yeniden çalıştırın için yönergeleri izleyin.<br /><br /> Nadiren de olsa, sisteminizi Windows eksik güncelleştirmelerin sayısı algıladı ve kuyrukta İleri güncelleştirmeyi yüklemek için yeniden başlatılıyor birden çok kez yeniden başlatmanız istenebilir.|  
|.NET Framework Kurulumu Program Uyumluluk modunda çalıştırılamaz.|Bkz: [Program Uyumluluk sorunları](#compat) bu makalenin devamındaki bölümü.|  
|Bileşen deposu bozuk olduğundan, .NET framework 4.5.x/4.6.x/4.7.x/4.8 yüklenmedi.|Bkz: [DISM ya da sistem güncelleştirme hazırlığı aracını kullanarak Windows güncelleştirme düzeltme hataları](https://support.microsoft.com/kb/947821) daha fazla bilgi için.|  
|Windows Installer Hizmeti bu bilgisayarda kullanılamadığından kurulum çalıştırılamıyor.|Bkz: [yüklerken veya güncellerken programlar Windows Installer hizmeti hatası](https://go.microsoft.com/fwlink/p/?LinkId=248684) Microsoft Support Web sitesi.|  
|Windows Update Hizmeti bu bilgisayarda kullanılamadığından kurulum düzgün çalışmayabilir.|Bilgisayar, Microsoft Windows Update yerine Windows Server Update Services (WSUS) kullanacak şekilde yapılandırılabilir. Daha fazla bilgi için hata kodu 0x800F0906 bölümüne bakın [Windows 8 veya Windows Server 2012 ' .NET Framework 3.5 yüklemeye çalıştığınızda hata kodları](https://support.microsoft.com/kb/2734782).<br /><br /> Ayrıca bkz: [bir bilgisayardaki güncelleştirmeleri yönetmenize yardımcı olmak için Windows Update Aracısı'nın en son sürümünü elde etme](https://go.microsoft.com/fwlink/p/?LinkId=248437) Microsoft Support Web sitesi.|  
|Arka Plan Akıllı Aktarım Hizmeti (BITS) bu bilgisayarda kullanılamadığından kurulum düzgün çalışmayabilir.|Bkz: [bir Windows Vista tabanlı bilgisayarlarda bir arka plan Akıllı Aktarım Hizmeti (BITS) kilitlenmesini engellemek için bir güncelleştirme](https://go.microsoft.com/fwlink/p/?LinkId=248680) Microsoft Support Web sitesi.|  
|Windows update bir hatayla karşılaştı ve hata kodu 0x80070643 veya 0x643 görüntülenen olduğundan kurulum düzgün çalışmayabilir.|Bkz: [.NET Framework güncelleştirme yükleme hatası: "0x80070643" veya "0x643"](https://support.microsoft.com/kb/976982) Microsoft Support Web sitesi.|  
|.NET Framework 4.5.x/4.6.x/4.7.x/4.8 zaten bu işletim sisteminin bir parçasıdır. Yeniden dağıtılabilir .NET Framework 4.5.x/4.6.x/4.7.x/4.8 yüklemeniz gerekmez.|Eylem yok.<br /><br /> Bir sistemde hangi .NET Framework sürümlerinin yüklü olduğunu saptamak için bkz: [nasıl yapılır: Hangi .NET Framework sürümlerinin yüklü olduğunu belirleme](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md). Bkz: [sistem gereksinimleri](../../../docs/framework/get-started/system-requirements.md) desteklenen işletim sistemleri için.|  
|.NET Framework 4.5.x/4.6.x/4.7.x/4.8 Bu işletim sisteminde desteklenmiyor.|Bkz: [sistem gereksinimleri](../../../docs/framework/get-started/system-requirements.md) desteklenen işletim sistemleri için.<br /><br /> Windows 7 .NET Framework'ün başarısız yüklemeler için bu ileti genellikle Windows 7 SP1 yüklü olmadığını gösterir. Windows 7 sistemlerde, Windows 7 SP1 .NET Framework gerektirir. Windows 7'de olan ve henüz Service Pack 1 yüklü değilse .NET Framework'ü yüklemeden önce yapmanız gerekir. Windows 7 SP1 yükleme hakkında daha fazla bilgi için bkz. [Windows 7 Service Pack 1 (SP1) yüklemeyi öğrenin](https://windows.microsoft.com/windows7/install-windows-7-service-pack-1).|  
|Bilgisayarınızda şu anda Windows Server 2008 işletim sisteminin Sunucu Çekirdeği yüklemesi çalışıyor. .NET Framework 4.5.x tam sürümünü işletim sistemi ya da Server Core 2008 R2 SP1 gerektirir. Lütfen tam bir Windows Server 2008 SP2 veya Windows Server 2008 R2 SP1 ya da Server Core 2008 R2 SP1 sürümünü yükleyin ve .NET Framework yeniden 4.5.x kurulumu.|The .NET Framework , Windows Server 2008 R2 SP1 veya sonrası ile birlikte Sunucu Çekirdeği Rolünde desteklenir. Bkz: [sistem gereksinimleri](../../../docs/framework/get-started/system-requirements.md).|  
|.NET Framework 4.5.x zaten bu işletim sisteminin bir parçasıdır ancak şu anda kapalı durumdadır ([!INCLUDE[winserver8](../../../includes/winserver8-md.md)] yalnızca).|Bkz: [kapatma Windows özelliklerini aç veya Kapat](https://go.microsoft.com/fwlink/p/?LinkId=248438) Windows Web sitesinde.|  
|Bu kurulum programı bir x86 bilgisayar gerektiriyor. x64 veya IA64 bilgisayarlara yüklenemez.|Bkz: [sistem gereksinimleri](../../../docs/framework/get-started/system-requirements.md).|  
|Bu kurulum programı bir x64 veya x86 bilgisayar gerektiriyor. IA64 bilgisayarlara yüklenemez.|Bkz: [sistem gereksinimleri](../../../docs/framework/get-started/system-requirements.md).|  

<a name="compat"></a>
### <a name="program-compatibility-issues"></a>Program Uyumluluk sorunları

.NET Framework 4.5 veya onun nokta sürümleri yüklemesi Windows programı uyumluluk modunda çalışırken 1603 hata kodu veya bloklar ile başarısız oluyor. **Program Uyumluluk Yardımcısı** .NET Framework düzgün yüklenmemiş ve önerilen ayarı (Program uyumluluğu modu) kullanarak yeniden yüklemenizi ister gösterir. Program Uyumluluğu modu, başarısız olan veya iptal edilen önceki .NET Framework Kurulumu Programını çalıştırma girişimlerinde Program Uyumluluk Yardımcısı tarafından da ayarlanmış olabilir.

.NET Framework yükleyicisi Program Uyumluluk modunda çalıştırılamaz. Bu engelleme sorununu çözmek için sistem genelinde uyumluluk modu ayarının etkin değil emin olmak için Kayıt Defteri Düzenleyicisi'ni kullanmanız gerekir:

1. Seçin **Başlat** düğmesine ve ardından **çalıştırma**.

1. İçinde **çalıştırma** iletişim kutusu, "regedit" yazın ve ardından **Tamam**.

1. Kayıt Defteri Düzenleyicisi'nde, aşağıdaki alt anahtarlara göz atın:

   - HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Compatibility Assistant\Persisted

   - HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers

1. Ad sütununda, .NET Framework 4.5 için 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, konum veya 4.7.2 indirme adlarını girin bağlı olarak hangi sürümün yüklemekte olduğunuz ve bu girişleri silin. İndirme adları için bkz. [geliştiriciler için .NET Framework yükleme](../../../docs/framework/install/guide-for-developers.md) makalesi.

1. Sürüm 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1 veya 4.7.2 için .NET Framework yükleyiciyi yeniden çalıştırın.

## <a name="see-also"></a>Ayrıca bkz.

- [Geliştiriciler için .NET Framework'ü yükleme](../../../docs/framework/install/guide-for-developers.md)
- [Nasıl yapılır: Hangi .NET Framework sürümlerinin yüklü olduğunu belirleme](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)
- [Sürümler ve Bağımlılıklar](../../../docs/framework/migration-guide/versions-and-dependencies.md)
