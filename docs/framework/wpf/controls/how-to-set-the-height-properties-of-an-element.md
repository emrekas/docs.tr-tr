---
title: 'Nasıl yapılır: Öğenin Yükseklik Özelliklerini Ayarlama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
ms.openlocfilehash: fb655630336c3b69afdc726a2e3c5a2cb8838667
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59221593"
---
# <a name="how-to-set-the-height-properties-of-an-element"></a><span data-ttu-id="79cd8-102">Nasıl yapılır: Öğenin Yükseklik Özelliklerini Ayarlama</span><span class="sxs-lookup"><span data-stu-id="79cd8-102">How to: Set the Height Properties of an Element</span></span>
## <a name="example"></a><span data-ttu-id="79cd8-103">Örnek</span><span class="sxs-lookup"><span data-stu-id="79cd8-103">Example</span></span>  
 <span data-ttu-id="79cd8-104">Bu örnek, görsel olarak işleme davranışı dört yükseklik ilgili özellikleri arasında farklılıklar gösterir [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79cd8-104">This example visually shows the differences in rendering behavior among the four height-related properties in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="79cd8-105"><xref:System.Windows.FrameworkElement> Sınıfı, bir öğenin yükseklik özelliklerini tanımlayan dört özelliği sunar.</span><span class="sxs-lookup"><span data-stu-id="79cd8-105">The <xref:System.Windows.FrameworkElement> class exposes four properties that describe the height characteristics of an element.</span></span> <span data-ttu-id="79cd8-106">Bu dört özellik çakışabilir ve bunu yaptıklarında önceliklidir değeri aşağıdaki şekilde belirlenir: <xref:System.Windows.FrameworkElement.MinHeight%2A> değeri önceliklidir <xref:System.Windows.FrameworkElement.MaxHeight%2A> sırayla önceliklidir değeri <xref:System.Windows.FrameworkElement.Height%2A> değeri.</span><span class="sxs-lookup"><span data-stu-id="79cd8-106">These four properties can conflict, and when they do, the value that takes precedence is determined as follows: the <xref:System.Windows.FrameworkElement.MinHeight%2A> value takes precedence over the <xref:System.Windows.FrameworkElement.MaxHeight%2A> value, which in turn takes precedence over the <xref:System.Windows.FrameworkElement.Height%2A> value.</span></span> <span data-ttu-id="79cd8-107">Dördüncü bir özellik <xref:System.Windows.FrameworkElement.ActualHeight%2A>, salt okunur ve düzen işlemine etkileşim tarafından belirlendiği gerçek yüksekliği bildirir.</span><span class="sxs-lookup"><span data-stu-id="79cd8-107">A fourth property, <xref:System.Windows.FrameworkElement.ActualHeight%2A>, is read-only, and reports the actual height as determined by interactions with the layout process.</span></span>  
  
 <span data-ttu-id="79cd8-108">Aşağıdaki [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] örnekler çizmek bir <xref:System.Windows.Shapes.Rectangle> öğesi (`rect1`) bir alt öğesi olarak <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="79cd8-108">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples draw a <xref:System.Windows.Shapes.Rectangle> element (`rect1`) as a child of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="79cd8-109">Yükseklik özelliklerini değiştirmek bir <xref:System.Windows.Shapes.Rectangle> bir dizi kullanarak <xref:System.Windows.Controls.ListBox> özellik değerlerini temsil eden öğeler <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, ve <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="79cd8-109">You can change the height properties of a <xref:System.Windows.Shapes.Rectangle> by using a series of <xref:System.Windows.Controls.ListBox> elements that represent the property values of <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="79cd8-110">Bu şekilde, her bir özellik önceliğini görsel olarak görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="79cd8-110">In this manner, the precedence of each property is visually displayed.</span></span>  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="79cd8-111">Aşağıdaki arka plan kod örnekleri olaylarını işlemek, <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> olayını başlatır.</span><span class="sxs-lookup"><span data-stu-id="79cd8-111">The following code-behind examples handle the events that the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event raises.</span></span> <span data-ttu-id="79cd8-112">Her işleyici girişini alır <xref:System.Windows.Controls.ListBox>, değer olarak ayrıştırır bir <xref:System.Double>ve belirtilen yükseklik ilgili özellik için değer geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="79cd8-112">Each handler takes the input from the <xref:System.Windows.Controls.ListBox>, parses the value as a <xref:System.Double>, and applies the value to the specified height-related property.</span></span> <span data-ttu-id="79cd8-113">Yükseklik değerleri de bir dizeye dönüştürülür ve çeşitli yazılan <xref:System.Windows.Controls.TextBlock> öğeleri (söz konusu öğelerin tanımı içinde seçili XAML gösterilmez).</span><span class="sxs-lookup"><span data-stu-id="79cd8-113">The height values are also converted to a string and written to various <xref:System.Windows.Controls.TextBlock> elements (definition of those elements is not shown in the selected XAML).</span></span>  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 <span data-ttu-id="79cd8-114">Tam bir örnek için bkz. [yükseklik özellikleri örneği](https://go.microsoft.com/fwlink/?LinkID=159993).</span><span class="sxs-lookup"><span data-stu-id="79cd8-114">For the complete sample, see [Height Properties Sample](https://go.microsoft.com/fwlink/?LinkID=159993).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79cd8-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="79cd8-115">See also</span></span>

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.ActualHeight%2A>
- <xref:System.Windows.FrameworkElement.MaxHeight%2A>
- <xref:System.Windows.FrameworkElement.MinHeight%2A>
- <xref:System.Windows.FrameworkElement.Height%2A>
- [<span data-ttu-id="79cd8-116">Öğenin Genişlik Özelliklerini Ayarlama</span><span class="sxs-lookup"><span data-stu-id="79cd8-116">Set the Width Properties of an Element</span></span>](how-to-set-the-width-properties-of-an-element.md)
- [<span data-ttu-id="79cd8-117">Panellere Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="79cd8-117">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="79cd8-118">Yükseklik özellikleri örneği</span><span class="sxs-lookup"><span data-stu-id="79cd8-118">Height Properties Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159993)
