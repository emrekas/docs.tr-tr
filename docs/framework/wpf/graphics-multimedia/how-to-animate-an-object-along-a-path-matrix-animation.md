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
ms.openlocfilehash: 836f61e062b921c7e51166a35d8169f903fcbab9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738306"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation"></a><span data-ttu-id="d7ee8-102">Nasıl yapılır: Bir Nesnenin Yol Üzerinde Animasyonunu Oluşturma (Matris Animasyonu)</span><span class="sxs-lookup"><span data-stu-id="d7ee8-102">How to: Animate an Object Along a Path (Matrix Animation)</span></span>
<span data-ttu-id="d7ee8-103">Bu örnek nasıl kullanılacağını gösterir <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> sınıfının bir nesnenin tarafından tanımlanan bir yol üzerinde animasyonunu bir <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="d7ee8-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path that is defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7ee8-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="d7ee8-104">Example</span></span>  
 <span data-ttu-id="d7ee8-105">Aşağıdaki örnek, aşağıdakileri yaparak bir nesnenin yol canlandırın:</span><span class="sxs-lookup"><span data-stu-id="d7ee8-105">The following example animates an object along a path by doing the following:</span></span>  
  
-   <span data-ttu-id="d7ee8-106">Geçerli bir <xref:System.Windows.Media.MatrixTransform> taşımak için nesne.</span><span class="sxs-lookup"><span data-stu-id="d7ee8-106">Applies a <xref:System.Windows.Media.MatrixTransform> to the object in order to move it.</span></span>  
  
-   <span data-ttu-id="d7ee8-107">Yolu kullanarak tanımlayan bir <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="d7ee8-107">Defines the path by using a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
-   <span data-ttu-id="d7ee8-108">Oluşturur bir <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> ve animasyon uygulamak için kullandığı <xref:System.Windows.Media.Matrix> özelliği <xref:System.Windows.Media.MatrixTransform>.</span><span class="sxs-lookup"><span data-stu-id="d7ee8-108">Creates a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> and uses it to animate the <xref:System.Windows.Media.Matrix> property of the <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="d7ee8-109"><xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> Alır <xref:System.Windows.Media.PathGeometry> ve oluşturmak için kullandığı <xref:System.Windows.Media.Matrix> değerleri.</span><span class="sxs-lookup"><span data-stu-id="d7ee8-109">The <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> takes the <xref:System.Windows.Media.PathGeometry> and uses it to generate <xref:System.Windows.Media.Matrix> values.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexample.xaml#matrixanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExample.cs#matrixanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExample.vb#matrixanimationusingpathwholepage)]  
  
 <span data-ttu-id="d7ee8-110">Tam bir örnek için bkz. [yol animasyonu örneği](https://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="d7ee8-110">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span> <span data-ttu-id="d7ee8-111">Geometrik yollar hakkında daha fazla bilgi için bkz. [geometrisi](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d7ee8-111">For more information about geometric paths, see the [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7ee8-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d7ee8-112">See also</span></span>
- [<span data-ttu-id="d7ee8-113">Animasyona Genel bakış</span><span class="sxs-lookup"><span data-stu-id="d7ee8-113">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="d7ee8-114">Yol animasyonu örneği</span><span class="sxs-lookup"><span data-stu-id="d7ee8-114">Path Animation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160028)
- [<span data-ttu-id="d7ee8-115">Yol Animasyonu ile İlgili Nasıl Yapılır Konuları</span><span class="sxs-lookup"><span data-stu-id="d7ee8-115">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
