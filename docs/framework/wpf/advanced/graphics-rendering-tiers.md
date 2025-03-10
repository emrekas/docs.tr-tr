---
title: Grafik İşleme Katmanları
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], performance
- rendering graphics [WPF]
- rendering tiers [WPF]
- graphics rendering tiers [WPF]
- graphics [WPF], rendering tiers
ms.assetid: 08dd1606-02a2-4122-9351-c0afd2ec3a70
ms.openlocfilehash: 9da519f8d258673498f45a425c13863437cac597
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937528"
---
# <a name="graphics-rendering-tiers"></a>Grafik İşleme Katmanları
Bir işleme katmanı, bir [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] uygulamayı çalıştıran bir cihaz için grafik donanım yeteneği ve performansının düzeyini tanımlar.  

<a name="graphics_hardware"></a>   
## <a name="graphics-hardware"></a>Grafik donanımı  
 İşleme katmanı düzeylerini en çok etkileyen grafik donanımının özellikleri şunlardır:  
  
- **VIDEO RAM** 'i Grafik donanımındaki video belleği miktarı, birleştirme grafikleri için kullanılabilecek arabelleklerin boyutunu ve sayısını belirler.  
  
- **Piksel gölgelendiricisi** Piksel gölgelendiricisi, her piksel temelinde etkileri hesaplayan bir grafik işleme işlevidir. Görüntülenen grafiklerin çözümüne bağlı olarak, her bir görüntüleme çerçevesi için işlenmesi gereken birkaç milyon piksel olabilir.  
  
- **Köşe gölgelendiricisi** Köşe gölgelendiricisi, nesnenin köşe verilerinde matematik işlemleri gerçekleştiren bir grafik işleme işlevidir.  
  
- **Multitexture desteği** Multitexture desteği, 3B grafik nesnesindeki bir karıştırma işlemi sırasında iki veya daha fazla farklı doku uygulama imkanını ifade eder. Çoklu doku desteğinin derecesi, Grafik donanımındaki çok modelli birim sayısına göre belirlenir.  
  
<a name="rendering_tier_definitions"></a>   
## <a name="rendering-tier-definitions"></a>İşleme katmanı tanımları  
 Grafik donanımının özellikleri, bir [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] uygulamanın işleme yeteneğini tespit. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Sistem üç işleme katmanı tanımlar:  
  
- **Işleme katmanı 0** Grafik donanım hızlandırma yok. Tüm grafik özellikleri yazılım hızlandırma kullanır. DirectX sürüm düzeyi 9,0 sürümünden düşüktür.  
  
- **Işleme katmanı 1** Bazı grafik özellikleri grafik donanım hızlandırmasını kullanır. DirectX sürüm düzeyi 9,0 sürümüne eşit veya ondan daha büyük.  
  
- **Işleme katmanı 2** Çoğu grafik özelliği grafik donanım hızlandırmasını kullanır. DirectX sürüm düzeyi 9,0 sürümüne eşit veya ondan daha büyük.  
  
 <xref:System.Windows.Media.RenderCapability.Tier%2A?displayProperty=nameWithType> Özelliği, uygulama çalışma zamanında işleme katmanını almanızı sağlar. Cihazın, donanım hızlandırmalı belirli grafik özelliklerini destekleyip desteklemediğini öğrenmek için işleme katmanını kullanın. Uygulamanız daha sonra çalışma zamanında cihaz tarafından desteklenen işleme katmanına bağlı olarak farklı kod yolları alabilir.  
  
### <a name="rendering-tier-0"></a>İşleme katmanı 0  
 0 işleme katmanı değeri, cihazda uygulama için kullanılabilecek grafik donanım hızlandırma olmadığı anlamına gelir. Bu katman düzeyinde, tüm grafiklerin donanım hızlandırma olmadan yazılım tarafından işleneceğini varsaymalısınız. Bu katmanın işlevselliği 9,0 ' dan küçük bir DirectX sürümüne karşılık geliyor.  
  
### <a name="rendering-tier-1-and-rendering-tier-2"></a>İşleme katmanı 1 ve Işleme katmanı 2  
  
> [!NOTE]
> .NET Framework 4 ' ten başlayarak, işleme katmanı 1 yalnızca DirectX 9,0 veya üstünü destekleyen grafik donanımını içerecek şekilde yeniden tanımlandı. DirectX 7 veya 8 ' i destekleyen grafik donanımı artık işleme katmanı 0 olarak tanımlandı.  
  
 1 veya 2. bir işleme katmanı değeri, ' ın grafik özelliklerinin [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] çoğunun, gerekli sistem kaynakları kullanılabilir olduğunda ve tükenmemiş olması halinde donanım hızlandırmasını kullanacağı anlamına gelir. Bu, 9,0 'den büyük veya buna eşit bir DirectX sürümüne karşılık gelir.  
  
 Aşağıdaki tabloda, katman 1 ve işleme katmanı 2 için grafik donanım gereksinimlerindeki farklılıklar gösterilmektedir:  
  
