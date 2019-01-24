---
title: 'Nasıl yapılır: PathGeometry Kullanarak Şekil Oluşturma'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
ms.openlocfilehash: acc50c279995835111e98dd2b74d06f705776f9c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649368"
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a><span data-ttu-id="d1227-102">Nasıl yapılır: PathGeometry Kullanarak Şekil Oluşturma</span><span class="sxs-lookup"><span data-stu-id="d1227-102">How to: Create a Shape by Using a PathGeometry</span></span>
<span data-ttu-id="d1227-103">Bu örnekte, kullanarak şekil oluşturma işlemi gösterilmektedir <xref:System.Windows.Media.PathGeometry> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="d1227-103">This example shows how to create a shape using the <xref:System.Windows.Media.PathGeometry> class.</span></span> <span data-ttu-id="d1227-104"><xref:System.Windows.Media.PathGeometry> nesnelerinden oluşan bir veya daha fazla <xref:System.Windows.Media.PathFigure> nesneleri; her <xref:System.Windows.Media.PathFigure> farklı "Şekil" veya şekli temsil eder.</span><span class="sxs-lookup"><span data-stu-id="d1227-104"><xref:System.Windows.Media.PathGeometry> objects are composed of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="d1227-105">Her <xref:System.Windows.Media.PathFigure> kendisi bir veya daha fazla oluşur <xref:System.Windows.Media.PathSegment> , her biri bir resim veya şekil bağlı bir bölümünü temsil eden nesneleri.</span><span class="sxs-lookup"><span data-stu-id="d1227-105">Each <xref:System.Windows.Media.PathFigure> is itself composed of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="d1227-106">Segment türler <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, ve <xref:System.Windows.Media.BezierSegment>.</span><span class="sxs-lookup"><span data-stu-id="d1227-106">Segment types include <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, and <xref:System.Windows.Media.BezierSegment>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1227-107">Örnek</span><span class="sxs-lookup"><span data-stu-id="d1227-107">Example</span></span>  
 <span data-ttu-id="d1227-108">Aşağıdaki örnekte bir <xref:System.Windows.Media.PathGeometry> bir üçgen oluşturmak için.</span><span class="sxs-lookup"><span data-stu-id="d1227-108">The following example uses a <xref:System.Windows.Media.PathGeometry> to create a triangle.</span></span> <span data-ttu-id="d1227-109"><xref:System.Windows.Media.PathGeometry> Kullanarak görüntülenen bir <xref:System.Windows.Shapes.Path> öğesi.</span><span class="sxs-lookup"><span data-stu-id="d1227-109">The  <xref:System.Windows.Media.PathGeometry> is displayed using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 [!code-xaml[GeometrySample#49](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 <span data-ttu-id="d1227-110">Önceki örnekte oluşturulan şekli aşağıda gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="d1227-110">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="d1227-111">![PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span><span class="sxs-lookup"><span data-stu-id="d1227-111">![A PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span></span>  
<span data-ttu-id="d1227-112">PathGeometry ile oluşturulan bir üçgen</span><span class="sxs-lookup"><span data-stu-id="d1227-112">A triangle created with a PathGeometry</span></span>  
  
 <span data-ttu-id="d1227-113">Önceki örnekte, bir üçgen oldukça basit bir şekil nasıl oluşturulacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="d1227-113">The previous example showed how to create a relatively simple shape, a triangle.</span></span> <span data-ttu-id="d1227-114">A <xref:System.Windows.Media.PathGeometry> yaylar ve eğriler gibi daha karmaşık şekiller oluşturmak için de kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="d1227-114">A <xref:System.Windows.Media.PathGeometry> can also be used to create more complex shapes, including arcs and curves.</span></span> <span data-ttu-id="d1227-115">Örnekler için bkz [elips yay oluşturma](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md), [üçüncü dereceden Bezier eğrisi oluşturma](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md), ve [ikinci dereceden Bezier eğrisi oluşturma](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).</span><span class="sxs-lookup"><span data-stu-id="d1227-115">For examples, see [Create an Elliptical Arc](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md), [Create a Cubic Bezier Curve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md), and [Create a Quadratic Bezier Curve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).</span></span>  
  
 <span data-ttu-id="d1227-116">Bu örnek, daha büyük örnek bir parçasıdır; tam bir örnek için bkz. [geometri örneği](https://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="d1227-116">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1227-117">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d1227-117">See also</span></span>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [<span data-ttu-id="d1227-118">Geometriye Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="d1227-118">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
- [<span data-ttu-id="d1227-119">Geometriler ile ilgili örnek</span><span class="sxs-lookup"><span data-stu-id="d1227-119">Geometries Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159989)
