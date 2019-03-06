---
title: 'Nasıl yapılır: Anahtar Çerçeveler Kullanarak bir Noktaya Animasyon Ekleme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating Points with
- Points [WPF], animating with key frames
- animation [WPF], Points with key frames
ms.assetid: d2e2ef10-0773-4133-856e-d41c09f60ded
ms.openlocfilehash: 4eeb7aa271883e1c76d5cac77f49accbdff39aea
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357241"
---
# <a name="how-to-animate-a-point-by-using-key-frames"></a><span data-ttu-id="cdc0b-102">Nasıl yapılır: Anahtar Çerçeveler Kullanarak bir Noktaya Animasyon Ekleme</span><span class="sxs-lookup"><span data-stu-id="cdc0b-102">How to: Animate a Point by Using Key Frames</span></span>
<span data-ttu-id="cdc0b-103">Bu örnek nasıl kullanılacağını gösterir <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> animasyon uygulamak için sınıfı bir <xref:System.Windows.Point>.</span><span class="sxs-lookup"><span data-stu-id="cdc0b-103">This example shows how to use the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> class to animate a <xref:System.Windows.Point>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdc0b-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="cdc0b-104">Example</span></span>  
 <span data-ttu-id="cdc0b-105">Aşağıdaki örnek, bir elips üçgen yol boyunca taşır.</span><span class="sxs-lookup"><span data-stu-id="cdc0b-105">The following example moves an ellipse along a triangular path.</span></span> <span data-ttu-id="cdc0b-106">Örnekte <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> animasyon uygulamak için sınıfı <xref:System.Windows.Media.EllipseGeometry.Center%2A> özelliği bir <xref:System.Windows.Media.EllipseGeometry>.</span><span class="sxs-lookup"><span data-stu-id="cdc0b-106">The example uses the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> property of an <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="cdc0b-107">Bu animasyonu üç anahtar çerçeveler şu şekilde kullanılır:</span><span class="sxs-lookup"><span data-stu-id="cdc0b-107">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="cdc0b-108">İlk yarım saniye boyunca bir örneği kullanan <xref:System.Windows.Media.Animation.LinearPointKeyFrame> elips yol boyunca başlangıç konumundan bir hızda taşımak için sınıf.</span><span class="sxs-lookup"><span data-stu-id="cdc0b-108">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearPointKeyFrame> class to move the ellipse along a path at a steady rate from its starting position.</span></span> <span data-ttu-id="cdc0b-109">Gibi anahtar doğrusal çerçeveler <xref:System.Windows.Media.Animation.LinearPointKeyFrame> değerler arasında sorunsuz bir doğrusal ilişkilendirme oluşturun.</span><span class="sxs-lookup"><span data-stu-id="cdc0b-109">Linear key frames like <xref:System.Windows.Media.Animation.LinearPointKeyFrame> create a smooth linear interpolation between values.</span></span>  
  
2.  <span data-ttu-id="cdc0b-110">Sonraki sonuna sırasında yarım saniye kullanan bir örneğini <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> aniden elips yol boyunca sonraki konuma taşımak için sınıf.</span><span class="sxs-lookup"><span data-stu-id="cdc0b-110">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> class to suddenly move the ellipse along the path to the next position.</span></span> <span data-ttu-id="cdc0b-111">Gibi ayrı anahtar çerçeveler <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> değerleri arasında ani atlamalar oluşturun.</span><span class="sxs-lookup"><span data-stu-id="cdc0b-111">Discrete key frames like <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> create sudden jumps between values.</span></span>  
  
3.  <span data-ttu-id="cdc0b-112">Son iki saniye boyunca bir örneği kullanan <xref:System.Windows.Media.Animation.SplinePointKeyFrame> elipsin başlangıç konumuna geri taşımak için sınıf.</span><span class="sxs-lookup"><span data-stu-id="cdc0b-112">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplinePointKeyFrame> class to move the ellipse back to its starting position.</span></span> <span data-ttu-id="cdc0b-113">Eğri anahtar çercevesi ister <xref:System.Windows.Media.Animation.SplinePointKeyFrame> değerlerine göre değerleri arasında bir değişken geçiş oluşturmak <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="cdc0b-113">Spline key frames like <xref:System.Windows.Media.Animation.SplinePointKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="cdc0b-114">Bu örnekte, animasyon yavaş başlar ve zaman diliminin sonuna doğru katlanarak hızlandırır.</span><span class="sxs-lookup"><span data-stu-id="cdc0b-114">In this example, the animation begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="cdc0b-115">Tam bir örnek için bkz. [ana kare animasyon örnek](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="cdc0b-115">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
 <span data-ttu-id="cdc0b-116">Diğer animasyon örnekleriyle tutarlılık sağlamak için bu örnek kod sürümleri kullanan bir <xref:System.Windows.Media.Animation.Storyboard> uygulanacak nesne <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>.</span><span class="sxs-lookup"><span data-stu-id="cdc0b-116">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>.</span></span> <span data-ttu-id="cdc0b-117">Ancak, tek bir animasyonu kod uygularken kullanmak daha basit olduğu <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> yöntemi kullanmak yerine bir <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="cdc0b-117">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="cdc0b-118">Bir örnek için bkz. [özelliği olmadan kullanarak bir görsel taslak animasyon](how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="cdc0b-118">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdc0b-119">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="cdc0b-119">See also</span></span>
- <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.EllipseGeometry>
- [<span data-ttu-id="cdc0b-120">Anahtar-Çerçeve Animasyonlara Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="cdc0b-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="cdc0b-121">Anahtar Çerçeve ile İlgili Nasıl Yapılır Konuları</span><span class="sxs-lookup"><span data-stu-id="cdc0b-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
