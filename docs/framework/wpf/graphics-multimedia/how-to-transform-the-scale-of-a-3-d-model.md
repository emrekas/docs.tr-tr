---
title: 'Nasıl yapılır: 3B Model Ölçeğinin Dönüşümü'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], 3-D objects
- 3-D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
ms.openlocfilehash: 13f718451cb1b753a41304efde7db55360d3f687
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672903"
---
# <a name="how-to-transform-the-scale-of-a-3-d-model"></a>Nasıl yapılır: 3B Model Ölçeğinin Dönüşümü
Bu örnek, 3B nesnenin ölçeklendirme gösterir. 3B nesnenin ölçeklendirmek için kullanmak bir <xref:System.Windows.Media.Media3D.ScaleTransform3D>. <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, Ve <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> özellikleri belirttiğiniz faktörüyle öğe yeniden boyutlandırır. Örneğin, bir <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> 1.5 değerini uzatır özgün genişliğinin yüzde 150'si bir nesne. A <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> 0,5 değerini yüzde 50 nesnenin yüksekliğini küçültür. Aşağıdaki kodu kullanarak gösteren bir <xref:System.Windows.Media.Media3D.ScaleTransform3D> olarak dönüştürme için bir <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, tüm örnek gösterir.  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a>Ayrıca bkz.
- [3B Çevirilerine Animasyon Ekleme](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-3-d-translations.md)
- [3B Görünümü Oluşturma](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)
- [3B Grafiklere Genel Bakış](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
