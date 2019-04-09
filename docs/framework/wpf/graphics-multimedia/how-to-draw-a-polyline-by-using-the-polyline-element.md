---
title: 'Nasıl yapılır: Çoklu Çizgi Öğesi Kullanarak Çoklu Çizgi Çizme'
ms.date: 03/30/2017
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
ms.openlocfilehash: 4f55ecc206be0ef4947923047e796c36131c70ec
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59114852"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a>Nasıl yapılır: Çoklu Çizgi Öğesi Kullanarak Çoklu Çizgi Çizme
Bu örnekte bir dizi bağlantılı çizgiler kullanmaktır çoklu çizgi çizme gösterilmektedir <xref:System.Windows.Shapes.Polyline> öğesi.  
  
 Çoklu çizgi çizme için oluşturma bir <xref:System.Windows.Shapes.Polyline> öğesi ve kullanımı, <xref:System.Windows.Shapes.Polyline.Points%2A> şeklin köşe belirtmek için özellik. Son olarak, <xref:System.Windows.Shapes.Shape.Stroke%2A> ve <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> özelliklerini çoklu çizgi açıklamak için bir çizgi görünmez olduğundan genel çizgileriyle belirtin.  
  
> [!NOTE]
>  Çünkü <xref:System.Windows.Shapes.Polyline> öğesi kapalı bir şekil değil <xref:System.Windows.Shapes.Shape.Fill%2A> özelliği, şeklin dış hattının kapatsanız bile hiçbir etkiye sahiptir. Kapalı bir şekil ile oluşturmak için bir <xref:System.Windows.Shapes.Shape.Fill%2A>, kullanan bir <xref:System.Windows.Shapes.Polygon> öğesi.  
  
 Aşağıdaki örnek iki çizer <xref:System.Windows.Shapes.Polyline> içinde öğeleri bir <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Örnek  
 İçinde [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], noktaları için geçerli sözdizimi virgülle ayrılmış x ve y-koordinatını çiftlerinin boşlukla ayrılmış bir listesini aşağıdaki gibidir.  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 Bu örnek kullansa da bir <xref:System.Windows.Controls.Canvas> kullansa içerecek şekilde çoklu çizgi öğelerini (ve diğer tüm şekil öğelerine) ile kullanabilirsiniz <xref:System.Windows.Controls.Panel> veya <xref:System.Windows.Controls.Control> , metin olmayan içerikleri destekler.  
  
 Bu örnek, daha büyük bir örnek bir parçasıdır; tam bir örnek için bkz. [şekil öğeleri örneği](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [Şekil öğeleri örneği](https://go.microsoft.com/fwlink/?LinkID=160037)
- [WPF Genel Bakışı İçinde Şekiller ve Temel Çizimler](shapes-and-basic-drawing-in-wpf-overview.md)