|Özellik|Katman 1|Katman 2|  
|-------------|------------|------------|  
|DirectX sürümü|9,0 değerinden büyük veya buna eşit olmalıdır.|9,0 değerinden büyük veya buna eşit olmalıdır.|  
|Video RAM 'i|60 MB 'tan büyük veya buna eşit olmalıdır.|120MB 'den büyük veya buna eşit olmalıdır.|  
|Piksel gölgelendiricisi|Sürüm düzeyi 2,0 'den büyük veya buna eşit olmalıdır.|Sürüm düzeyi 2,0 'den büyük veya buna eşit olmalıdır.|  
|Köşe gölgelendiricisi|Gereksinim yok.|Sürüm düzeyi 2,0 'den büyük veya buna eşit olmalıdır.|  
|Multitexture birimleri|Gereksinim yok.|Birim sayısı 4 ' ten büyük veya buna eşit olmalıdır.|  
  
 Aşağıdaki özellikler ve yetenekler, işleme katmanı 1 ve işleme katmanı 2 için donanım hızlandırılır:  
  
|Özellik|Notlar|  
|-------------|-----------|  
|2B işleme|En 2B işleme desteklenir.|  
|3B Tarama|3B rasterleştirme çoğu desteklenir.|  
|3B aniztropıc filtrelemesi|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]3D içeriği işlerken anısotropıc filtrelemeyi kullanmaya çalışır. Anısotropıc filtresi, kameraya göre uzakta ve çok daha fazla açılı olan yüzeylerde dokuların görüntü kalitesini geliştirmek anlamına gelir.|  
|3B MıP eşlemesi|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]3B içeriği işlerken MıP eşlemesini kullanmaya çalışır. MıP eşlemesi, bir doku bir <xref:System.Windows.Controls.Viewport3D>görünümünde daha küçük bir görünüm alanı kapladığı zaman doku işleme kalitesini geliştirir.|  
|Radyal degradeler|Desteklenirken, büyük nesneler <xref:System.Windows.Media.RadialGradientBrush> üzerinde kullanmaktan kaçının.|  
|3B aydınlatma hesaplamaları|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Her köşede bir kafeste uygulanan her bir tepe için bir hafif şiddette hesaplanacak olması anlamına gelen, köşe başına aydınlatma gerçekleştirir.|  
|Metin işleme|Alt piksel yazı tipi işleme, grafik donanımında kullanılabilir Piksel gölgelendiricileri kullanır.|  
  
 Aşağıdaki özellikler ve yetenekler yalnızca işleme katmanı 2 için donanım hızlandırılır:  
  
|Özellik|Notlar|  
|-------------|-----------|  
|3B kenar yumuşatma|3B kenar yumuşatma yalnızca, [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] ve [!INCLUDE[win7](../../../../includes/win7-md.md)]gibi Windows görüntü sürücü modelini (WDDM) destekleyen işletim sistemlerinde desteklenir.|  
  
 Aşağıdaki özellikler ve yetenekler donanım hızlandırılmamış **değildir** :  
  
|Özellik|Notlar|  
|-------------|-----------|  
|Yazdırılmış içerik|Tüm yazdırılan içerikler [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] yazılım işlem hattı kullanılarak işlenir.|  
|Kullanan taranmış içerik<xref:System.Windows.Media.Imaging.RenderTargetBitmap>|<xref:System.Windows.Media.Imaging.RenderTargetBitmap.Render%2A>Yöntemikullanılarak işlenmiş içerik. <xref:System.Windows.Media.Imaging.RenderTargetBitmap>|  
|Tarafından kullanılan döşeli içerik<xref:System.Windows.Media.TileBrush>|<xref:System.Windows.Media.TileBrush.TileMode%2A> Öğesinin özelliğinin olarak ayarlandığı<xref:System.Windows.Media.TileMode.Tile>döşeli içerik. <xref:System.Windows.Media.TileBrush>|  
|Grafik donanımının en büyük doku boyutunu aşan yüzeyler|Çoğu grafik donanımında, büyük yüzeyler 20 48x2048 veya 4096x4096 piksel boyutlardır.|  
|Video RAM gereksinimi grafik donanımının belleğini aşan tüm işlemler|Uygulama video RAM kullanımını, Windows SDK [WPF Performans paketine](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa969767(v=vs.100)) dahil olan Perforator aracını kullanarak izleyebilirsiniz.|  
|Katmanlı pencereler|Katmanlı pencereler, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] uygulamaların dikdörtgen olmayan bir pencerede ekran üzerinde içerik işlemesine izin verir. [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] Ve[!INCLUDE[win7](../../../../includes/win7-md.md)]gibi Windows görüntü sürücü modelini (WDDM) destekleyen işletim sistemlerinde, katmanlı pencereler donanım hızlandırılır. Gibi diğer sistemlerde [!INCLUDE[winxp](../../../../includes/winxp-md.md)], katmanlı pencereler donanım ivmesi olmadan yazılım tarafından işlenir.<br /><br /> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Aşağıdaki<xref:System.Windows.Window> özellikleri ayarlayarak ' de katmanlı pencereleri etkinleştirebilirsiniz:<br /><br /> -   <xref:System.Windows.Window.WindowStyle%2A> = <xref:System.Windows.WindowStyle.None><br />-   <xref:System.Windows.Window.AllowsTransparency%2A> = `true`<br />-   <xref:System.Windows.Controls.Control.Background%2A> = <xref:System.Windows.Media.Brushes.Transparent%2A>|  
  
