---
title: 'Nasıl yapılır: Yansıma Oluşturma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating reflections [WPF]
- brushes [WPF], creating reflections
- reflections [WPF], creating
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
ms.openlocfilehash: 0fae98966481003c7906f5cbb34afaea666d583d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559040"
---
# <a name="how-to-create-a-reflection"></a><span data-ttu-id="ec3b9-102">Nasıl yapılır: Yansıma Oluşturma</span><span class="sxs-lookup"><span data-stu-id="ec3b9-102">How to: Create a Reflection</span></span>
<span data-ttu-id="ec3b9-103">Bu örnek nasıl kullanılacağını gösterir. bir <xref:System.Windows.Media.VisualBrush> yansımasını oluşturmak için.</span><span class="sxs-lookup"><span data-stu-id="ec3b9-103">This example shows how to use a <xref:System.Windows.Media.VisualBrush> to create a reflection.</span></span> <span data-ttu-id="ec3b9-104">Çünkü bir <xref:System.Windows.Media.VisualBrush> mevcut bir görselin görüntüleyebilir, yansıma ve büyütme gibi ilgi çekici görsel efektler üretmek için bu özelliği kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ec3b9-104">Because a <xref:System.Windows.Media.VisualBrush> can display an existing visual, you can use this capability to produce interesting visual effects, such as reflections and magnification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec3b9-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="ec3b9-105">Example</span></span>  
 <span data-ttu-id="ec3b9-106">Aşağıdaki örnekte bir <xref:System.Windows.Media.VisualBrush> yansımasını oluşturmak için bir <xref:System.Windows.Controls.Border> , çeşitli öğeleri içerir.</span><span class="sxs-lookup"><span data-stu-id="ec3b9-106">The following example uses a <xref:System.Windows.Media.VisualBrush> to create a reflection of a <xref:System.Windows.Controls.Border> that contains several elements.</span></span> <span data-ttu-id="ec3b9-107">Bu örneğin oluşturduğu çıktı aşağıda gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="ec3b9-107">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="ec3b9-108">![Bir görsel nesne yansıtılan](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span><span class="sxs-lookup"><span data-stu-id="ec3b9-108">![A reflected Visual object](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span></span>  
<span data-ttu-id="ec3b9-109">Yansıtılan bir görsel nesneyi</span><span class="sxs-lookup"><span data-stu-id="ec3b9-109">A reflected Visual object</span></span>  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 <span data-ttu-id="ec3b9-110">Ekran bölümlerinin nasıl ve yansımaların nasıl oluşturulacağını gösteren örnekleri içeren, tam örnek için bkz [büyütüldüğünü](https://go.microsoft.com/fwlink/?LinkID=160049).</span><span class="sxs-lookup"><span data-stu-id="ec3b9-110">For the complete sample, which includes examples that show how to magnify parts of the screen and how to create reflections, see [VisualBrush Sample](https://go.microsoft.com/fwlink/?LinkID=160049).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec3b9-111">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="ec3b9-111">See also</span></span>
- <xref:System.Windows.Media.VisualBrush>
- [<span data-ttu-id="ec3b9-112">Görüntüler, Çizimler ve Görsellerle Boyama</span><span class="sxs-lookup"><span data-stu-id="ec3b9-112">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
