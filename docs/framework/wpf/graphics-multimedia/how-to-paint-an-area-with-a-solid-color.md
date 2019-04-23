---
title: 'Nasıl yapılır: Düz Renk ile bir Alanı Boyama'
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: c85ba72c858d155f29875bb944824db1c44ffaab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086851"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a><span data-ttu-id="824ad-102">Nasıl yapılır: Düz Renk ile bir Alanı Boyama</span><span class="sxs-lookup"><span data-stu-id="824ad-102">How to: Paint an Area with a Solid Color</span></span>
<span data-ttu-id="824ad-103">Düz renk ile bir alanı boyama için önceden tanımlanmış sistem fırça gibi kullanabilirsiniz <xref:System.Windows.Media.Brushes.Red%2A> veya <xref:System.Windows.Media.Brushes.Blue%2A>, ya da yeni bir oluşturabilirsiniz <xref:System.Windows.Media.SolidColorBrush> ve açıklayan kendi <xref:System.Windows.Media.SolidColorBrush.Color%2A> alfa, kırmızı, yeşil ve mavi değerleri kullanarak.</span><span class="sxs-lookup"><span data-stu-id="824ad-103">To paint an area with a solid color, you can use a predefined system brush, such as <xref:System.Windows.Media.Brushes.Red%2A> or <xref:System.Windows.Media.Brushes.Blue%2A>, or you can create a new <xref:System.Windows.Media.SolidColorBrush> and describe its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using alpha, red, green, and blue values.</span></span> <span data-ttu-id="824ad-104">XAML içinde onaltılık gösterim kullanarak da düz renk ile bir alanı boyama.</span><span class="sxs-lookup"><span data-stu-id="824ad-104">In XAML, you may also paint an area with a solid color by using hexidecimal notation.</span></span>  
  
 <span data-ttu-id="824ad-105">Aşağıdaki örnekler boyamak için her tekniğin kullanan bir <xref:System.Windows.Shapes.Rectangle> mavi.</span><span class="sxs-lookup"><span data-stu-id="824ad-105">The following examples uses each of these techniques to paint a <xref:System.Windows.Shapes.Rectangle> blue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="824ad-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="824ad-106">Example</span></span>  
 <span data-ttu-id="824ad-107">**Önceden tanımlanmış bir fırça kullanma**</span><span class="sxs-lookup"><span data-stu-id="824ad-107">**Using a Predefined Brush**</span></span>  
  
 <span data-ttu-id="824ad-108">Aşağıdaki örnekte önceden tanımlanmış bir fırçanın kullanan <xref:System.Windows.Media.Brushes.Blue%2A> mavi bir dikdörtgen boyamak için.</span><span class="sxs-lookup"><span data-stu-id="824ad-108">In the following example uses the predefined brush <xref:System.Windows.Media.Brushes.Blue%2A> to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 <span data-ttu-id="824ad-109">**Onaltılık gösterim kullanılarak**</span><span class="sxs-lookup"><span data-stu-id="824ad-109">**Using Hexadecimal Notation**</span></span>  
  
 <span data-ttu-id="824ad-110">Sonraki örnek, mavi bir dikdörtgen boyamak için 8 basamaklı onaltılık gösterim kullanır.</span><span class="sxs-lookup"><span data-stu-id="824ad-110">The next example uses 8-digit hexadecimal notation to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 <span data-ttu-id="824ad-111">**ARGB değerlerini kullanma**</span><span class="sxs-lookup"><span data-stu-id="824ad-111">**Using ARGB Values**</span></span>  
  
 <span data-ttu-id="824ad-112">Sonraki örnek, oluşturur bir <xref:System.Windows.Media.SolidColorBrush> ve açıklar, <xref:System.Windows.Media.SolidColorBrush.Color%2A> ARGB kullanarak mavi renk için değerler.</span><span class="sxs-lookup"><span data-stu-id="824ad-112">The next example creates a <xref:System.Windows.Media.SolidColorBrush> and describes its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using the ARGB values for the color blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 <span data-ttu-id="824ad-113">Renk açıklayan diğer yolları için bkz. <xref:System.Windows.Media.Color> yapısı.</span><span class="sxs-lookup"><span data-stu-id="824ad-113">For other ways of describing color, see the <xref:System.Windows.Media.Color> structure.</span></span>  
  
 <span data-ttu-id="824ad-114">**İlgili Konular**</span><span class="sxs-lookup"><span data-stu-id="824ad-114">**Related Topics**</span></span>  
  
 <span data-ttu-id="824ad-115">Hakkında daha fazla bilgi için <xref:System.Windows.Media.SolidColorBrush> ve diğer örnekler [düz renkler ve gradyanlar genel bakış boyama](painting-with-solid-colors-and-gradients-overview.md) genel bakış.</span><span class="sxs-lookup"><span data-stu-id="824ad-115">For more information about <xref:System.Windows.Media.SolidColorBrush> and additional examples, see the [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md) overview.</span></span>  
  
 <span data-ttu-id="824ad-116">Bu kod örneği için sağlanan daha büyük bir örneğin parçasıdır <xref:System.Windows.Media.SolidColorBrush> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="824ad-116">This code example is part of a larger example provided for the <xref:System.Windows.Media.SolidColorBrush> class.</span></span> <span data-ttu-id="824ad-117">Tam bir örnek için bkz. [Fırçalar örnek](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="824ad-117">For the complete sample, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="824ad-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="824ad-118">See also</span></span>

- <xref:System.Windows.Media.Brushes>
