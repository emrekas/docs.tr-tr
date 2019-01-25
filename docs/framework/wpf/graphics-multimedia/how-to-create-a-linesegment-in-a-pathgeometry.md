---
title: 'Nasıl yapılır: PathGeometry İçinde LineSegment Oluşturma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- line segments [WPF], creating
- graphics [WPF], line segments
ms.assetid: 0155ed47-a20d-49a7-a306-186d8e07fbc4
ms.openlocfilehash: 9aa17a361e8e0ca5b43b2646c38926e0123818c1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712135"
---
# <a name="how-to-create-a-linesegment-in-a-pathgeometry"></a><span data-ttu-id="36b50-102">Nasıl yapılır: PathGeometry İçinde LineSegment Oluşturma</span><span class="sxs-lookup"><span data-stu-id="36b50-102">How to: Create a LineSegment in a PathGeometry</span></span>
<span data-ttu-id="36b50-103">Bu örnek, bir çizgi kesimi oluşturma işlemi gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="36b50-103">This example shows how to create a line segment.</span></span> <span data-ttu-id="36b50-104">Bir çizgi kesimi oluşturmak için kullanın <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, ve <xref:System.Windows.Media.LineSegment> sınıfları.</span><span class="sxs-lookup"><span data-stu-id="36b50-104">To create a line segment, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.LineSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36b50-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="36b50-105">Example</span></span>  
 <span data-ttu-id="36b50-106">Aşağıdaki örnekler çizmek bir <xref:System.Windows.Media.LineSegment> gelen (10, 50) için (200, 70).</span><span class="sxs-lookup"><span data-stu-id="36b50-106">The following examples draw a <xref:System.Windows.Media.LineSegment> from (10, 50) to (200, 70).</span></span> <span data-ttu-id="36b50-107">Sonuç, aşağıdaki resimde gösterilmektedir <xref:System.Windows.Media.LineSegment>; kılavuz arka planı koordinat sistemini göstermek için eklenmiştir.</span><span class="sxs-lookup"><span data-stu-id="36b50-107">The following illustration shows the resulting <xref:System.Windows.Media.LineSegment>; a grid background was added to show the coordinate system.</span></span>  
  
 <span data-ttu-id="36b50-108">![İçinde bir LineSegment LineSegment](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-pathgeometrylinesegment.png "graphicsmm_pathgeometrylinesegment")</span><span class="sxs-lookup"><span data-stu-id="36b50-108">![A LineSegment in a PathFigure](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-pathgeometrylinesegment.png "graphicsmm_pathgeometrylinesegment")</span></span>  
<span data-ttu-id="36b50-109">(10,50)'den (200,70) için çizilmiş LineSegment</span><span class="sxs-lookup"><span data-stu-id="36b50-109">A LineSegment drawn from (10,50) to (200,70)</span></span>  
  
 <span data-ttu-id="36b50-110">[xaml]</span><span class="sxs-lookup"><span data-stu-id="36b50-110">[xaml]</span></span>  
  
 <span data-ttu-id="36b50-111">İçinde [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], bir yol tanımlamak için öznitelik sözdizimini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="36b50-111">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may use attribute syntax to describe a path.</span></span>  
  
```xaml  
<Path Stroke="Black" StrokeThickness="1"    
  Data="M 10,50 L 200,70" />  
```  
  
 <span data-ttu-id="36b50-112">[xaml]</span><span class="sxs-lookup"><span data-stu-id="36b50-112">[xaml]</span></span>  
  
 <span data-ttu-id="36b50-113">(Aslında bu öznitelik sözdizimi oluşturan Not bir <xref:System.Windows.Media.StreamGeometry>, daha basit sürümü bir <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="36b50-113">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="36b50-114">Daha fazla bilgi için [yol işaretleme söz dizimi](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) sayfası.)</span><span class="sxs-lookup"><span data-stu-id="36b50-114">For more information, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="36b50-115">İçinde [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], nesne öğesi sözdizimi kullanılarak bir doğru parçası çizebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="36b50-115">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you may also draw a line segment by using object element syntax.</span></span> <span data-ttu-id="36b50-116">Aşağıdaki önceki eşdeğerdir [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] örnek.</span><span class="sxs-lookup"><span data-stu-id="36b50-116">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
```xaml  
<Path Stroke="Black" StrokeThickness="1">  
  <Path.Data>  
    <PathGeometry>  
      <PathFigure StartPoint="10,50">  
        <LineSegment Point="200,70" />  
      </PathFigure>  
    </PathGeometry>  
  </Path.Data>  
</Path>  
```  
  
```csharp  
PathFigure myPathFigure = new PathFigure();  
myPathFigure.StartPoint = new Point(10, 50);  
  
LineSegment myLineSegment = new LineSegment();  
myLineSegment.Point = new Point(200, 70);  
  
PathSegmentCollection myPathSegmentCollection = new PathSegmentCollection();  
myPathSegmentCollection.Add(myLineSegment);  
  
myPathFigure.Segments = myPathSegmentCollection;  
  
PathFigureCollection myPathFigureCollection = new PathFigureCollection();  
myPathFigureCollection.Add(myPathFigure);  
  
PathGeometry myPathGeometry = new PathGeometry();  
myPathGeometry.Figures = myPathFigureCollection;  
  
Path myPath = new Path();  
myPath.Stroke = Brushes.Black;  
myPath.StrokeThickness = 1;  
myPath.Data = myPathGeometry;  
```  
  
```vb  
Dim myPathFigure As New PathFigure()  
            myPathFigure.StartPoint = New Point(10, 50)  
  
            Dim myLineSegment As New LineSegment()  
            myLineSegment.Point = New Point(200, 70)  
  
            Dim myPathSegmentCollection As New PathSegmentCollection()  
            myPathSegmentCollection.Add(myLineSegment)  
  
            myPathFigure.Segments = myPathSegmentCollection  
  
            Dim myPathFigureCollection As New PathFigureCollection()  
            myPathFigureCollection.Add(myPathFigure)  
  
            Dim myPathGeometry As New PathGeometry()  
            myPathGeometry.Figures = myPathFigureCollection  
  
            Dim myPath As New Path()  
            myPath.Stroke = Brushes.Black  
            myPath.StrokeThickness = 1  
            myPath.Data = myPathGeometry  
```  
  
 <span data-ttu-id="36b50-117">Bu örnek, daha büyük örnek bir parçasıdır; tam bir örnek için bkz. [geometri örneği](https://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="36b50-117">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36b50-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="36b50-118">See also</span></span>
- <xref:System.Windows.Media.PathFigure>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.GeometryDrawing>
- <xref:System.Windows.Shapes.Path>
- [<span data-ttu-id="36b50-119">Geometriye Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="36b50-119">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
