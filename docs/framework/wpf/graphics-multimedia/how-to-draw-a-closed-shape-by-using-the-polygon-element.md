---
title: 'Nasıl yapılır: Çokgen Öğe Kullanarak Kapalı Şekil Çizme'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
ms.openlocfilehash: 533c341e2fae528ec896bf38bafa13974af1d127
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003242"
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a><span data-ttu-id="83732-102">Nasıl yapılır: Çokgen Öğe Kullanarak Kapalı Şekil Çizme</span><span class="sxs-lookup"><span data-stu-id="83732-102">How to: Draw a Closed Shape by Using the Polygon Element</span></span>
<span data-ttu-id="83732-103">Bu örnekte kullanarak kapalı şekil çizme gösterilmektedir <xref:System.Windows.Shapes.Polygon> öğesi.</span><span class="sxs-lookup"><span data-stu-id="83732-103">This example shows how to draw a closed shape by using the <xref:System.Windows.Shapes.Polygon> element.</span></span> <span data-ttu-id="83732-104">Kapalı şekil çizme için oluşturma bir <xref:System.Windows.Shapes.Polygon> öğesi ve kullanım kendi <xref:System.Windows.Shapes.Polygon.Points%2A> özelliği bir şeklin köşe belirtmek için.</span><span class="sxs-lookup"><span data-stu-id="83732-104">To draw a closed shape, create a <xref:System.Windows.Shapes.Polygon> element and use its <xref:System.Windows.Shapes.Polygon.Points%2A> property to specify the vertices of a shape.</span></span> <span data-ttu-id="83732-105">Bir çizgi ilk ve son noktalarına bağlayan otomatik olarak çizilir.</span><span class="sxs-lookup"><span data-stu-id="83732-105">A line is automatically drawn that connects the first and last points.</span></span> <span data-ttu-id="83732-106">Son olarak, belirtin bir <xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>, veya her ikisini de.</span><span class="sxs-lookup"><span data-stu-id="83732-106">Finally, specify a <xref:System.Windows.Shapes.Shape.Fill%2A>, a <xref:System.Windows.Shapes.Shape.Stroke%2A>, or both.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83732-107">Örnek</span><span class="sxs-lookup"><span data-stu-id="83732-107">Example</span></span>  
 <span data-ttu-id="83732-108">İçinde [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], noktaları için geçerli sözdizimi virgülle ayrılmış x ve y-koordinatını çiftlerinin boşlukla ayrılmış bir listesini aşağıdaki gibidir.</span><span class="sxs-lookup"><span data-stu-id="83732-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 <span data-ttu-id="83732-109">Örnek kullansa da bir <xref:System.Windows.Controls.Canvas> çokgenler içermek için Çokgen öğeler (ve diğer tüm şekil öğelerine) ile kullanabileceğiniz <xref:System.Windows.Controls.Panel> veya <xref:System.Windows.Controls.Control> , metin olmayan içerikleri destekler.</span><span class="sxs-lookup"><span data-stu-id="83732-109">Although the example uses a <xref:System.Windows.Controls.Canvas> to contain the polygons, you can use polygon elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="83732-110">Bu örnek, daha büyük bir örnek bir parçasıdır; tam bir örnek için bkz. [şekil öğeleri örneği](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="83732-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>
