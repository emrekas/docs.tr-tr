---
title: "Nasıl yapılır: EllipseGeometry'ye Animasyon Ekleme"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], EllipseGeometry objects [WPF]
- EllipseGeometry objects [WPF], animating
- graphics [WPF], animation
ms.assetid: 767b9b6e-9cb7-482e-b6c2-fee7750c3995
ms.openlocfilehash: dd92de2cf32a11b81f991939b614a899a25ff4ca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565000"
---
# <a name="how-to-animate-an-ellipsegeometry"></a><span data-ttu-id="8c078-102">Nasıl yapılır: EllipseGeometry'ye Animasyon Ekleme</span><span class="sxs-lookup"><span data-stu-id="8c078-102">How to: Animate an EllipseGeometry</span></span>
<span data-ttu-id="8c078-103">Bu örnek nasıl animasyon gösterir bir <xref:System.Windows.Media.Geometry> içinde bir <xref:System.Windows.Shapes.Path> öğesi.</span><span class="sxs-lookup"><span data-stu-id="8c078-103">This example shows how to animate a <xref:System.Windows.Media.Geometry> within a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="8c078-104">Aşağıdaki örnekte, bir <xref:System.Windows.Media.Animation.PointAnimation> animasyon uygulamak için kullanılan <xref:System.Windows.Media.EllipseGeometry.Center%2A> , bir <xref:System.Windows.Media.EllipseGeometry>.</span><span class="sxs-lookup"><span data-stu-id="8c078-104">In the following example, a <xref:System.Windows.Media.Animation.PointAnimation> is used to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> of an <xref:System.Windows.Media.EllipseGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c078-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="8c078-105">Example</span></span>  
 [!code-xaml[animatepath_snip_XAML#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animatepath_snip_XAML/CS/EllipseGeometryExample.xaml#1)]  
  
 [!code-csharp[animatepath_snip#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animatepath_snip/CSharp/EllipseGeometryExample.cs#101)]  
  
 [!code-vb[animatepath_snip#201](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animatepath_snip/VisualBasic/EllipseGeometryExample.vb#201)]  
  
## <a name="see-also"></a><span data-ttu-id="8c078-106">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="8c078-106">See also</span></span>
- [<span data-ttu-id="8c078-107">Animasyona Genel bakış</span><span class="sxs-lookup"><span data-stu-id="8c078-107">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="8c078-108">Geometriye Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="8c078-108">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
