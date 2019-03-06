---
title: 'Nasıl yapılır: Çizgi Çizme'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: a194fad5471cafcb567aa00522a597a4186ef4af
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374198"
---
# <a name="how-to-draw-a-line"></a>Nasıl yapılır: Çizgi Çizme
Bu örnekte kullanarak çizgi çizmek gösterilmektedir <xref:System.Windows.Shapes.Line> öğesi.  
  
 Bir çizgi çizmek için oluşturma bir <xref:System.Windows.Shapes.Line> öğesi. Kullanın, <xref:System.Windows.Shapes.Line.X1%2A> ve <xref:System.Windows.Shapes.Line.Y1%2A> özellikleri, başlangıç noktası; ve kullanmak için kendi <xref:System.Windows.Shapes.Line.X2%2A> ve <xref:System.Windows.Shapes.Line.Y2%2A> uç noktasına ayarlamak için özellikler. Son olarak ayarlayın, <xref:System.Windows.Shapes.Shape.Stroke%2A> ve <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> çünkü bir çizgi görünmez.  
  
 Ayar <xref:System.Windows.Shapes.Shape.Fill%2A> öğesi bir satır için hiçbir iç çizginin olmadığı için hiçbir etkiye sahiptir.  
  
 Aşağıdaki örnek üç satır içinde çizen bir <xref:System.Windows.Controls.Canvas> öğesi.  
  
## <a name="example"></a>Örnek  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 Bu örnek, daha büyük bir örnek bir parçasıdır; tam bir örnek için bkz. [şekil öğeleri örneği](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Ayrıca bkz.
- <xref:System.Windows.Shapes.Line>
- [Şekil öğeleri örneği](https://go.microsoft.com/fwlink/?LinkID=160037)
