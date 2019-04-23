---
title: 'Nasıl yapılır: Anahtar Çerçeveler Kullanarak bir Çifte Animasyon Ekleme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Doubles [WPF], animating with key frames
- animation [WPF], Doubles with key frames
- key frames [WPF], animating Doubles with
ms.assetid: 3a1a7dba-7694-4907-8a2f-3408baebfa82
ms.openlocfilehash: 73cbeab8aee566313bad8e8a18a5500374287de0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59305591"
---
# <a name="how-to-animate-a-double-by-using-key-frames"></a><span data-ttu-id="89258-102">Nasıl yapılır: Anahtar Çerçeveler Kullanarak bir Çifte Animasyon Ekleme</span><span class="sxs-lookup"><span data-stu-id="89258-102">How to: Animate a Double by Using Key Frames</span></span>
<span data-ttu-id="89258-103">Bu örnek, alan bir özelliğin değerine animasyon ekleme işlemi gösterilmektedir bir <xref:System.Double> anahtar çerçeveler kullanarak.</span><span class="sxs-lookup"><span data-stu-id="89258-103">This example shows how to animate the value of a property that takes a <xref:System.Double> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89258-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="89258-104">Example</span></span>  
 <span data-ttu-id="89258-105">Aşağıdaki örnek bir dikdörtgen ekran boyunca taşır.</span><span class="sxs-lookup"><span data-stu-id="89258-105">The following example moves a rectangle across a screen.</span></span> <span data-ttu-id="89258-106">Örnekte <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> animasyon uygulamak için sınıfı <xref:System.Windows.Media.TranslateTransform.X%2A> özelliği bir <xref:System.Windows.Media.TranslateTransform> uygulanan bir <xref:System.Windows.Shapes.Rectangle>.</span><span class="sxs-lookup"><span data-stu-id="89258-106">The example uses the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.TranslateTransform.X%2A> property of a <xref:System.Windows.Media.TranslateTransform> applied to a <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="89258-107">Süresiz olarak yinelenen animasyon, üç anahtar çerçeveler aşağıdaki şekilde kullanır:</span><span class="sxs-lookup"><span data-stu-id="89258-107">This animation, which repeats indefinitely, uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="89258-108">İlk üç saniye boyunca bir örneği kullanan <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> yol dikdörtgen bir hızda başlangıç konumundan 500 konuma taşımak için sınıf.</span><span class="sxs-lookup"><span data-stu-id="89258-108">During the first three seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> class to move the rectangle along a path at a steady rate from its starting position to the 500 position.</span></span> <span data-ttu-id="89258-109">Gibi anahtar doğrusal çerçeveler <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> değerler arasında sorunsuz bir doğrusal geçişi oluşturun.</span><span class="sxs-lookup"><span data-stu-id="89258-109">Linear key frames like <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="89258-110">Dördüncü ikinci sonunda bir örneği kullanan <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> aniden dikdörtgen sonraki konuma taşımak için sınıf.</span><span class="sxs-lookup"><span data-stu-id="89258-110">At the end of the fourth second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> class to suddenly move the rectangle to the next position.</span></span> <span data-ttu-id="89258-111">Gibi ayrı anahtar çerçeveler <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> değerleri arasında ani atlamalar oluşturun.</span><span class="sxs-lookup"><span data-stu-id="89258-111">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> create sudden jumps between values.</span></span> <span data-ttu-id="89258-112">Bu örnekte, dikdörtgen başlangıç konumunda ve aniden 500 konumunda görünür.</span><span class="sxs-lookup"><span data-stu-id="89258-112">In this example, the rectangle is at the starting position and then suddenly appears at the 500 position.</span></span>  
  
3. <span data-ttu-id="89258-113">Son iki saniye içinde bir örneği kullanan <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> rectangle geri başlangıç konumuna taşımak için sınıf.</span><span class="sxs-lookup"><span data-stu-id="89258-113">In the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> class to move the rectangle back to its starting position.</span></span> <span data-ttu-id="89258-114">Eğri anahtar çercevesi ister <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> değerini göre değerler arasında değişken bir geçiş oluşturmak <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="89258-114">Spline key frames like <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> create a variable transition between values according to the value of the <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="89258-115">Bu örnekte, dikdörtgen yavaş taşıyarak başlar ve ardından katlanarak zaman diliminin sonuna doğru hızlandırır.</span><span class="sxs-lookup"><span data-stu-id="89258-115">In this example, the rectangle begins by moving slowly and then speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="89258-116">Tam bir örnek için bkz. [ana kare animasyon örnek](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="89258-116">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
 <span data-ttu-id="89258-117">Diğer animasyon örnekleriyle tutarlılık sağlamak için bu örnek kod sürümleri kullanan bir <xref:System.Windows.Media.Animation.Storyboard> uygulanacak nesne <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span><span class="sxs-lookup"><span data-stu-id="89258-117">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span></span> <span data-ttu-id="89258-118">Alternatif olarak, kod içinde tek bir animasyonu uygularken kullanmak daha basit olduğu <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> yöntemi kullanmak yerine bir <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="89258-118">Alternatively, when applying a single animation in code, it is simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="89258-119">Bir örnek için bkz. [özelliği olmadan kullanarak bir görsel taslak animasyon](how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="89258-119">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89258-120">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="89258-120">See also</span></span>

- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Shapes.Rectangle>
- <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>
- <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>
- [<span data-ttu-id="89258-121">Anahtar-Çerçeve Animasyonlara Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="89258-121">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="89258-122">Anahtar Çerçeve ile İlgili Nasıl Yapılır Konuları</span><span class="sxs-lookup"><span data-stu-id="89258-122">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
