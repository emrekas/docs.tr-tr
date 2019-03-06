---
title: 'Nasıl yapılır: Üçüncü Dereceden Bezier Eğrisi Oluşturma'
ms.date: 03/30/2017
helpviewer_keywords:
- curves [WPF], cubic Bezier
- Bezier curves [WPF], cubic
- graphics [WPF], cubic Bezier curves
- cubic Bezier curves [WPF]
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
ms.openlocfilehash: da5472408caf8db92fd025730de48b820397f372
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364573"
---
# <a name="how-to-create-a-cubic-bezier-curve"></a>Nasıl yapılır: Üçüncü Dereceden Bezier Eğrisi Oluşturma
Bu örnek, üçüncü dereceden Bezier eğrisi oluşturma işlemi gösterilmektedir. Üçüncü dereceden Bezier eğrisi oluşturmak için kullanın <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, ve <xref:System.Windows.Media.BezierSegment> sınıfları.  Sonuçta elde edilen geometri görüntülemek için kullanın bir <xref:System.Windows.Shapes.Path> öğesi veya onunla bir <xref:System.Windows.Media.GeometryDrawing> veya <xref:System.Windows.Media.DrawingContext>. Üçüncü dereceden Bezier eğrisi çizilir aşağıdaki örneklerde (10, 100) için (300, 100). Eğri denetim noktaları vardır (100, 0) ve (200, 200).  
  
## <a name="example"></a>Örnek  
 [xaml]  
  
 İçinde [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], kısaltılmış biçimlendirme sözdizimi bir yolunu tanımlamak için kullanabilirsiniz.  
  
 [!code-xaml[GeometrySample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]  
  
 [xaml]  
  
 İçinde [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], nesne etiketleri kullanarak üçüncü dereceden Bezier eğrisi da çizebilirsiniz. Aşağıdaki önceki eşdeğerdir [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] örnek.  
  
 [!code-xaml[GeometrySample#33](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 Bu örnek, daha büyük örnek bir parçasıdır; tam bir örnek için bkz. [geometri örneği](https://go.microsoft.com/fwlink/?LinkID=159989).  
  
## <a name="see-also"></a>Ayrıca bkz.
- [Elips Yay Oluşturma](how-to-create-an-elliptical-arc.md)
- [PathGeometry İçinde LineSegment Oluşturma](how-to-create-a-linesegment-in-a-pathgeometry.md)
- [Üçüncü Dereceden Bezier Eğrisi Oluşturma](how-to-create-a-cubic-bezier-curve.md)
- [İkinci Dereceden Bezier Eğrisi Oluşturma](how-to-create-a-quadratic-bezier-curve.md)
