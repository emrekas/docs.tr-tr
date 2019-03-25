---
title: 'Nasıl yapılır: Geometriyi Parametre Olarak Kullanan Tıklama Testi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects using Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], hit tests on visual objects [WPF]
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
ms.openlocfilehash: 3d6f4190a5b5c8410a6be01d2645df9c123f9ac4
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410621"
---
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a><span data-ttu-id="5b50d-102">Nasıl yapılır: Geometriyi Parametre Olarak Kullanan Tıklama Testi</span><span class="sxs-lookup"><span data-stu-id="5b50d-102">How to: Hit Test Using Geometry as a Parameter</span></span>
<span data-ttu-id="5b50d-103">Bu örnek gösterir kullanarak visual nesne üzerinde bir isabet testi gerçekleştirmek nasıl bir <xref:System.Windows.Media.Geometry> parametre isabet testi.</span><span class="sxs-lookup"><span data-stu-id="5b50d-103">This example shows how to perform a hit test on a visual object using a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b50d-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="5b50d-104">Example</span></span>  
 <span data-ttu-id="5b50d-105">Aşağıdaki örnek bir isabet sınaması kullanılarak ayarlanan gösterilmiştir <xref:System.Windows.Media.GeometryHitTestParameters> için <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="5b50d-105">The following example shows how to set up a hit test using <xref:System.Windows.Media.GeometryHitTestParameters> for the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method.</span></span> <span data-ttu-id="5b50d-106"><xref:System.Windows.Point> Geçirilen değer `OnMouseDown` yöntemi oluşturmak için kullanılan bir <xref:System.Windows.Media.Geometry> isabet sınaması aralığını genişletmek için nesne.</span><span class="sxs-lookup"><span data-stu-id="5b50d-106">The <xref:System.Windows.Point> value that is passed to the `OnMouseDown` method is used to create a <xref:System.Windows.Media.Geometry> object in order to expand the range of the hit test.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 <span data-ttu-id="5b50d-107"><xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> Özelliği <xref:System.Windows.Media.GeometryHitTestResult> kullanan isabet sınaması sonuçlarıyla ilgili bilgi sağlar bir <xref:System.Windows.Media.Geometry> parametre isabet testi.</span><span class="sxs-lookup"><span data-stu-id="5b50d-107">The <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property of <xref:System.Windows.Media.GeometryHitTestResult> provides information about the results of a hit test that uses a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span> <span data-ttu-id="5b50d-108">İsabet testi geometrisi (mavi daire) ve işlenmiş içeriği hedef visual nesnenin (kırmızı kare) arasındaki ilişki aşağıda gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="5b50d-108">The following illustration shows the relationship between the hit test geometry (the blue circle) and the rendered content of the target visual object (the red square).</span></span>  
  
 ![İsabet sınaması kullanılan IntersectionDetail gösteren diyagram.](./media/how-to-hit-test-using-geometry-as-a-parameter/intersectiondetail-hit-test.png)  
  
 <span data-ttu-id="5b50d-110">Aşağıdaki örnek, bir isabet sınaması geri çağırmanızı uygulamak gösterilmektedir, bir <xref:System.Windows.Media.Geometry> isabet sınaması parametre olarak kullanılır.</span><span class="sxs-lookup"><span data-stu-id="5b50d-110">The following example shows how to implement a hit test callback when a <xref:System.Windows.Media.Geometry> is used as a hit test parameter.</span></span> <span data-ttu-id="5b50d-111">`result` Parametre türünden bir <xref:System.Windows.Media.GeometryHitTestResult> değerini almak için <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="5b50d-111">The `result` parameter is cast to a <xref:System.Windows.Media.GeometryHitTestResult> in order to retrieve the value of the <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property.</span></span> <span data-ttu-id="5b50d-112">Özellik değeri, belirlemenize olanak tanır <xref:System.Windows.Media.Geometry> isabet sınaması parametresi tamamen veya kısmen yer alan isabet sınaması hedef işlenmiş içeriği içinde.</span><span class="sxs-lookup"><span data-stu-id="5b50d-112">The property value allows you to determine if the <xref:System.Windows.Media.Geometry> hit test parameter is fully or partially contained within the rendered content of the hit test target.</span></span> <span data-ttu-id="5b50d-113">Bu durumda, örnek kod için tam olarak hedef sınırları içinde bulunan görselleri listesine yalnızca isabet testi sonuçlarını eklemektir.</span><span class="sxs-lookup"><span data-stu-id="5b50d-113">In this case, the sample code is only adding hit test results to the list for visuals that are fully contained within the target boundary.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
>  <span data-ttu-id="5b50d-114"><xref:System.Windows.Media.HitTestResult> Kesişimi ayrıntı olduğunda geri çağırma çağırılmalıdır <xref:System.Windows.Media.IntersectionDetail.Empty>.</span><span class="sxs-lookup"><span data-stu-id="5b50d-114">The <xref:System.Windows.Media.HitTestResult> callback should not be called when the intersection detail is <xref:System.Windows.Media.IntersectionDetail.Empty>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b50d-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="5b50d-115">See also</span></span>
- [<span data-ttu-id="5b50d-116">Görsel Katmanda Tıklama Testi</span><span class="sxs-lookup"><span data-stu-id="5b50d-116">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="5b50d-117">Görselde Tıklama Testi Geometrisi</span><span class="sxs-lookup"><span data-stu-id="5b50d-117">Hit Test Geometry in a Visual</span></span>](how-to-hit-test-geometry-in-a-visual.md)
