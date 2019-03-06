---
title: "Mürekkep Nesnesi Modeli: Windows Forms ve WPF'ye karşı COM"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling ink [WPF]
- InkCanvas control [WPF]
- ink object model [WPF]
- tablet pen [WPF], events [WPF]
- ink [WPF], enabling
- events [WPF], tablet pen
ms.assetid: 577835be-b145-4226-8570-1d309e9b3901
ms.openlocfilehash: 68003943041fe0ba405eff1236c43a8e7e9c2b71
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356838"
---
# <a name="the-ink-object-model-windows-forms-and-com-versus-wpf"></a>Mürekkep Nesnesi Modeli: Windows Forms ve WPF'ye karşı COM

Dijital Mürekkep desteği temelde üç platformda vardır: Tablet PC Windows Forms platform, Tablet PC COM platformu ve Windows Presentation Foundation (WPF) platform.  Benzer bir nesne modeli, ancak nesne modeli için Windows Forms ve COM platformları paylaşımını [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] platform önemli ölçüde farklıdır.  Bir nesne modeliyle hakkında deneyimli olduğunuzu geliştiriciler diğer daha iyi anlayabilmeniz bu konuda, bir üst düzey farklılıklar açıklanmaktadır.  
  
## <a name="enabling-ink-in-an-application"></a>Bir uygulamada mürekkebi etkinleştirme  
 Tüm üç platformlar, nesneleri ve tablet kalem girişi almak uygulamanın denetimleri gönderin.  Windows Forms ve COM platformları ile birlikte [Microsoft.Ink.InkPicture](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90)), [Microsoft.Ink.InkEdit](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552265(v=vs.90)), [Microsoft.Ink.InkOverlay](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)) ve [ Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) sınıfları.  [Microsoft.Ink.InkPicture](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90)) ve [Microsoft.Ink.InkEdit](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552265(v=vs.90)) ekleyebileceğiniz denetimler mürekkep toplamak için bir uygulama.  [Microsoft.Ink.InkOverlay](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)) ve [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) mürekkebi etkinleştirme windows ve özel denetimler varolan pencereye iliştirilebilir.  
  
 WPF platform içerir <xref:System.Windows.Controls.InkCanvas> denetimi.  Ekleyebileceğiniz bir <xref:System.Windows.Controls.InkCanvas> uygulamanıza ve mürekkep hemen toplamaya başlayın. İle <xref:System.Windows.Controls.InkCanvas>, kullanıcı kopyalayın, seçebilir ve mürekkep yeniden boyutlandırın.  Diğer denetimlere ekleyebilirsiniz <xref:System.Windows.Controls.InkCanvas>, ve kullanıcının bu denetimlerin üzerine çok el yazısı.  Mürekkep özellikli bir özel denetim ekleyerek oluşturabilirsiniz bir <xref:System.Windows.Controls.InkPresenter> ve ekran kalemi noktalarından toplama.  
  
 Aşağıdaki tabloda, uygulamada mürekkebi etkinleştirme hakkında daha fazla bilgi nereye listelenmektedir:  
  
|Bunu yapmak için...|WPF platformunda...|Windows Forms/COM platformlarda...|  
|-----------------|--------------------------|------------------------------------------|  
|Mürekkep etkin bir denetim için uygulama ekleme|Bkz: [mürekkep ile çalışmaya başlama](getting-started-with-ink.md).|Bkz: [otomatik talep Form örneği](/windows/desktop/tablet/auto-claims-form-sample)|  
|Özel denetim üzerinde mürekkep etkinleştir|Bkz: [oluşturma mürekkep giriş denetimi](creating-an-ink-input-control.md).|Bkz: [mürekkep Pano örnek](/windows/desktop/tablet/ink-clipboard-sample).|  
  
