---
title: WPF Windows'a Genel Bakış
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], displaying content via
- XAML pages [WPF], displaying
- content [WPF], displaying via XAML
- window objects [WPF]
- hosting [WPF], applications
- managing windows [WPF]
- dialog boxes [WPF]
- Page object [WPF]
- NavigationWindow objects [WPF]
- applications [WPF], hosting
- content [WPF], displaying
- events [WPF]
- content [WPF], displaying via procedural code
- modal windows [WPF]
- procedural code [WPF], displaying content via
- displaying content via procedural code [WPF]
- window management [WPF]
- displaying content [WPF]
- window events [WPF]
- windows [WPF]
- modal dialog boxes [WPF]
- displaying XAML pages [WPF]
ms.assetid: 737d04ec-8861-46c3-8d44-fa11d3528d23
ms.openlocfilehash: 16f4155cefea20868185febb3d2a566dc1524cc4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956280"
---
# <a name="wpf-windows-overview"></a>WPF Windows'a Genel Bakış
Kullanıcılar Windows aracılığıyla Windows Presentation Foundation (WPF) tek başına uygulamalarıyla etkileşime geçer. Bir pencerenin birincil amacı, verileri görselleştirerek kullanıcıların verilerle etkileşime geçmesini sağlayan içeriği barındırmak için kullanılır. Tek [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] başına uygulamalar, <xref:System.Windows.Window> sınıfını kullanarak kendi pencerelerini sağlar. Bu konu, <xref:System.Windows.Window> Windows 'un tek başına uygulamalarda oluşturulması ve yönetilmesi ile ilgili temel bilgileri kapsamadan önce tanıtılmıştır.  
  
> [!NOTE]
> Tarayıcı tarafından barındırılan [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] uygulamalar, ve [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] gevşek [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] sayfalar dahil, kendi pencerelerini sağlamıyor. Bunun yerine, Windows Internet Explorer tarafından sunulan Windows 'da barındırılır. Bkz. [WPF XAML tarayıcı uygulamalarına genel bakış](wpf-xaml-browser-applications-overview.md).  

<a name="TheWindowClass"></a>   
## <a name="the-window-class"></a>Pencere sınıfı  
 Aşağıdaki şekilde pencerenin yapısal kısımları gösterilmektedir:  
  
 ![Pencere öğelerini gösteren ekran görüntüsü.](./media/wpf-windows-overview/window-constituent-elements.png)  
  
 Bir pencere iki alana ayrılmıştır: istemci olmayan alan ve istemci alanı.  
  
 Bir pencerenin *istemci olmayan alanı* tarafından [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] uygulanır ve aşağıdakiler dahil olmak üzere çoğu Windows için ortak olan bir pencerenin parçalarını içerir:  
  
- Bir kenarlık.  
  
- Başlık çubuğu.  
  
- Bir simge.  
  
- Küçült, Ekranı Kapla ve geri yükle düğmeleri.  
  
- Kapat düğmesi.  
  
- Kullanıcıların bir pencereyi en aza indirmenize, ekranı kaplamaya, geri yüklemelerine, taşımasına, yeniden boyutlandırmaya ve kapatılmasına izin veren menü öğeleriyle bir sistem menüsü.  
  
 Pencerenin *istemci alanı* , bir pencerenin istemci olmayan alanındaki alanıdır ve geliştiriciler tarafından menü çubukları, araç çubukları ve denetimler gibi uygulamaya özgü içerik eklemek için kullanılır.  
  
 ' [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]De, bir pencere, aşağıdakileri yapmak <xref:System.Windows.Window> için kullandığınız sınıfa göre kapsüllenir:  
  
- Bir pencere görüntüleyin.  
  
- Pencerenin boyutunu, konumunu ve görünümünü yapılandırın.  
  
- Uygulamaya özgü içeriği barındırın.  
  
- Pencerenin ömrünü yönetin.  
  
