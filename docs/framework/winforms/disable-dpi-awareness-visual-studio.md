---
title: Visual Studio'da DPI tanıma devre dışı bırak
description: Windows Form Tasarımcısı HDPI monitörlerde Visual Studio, DPI kullanmayan bir işlem olarak çalıştırmayı öğrenin ve sınırlamalar açıklanır.
ms.date: 12/17/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
author: gewarren
ms.author: gewarren
ms.openlocfilehash: 92096663032b85058dc8c918d1f90153820f6f71
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710543"
---
# <a name="disable-dpi-awareness-in-visual-studio"></a>Visual Studio'da DPI tanıma devre dışı bırak

Visual Studio otomatik olarak görünen ölçekler anlamına gelir inç (DPI) kullanan uygulama başına bir nokta var. Uygulamanın DPI kullanan geçersiz olduğunu belirtiyor, işletim sistemi uygulamayı bir bit eşlem olarak ölçeklendirir. Bu davranış, DPI sanallaştırma olarak da adlandırılır. Uygulamayı hala % 100 ölçeklendirme veya 96 DPI çalışır olduğunu düşünüyor.

## <a name="windows-forms-designer-on-hdpi-monitors"></a>HDPI monitörde Windows Form Tasarımcısı

**Windows Form Tasarımcısı** ölçeklendirme desteği, Visual Studio'da yok. Bazı formlarında açtığınızda bu görüntü sorunları neden **Windows Form Tasarımcısı** üzerinde yüksek nokta / inç (HDPI) izleyiciler. Örnekler için aşağıdaki görüntüde gösterildiği gibi çakıştırmayı denetimleri görünebilir:

![Windows Form Tasarımcısı HDPI İzleyicisi](./media/disable-dpi-awareness-visual-studio/win-forms-designer-hdpi.png)

Visual Studio 2017 sürüm 15,8 ve daha sonra bir formda açtığınızda **Windows Form Tasarımcısı** HDPI izleyicide bir Visual Studio Tasarımcı üst kısmında sarı bir bilgi çubuğu görüntüler:

