---
title: 'Nasıl yapılır: Öğenin Genişlik Özelliklerini Ayarlama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- width properties [WPF]
- Panel control [WPF], width properties of elements
ms.assetid: 6ee04a9d-63f0-4f5b-a406-0a8cd4c35729
ms.openlocfilehash: 739b041d8ca89abb9bd1934abb997d1154f08c95
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54673991"
---
# <a name="how-to-set-the-width-properties-of-an-element"></a>Nasıl yapılır: Öğenin Genişlik Özelliklerini Ayarlama
## <a name="example"></a>Örnek  
 Bu örnek, görsel olarak işleme davranışı dört genişliği ile ilgili özellikleri arasında farklılıklar gösterir [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 <xref:System.Windows.FrameworkElement> Sınıfı, bir öğenin genişlik özelliklerini tanımlayan dört özelliği sunar. Bu dört özellik çakışabilir ve bunu yaptıklarında önceliklidir değeri aşağıdaki şekilde belirlenir: <xref:System.Windows.FrameworkElement.MinWidth%2A> değeri önceliklidir <xref:System.Windows.FrameworkElement.MaxWidth%2A> sırayla önceliklidir değeri <xref:System.Windows.FrameworkElement.Width%2A> değeri. Dördüncü bir özellik <xref:System.Windows.FrameworkElement.ActualWidth%2A>, salt okunur ve düzen işlemine etkileşim tarafından belirlendiği gerçek genişliğini bildirir.  
  
 Aşağıdaki [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] örnekler çizmek bir <xref:System.Windows.Shapes.Rectangle> öğesi (`rect1`) bir alt öğesi olarak <xref:System.Windows.Controls.Canvas>. Genişlik özelliklerini değiştirmek bir <xref:System.Windows.Shapes.Rectangle> bir dizi kullanarak <xref:System.Windows.Controls.ListBox> özellik değerlerini temsil eden öğeler <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, ve <xref:System.Windows.FrameworkElement.Width%2A>. Bu şekilde, her bir özellik önceliğini görsel olarak görüntülenir.  
  
 [!code-xaml[WidthMinWidthMaxWidth#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#1)]  
[!code-xaml[WidthMinWidthMaxWidth#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#2)]  
  
 Aşağıdaki arka plan kod örnekleri olaylarını işlemek, <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> olayını başlatır. Özel yöntemler girişten alır <xref:System.Windows.Controls.ListBox>, değer olarak ayrıştırır bir <xref:System.Double>ve belirtilen genişlik ilgili özellik için değer geçerlidir. Genişlik değerleri de bir dizeye dönüştürülür ve çeşitli yazılan <xref:System.Windows.Controls.TextBlock> öğeleri (söz konusu öğelerin tanımı içinde seçili XAML gösterilmez).  
  
 [!code-csharp[WidthMinWidthMaxWidth#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml.cs#3)]
 [!code-vb[WidthMinWidthMaxWidth#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WidthMinWidthMaxWidth/VisualBasic/Window1.xaml.vb#3)]  
  
 Tam bir örnek için bkz. [genişlik özelliklerini karşılaştırma örneği](https://go.microsoft.com/fwlink/?LinkID=160050).  
  
## <a name="see-also"></a>Ayrıca bkz.
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.ActualWidth%2A>
- <xref:System.Windows.FrameworkElement.MaxWidth%2A>
- <xref:System.Windows.FrameworkElement.MinWidth%2A>
- <xref:System.Windows.FrameworkElement.Width%2A>
- [Panellere Genel Bakış](../../../../docs/framework/wpf/controls/panels-overview.md)
- [Öğenin Yükseklik Özelliklerini Ayarlama](../../../../docs/framework/wpf/controls/how-to-set-the-height-properties-of-an-element.md)
- [Genişlik özelliklerini karşılaştırma örneği](https://go.microsoft.com/fwlink/?LinkID=160050)