<a name="DefiningAWindow"></a>   
## <a name="implementing-a-window"></a>Pencere uygulama  
 Tipik bir pencerenin uygulanması, görünümün ve davranışın yanı sıra, *görünümün* kullanıcılar tarafından kullanıcılara nasıl göründüğünü ve *davranışın* Kullanıcı tarafından etkileşim kurma şeklini tanımlar. ' [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]De, kod veya [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] biçimlendirme kullanarak bir pencerenin görünümünü ve davranışını uygulayabilirsiniz.  
  
 Ancak, genel olarak, bir pencerenin görünümü biçimlendirme kullanılarak [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] uygulanır ve davranışı aşağıdaki örnekte gösterildiği gibi arka plan kodu kullanılarak uygulanır.  
  
 [!code-xaml[WindowsOverviewSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
 Bir [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] işaretleme dosyası ve arka plan kod dosyasının birlikte çalışmasını sağlamak için aşağıdakiler gereklidir:  
  
- Biçimlendirme ' de, `Window` öğesi `x:Class` özniteliğini içermelidir. Uygulama yapılandırıldığında, biçimlendirme `x:Class` dosyasında bulunması Microsoft Build Engine (MSBuild) ' den <xref:System.Windows.Window> türetilen ve `x:Class` özniteliği tarafından belirtilen adı içeren bir `partial` sınıf oluşturmasına neden olur. Bu, [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] şema ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ) için bir ad alanı bildiriminin eklenmesini gerektirir. Oluşturulan `partial` sınıf, olayları kaydetmek `InitializeComponent` ve biçimlendirmede uygulanan özellikleri ayarlamak için çağrılan yöntemini uygular.  
  
- Arka plan kod içinde, sınıf, biçimlendirme içindeki `partial` `x:Class` özniteliği tarafından belirtilen aynı ada sahip bir sınıf olmalıdır ve ' den <xref:System.Windows.Window>türetmelidir. Bu, arka plan kod dosyasının, uygulama oluşturulduğunda biçimlendirme dosyası için `partial` oluşturulan sınıfla ilişkilendirilmesini sağlar (bkz. [WPF uygulaması oluşturma](building-a-wpf-application-wpf.md)).  
  
- Arka plan kod içinde, <xref:System.Windows.Window> sınıfının `InitializeComponent` yöntemini çağıran bir Oluşturucu uygulaması gerekir. `InitializeComponent`, biçimlendirme dosyasının oluşturulan `partial` sınıfı tarafından olayları kaydetmek ve biçimlendirmede tanımlanan özellikleri ayarlamak için uygulanır.  
  
> [!NOTE]
> <xref:System.Windows.Window> Kullanarak <xref:System.Windows.Window> projenizeyeni[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]bir eklediğinizde,, hem biçimlendirme hem de arka plan kodu kullanılarak uygulanır ve, biçimlendirme ve arka plan kod dosyaları arasındaki ilişkiyi oluşturmak için gereken yapılandırmayı içerir burada açıklanmıştır.  
  
 Bu yapılandırmayla birlikte, biçimlendirme ' de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pencerenin görünümünü tanımlamaya ve davranışını arka plan kodu ' nda uygulamaya odaklanırsınız. Aşağıdaki örnek, bir düğme içeren bir pencereyi, biçimlendirme ' de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] uygulanan bir pencere ve <xref:System.Windows.Controls.Primitives.ButtonBase.Click> düğmenin olayı için bir olay işleyicisi gösterir ve arka plan kod içinde uygulanır.  
  
 [!code-xaml[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
<a name="ConfiguringWindowForMSBuild"></a>   
## <a name="configuring-a-window-definition-for-msbuild"></a>MSBuild için pencere tanımı yapılandırma  
 Pencerenizi nasıl uyguladığınız, MSBuild için nasıl yapılandırıldığını belirler. Hem biçimlendirme hem de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] arka plan kodu kullanılarak tanımlanan bir pencere için:  
  
- XAML biçimlendirme dosyaları MSBuild `Page` öğeleri olarak yapılandırılır.  
  
- Arka plan kod dosyaları MSBuild `Compile` öğeleri olarak yapılandırılır.  
  
 Bu, aşağıdaki MSBuild proje dosyasında gösterilmiştir.  
  
```xml  
<Project ...  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    ...  
    <Page Include="MarkupAndCodeBehindWindow.xaml" />  
    <Compile Include=" MarkupAndCodeBehindWindow.xaml.cs" />  
    ...  
</Project>  
```  
  
 Uygulama oluşturma [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] hakkında daha fazla bilgi için bkz. [WPF uygulaması oluşturma](building-a-wpf-application-wpf.md).  
  
<a name="WindowLifetime"></a>   
## <a name="window-lifetime"></a>Pencere ömrü  
 Herhangi bir sınıfta olduğu gibi, bir pencere ilk kez başlatıldığında başlayan, açıldıktan sonra, etkin ve devre dışı bırakılmış ve sonunda kapatılan bir yaşam süresine sahiptir.  

<a name="Opening_a_Window"></a>   
### <a name="opening-a-window"></a>Pencere açma  
 Bir pencereyi açmak için ilk olarak bir örneği oluşturursunuz, bu, aşağıdaki örnekte gösterilmiştir.  
  
 [!code-xaml[WindowsOverviewStartupEventSnippets#AppMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml#appmarkup)]  
  
 [!code-csharp[WindowsOverviewStartupEventSnippets#AppCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml.cs#appcodebehind)]  
  
 Bu örnekte `MarkupAndCodeBehindWindow` , uygulama başladığında oluşur <xref:System.Windows.Application.Startup> ve olay tetiklenir.  
  
 Bir pencere oluşturulduğunda, <xref:System.Windows.Application> nesne tarafından yönetilen bir Windows listesine otomatik olarak bir başvuru eklenir (bkz <xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType>.). Ayrıca, örneği oluşturulacak ilk pencere, varsayılan olarak, ana uygulama penceresi (bkz <xref:System.Windows.Application> <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>.) olarak ayarlanır.  
  
 Pencere son olarak <xref:System.Windows.Window.Show%2A> yöntemi çağırarak açılır; sonuç aşağıdaki şekilde gösterilmiştir.  
  
 ![Window. Show çağırarak bir pencere açıldı](./media/wpf-windows-overview//window-opened-show-method.png)  
  
 Çağırarak <xref:System.Windows.Window.Show%2A> açılan bir pencere, uygulamanın, kullanıcıların aynı uygulamadaki diğer pencereleri etkinleştirmesine izin veren bir modda çalıştığı, geçici bir pencere olduğunu belirtir.  
  
> [!NOTE]
> <xref:System.Windows.Window.ShowDialog%2A>, iletişim kutuları gibi pencere açmak için çağrılır. Daha fazla bilgi için bkz. [Iletişim kutularına genel bakış](dialog-boxes-overview.md) .  
  
 <xref:System.Windows.Window.Show%2A> Çağrıldığında, bir pencere, Kullanıcı girişi almasına izin veren altyapıyı kurmak üzere gösterilmeden önce başlatma işini gerçekleştirir. Pencere başlatıldığında <xref:System.Windows.Window.SourceInitialized> olay tetiklenir ve pencere görüntülenir.  
  
 Bir kısayol olarak, <xref:System.Windows.Application.StartupUri%2A> bir uygulama başlatıldığında otomatik olarak açılan ilk pencereyi belirtmek için ayarlanabilir.  
  
 [!code-xaml[WindowsOverviewSnippets#ApplicationStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/App.xaml#applicationstartupurimarkup)]  
  
 Uygulama başlatıldığında, değeri <xref:System.Windows.Application.StartupUri%2A> tarafından belirtilen pencere modelessly olarak açılır; dahili olarak pencere <xref:System.Windows.Window.Show%2A> yöntemi çağırarak açılır.  
  
<a name="Ownership"></a>   
#### <a name="window-ownership"></a>Pencere sahipliği  
 <xref:System.Windows.Window.Show%2A> Yöntemi kullanılarak açılan bir pencere, kendisini oluşturan pencereyle örtük bir ilişkiye sahip değildir; kullanıcılar, herhangi bir pencereyle bağımsız olarak etkileşime girebilir, yani her iki pencere de şunları yapabilir:  
  
- Diğerini (pencerelerin <xref:System.Windows.Window.Topmost%2A> bir özelliği olarak `true`ayarlanmış değilse) kapsar.  
  
- Diğerini etkilemeden simge durumuna küçültülmüş, ekranı kaplamış ve geri yüklenmiş olmalıdır.  
  
 Bazı pencereler, açan pencereyle bir ilişki gerektirir. Örneğin, tümleşik bir geliştirme ortamı (IDE) uygulaması, normal davranışı kendilerini oluşturan pencereyi kapsayan özellik pencerelerini ve araç pencerelerini açabilir. Ayrıca, bu gibi pencerelerin her zaman, bunları oluşturan pencereyle birlikte her zaman kapatmaları, en üst düzeye çıkarması ve geri yüklenmesi gerekir. Bu tür bir ilişki, bir pencere diğeri tarafından oluşturulabilir ve sahip pencerenin <xref:System.Windows.Window.Owner%2A> özelliği *sahip penceresine*bir başvuru olarak ayarlanarak elde edilebilir . Bu, aşağıdaki örnekte gösterilir.  
  
 [!code-csharp[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/CSharp/MainWindow.xaml.cs#setwindowownercode)]
 [!code-vb[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/visualbasic/mainwindow.xaml.vb#setwindowownercode)]  
  
 Sahiplik kurulduktan sonra:  
  
- Sahibi olan pencere, <xref:System.Windows.Window.Owner%2A> özelliğinin değerini inceleyerek sahip penceresine başvurabilir.  
  
- Sahip penceresi, <xref:System.Windows.Window.OwnedWindows%2A> özelliğinin değerini inceleyerek sahip olduğu tüm pencereleri bulabilir.  
  
<a name="Preventing"></a>   
#### <a name="preventing-window-activation"></a>Windows etkinleştirmesini önler  
 Internet Messenger stili uygulamanın konuşma pencereleri veya bir e-posta uygulamasının bildirim pencereleri gibi, gösterildiğinde Windows 'un etkinleştirilmemesi gereken senaryolar vardır.  
  
 Uygulamanızda, gösterildiğinde etkinleştirilmemelidir bir pencere varsa, <xref:System.Windows.Window.ShowActivated%2A> <xref:System.Windows.Window.Show%2A> yöntemi ilk kez çağrılmadan önce özelliğini olarak `false` ayarlayabilirsiniz. Sonuç olarak:  
  
- Pencere etkin değil.  
  
- Pencerenin <xref:System.Windows.Window.Activated> olayı çıkarılmadı.  
  
- Etkin durumda olan pencere etkin kalır.  
  
 Ancak, Kullanıcı istemciyi veya istemci dışı alanı tıklatarak etkinleştirdiğinde, pencere etkinleştirilir. Bu durumda:  
  
- Pencere etkinleştirilir.  
  
- Pencerenin <xref:System.Windows.Window.Activated> olayı tetiklenir.  
  
- Önceden etkinleştirilen pencere devre dışı bırakıldı.  
  
- Pencere <xref:System.Windows.Window.Deactivated> ve<xref:System.Windows.Window.Activated> olayları daha sonra kullanıcı eylemlerine yanıt olarak beklendiği gibi oluşturulur.  
  
<a name="Window_Activation"></a>   
### <a name="window-activation"></a>Pencere etkinleştirme  
 Bir pencere ilk açıldığında etkin pencere olur (olarak <xref:System.Windows.Window.ShowActivated%2A> `false`ayarlanmış olarak gösterilmediği takdirde). *Etkin pencere* , anahtar vuruşları ve fare tıklamaları gibi şu anda Kullanıcı girişi yakalama penceresidir. Bir pencere etkin olduğunda <xref:System.Windows.Window.Activated> olayı başlatır.  
  
> [!NOTE]
> Bir pencere ilk açıldığında, <xref:System.Windows.FrameworkElement.Loaded> ve <xref:System.Windows.Window.ContentRendered> olayları yalnızca <xref:System.Windows.Window.Activated> olay oluşturulduktan sonra tetiklenir. Bu şekilde aklınızda, bir pencere başlatıldığında açık <xref:System.Windows.Window.ContentRendered> olarak kabul edilebilir.  
  
 Bir pencere etkin olduktan sonra, Kullanıcı aynı uygulamadaki başka bir pencereyi etkinleştirebilir veya başka bir uygulamayı etkinleştirebilir. Bu durumda, etkin olan pencere devre dışı bırakılır ve <xref:System.Windows.Window.Deactivated> olayı başlatır. Benzer şekilde, Kullanıcı şu anda devre dışı bırakılmış bir pencere seçtiğinde pencere yeniden etkin hale gelir <xref:System.Windows.Window.Activated> ve oluşturulur.  
  
 İşlemenin <xref:System.Windows.Window.Activated> yaygın bir nedeni ve <xref:System.Windows.Window.Deactivated> yalnızca bir pencere etkin olduğunda çalışabilen işlevselliği etkinleştirmek ve devre dışı bırakmak. Örneğin, bazı pencereler, Oyunlar ve video oynatıcılar dahil olmak üzere sabit Kullanıcı girişi veya ilgilenilmesi gereken etkileşimli içeriği görüntüler. Aşağıdaki örnek, bu davranışın nasıl işleneceğini <xref:System.Windows.Window.Activated> ve <xref:System.Windows.Window.Deactivated> uygulanacağını gösteren basitleştirilmiş bir video oynatıcı örneğidir.  
  
 [!code-xaml[WindowsOverviewSnippets#ActivationDeactivationMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml#activationdeactivationmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml.cs#activationdeactivationcodebehind)]
 [!code-vb[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/CustomMediaPlayerWindow.xaml.vb#activationdeactivationcodebehind)]  
  
 Bir pencere devre dışı bırakıldığında diğer uygulama türleri de arka planda kod çalıştırabilir. Örneğin, bir posta istemcisi, Kullanıcı başka uygulamalar kullanırken posta sunucusunu yoklamaya devam edebilir. Bunlar gibi uygulamalar, ana pencere devre dışı bırakıldığında farklı veya ek bir davranış sağlar. Posta programına göre, bu durum hem gelen kutusuna yeni posta öğesini ekleyip hem de sistem tepsisine bir bildirim simgesi eklemeye anlamına gelebilir. Bildirim simgesi yalnızca posta penceresi etkin olmadığında, <xref:System.Windows.Window.IsActive%2A> özelliği inceleyerek belirlenebilir.  
  
 Bir arka plan görevi tamamlanırsa, bir pencere, metodu çağırarak <xref:System.Windows.Window.Activate%2A> kullanıcıya daha akıllıca bildirimde bulunmasını isteyebilir. Kullanıcı çağrıldığında etkinleştirilen <xref:System.Windows.Window.Activate%2A> başka bir uygulamayla etkileşim kurmaktadır, pencerenin görev çubuğu düğmesi yanıp sönmelidir. Bir Kullanıcı geçerli uygulamayla etkileşim kursunsam, çağıran <xref:System.Windows.Window.Activate%2A> pencereyi ön plana getirir.  
  
> [!NOTE]
> Uygulama kapsamı etkinleştirmesini <xref:System.Windows.Application.Activated?displayProperty=nameWithType> ve <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> olaylarını kullanarak işleyebilirsiniz.  
  
<a name="Closing_a_Window"></a>   
### <a name="closing-a-window"></a>Pencereyi kapatma  
 Bir pencerenin ömrü, bir kullanıcı tarafından kapandığında bir uca geliyor. Bir pencere, aşağıdakiler de dahil olmak üzere istemci olmayan alandaki öğeler kullanılarak kapatılabilir:  
  
- **Sistem** menüsünün **Kapanış** öğesi.  
  
- ALT + F4 tuşlarına basın.  
  
- **Kapat** düğmesine basma.  
  
 Bir pencereyi kapatmak için istemci alanına ek mekanizmalar sağlayabilirsiniz, daha yaygın olarak şunları içerir:  
  
- Genellikle ana uygulama pencereleri için **Dosya** menüsündeki **Çıkış** öğesi.  
  
- **Dosya** menüsünde, genellikle ikincil bir uygulama penceresinde bir **Kapanış** öğesi.  
  
- Genellikle kalıcı iletişim kutusunda bir **iptal** düğmesi.  
  
- Genellikle kalıcı olmayan iletişim kutusunda **Kapat** düğmesi.  
  
 Bu özel mekanizmalardan birine yanıt olarak bir pencereyi kapatmak için <xref:System.Windows.Window.Close%2A> yöntemini çağırmanız gerekir. Aşağıdaki örnek, **Dosya** menüsünden **Çıkış** ' i seçerek bir pencereyi kapatma özelliğini uygular.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowWithFileExitMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml#windowwithfileexitmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml.cs#windowwithfileexitcodebehind)]
 [!code-vb[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/WindowWithFileExit.xaml.vb#windowwithfileexitcodebehind)]  
  
 Bir pencere kapandığında iki olay oluşturur: <xref:System.Windows.Window.Closing> ve. <xref:System.Windows.Window.Closed>  
  
 <xref:System.Windows.Window.Closing>pencere kapandıktan sonra tetiklenir ve pencere kapanışının önlenbileceği bir mekanizma sağlar. Pencere kapanışı önlemediği bir yaygın nedeni, pencere içeriğinin değiştirilen verileri içermi. Bu durumda, <xref:System.Windows.Window.Closing> verilerin kirli olup olmadığını ve bu durumda kullanıcıdan, verileri kaydetmeden pencereyi kapatmaya devam edip etmediğini veya pencere kapanışını iptal etmeyi isteyip istemediğini sormak için olay işlenebilir. Aşağıdaki örnek, işlemenin <xref:System.Windows.Window.Closing>önemli yönlerini gösterir.  
  
 [!code-csharp[WindowClosingSnippets](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs)]
 [!code-vb[WindowClosingSnippets](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb)]  

 `Boolean` <xref:System.ComponentModel.CancelEventArgs> `true` <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> Olay işleyicisi, bir pencerenin kapatmasını engellemek için olarak ayarladığınız özelliğini uygulayan bir öğesine geçirilir. <xref:System.Windows.Window.Closing>  
  
 <xref:System.Windows.Window.Closing> İşlenmezse veya işlenirse ancak iptal edilmezse pencere kapanır. Pencerenin gerçekten kapanmadan hemen önce, <xref:System.Windows.Window.Closed> tetiklenir. Bu noktada, bir pencerenin kapatılması engellenemez.  
  
> [!NOTE]
> Uygulama, ana uygulama penceresi kapandığında (bkz <xref:System.Windows.Application.MainWindow%2A>.) ya da son pencere kapandığında otomatik olarak kapatılacak şekilde yapılandırılabilir. Ayrıntılar için bkz <xref:System.Windows.Application.ShutdownMode%2A>.  
  
 Bir pencere, istemci olmayan ve istemci alanlarında belirtilen mekanizmalarla açıkça kapatılaken, aşağıdakiler de dahil olmak üzere uygulamanın veya pencerelerin diğer bölümlerinde davranış sonucu olarak bir pencere de dolaylı olarak kapatılabilir:  
  
- Kullanıcı oturumu kapatır veya Windows oturumunu kapatır.  
  
- Pencerenin sahibi kapanır (bkz <xref:System.Windows.Window.Owner%2A>.).  
  
- Ana uygulama penceresi kapalıdır ve ' <xref:System.Windows.Application.ShutdownMode%2A> dir. <xref:System.Windows.ShutdownMode.OnMainWindowClose>  
  
- <xref:System.Windows.Application.Shutdown%2A>çağırılır.  
  
> [!NOTE]
> Pencere kapatıldıktan sonra yeniden açılamaz.  
  
<a name="Window_Lifetime_Events"></a>   
### <a name="window-lifetime-events"></a>Pencere yaşam süresi olayları  
 Aşağıdaki çizimde, bir pencerenin kullanım ömrü içinde asıl olayların sırası gösterilmektedir:  
  
 ![Bir pencerenin ömrü içindeki olayları gösteren diyagram.](./media/wpf-windows-overview/window-lifetime-events.png)  
  
 Aşağıdaki çizimde, bir pencerenin kullanım ömrü olmadan gösterilen (<xref:System.Windows.Window.ShowActivated%2A> pencere gösterilmeden önce olarak `false` ayarlanır) bir pencerenin ömrü içindeki asıl olayların sırası gösterilmektedir:  
  
 ![Etkin olmayan olayları etkinleştirme olmadan bir pencerede gösteren diyagram.](./media/wpf-windows-overview/window-lifetime-no-activation.png)  
  
<a name="WindowLocation"></a>   
## <a name="window-location"></a>Pencere konumu  
 Bir pencere açıkken, masaüstüne göre x ve y boyutlarında bir konum vardır. Bu konum, sırasıyla <xref:System.Windows.Window.Left%2A> ve <xref:System.Windows.Window.Top%2A> özelliklerini inceleyerek belirlenebilir. Bu özellikleri pencerenin konumunu değiştirmek için ayarlayabilirsiniz.  
  
 Aşağıdaki <xref:System.Windows.Window.WindowStartupLocation%2A> <xref:System.Windows.Window> sabit<xref:System.Windows.WindowStartupLocation> listesi değerlerinden biriyle özelliği ayarlayarak ilk göründüğünde bir başlangıç konumunu da belirtebilirsiniz:  
  
- <xref:System.Windows.WindowStartupLocation.CenterOwner>varsayılanını  
  
- <xref:System.Windows.WindowStartupLocation.CenterScreen>  
  
- <xref:System.Windows.WindowStartupLocation.Manual>  
  
 Başlangıç konumu olarak <xref:System.Windows.WindowStartupLocation.Manual>belirtilmişse <xref:System.Windows.Window.Left%2A> ve ve <xref:System.Windows.Window.Top%2A> özellikleri ayarlanmamışsa <xref:System.Windows.Window> , Windows 'un bir konum görünmesini ister.  
  
<a name="Topmost_Windows_and_Z_Order"></a>   
### <a name="topmost-windows-and-z-order"></a>En üstteki pencere ve Z düzeni  
 X ve y konumuna sahip olmanın yanı sıra, bir pencere z boyutunda bir konuma da sahiptir ve bu da diğer pencereler açısından dikey konumunu belirler. Bu, pencerenin z düzeni olarak bilinir ve iki tür vardır: normal z düzeni ve en üstteki z düzeni. *Normal z düzeninde* pencerenin konumu, şu anda etkin olup olmadığına göre belirlenir. Varsayılan olarak, bir pencere normal z düzeninde bulunur. *En üstteki z düzeninde* pencerenin konumu, şu anda etkin olup olmadığına göre belirlenir. Ayrıca, en üstteki z düzeninde bulunan pencereler her zaman normal z düzeninde Windows üzerinde bulunur. Bir pencere, <xref:System.Windows.Window.Topmost%2A> özelliği olarak `true`ayarlanarak en üstteki z düzeninde bulunur.  
  
 [!code-xaml[WindowsOverviewSnippets#TopmostWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup1)]  
  
 Her z düzeninde, etkin olan pencere aynı z düzeninde diğer tüm pencerelerin üstünde görünür.  
  
<a name="WindowSize"></a>   
## <a name="window-size"></a>Pencere boyutu  
 Masaüstü konumuna sahip olmanın yanı sıra, bir pencere çeşitli genişlik ve yükseklik özellikleri <xref:System.Windows.Window.SizeToContent%2A>de dahil olmak üzere çeşitli özelliklerle belirlenen bir boyuta sahiptir.  
  
 <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Width%2A> ve<xref:System.Windows.FrameworkElement.MaxWidth%2A> bir pencerenin ömrü boyunca sahip olduğu ve aşağıdaki örnekte gösterildiği gibi yapılandırıldığı genişlikler aralığını yönetmek için kullanılır.  
  
 [!code-xaml[WindowsOverviewSnippets#WidthWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup1)]  
  
 Pencere yüksekliği, <xref:System.Windows.FrameworkElement.Height%2A>, ve <xref:System.Windows.FrameworkElement.MinHeight%2A> <xref:System.Windows.FrameworkElement.MaxHeight%2A>tarafından yönetilir ve aşağıdaki örnekte gösterildiği gibi yapılandırılır.  
  
 [!code-xaml[WindowsOverviewSnippets#HeightWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup1)]  
  
 Çeşitli genişlik değerleri ve yükseklik değerleri her biri bir Aralık belirttiği için, yeniden boyutlandırılabilir bir pencerenin genişlik ve yüksekliğinin ilgili boyut için belirtilen aralık dahilinde herhangi bir yerde olması mümkündür. Geçerli genişlik ve yüksekliğini algılamak için sırasıyla ve <xref:System.Windows.FrameworkElement.ActualWidth%2A> <xref:System.Windows.FrameworkElement.ActualHeight%2A>' yi inceleyin.  
  
 Pencerenin genişlik ve yüksekliğinin pencere içeriğinin boyutuna uygun bir boyuta sahip olmasını istiyorsanız, aşağıdaki değerlere sahip olan <xref:System.Windows.Window.SizeToContent%2A> özelliğini kullanabilirsiniz:  
  
- <xref:System.Windows.SizeToContent.Manual>. Efekt yok (varsayılan).  
  
- <xref:System.Windows.SizeToContent.Width>. Hem hem de <xref:System.Windows.FrameworkElement.MinWidth%2A> <xref:System.Windows.FrameworkElement.MaxWidth%2A> içeriğin genişliğine göre aynı etkiye sahip olan içerik genişliğine uygun hale gelir.  
  
- <xref:System.Windows.SizeToContent.Height>. Hem hem de <xref:System.Windows.FrameworkElement.MinHeight%2A> <xref:System.Windows.FrameworkElement.MaxHeight%2A> içeriğin yüksekliğine göre aynı etkiye sahip olan içerik yüksekliğine Sığdır.  
  
- <xref:System.Windows.SizeToContent.WidthAndHeight>. Hem <xref:System.Windows.FrameworkElement.MinHeight%2A> <xref:System.Windows.FrameworkElement.MinWidth%2A> <xref:System.Windows.FrameworkElement.MaxWidth%2A> hem de içeriğin yüksekliğine ayarlanmasına ve hem hem de içeriğin genişliğine ayarlanmasına benzer etkiye sahip içerik genişliğine ve yüksekliğe uygun hale gelir. <xref:System.Windows.FrameworkElement.MaxHeight%2A>  
  
 Aşağıdaki örnek, ilk başta gösterildiği gibi, hem dikey hem de yatay olarak içeriğini sığdırmak için otomatik olarak ölçeklenebilen bir pencere gösterir.  
  
 [!code-xaml[WindowsOverviewSnippets#SizeToContentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup1)]  
  
 Aşağıdaki örnek, bir pencerenin içeriği sığdırmak için <xref:System.Windows.Window.SizeToContent%2A> nasıl yeniden boyutlandırılacağını belirtmek üzere koddaki özelliğinin nasıl ayarlanacağını gösterir.
  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]  
  
<a name="OrderOfPrecedence"></a>   
## <a name="order-of-precedence-for-sizing-properties"></a>Boyutlandırma özellikleri için öncelik sırası  
 Temelde, bir pencerenin çeşitli boyutlar özellikleri, yeniden boyutlandırılabilir bir pencerenin genişlik ve yükseklik aralığını tanımlamak için birleştirilir. Geçerli bir aralığın korunduğundan emin olmak için, <xref:System.Windows.Window> aşağıdaki öncelik emirlerini kullanarak boyut özelliklerinin değerlerini değerlendirir.  
  
 **Yükseklik özellikleri için:**  
  
1. <xref:System.Windows.FrameworkElement.MinHeight%2A?displayProperty=nameWithType>
  
2. <xref:System.Windows.FrameworkElement.MaxHeight%2A?displayProperty=nameWithType>
  
3. <xref:System.Windows.SizeToContent.Height?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
  
4. <xref:System.Windows.FrameworkElement.Height%2A?displayProperty=nameWithType>  
  
 **Genişlik özellikleri için:**  
  
1. <xref:System.Windows.FrameworkElement.MinWidth%2A?displayProperty=nameWithType>
  
2. <xref:System.Windows.FrameworkElement.MaxWidth%2A?displayProperty=nameWithType>
  
3. <xref:System.Windows.SizeToContent.Width?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
  
4. <xref:System.Windows.FrameworkElement.Width%2A?displayProperty=nameWithType>  
  
 Öncelik sırası, <xref:System.Windows.Window.WindowState%2A> özelliği ile yönetilen, ekranı kaplayan bir pencerenin boyutunu da belirleyebilir.  
  
<a name="WindowState"></a>   
## <a name="window-state"></a>Pencere durumu  
 Yeniden boyutlandırılabilir bir pencerenin ömrü boyunca üç durum olabilir: normal, simge durumuna küçültülmüş ve ekranı kaplamış. *Normal* duruma sahip bir pencere, pencerenin varsayılan durumudur. Bu duruma sahip bir pencere, yeniden boyutlandırılması durumunda bir yeniden boyutlandırma tutamacı veya kenarlık kullanarak, kullanıcının onu taşımasını ve yeniden boyutlandırmasını sağlar.  
  
 *Simge durumuna küçültülmüş* bir pencere, olarak <xref:System.Windows.Window.ShowInTaskbar%2A> `true`ayarlandıysa görev çubuğu düğmesine daraltılır; Aksi takdirde, mümkün olan en küçük boyuta daraltır ve masaüstünün sol alt köşesine yeniden konumlandırmalar. Simge durumuna küçültülmüş pencere türü, bir kenarlık veya yeniden boyutlandırma tutamacı kullanılarak yeniden boyutlandırılabilir, ancak görev çubuğunda görünmeyen simge durumuna küçültülmüş bir pencere masaüstü etrafında sürüklenebilir.  
  
 *Ekranı kaplayan* bir pencere <xref:System.Windows.FrameworkElement.MaxWidth%2A>, en büyük boyuta genişletilir, bu da yalnızca,, <xref:System.Windows.FrameworkElement.MaxHeight%2A>ve <xref:System.Windows.Window.SizeToContent%2A> özellikleri dikte eder. Simge durumuna küçültülmüş bir pencere gibi, ekranı kaplayan bir pencere yeniden boyutlandırma tutamacı kullanılarak veya kenarlıkları sürükleyerek yeniden boyutlandırılamaz.  
  
> [!NOTE]
> Pencerenin <xref:System.Windows.Window.Top%2A> ,<xref:System.Windows.Window.Left%2A>,, ve<xref:System.Windows.FrameworkElement.Height%2A> özelliklerinin değerleri, pencere şu anda büyütülmüş veya küçültülmüş olsa bile normal durum için her zaman değerleri temsil eder. <xref:System.Windows.FrameworkElement.Width%2A>  
  
 Bir pencerenin durumu, <xref:System.Windows.Window.WindowState%2A> özelliği ayarlanarak yapılandırılabilir ve bu, aşağıdaki <xref:System.Windows.WindowState> sabit listesi değerlerinden birine sahip olabilir:  
  
- <xref:System.Windows.WindowState.Normal>varsayılanını  
  
- <xref:System.Windows.WindowState.Maximized>  
  
- <xref:System.Windows.WindowState.Minimized>  
  
 Aşağıdaki örnek, açıldığında ekranı kaplamış olarak gösterilen bir pencerenin nasıl oluşturulacağını gösterir.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStateWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup1)]  
  
 Genel olarak, bir pencerenin başlangıç <xref:System.Windows.Window.WindowState%2A> durumunu yapılandırmak için ayarlamanız gerekir. Yeniden boyutlandırılabilir bir pencere gösterildiğinde, kullanıcılar pencere durumunu değiştirmek için pencerenin başlık çubuğundaki simge durumuna küçült, Ekranı Kapla ve geri yükle düğmelerine basabilir.  
  
<a name="WindowAppearance"></a>   
## <a name="window-appearance"></a>Pencere görünümü  
 Pencerenin istemci alanının görünümünü, düğme, Etiketler ve metin kutuları gibi pencereye özgü içerik ekleyerek değiştirirsiniz. İstemci dışı alanı yapılandırmak için, <xref:System.Windows.Window> bir pencerenin simgesini ayarlamak ve <xref:System.Windows.Window.Title%2A> başlığını ayarlamak için <xref:System.Windows.Window.Icon%2A> dahil olmak üzere çeşitli özellikler sağlar.  
  
 Ayrıca, bir pencerenin yeniden boyutlandırma modu, pencere stili ve masaüstü görev çubuğunda düğme olarak görünüp görüntülenmediğini yapılandırarak, istemci olmayan alan kenarlığının görünümünü ve davranışını değiştirebilirsiniz.  

<a name="Resize_Mode"></a>   
### <a name="resize-mode"></a>Yeniden boyutlandırma modu  
 <xref:System.Windows.Window.WindowStyle%2A> Özelliğine bağlı olarak, kullanıcıların pencereyi yeniden boyutlandırıp nasıl (ve ne olduğunu) kontrol edebilirsiniz. Pencere stili seçimi, bir kullanıcının kenarlığını fareyle sürükleyerek, **simge durumuna küçültme**, **Ekranı Kapla**ve **yeniden boyutlandır** düğmelerinin istemci olmayan alanda görünüp görünmeyeceğini ve görünüp görünmeyeceğini belirler. etkinletir.  
  
 <xref:System.Windows.Window.ResizeMode%2A> Aşağıdaki<xref:System.Windows.ResizeMode> sabit listesi değerlerinden biri olabilecek özelliğini ayarlayarak pencerenin nasıl yeniden boyutlandırılacağını yapılandırabilirsiniz:  
  
- <xref:System.Windows.ResizeMode.NoResize>  
  
- <xref:System.Windows.ResizeMode.CanMinimize>  
  
- <xref:System.Windows.ResizeMode.CanResize>varsayılanını  
  
- <xref:System.Windows.ResizeMode.CanResizeWithGrip>  
  
 ' De olduğu gibi, bir pencerenin yeniden boyutlandırma modunun ömrü boyunca değişmeme olasılığı düşüktür, bu da büyük olasılıkla [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] bu değeri biçimlendirmeden ayarlamanız anlamına gelir. <xref:System.Windows.Window.WindowStyle%2A>  
  
 [!code-xaml[WindowsOverviewSnippets#ResizeModeWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup1)]  
  
 <xref:System.Windows.Window.WindowState%2A> Özelliği inceleyerek pencerenin ekranı kaplayacağını, simge durumuna küçültülmüş veya geri yüklendiğini tespit edebilirsiniz.  
  
<a name="Window_Style"></a>   
### <a name="window-style"></a>Pencere stili  
 Pencerenin istemci olmayan alanından gösterilen kenarlık çoğu uygulama için uygundur. Bununla birlikte, farklı tür kenarlıkların gerekli olduğu veya pencere türüne bağlı olarak hiçbir kenarlığı gerekmeyen durumlar vardır.  
  
 Pencerenin ne tür kenarlığı kontrol etmek için, <xref:System.Windows.Window.WindowStyle%2A> özelliğini, <xref:System.Windows.WindowStyle> numaralandırmanın aşağıdaki değerlerinden biriyle ayarlarsınız:  
  
- <xref:System.Windows.WindowStyle.None>  
  
- <xref:System.Windows.WindowStyle.SingleBorderWindow>varsayılanını  
  
- <xref:System.Windows.WindowStyle.ThreeDBorderWindow>  
  
- <xref:System.Windows.WindowStyle.ToolWindow>  
  
 Bu pencere stillerinin etkisi aşağıdaki şekilde gösterilmiştir:  
  
 ![Pencere kenarlık stillerinin çizimi.](./media/wpf-windows-overview/window-border-styles.png)  
  
 Bir pencerenin ömrü <xref:System.Windows.Window.WindowStyle%2A> boyunca değiştirilmesi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] muhtemel olmadığından biçimlendirme veya kod kullanarak ayarlayabilirsiniz; bu, büyük olasılıkla biçimlendirme kullanarak [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] yapılandıracaksınız.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStyleWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup1)]  
  
#### <a name="non-rectangular-window-style"></a>Dikdörtgen olmayan pencere stili  
 Ayrıca, <xref:System.Windows.Window.WindowStyle%2A> izin veren kenarlık stillerinin yeterli olmadığı durumlar da vardır. Örneğin, kullanımları gibi [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] dikdörtgen olmayan kenarlıkla bir uygulama oluşturmak isteyebilirsiniz.  
  
 Örneğin, aşağıdaki şekilde gösterilen konuşma balonu penceresini göz önünde bulundurun:  
  
 ![Beni sürükle olarak belirten bir konuşma balonu penceresi.](./media/wpf-windows-overview/non-rectangular-window-figure.png)  
  
 Bu tür bir pencere <xref:System.Windows.Window.WindowStyle%2A> <xref:System.Windows.WindowStyle.None>, özelliği olarak ayarlanarak ve saydamlık için olan özel destek <xref:System.Windows.Window> kullanılarak oluşturulabilir.  
  
 [!code-xaml[WindowsOverviewSnippets#TransparentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup1)]  
  
 Bu değer birleşimi, pencereye tamamen saydam bir şekilde işlemesini söyler. Bu durumda, pencerenin istemci olmayan alanı donnlar (kapatma menüsü, simge durumuna küçült, Ekranı Kapla ve geri yükleme düğmeleri vb.) kullanılamaz. Sonuç olarak, kendinizinkini sağlamanız gerekir.  
  
<a name="Task_Bar_Presence"></a>   
### <a name="task-bar-presence"></a>Görev çubuğu varlığı  

Pencerenin varsayılan görünümü, aşağıdaki şekilde gösterildiği gibi bir görev çubuğu düğmesi içerir:

 ![Görev çubuğu düğmesi olan bir pencere gösteren ekran görüntüsü.](./media/wpf-windows-overview/window-taskbar-button.png)  
  
 Bazı Windows türlerinde ileti kutuları ve iletişim kutuları gibi bir görev çubuğu düğmesi yoktur (bkz. [Iletişim kutularına genel bakış](dialog-boxes-overview.md)). Bir pencere için görev çubuğu düğmesinin, <xref:System.Windows.Window.ShowInTaskbar%2A> özelliği ayarlayarak (`true` varsayılan olarak) gösterilip gösterilmeyeceğini kontrol edebilirsiniz.  
  
 [!code-xaml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup1)]  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations"></a>Güvenlik Değerlendirmeleri  
 <xref:System.Windows.Window>örneği `UnmanagedCode` oluşturulacak güvenlik izninin olması gerekir. Üzerinde yüklü olan ve yerel makineden başlatılan uygulamalar için, bu, uygulamaya verilen izinler kümesi içinde yer alır.  
  
 Bununla birlikte, bu, ClickOnce kullanılarak Internet 'ten veya yerel intranet bölgesinden başlatılan uygulamalara verilen izin kümesinin dışındadır. Sonuç olarak, kullanıcılar bir ClickOnce güvenlik uyarısı alır ve uygulamanın izin kümesini tam güvenle yükseltmek gerekecektir.  
  
 Ayrıca, [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] varsayılan olarak Windows veya iletişim kutuları gösterilemez. Tek başına uygulama güvenliği konuları hakkında bir tartışma için bkz. [WPF Güvenlik Stratejisi-Platform güvenliği](../wpf-security-strategy-platform-security.md).  
  
<a name="Other_Types_of_Windows"></a>   
## <a name="other-types-of-windows"></a>Diğer Windows türleri  
 <xref:System.Windows.Navigation.NavigationWindow>, gezinebilir içeriği barındırmak için tasarlanan bir penceredir. Daha fazla bilgi için bkz. [gezintiye genel bakış](navigation-overview.md)).  
  
 İletişim kutuları, genellikle bir işlevi bir kullanıcıdan tamamlamaya yönelik bilgi toplamak için kullanılan bir Windows. Örneğin, bir Kullanıcı bir dosyayı açmak istediğinde dosya **Aç** iletişim kutusu genellikle bir uygulama tarafından dosya adını kullanıcıdan almak için görüntülenir. Daha fazla bilgi için bkz. [Iletişim kutularına genel bakış](dialog-boxes-overview.md).  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Windows.Window>
- <xref:System.Windows.MessageBox>
- <xref:System.Windows.Navigation.NavigationWindow>
- <xref:System.Windows.Application>
- [İletişim Kutularına Genel Bakış](dialog-boxes-overview.md)
- [WPF Uygulaması Derleme](building-a-wpf-application-wpf.md)
