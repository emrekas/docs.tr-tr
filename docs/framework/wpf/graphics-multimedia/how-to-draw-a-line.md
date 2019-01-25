---
title: 'Nasıl yapılır: Çizgi Çizme'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: 54152b6b68dd453c565afa2ffb23edfe8132a441
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629026"
---
# <a name="how-to-draw-a-line"></a><span data-ttu-id="65636-102">Nasıl yapılır: Çizgi Çizme</span><span class="sxs-lookup"><span data-stu-id="65636-102">How to: Draw a Line</span></span>
<span data-ttu-id="65636-103">Bu örnekte kullanarak çizgi çizmek gösterilmektedir <xref:System.Windows.Shapes.Line> öğesi.</span><span class="sxs-lookup"><span data-stu-id="65636-103">This example shows you how to draw lines by using the <xref:System.Windows.Shapes.Line> element.</span></span>  
  
 <span data-ttu-id="65636-104">Bir çizgi çizmek için oluşturma bir <xref:System.Windows.Shapes.Line> öğesi.</span><span class="sxs-lookup"><span data-stu-id="65636-104">To draw a line, create a <xref:System.Windows.Shapes.Line> element.</span></span> <span data-ttu-id="65636-105">Kullanın, <xref:System.Windows.Shapes.Line.X1%2A> ve <xref:System.Windows.Shapes.Line.Y1%2A> özellikleri, başlangıç noktası; ve kullanmak için kendi <xref:System.Windows.Shapes.Line.X2%2A> ve <xref:System.Windows.Shapes.Line.Y2%2A> uç noktasına ayarlamak için özellikler.</span><span class="sxs-lookup"><span data-stu-id="65636-105">Use its <xref:System.Windows.Shapes.Line.X1%2A> and <xref:System.Windows.Shapes.Line.Y1%2A> properties to set its start point; and use its <xref:System.Windows.Shapes.Line.X2%2A> and <xref:System.Windows.Shapes.Line.Y2%2A> properties to set its end point.</span></span> <span data-ttu-id="65636-106">Son olarak ayarlayın, <xref:System.Windows.Shapes.Shape.Stroke%2A> ve <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> çünkü bir çizgi görünmez.</span><span class="sxs-lookup"><span data-stu-id="65636-106">Finally, set its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> because a line without a stroke is invisible.</span></span>  
  
 <span data-ttu-id="65636-107">Ayar <xref:System.Windows.Shapes.Shape.Fill%2A> öğesi bir satır için hiçbir iç çizginin olmadığı için hiçbir etkiye sahiptir.</span><span class="sxs-lookup"><span data-stu-id="65636-107">Setting the <xref:System.Windows.Shapes.Shape.Fill%2A> element for a line has no effect, because a line has no interior.</span></span>  
  
 <span data-ttu-id="65636-108">Aşağıdaki örnek üç satır içinde çizen bir <xref:System.Windows.Controls.Canvas> öğesi.</span><span class="sxs-lookup"><span data-stu-id="65636-108">The following example draws three lines inside a <xref:System.Windows.Controls.Canvas> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65636-109">Örnek</span><span class="sxs-lookup"><span data-stu-id="65636-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 <span data-ttu-id="65636-110">Bu örnek, daha büyük bir örnek bir parçasıdır; tam bir örnek için bkz. [şekil öğeleri örneği](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="65636-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65636-111">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="65636-111">See also</span></span>
- <xref:System.Windows.Shapes.Line>
- [<span data-ttu-id="65636-112">Şekil öğeleri örneği</span><span class="sxs-lookup"><span data-stu-id="65636-112">Shape Elements Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160037)
