---
title: 'Nasıl yapılır: Doğrusal Gradyan ile bir Alanı Boyama'
ms.date: 03/30/2017
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
ms.openlocfilehash: c48ff13811d784ecc7042b73b964a9e6f2d42a34
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367251"
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a><span data-ttu-id="96095-102">Nasıl yapılır: Doğrusal Gradyan ile bir Alanı Boyama</span><span class="sxs-lookup"><span data-stu-id="96095-102">How to: Paint an Area with a Linear Gradient</span></span>
<span data-ttu-id="96095-103">Bu örnek nasıl kullanılacağını gösterir <xref:System.Windows.Media.LinearGradientBrush> doğrusal gradyan ile bir alanı boyama için sınıf.</span><span class="sxs-lookup"><span data-stu-id="96095-103">This example shows how to use the <xref:System.Windows.Media.LinearGradientBrush> class to paint an area with a linear gradient.</span></span> <span data-ttu-id="96095-104">Aşağıdaki örnekte, <xref:System.Windows.Shapes.Shape.Fill%2A> , bir <xref:System.Windows.Shapes.Rectangle> sarı kırmızı, mavi yeşile geçişleri çapraz bir doğrusal gradyan ile boyanır.</span><span class="sxs-lookup"><span data-stu-id="96095-104">In the following example, the <xref:System.Windows.Shapes.Shape.Fill%2A> of a <xref:System.Windows.Shapes.Rectangle> is painted with a diagonal linear gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96095-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="96095-105">Example</span></span>  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 <span data-ttu-id="96095-106">Aşağıdaki resimde önceki örnekte oluşturulan gradyanı gösterir.</span><span class="sxs-lookup"><span data-stu-id="96095-106">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="96095-107">![Çapraz doğrusal gradyan](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span><span class="sxs-lookup"><span data-stu-id="96095-107">![Diagonal linear gradient](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span></span>  
  
 <span data-ttu-id="96095-108">Yatay doğrusal gradyan oluşturmak isterseniz değiştirme <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> ve <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> , <xref:System.Windows.Media.LinearGradientBrush> ' ini (0,0.5) ve (1,0.5)'e.</span><span class="sxs-lookup"><span data-stu-id="96095-108">To create a horizontal linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0,0.5) and (1,0.5).</span></span> <span data-ttu-id="96095-109">Aşağıdaki örnekte, bir <xref:System.Windows.Shapes.Rectangle> yatay bir doğrusal gradyan ile boyanır.</span><span class="sxs-lookup"><span data-stu-id="96095-109">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a horizontal linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 <span data-ttu-id="96095-110">Aşağıdaki resimde önceki örnekte oluşturulan gradyanı gösterir.</span><span class="sxs-lookup"><span data-stu-id="96095-110">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="96095-111">![Yatay doğrusal gradyan](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span><span class="sxs-lookup"><span data-stu-id="96095-111">![A horizontal linear gradient](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span></span>  
  
 <span data-ttu-id="96095-112">Dikey doğrusal gradyan oluşturmak isterseniz değiştirme <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> ve <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> , <xref:System.Windows.Media.LinearGradientBrush> ' ini (0.5,0) ve (0.5,1)'e.</span><span class="sxs-lookup"><span data-stu-id="96095-112">To create a vertical linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0.5,0) and (0.5,1).</span></span> <span data-ttu-id="96095-113">Aşağıdaki örnekte, bir <xref:System.Windows.Shapes.Rectangle> dikey bir doğrusal gradyan ile boyanır.</span><span class="sxs-lookup"><span data-stu-id="96095-113">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a vertical linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 <span data-ttu-id="96095-114">Aşağıdaki resimde önceki örnekte oluşturulan gradyanı gösterir.</span><span class="sxs-lookup"><span data-stu-id="96095-114">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="96095-115">![Dikey doğrusal gradyan](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span><span class="sxs-lookup"><span data-stu-id="96095-115">![Vertical linear gradient](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96095-116">Bu konudaki örnekler, başlangıç ve bitiş noktalarını ayarlamak için varsayılan koordinat sistemini kullanır.</span><span class="sxs-lookup"><span data-stu-id="96095-116">The examples in this topic use the default coordinate system for setting start points and end points.</span></span> <span data-ttu-id="96095-117">Varsayılan koordinat sistemi göreli bir sınırlayıcı kutu şöyledir: 0 gösterir sınırlayıcı kutusunun yüzde 0 ve 1, sınırlayıcı kutunun yüzde 100 gösterir.</span><span class="sxs-lookup"><span data-stu-id="96095-117">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="96095-118">Ayarlayarak bu koordinat sistemini değiştirebilirsiniz <xref:System.Windows.Media.GradientBrush.MappingMode%2A> özellik değerine <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="96095-118">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="96095-119">Mutlak koordinat sistemi bir sınırlayıcı kutu göreli değil.</span><span class="sxs-lookup"><span data-stu-id="96095-119">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="96095-120">Değerleri, doğrudan yerel alan yorumlanır.</span><span class="sxs-lookup"><span data-stu-id="96095-120">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="96095-121">Diğer örnekler için [Fırçalar örnek](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="96095-121">For additional examples, see [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="96095-122">Gradyanlar ve diğer türleri Fırçalar hakkında daha fazla bilgi için bkz: [düz renkler ve gradyanlar genel bakış boyama](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="96095-122">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
