---
title: 'Nasıl yapılır: Görüntü Kırpma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], cropping
- cropping images [WPF]
ms.assetid: c6bba109-c6e7-4cf8-bfe6-9cf8d01bb4fc
ms.openlocfilehash: dab4b2907f3aeeb2c480adb952a9afc92b6d5c17
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2019
ms.locfileid: "56745939"
---
# <a name="how-to-crop-an-image"></a><span data-ttu-id="6e62a-102">Nasıl yapılır: Görüntü Kırpma</span><span class="sxs-lookup"><span data-stu-id="6e62a-102">How to: Crop an Image</span></span>
<span data-ttu-id="6e62a-103">Bu örnek gösterir kullanarak bir görüntü kırpma <xref:System.Windows.Media.Imaging.CroppedBitmap>.</span><span class="sxs-lookup"><span data-stu-id="6e62a-103">This example shows how to crop an image using <xref:System.Windows.Media.Imaging.CroppedBitmap>.</span></span>  
  
 <span data-ttu-id="6e62a-104"><xref:System.Windows.Media.Imaging.CroppedBitmap> öncelikle bir resim kırpılmış bir sürümünü kodlarken çıkış bir dosyaya kaydetmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="6e62a-104"><xref:System.Windows.Media.Imaging.CroppedBitmap> is primarily used when encoding a cropped version of an image to save out to a file.</span></span> <span data-ttu-id="6e62a-105">Görüntüleme amaçları için bkz. görüntü kırpma için [nasıl yapılır: Kırpma bölgesini oluşturma](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms746710(v=vs.90)) konu.</span><span class="sxs-lookup"><span data-stu-id="6e62a-105">To crop an image for display purposes see the [How to: Create a Clip Region](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms746710(v=vs.90)) topic.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e62a-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="6e62a-106">Example</span></span>  
 <span data-ttu-id="6e62a-107">Aşağıdaki [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] örnekleri içinde kullanılan kaynakları tanımlar.</span><span class="sxs-lookup"><span data-stu-id="6e62a-107">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] defines resources used within the samples below.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml1)]  
  
 <span data-ttu-id="6e62a-108">Aşağıdaki örnek, kullanarak bir görüntü oluşturur. bir <xref:System.Windows.Media.Imaging.CroppedBitmap> kaynağı olarak.</span><span class="sxs-lookup"><span data-stu-id="6e62a-108">The following example creates an image using a <xref:System.Windows.Media.Imaging.CroppedBitmap> as its source.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml2)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp1)]
 [!code-vb[imageelementexample#CroppedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp1)]  
  
 <span data-ttu-id="6e62a-109"><xref:System.Windows.Media.Imaging.CroppedBitmap> De başka bir kaynak olarak kullanılabilir <xref:System.Windows.Media.Imaging.CroppedBitmap>, kırpma zincirleme.</span><span class="sxs-lookup"><span data-stu-id="6e62a-109">The <xref:System.Windows.Media.Imaging.CroppedBitmap> can also be used as the source of another <xref:System.Windows.Media.Imaging.CroppedBitmap>, chaining the cropping.</span></span> <span data-ttu-id="6e62a-110">Unutmayın <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> kaynak bit eşlem ve olmayan ilk resim kırpılmış göreli olan değerleri kullanır.</span><span class="sxs-lookup"><span data-stu-id="6e62a-110">Note that the <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> uses values that are relative to the source cropped bitmap and not the initial image.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml3)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp2)]
 [!code-vb[imageelementexample#CroppedCSharp2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp2)]  
  
## <a name="see-also"></a><span data-ttu-id="6e62a-111">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="6e62a-111">See also</span></span>
- <span data-ttu-id="6e62a-112">[Nasıl yapılır: Kırpma bölgesi oluşturma](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms746710(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="6e62a-112">[How to: Create a Clip Region](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms746710(v=vs.90))</span></span>