![DPI uyumlu modda yeniden Visual Studio'da bilgi çubuğu](./media/disable-dpi-awareness-visual-studio/scaling-gold-bar.png)

İletiyi okur **ölçeklendirme, ana görüntü %200 (192 dpi) ayarlayın. Bu, Tasarımcı penceresinin içinde işleme sorunlara neden olabilir.**

Tasarımcıda çalışmayan ve formunuzu düzenleme gerekmez bilgi çubuğu yoksay ve Kod Düzenleyicisi'ni veya diğer türde tasarımcıları çalışma devam edin. (Ayrıca [bildirimleri devre dışı bırak](#disable-notifications) böylece bilgi çubuğu görünmeye devam etmez.) Yalnızca **Windows Form Tasarımcısı** etkilenir. Çalışmak ihtiyacınız varsa **Windows Form Tasarımcısı**, sonraki bölümde yardımcı [sorununu](#to-resolve-the-problem).

## <a name="to-resolve-the-problem"></a>Bu sorunu gidermek için

Görünen bu sorunu gidermek için kullanabileceğiniz üç seçenek vardır.

### <a name="restart-visual-studio-as-a-dpi-unaware-process"></a>DPI kullanmayan bir işlem olarak Visual Studio'yu yeniden başlatın

Sarı bilgi çubuğunda seçeneğini belirleyerek, DPI kullanmayan bir işlem olarak Visual Studio yeniden başlatabilirsiniz. Bu sorunu çözümleme tercih edilen yoludur.

Visual Studio, DPI kullanmayan bir işlem olarak çalıştığında, Tasarımcı düzen sorunları çözümlendi ancak yazı tipleri bulanık görünebilir. Visual Studio bildiren DPI kullanmayan bir işlem olarak çalışır, farklı bir sarı bilgilendirme iletisi görüntüler **Visual Studio, DPI kullanmayan bir işlem olarak çalışıyor. WPF ve XAML tasarımcıları düzgün görüntülenmeyebilir.** Bilgi çubuğu için bir seçenek de sağlar. **DPI kullanan bir işlem olarak Visual Studio'yu yeniden başlatın**.

> [!NOTE]
> - Bu araç pencereleri konumunu, DPI kullanmayan bir işlem olarak yeniden başlatma seçeneğini seçtiğinizde Visual Studio araç pencerelerinde akıyor, değişebilir.
> - Varsayılan Visual Basic profil kullanıyorsanız veya varsa **oluşturulduğunda yeni projeleri Kaydet** seçeneği seçili olarak **Araçları** > **seçenekleri**  >  **Projeler ve çözümler**, DPI kullanmayan bir işlem olarak yeniden başlatıldığında, Visual Studio projenizi yeniden açamıyor. Ancak, proje altında seçerek açabileceğiniz **dosya** > **son projeler ve çözümler**.

İşiniz bittiğinde çalışan DPI kullanan bir işlem olarak Visual Studio'yu yeniden önemlidir **Windows Form Tasarımcısı**. DPI kullanmayan bir işlem olarak çalıştırılırken, yazı tipleri konum bulanık ve diğer tasarımcılar sorunları gibi görebilirsiniz **XAML Tasarımcısı**. Kapatıp DPI uyumlu modda çalışırken Visual Studio, bu duruma DPI kullanan yeniden. Ayrıca **DPI kullanan bir işlem olarak Visual Studio'yu yeniden başlatın** bilgi çubuğunda seçeneği.

### <a name="add-a-registry-entry"></a>Bir kayıt defteri girdisini ekleyin

Kayıt defteri değişikliği yaparak Visual Studio DPI uyumlu işaretleyebilirsiniz. Açık **Kayıt Defteri Düzenleyicisi'ni** ve bir girdiyi **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers** alt anahtarı:

**Giriş**: C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE\devenv.exe

   > [!NOTE]
   > Visual Studio 2017 Professional veya Enterprise edition kullanıyorsanız değiştirin **topluluk** ile **Professional** veya **Kurumsal** giriş. Ayrıca, sürücü harfini gerektiği gibi değiştirin.

**Tür**: REG_SZ

**Değer**: DPIUNAWARE

> [!NOTE]
> Kayıt defteri girişini kaldırın kadar visual Studio, DPI kullanmayan modda kalır.

### <a name="set-your-display-scaling-setting-to-100"></a>Ekranınıza ayarı % 100 ölçeklendirme ayarlayın

Windows 10'da ayarı % 100 ölçeklendirme ekranınıza ayarlamak için şunu yazın **görüntü ayarlarını** görev çubuğunda arama kutusuna tıklayın ve ardından **görünüm ayarlarını değiştirme**. İçinde **ayarları** penceresinde **metin, uygulamaları ve diğer öğelerin boyutunu değiştirme** için **% 100**.

Kullanıcı arabiriminin kullanılabilmesi için çok küçük zorlaştırabilir çünkü ayarı % 100'e ölçeklendirmeyi ekranınıza istenmeyen, olabilir.

## <a name="disable-notifications"></a>Bildirimleri devre dışı bırak

DPI değeri bildirilmesini değil, Visual Studio'da sorunları ölçeklendirme seçebilirsiniz. Bildirim Tasarımcısı'nda, örneğin çalışmayan durumunda devre dışı bırakmak isteyebilirsiniz.

Bildirimleri devre dışı bırakmayı tercih **Araçları** > **seçenekleri** açmak için **seçenekleri** iletişim. Ardından, **Windows Form Tasarımcısı** > **genel**, ayarlayıp **DPI ölçeklendirme bildirimleri** için **False**.

![Visual Studio'da bildirimleri seçeneği ölçeklendirme, DPI](./media/disable-dpi-awareness-visual-studio/notifications-option.png)

Ölçeklendirme bildirimleri daha sonra yeniden etkinleştirmek istiyorsanız, özellik kümesine **True**.

## <a name="troubleshoot"></a>Sorun giderme

DPI tanıma geçiş Visual Studio'da beklendiği gibi çalışmıyorsa, sahip olup olmadığını denetleyin `dpiAwareness` değerini **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows nt\currentversion\ımage dosya yürütme Options\devenv.exe**  Kayıt Defteri Düzenleyicisi'nde alt anahtar. Varsa, bu değeri silin.

## <a name="see-also"></a>Ayrıca bkz.

- [Windows Forms'ta otomatik ölçeklendirme](automatic-scaling-in-windows-forms.md)
