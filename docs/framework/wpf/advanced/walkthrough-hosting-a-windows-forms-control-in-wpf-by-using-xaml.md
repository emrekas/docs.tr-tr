---
title: 'İzlenecek yol: XAML Kullanarak WPF İçerisinde bir Windows Forms Denetimi Barındırma'
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: 61a234a679d9937cb38a753a3d73f2ecc9ec891a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190375"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a>İzlenecek yol: XAML Kullanarak WPF İçerisinde bir Windows Forms Denetimi Barındırma
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pek çok denetimi ile zengin özellik kümesi sağlar. Ancak, bazen kullanmak isteyebilirsiniz [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] denetimlerini, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sayfaları. Örneğin, var olan önemli bir yatırım olabilir [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] denetimleri veya olabilir bir [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] benzersiz işlevsellik sağlayan denetimi.  
  
 Bu yönerge, bir Windows Forms barındırmak nasıl gösterir <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> denetimi bir [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] kullanarak sayfa [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Bu izlenecek yolda gösterilen görevler tam kod listesi için bkz. [WPF kullanarak XAML örnek olarak bir Windows Forms denetimi barındırma](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).
  
## <a name="prerequisites"></a>Önkoşullar  

Bu izlenecek yolu tamamlamak için Visual Studio ihtiyacınız vardır.  
  
## <a name="hosting-the-windows-forms-control"></a>Windows Forms denetimi barındırma  
  
#### <a name="to-host-the-maskedtextbox-control"></a>MaskedTextBox denetimi barındırma  
  
1.  Adlı bir WPF uygulaması projesi oluşturmak `HostingWfInWpfWithXaml`.  
  
2.  Aşağıdaki derlemelere başvurular ekleyin.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  İçinde MainWindow.xaml açın [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
4.  İçinde <xref:System.Windows.Window> öğesi, aşağıdaki ad alanı eşlemesi ekleyin. `wf` Ad alanı eşlemesi, Windows Forms denetimi içeren bütünleştirilmiş kod başvuru oluşturur.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  İçinde <xref:System.Windows.Controls.Grid> aşağıdaki XAML öğesini ekleyin.  
  
     <xref:System.Windows.Forms.MaskedTextBox> Denetimi, bir alt öğesi olarak oluşturulur <xref:System.Windows.Forms.Integration.WindowsFormsHost> denetimi.  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6.  Derleme ve uygulamayı çalıştırmak için F5 tuşuna basın.  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Visual Studio’da XAML tasarlama](/visualstudio/designers/designing-xaml-in-visual-studio)
- [İzlenecek yol: WPF içinde Windows Forms Denetimi Barındırma](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [İzlenecek yol: WPF'de Windows Forms Bileşik Denetimini Barındırma](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [İzlenecek yol: WPF Bileşik Denetimini Windows Forms İçinde Barındırma](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Windows Forms Denetimleri ve Eşdeğer WPF Denetimleri](windows-forms-controls-and-equivalent-wpf-controls.md)
- [Örnek XAML kullanarak WPF içerisinde bir Windows Forms denetimi barındırma](https://go.microsoft.com/fwlink/?LinkID=160000)
