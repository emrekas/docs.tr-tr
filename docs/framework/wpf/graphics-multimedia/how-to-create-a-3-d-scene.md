---
title: 'Nasıl yapılır: 3B Görünümü Oluşturma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3-D
- 3-D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: 23e01934eac0d9e1ea9fb5fbbbc5d8c9d8aabbc5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494400"
---
# <a name="how-to-create-a-3-d-scene"></a><span data-ttu-id="4b607-102">Nasıl yapılır: 3B Görünümü Oluşturma</span><span class="sxs-lookup"><span data-stu-id="4b607-102">How to: Create a 3-D Scene</span></span>
<span data-ttu-id="4b607-103">Bu örnek düz bir yaprak Döndürülmüş kağıt gibi görünen bir 3B nesnesinin nasıl oluşturulacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="4b607-103">This example shows how to create a 3-D object that looks like a flat sheet of paper which has been rotated.</span></span> <span data-ttu-id="4b607-104">A <xref:System.Windows.Controls.Viewport3D> aşağıdaki bileşenlerin yanı sıra bu basit bir 3B görünümü oluşturmak için kullanılır:</span><span class="sxs-lookup"><span data-stu-id="4b607-104">A <xref:System.Windows.Controls.Viewport3D> along with the following components are used to create this simple 3-D scene:</span></span>  
  
-   <span data-ttu-id="4b607-105">Bir kamera kullanılarak oluşturulan bir <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span><span class="sxs-lookup"><span data-stu-id="4b607-105">A camera is created using a <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="4b607-106">Kamera, 3B Sahne hangi kısmının görüntülenebilir olduğunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="4b607-106">The camera specifies what part of the 3-D scene is viewable.</span></span>  
  
-   <span data-ttu-id="4b607-107">Bir 3B nesne (kağıdın) kullanma şekli belirtmek için oluşturulan <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> özelliği <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="4b607-107">A mesh is created to specify the shape of 3-D object (sheet of paper) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
-   <span data-ttu-id="4b607-108">Malzeme (Bu örnekte doğrusal gradyan) nesnesini kullanarak çalışma yüzeyinde görüntülenecek belirtilen <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> özelliği <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="4b607-108">A material is specified to be displayed on the surface of the object (linear gradient in this sample) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
-   <span data-ttu-id="4b607-109">Bir ışık kullanarak nesne üzerinde görünmek için oluşturulan <xref:System.Windows.Media.Media3D.DirectionalLight>.</span><span class="sxs-lookup"><span data-stu-id="4b607-109">A light is created to shine on the object using <xref:System.Windows.Media.Media3D.DirectionalLight>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b607-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="4b607-110">Example</span></span>  
 <span data-ttu-id="4b607-111">Aşağıdaki kod, XAML içinde 3B görünümü oluşturma işlemi gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="4b607-111">The code below shows how to create a 3-D scene in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="4b607-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="4b607-112">Example</span></span>  
 <span data-ttu-id="4b607-113">Aşağıdaki kod, yordam kodunda aynı 3B Sahne oluşturma işlemi gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="4b607-113">The code below shows how to create the same 3-D scene in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="4b607-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="4b607-114">See also</span></span>
- [<span data-ttu-id="4b607-115">3B Grafiklere Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="4b607-115">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