## <a name="ink-data"></a>Mürekkep verisi  
 Windows Forms ve COM platformları [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)), [Microsoft.Ink.InkOverlay](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)), [Microsoft.Ink.InkEdit](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552265(v=vs.90)), ve [ Microsoft.Ink.InkPicture](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90)) her sunmaya bir [Microsoft.Ink.Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) nesne. [Microsoft.Ink.Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) nesnesi, bir veya daha fazla bilgi için verileri içeren [Microsoft.Ink.Stroke](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552692(v=vs.90)) nesneleri ve ortak yöntemleri ve özellikleri yönetme ve bu strokes işlemek için kullanıma sunar.  [Microsoft.Ink.Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) nesnesi yönetir; içerdiği vuruşları ömrünü [Microsoft.Ink.Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) nesnesi oluşturur ve sahip olduğu vuruşları siler.  Her [Microsoft.Ink.Stroke](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552692(v=vs.90)) kendi üst öğe içinde benzersiz bir tanımlayıcıyı [Microsoft.Ink.Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) nesne.  
  
 WPF platformunda <xref:System.Windows.Ink.Stroke?displayProperty=nameWithType> sınıfı sahip olan ve kendi yaşam süresini yönetir. Bir grup <xref:System.Windows.Ink.Stroke> nesneleri toplanacak birlikte bir <xref:System.Windows.Ink.StrokeCollection>, isabet testi, silme, dönüştürme ve Mürekkep Serileştirme yöntemleri ortak mürekkep için veri yönetimi işlemleri gibi sağlayan. A <xref:System.Windows.Ink.Stroke> sıfır, bir veya daha fazla bilgi için ait olabilir <xref:System.Windows.Ink.StrokeCollection> herhangi bir nesnede zaman verin.  Yerine bir [Microsoft.Ink.Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) nesnesi <xref:System.Windows.Controls.InkCanvas> ve <xref:System.Windows.Controls.InkPresenter> içeren bir <xref:System.Windows.Ink.StrokeCollection?displayProperty=nameWithType>.  
  
 Aşağıdaki çizimler çiftinin mürekkep veri nesne modellerini karşılaştırır.  Windows Forms ve COM platformları [Microsoft.Ink.Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) nesne kullanım süresini kısıtlar [Microsoft.Ink.Stroke](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552692(v=vs.90)) nesneleri ve ekran kalemi paketler için tek tek vuruşları ait.  İki veya daha fazla strokes aynı başvurabilir [Microsoft.Ink.DrawingAttributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583636(v=vs.90)) aşağıdaki çizimde gösterildiği gibi nesne.  
  
 ![COM için Mürekkep Nesnesi Modeli Diyagramı&#47;Winforms. ](./media/ink-inkownsstrokes.png "Ink_InkOwnsStrokes")  
  
 Üzerinde [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], her <xref:System.Windows.Ink.Stroke?displayProperty=nameWithType> olduğunu bir şey buna bir başvuru olarak var olan bir ortak dil çalışma zamanı nesnesi.  Her <xref:System.Windows.Ink.Stroke> başvurular bir <xref:System.Windows.Input.StylusPointCollection> ve <xref:System.Windows.Ink.DrawingAttributes?displayProperty=nameWithType> ortak dil çalışma zamanı nesneleri olan nesne.  
  
 ![WPF için mürekkep nesnesi modeli diyagramı. ](./media/ink-wpfinkobjectmodel.png "Ink_WPFInkObjectModel")  
  
 Aşağıdaki tabloda karşılaştırılmıştır üzerinde bazı yaygın görevlerin nasıl [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] platformu ve Windows Forms ve COM platformlar.  
  
|Görev|Windows Presentation Foundation|Windows Forms ve COM|  
|----------|-------------------------------------|---------------------------|  
|Mürekkep Kaydet|<xref:System.Windows.Ink.StrokeCollection.Save%2A>|[Microsoft.Ink.Ink.Save](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms571335(v=vs.90))|  
|Mürekkep yükleme|Oluşturma bir <xref:System.Windows.Ink.StrokeCollection> ile <xref:System.Windows.Ink.StrokeCollection.%23ctor%2A> Oluşturucusu.|[Microsoft.Ink.Ink.Load](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms569609(v=vs.90))|  
|Tıklama testi|<xref:System.Windows.Ink.StrokeCollection.HitTest%2A>|[Microsoft.Ink.Ink.HitTest](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms571330(v=vs.90))|  
|Mürekkep kopyalayın|<xref:System.Windows.Controls.InkCanvas.CopySelection%2A>|[Microsoft.Ink.Ink.ClipboardCopy](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms571316(v=vs.90))|  
|Mürekkep yapıştırın|<xref:System.Windows.Controls.InkCanvas.Paste%2A>|[Microsoft.Ink.Ink.ClipboardPaste](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms571318(v=vs.90))|  
|Bir dizi vuruşunu erişimi özel özellikleri|<xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A> (özelliklerini dahili olarak depolanır ve üzerinden erişilen <xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A>, <xref:System.Windows.Ink.StrokeCollection.RemovePropertyData%2A>, ve <xref:System.Windows.Ink.StrokeCollection.ContainsPropertyData%2A>)|Kullanım [Microsoft.Ink.Ink.ExtendedProperties](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms582214(v=vs.90))|  
  
### <a name="sharing-ink-between-platforms"></a>Mürekkep platformlar arasında paylaşma  
 Mürekkep verisi için farklı nesne modellerinde platformları sahip olsa da, platformlar arasında veri paylaşımı çok kolaydır. Aşağıdaki örnekler, bir Windows Forms uygulamasından mürekkep kaydedin ve bir Windows Presentation Foundation uygulamasına mürekkep yükleyin.  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#SaveWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewinforms)]
[!code-vb[WinFormWPFInk#SaveWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewinforms)]  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#LoadWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwpf)]
[!code-vb[WinFormWPFInk#LoadWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwpf)]  
  
 Aşağıdaki örnekler, bir Windows Presentation Foundation uygulamasından mürekkep kaydedin ve bir Windows Forms uygulamasına mürekkep yükleyin.  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#SaveWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewpf)]
[!code-vb[WinFormWPFInk#SaveWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewpf)]  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#LoadWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwinforms)]
[!code-vb[WinFormWPFInk#LoadWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwinforms)]
## <a name="events-from-the-tablet-pen"></a>Tablet kalem olayları  

 [Microsoft.Ink.InkOverlay](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)), [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)), ve [Microsoft.Ink.InkPicture](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90)) Windows Forms ve COM platformlarda olayları almak, kullanıcı Giriş veri kalem. [Microsoft.Ink.InkOverlay](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)) veya [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) bir pencere veya bir denetime bağlı ve tablet girdi verilerini tarafından tetiklenen olayları için abone olabilirsiniz. Bu olaylar gerçekleştiği iş parçacığı olaylar Kalem, fare, yoksa oluşturulur bağlıdır veya programlama yoluyla. Bu olaylar ile ilgili iş parçacığı oluşturma hakkında daha fazla bilgi için bkz. [iş parçacığı temel noktalar](/windows/desktop/tablet/general-threading-considerations) ve [iş parçacıkları, bir olay özelliği kullanabilirsiniz](/windows/desktop/tablet/threads-on-which-an-event-can-fire).  
  
 Windows Presentation Foundation platformunda <xref:System.Windows.UIElement> sınıfında kalem girişi için olayları. Başka bir deyişle, her denetim, ekran kalemi olayların tam kümesini kullanıma sunar.  Ekran kalemi olayları tünel/tırmanma etkinliğiniz çiftlerini ve her zaman uygulama iş parçacığı üzerinde oluşur.  Daha fazla bilgi için [yönlendirilmiş olaylara genel bakış](routed-events-overview.md).  
  
 Aşağıdaki diyagramda gösterildiği ekran kalemi olay sınıfları için nesne modellerini karşılaştırır. Windows Presentation Foundation nesne modeli yalnızca tırmanma olayları değil tünel olay ortaklarınıza gösterir.  
  
 ![WPF ve Winforms ekran kalemi olayları diyagramı. ](./media/ink-stylusevents.png "Ink_StylusEvents")  
  
## <a name="pen-data"></a>Kalem veri  
 Tüm üç platformlar, müdahale tablet kaleminden gelen verileri işlemek için yöntemler sağlar.  Windows Forms ve COM platformları bu oluşturularak elde edilir bir [Microsoft.StylusInput.RealTimeStylus](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms585724(v=vs.90)), pencere veya denetim eklemeyi ve uygulayan bir sınıf oluşturma [ Microsoft.StylusInput.IStylusSyncPlugin](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms575201(v=vs.90)) veya [Microsoft.StylusInput.IStylusAsyncPlugin](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms575194(v=vs.90)) arabirimi. Özel eklentiniz için eklenti koleksiyonu sonra eklenir [Microsoft.StylusInput.RealTimeStylus](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms585724(v=vs.90)). Bu nesne modeli hakkında daha fazla bilgi için bkz. [StylusInput API'leri mimarisini](/windows/desktop/tablet/architecture-of-the-stylusinput-apis).  
  
 Üzerinde [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] platform <xref:System.Windows.UIElement> sınıfı gösterir eklentileri için tasarımda benzer koleksiyonunu [Microsoft.StylusInput.RealTimeStylus](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms585724(v=vs.90)).  Kalem verilerinize müdahale için devralınan bir sınıf oluşturmanız <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> ve nesneye ekleme <xref:System.Windows.UIElement.StylusPlugIns%2A> koleksiyonunu <xref:System.Windows.UIElement>. Bu etkileşim hakkında daha fazla bilgi için bkz: [kaleminden gelen girişi ekran kalemi ile](intercepting-input-from-the-stylus.md).  
  
 Tüm platformlarda, iş parçacığı havuzu, ekran kalemi olayları aracılığıyla mürekkep verileri alır ve uygulama iş parçacığına gönderir.  COM ve Windows platformlarını iş parçacığı oluşturma hakkında daha fazla bilgi için bkz. [StylusInput API'leri için iş parçacığı oluşturma konuları](/windows/desktop/tablet/threading-considerations-for-the-stylusinput-apis).  Windows Presentation yazılım iş parçacığı oluşturma hakkında daha fazla bilgi için bkz. [mürekkep iş parçacığı modeli](the-ink-threading-model.md).  
  
 Aşağıdaki çizimde, kalem iş parçacığı havuzundaki kalem veri sınıfları için nesne modellerini karşılaştırır.  
  
 ![StylusPlugIn modeline WPF ve Winforms diyagramı. ](./media/ink-stylusplugins.png "Ink_StylusPlugins")
