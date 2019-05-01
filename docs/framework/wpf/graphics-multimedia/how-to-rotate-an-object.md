---
title: 'Nasıl yapılır: Nesne Döndürme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rotating objects [WPF]
- rotating objects [WPF]
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
ms.openlocfilehash: d1c4700a5dc8f6ed99043552999d8f014116da8f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61804173"
---
# <a name="how-to-rotate-an-object"></a>Nasıl yapılır: Nesne Döndürme
Bu örnek, bir nesnenin nasıl döndürüleceğini gösterir. Örneğin ilk oluşturur bir <xref:System.Windows.Media.RotateTransform> ve ardından belirtir, <xref:System.Windows.Media.RotateTransform.Angle%2A> derece cinsinden.  
  
 Aşağıdaki örnek döndürür bir <xref:System.Windows.Shapes.Polyline> kendi üst sol löşede 45 derece nesne.  
  
## <a name="example"></a>Örnek  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 <xref:System.Windows.Media.RotateTransform.CenterX%2A> Ve <xref:System.Windows.Media.RotateTransform.CenterY%2A> özelliklerini <xref:System.Windows.Media.RotateTransform> nesne döndürüldüğü noktasını belirtin. Bu merkez noktasını dönüştürülür öğenin koordinat ifade edilir. Varsayılan olarak, döndürme (0,0), sol üst köşesinin dönüştürmek için nesnenin olduğu uygulanır.  
  
 Sonraki örnekte döndürür bir <xref:System.Windows.Shapes.Polyline> noktası (25,50) 45 derece saat yönünde nesne.  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 Uygulama sonuçlarını aşağıdaki çizimde bir <xref:System.Windows.Media.Transform> iki nesne için.  
  
 ![farklı merkezi noktalarıyla 45 derece döndürme](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
Döngüsel 45 derece farklı döndürmek iki nesne merkezleri  
  
 <xref:System.Windows.Shapes.Polyline> Önceki örneklerde olduğu bir <xref:System.Windows.UIElement>. Uyguladığınızda bir <xref:System.Windows.Media.Transform> için <xref:System.Windows.UIElement.RenderTransform%2A> özelliği bir <xref:System.Windows.UIElement>, kullanabileceğiniz <xref:System.Windows.UIElement.RenderTransformOrigin%2A> özelliği için bir kaynak belirtmek için her <xref:System.Windows.Media.Transform> öğeye uygulanacak. Çünkü <xref:System.Windows.UIElement.RenderTransformOrigin%2A> özelliği kullanan göreli koordinatlarda, boyutuna sahibi olmasanız bile, bir dönüştürme öğesinin merkezine uygulayabilirsiniz. Daha fazla bilgi ve örnek için bkz: [göreli değerler kullanarak dönüşümün kaynağını belirtme](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).  
  
 Tam bir örnek için bkz. [2B dönüşüm örnek](https://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Windows.Media.Transform>
- [Dönüşümlere Genel Bakış](transforms-overview.md)
- [Nasıl Yapılır Konuları](transformations-how-to-topics.md)
