---
title: 'Nasıl yapılır: Anahtar Çerçeveler Kullanarak Dikdörtgen Geometriye Animasyon Ekleme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
ms.openlocfilehash: 03953b79127ffceeb49e4ece2070d09f382448a5
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59311350"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a><span data-ttu-id="51fb8-102">Nasıl yapılır: Anahtar Çerçeveler Kullanarak Dikdörtgen Geometriye Animasyon Ekleme</span><span class="sxs-lookup"><span data-stu-id="51fb8-102">How to: Animate a Rectangle Geometry by Using Key Frames</span></span>
<span data-ttu-id="51fb8-103">Bu örnek, animasyon ekleme işlemi gösterilmektedir <xref:System.Windows.Media.RectangleGeometry.Rect%2A> özelliği bir <xref:System.Windows.Media.RectangleGeometry> anahtar çerçeveler kullanarak.</span><span class="sxs-lookup"><span data-stu-id="51fb8-103">This example shows how to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51fb8-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="51fb8-104">Example</span></span>  
 <span data-ttu-id="51fb8-105">Aşağıdaki örnekte <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> animasyon uygulamak için sınıfı <xref:System.Windows.Media.RectangleGeometry.Rect%2A> özelliği bir <xref:System.Windows.Media.RectangleGeometry>.</span><span class="sxs-lookup"><span data-stu-id="51fb8-105">The following example uses the <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry>.</span></span> <span data-ttu-id="51fb8-106">Bu animasyonu üç anahtar çerçeveler şu şekilde kullanılır:</span><span class="sxs-lookup"><span data-stu-id="51fb8-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="51fb8-107">İlk iki saniye boyunca bir örneği kullanan <xref:System.Windows.Media.Animation.LinearRectKeyFrame> konumunu, genişliğini ve bir dikdörtgenin yüksekliğini değişim animasyon uygulamak için sınıfı.</span><span class="sxs-lookup"><span data-stu-id="51fb8-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearRectKeyFrame> class to animate a gradual change in the position, width, and height of a rectangle.</span></span> <span data-ttu-id="51fb8-108">Gibi anahtar doğrusal çerçeveler <xref:System.Windows.Media.Animation.LinearRectKeyFrame> değerler arasında sorunsuz bir doğrusal geçişi oluşturun.</span><span class="sxs-lookup"><span data-stu-id="51fb8-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearRectKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="51fb8-109">Sonraki sonuna sırasında yarım saniye kullanan bir örneğini <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> aniden dikdörtgenin yüksekliğini azaltmak için sınıf.</span><span class="sxs-lookup"><span data-stu-id="51fb8-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> class to suddenly decrease the height of the rectangle.</span></span> <span data-ttu-id="51fb8-110">Gibi ayrı anahtar çerçeveler <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> ani değişiklikleri değerler arasında oluşturur, yükseklik hızla gerçekleşir ve ince değil.</span><span class="sxs-lookup"><span data-stu-id="51fb8-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> create sudden changes between values, that is, the decrease in height occurs quickly and is not subtle.</span></span>  
  
3. <span data-ttu-id="51fb8-111">Son iki saniye boyunca bir örneği kullanan <xref:System.Windows.Media.Animation.SplineRectKeyFrame> dikdörtgeni özgün boyutunu ve konumunu geri değiştirmek için sınıf.</span><span class="sxs-lookup"><span data-stu-id="51fb8-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame> class to change the rectangle back to its original size and position.</span></span> <span data-ttu-id="51fb8-112">Eğri anahtar çercevesi ister <xref:System.Windows.Media.Animation.SplineRectKeyFrame> değerlerine göre değerleri arasında bir değişken geçiş oluşturmak <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="51fb8-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineRectKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="51fb8-113">Bu örnekte, değişiklik yavaş başlar ve zaman diliminin sonuna doğru katlanarak hızlandırır.</span><span class="sxs-lookup"><span data-stu-id="51fb8-113">In this example, the change begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="51fb8-114">Tam bir örnek için bkz. [ana kare animasyon örnek](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="51fb8-114">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51fb8-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="51fb8-115">See also</span></span>

- <xref:System.Windows.Media.RectangleGeometry>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>
- [<span data-ttu-id="51fb8-116">Anahtar-Çerçeve Animasyonlara Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="51fb8-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="51fb8-117">Anahtar Çerçeve ile İlgili Nasıl Yapılır Konuları</span><span class="sxs-lookup"><span data-stu-id="51fb8-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