<a name="other_resources"></a>   
## <a name="other-resources"></a>Diğer Kaynaklar  
 Aşağıdaki kaynaklar, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] uygulamanızın performans özelliklerini çözümlemenize yardımcı olabilir.  
  
### <a name="graphics-rendering-registry-settings"></a>Grafik İşleme Kayıt Defteri Ayarları  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]oluşturmayı denetlemek [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] için dört kayıt defteri ayarı sağlar:  
  
|Ayar|Açıklama|  
|-------------|-----------------|  
|**Donanım hızlandırma seçeneğini devre dışı bırak**|Donanım hızlandırmasının etkinleştirilip etkinleştirilmeyeceğini belirtir.|  
|**Maksimum çok örnekli değer**|3-b içeriğini düzgünleştirmek için çoklu örnekleme derecesini belirtir.|  
|**Gerekli video sürücüsü tarih ayarı**|Sistemin donanım hızlandırmasını 2004 Kasım 'Dan önce yayınlanan sürücüler için devre dışı bırakıp bırakmadığını belirtir.|  
|**Başvuru tarayıcısı seçeneğini kullanma**|Başvuru tarayıcısının [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] kullanılması gerekip gerekmediğini belirtir.|  
  
 Bu ayarlara, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] kayıt defteri ayarlarına nasıl başvurulacağını bilen herhangi bir dış yapılandırma yardımcı programı tarafından erişilebilir. Bu ayarlar, Windows kayıt defteri Düzenleyicisi kullanılarak değerlere doğrudan erişerek da oluşturulabilir veya değiştirilebilir. Daha fazla bilgi için bkz. [grafik Işleme kayıt defteri ayarları](../graphics-multimedia/graphics-rendering-registry-settings.md).  
  
### <a name="wpf-performance-profiling-tools"></a>WPF Performans Profil Oluşturma Araçları  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], uygulamanızın çalışma zamanı davranışını çözümlemenize ve uygulayabileceğiniz performans iyileştirmeleri türlerini belirlemenize olanak tanıyan bir dizi performans profil araçları sağlar. Aşağıdaki tabloda, WPF performans paketi Windows SDK aracı 'nda bulunan performans profil oluşturma araçları listelenmektedir:  
  
|Aracı|Açıklama|  
|----------|-----------------|  
|Perforator|İşleme davranışını çözümlemek için kullanın.|  
|Visual Profil Oluşturucu|Görsel ağacındaki öğelere göre düzen ve [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] olay işleme gibi hizmetlerin kullanımını profil oluşturmak için kullanın.|  
  
 WPF performans paketi, performans verilerinin zengin ve grafik bir görünümünü sağlar. WPF Performans araçları hakkında daha fazla bilgi için bkz. [WPF performans paketi](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa969767(v=vs.100)).  
  
### <a name="directx-diagnostic-tool"></a>DirectX Tanılama Aracı  
 DirectX ile ilgili sorunları gidermenize yardımcı olmak üzere dxdiag. exe ' nin DirectX Tanılama aracı. DirectX Tanılama aracı için varsayılan yükleme klasörü:  
  
 `~\Windows\System32`  
  
 DirectX Tanılama aracını çalıştırdığınızda ana pencere, DirectX ile ilgili bilgileri görüntülemenizi ve tanılamanıza olanak tanıyan bir sekmeler kümesi içerir. Örneğin, **sistem** sekmesi bilgisayarınız hakkında sistem bilgileri sağlar ve bilgisayarınızda yüklü DirectX sürümünü belirtir.  
  
 ![Ekran etkin: DirectX Tanılama Aracı](./media/directxdiagnostictool-01.png "DirectXDiagnosticTool_01")  
DirectX Tanılama aracı ana penceresi  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Windows.Media.RenderCapability>
- <xref:System.Windows.Media.RenderOptions>
- [WPF Uygulama Performansını İyileştirme](optimizing-wpf-application-performance.md)
- [WPF performans paketi](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa969767(v=vs.100))
- [Grafik İşleme Kayıt Defteri Ayarları](../graphics-multimedia/graphics-rendering-registry-settings.md)
- [Animasyon İpuçları ve Püf Noktaları](../graphics-multimedia/animation-tips-and-tricks.md)
