---
title: 'Nasıl yapılır: Bir Nesnenin Yol Üzerinde Animasyonunu Oluşturma (Matris Animasyonu)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (matrix animation)
- matrix animation [WPF]
ms.assetid: 7000e697-1414-468c-b915-cf66062fc49e
ms.openlocfilehash: c0c4f1fad5ab6b8d30e6809aa866b4629d08af23
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363741"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation"></a>Nasıl yapılır: Bir Nesnenin Yol Üzerinde Animasyonunu Oluşturma (Matris Animasyonu)
Bu örnek nasıl kullanılacağını gösterir <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> sınıfının bir nesnenin tarafından tanımlanan bir yol üzerinde animasyonunu bir <xref:System.Windows.Media.PathGeometry>.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, aşağıdakileri yaparak bir nesnenin yol canlandırın:  
  
-   Geçerli bir <xref:System.Windows.Media.MatrixTransform> taşımak için nesne.  
  
-   Yolu kullanarak tanımlayan bir <xref:System.Windows.Media.PathGeometry>.  
  
-   Oluşturur bir <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> ve animasyon uygulamak için kullandığı <xref:System.Windows.Media.Matrix> özelliği <xref:System.Windows.Media.MatrixTransform>. <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> Alır <xref:System.Windows.Media.PathGeometry> ve oluşturmak için kullandığı <xref:System.Windows.Media.Matrix> değerleri.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexample.xaml#matrixanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExample.cs#matrixanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExample.vb#matrixanimationusingpathwholepage)]  
  
 Tam bir örnek için bkz. [yol animasyonu örneği](https://go.microsoft.com/fwlink/?LinkID=160028). Geometrik yollar hakkında daha fazla bilgi için bkz. [geometrisi](geometry-overview.md).  
  
## <a name="see-also"></a>Ayrıca bkz.
- [Animasyona Genel bakış](animation-overview.md)
- [Yol animasyonu örneği](https://go.microsoft.com/fwlink/?LinkID=160028)
- [Yol Animasyonu ile İlgili Nasıl Yapılır Konuları](path-animation-how-to-topics.md)
