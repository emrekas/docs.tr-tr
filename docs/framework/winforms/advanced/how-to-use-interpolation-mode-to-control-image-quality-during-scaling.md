---
title: 'Nasıl yapılır: Ölçeklendirme Sırasında Görüntü Kalitesini Denetlemek için İlişkilendirme Modunu Kullanma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interpolation mode [Windows Forms], controlling image quality
- images [Windows Forms], scaling
- images [Windows Forms], controlling quality
ms.assetid: fde9bccf-8aa5-4b0d-ba4b-788740627b02
ms.openlocfilehash: ab0ff93b3ee26467c0de448efd31b698167f95c2
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505718"
---
# <a name="how-to-use-interpolation-mode-to-control-image-quality-during-scaling"></a><span data-ttu-id="4c201-102">Nasıl yapılır: Ölçeklendirme Sırasında Görüntü Kalitesini Denetlemek için İlişkilendirme Modunu Kullanma</span><span class="sxs-lookup"><span data-stu-id="4c201-102">How to: Use Interpolation Mode to Control Image Quality During Scaling</span></span>
<span data-ttu-id="4c201-103">İlişkilendirme modu bir <xref:System.Drawing.Graphics> nesne yolu GDI +'da görüntüleri ölçekler (uzatır ve küçülür) etkiler.</span><span class="sxs-lookup"><span data-stu-id="4c201-103">The interpolation mode of a <xref:System.Drawing.Graphics> object influences the way GDI+ scales (stretches and shrinks) images.</span></span> <span data-ttu-id="4c201-104"><xref:System.Drawing.Drawing2D.InterpolationMode> Sabit listesi tanımlar birkaç ilişkilendirme modu, bazıları aşağıda gösterilmiştir:</span><span class="sxs-lookup"><span data-stu-id="4c201-104">The <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration defines several interpolation modes, some of which are shown in the following list:</span></span>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.Bilinear>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBilinear>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.Bicubic>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic>  
  
 <span data-ttu-id="4c201-105">Görüntü esnetme için her piksel Orijinal görüntüdeki piksel cinsinden daha büyük resmi grubuna eşlenmelidir.</span><span class="sxs-lookup"><span data-stu-id="4c201-105">To stretch an image, each pixel in the original image must be mapped to a group of pixels in the larger image.</span></span> <span data-ttu-id="4c201-106">Görüntü daraltmak için grupları piksel Orijinal görüntüdeki tek piksel cinsinden daha küçük resmi eşlenmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="4c201-106">To shrink an image, groups of pixels in the original image must be mapped to single pixels in the smaller image.</span></span> <span data-ttu-id="4c201-107">Bu eşlemeler gerçekleştiren algoritmalar verimliliğini ölçeklendirilmiş bir görüntü kalitesini belirler.</span><span class="sxs-lookup"><span data-stu-id="4c201-107">The effectiveness of the algorithms that perform these mappings determines the quality of a scaled image.</span></span> <span data-ttu-id="4c201-108">Daha fazla işleme süresi gerektirecek şekilde ölçeklenen daha kaliteli görüntüler oluşturan algoritmaları eğilimindedir.</span><span class="sxs-lookup"><span data-stu-id="4c201-108">Algorithms that produce higher-quality scaled images tend to require more processing time.</span></span> <span data-ttu-id="4c201-109">Yukarıdaki listede <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> düşük kaliteli modudur ve <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> yüksek kaliteli modudur.</span><span class="sxs-lookup"><span data-stu-id="4c201-109">In the preceding list, <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> is the lowest-quality mode and <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> is the highest-quality mode.</span></span>  
  
 <span data-ttu-id="4c201-110">İlişkilendirme modu ayarlamak için üyeleri birini atamanız <xref:System.Drawing.Drawing2D.InterpolationMode> sabit listesine <xref:System.Drawing.Graphics.InterpolationMode%2A> özelliği bir <xref:System.Drawing.Graphics> nesne.</span><span class="sxs-lookup"><span data-stu-id="4c201-110">To set the interpolation mode, assign one of the members of the <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration to the <xref:System.Drawing.Graphics.InterpolationMode%2A> property of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c201-111">Örnek</span><span class="sxs-lookup"><span data-stu-id="4c201-111">Example</span></span>  
 <span data-ttu-id="4c201-112">Aşağıdaki örnek, bir resim çizer ve sonra üç farklı ilişkilendirme modu görüntüsüyle küçültür.</span><span class="sxs-lookup"><span data-stu-id="4c201-112">The following example draws an image and then shrinks the image with three different interpolation modes.</span></span>  
  
 <span data-ttu-id="4c201-113">Aşağıdaki çizimde, orijinal görüntünün ve üç küçük resimleri gösterir.</span><span class="sxs-lookup"><span data-stu-id="4c201-113">The following illustration shows the original image and the three smaller images.</span></span>  
  
 ![Çeşitli ilişkilendirme ayarlarını içeren bir görüntü gösteren ekran görüntüsü.](./media/how-to-use-interpolation-mode-to-control-image-quality-during-scaling/varied-interpolation-settings.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#81](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#81)]
 [!code-vb[System.Drawing.WorkingWithImages#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#81)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4c201-115">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="4c201-115">Compiling the Code</span></span>  
 <span data-ttu-id="4c201-116">Yukarıdaki örnekte, Windows Forms ile kullanılmak üzere tasarlanmıştır ve gerektirir <xref:System.Windows.Forms.PaintEventArgs> `e`, parametre olduğu <xref:System.Windows.Forms.Control.Paint> olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="4c201-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c201-117">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="4c201-117">See also</span></span>

- [<span data-ttu-id="4c201-118">Görüntüler, Bit Eşlemler ve Meta Dosyaları</span><span class="sxs-lookup"><span data-stu-id="4c201-118">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="4c201-119">Görüntüler, Bit Eşlemler, Simgeler ve Meta Dosyaları ile Çalışma</span><span class="sxs-lookup"><span data-stu-id="4c201-119">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
