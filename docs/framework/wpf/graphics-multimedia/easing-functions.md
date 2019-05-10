---
title: Kolaylaştırıcı İşlevler
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applying mathematical formulas to animations [WPF]
- applying easing functions to animations [WPF]
- mathematical formulas [WPF], applying to animations
- animations [WPF], realistic movement
- easing functions [WPF]
- customizing easing functions [WPF]
- easing functions [WPF], definition
- easing functions [WPF], customizing
- animations [WPF], applying
ms.assetid: 075b9c2b-82c4-43fa-b3cd-de0b6236eb38
ms.openlocfilehash: a74142b8d8ee3a68daa9966e3f20f3b8e3becb72
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64615396"
---
# <a name="easing-functions"></a>Kolaylaştırıcı İşlevler
Kolaylaştırıcı işlevler özel matematik formülleri animasyonlarınızda uygulamanıza izin verir. Örneğin, bir nesnenin gerçekçi Sıçrama veya işlevmiş gibi üzerinde spring davranır isteyebilirsiniz. Bu etkilerle yaklaşık olarak belirlemenizi sağlayan anahtar-çerçeve veya bile gelen/için/göre animasyonlarına kullanabilirsiniz, ancak iş önemli miktarda götürecek ve animasyon matematiksel bir formül kullanmaktan daha az doğru olacaktır.  
  
 Kendi özel hızlandırma işlevini devralarak oluşturma yanı sıra <xref:System.Windows.Media.Animation.EasingFunctionBase>, ortak efektleri oluşturmak için çalışma zamanı tarafından sağlanan çeşitli kolaylaştırıcı işlevler birini kullanabilirsiniz.  
  
- <xref:System.Windows.Media.Animation.BackEase>: Belirtilen yolda animasyon uygulamak başlamadan önce bir animasyon hareket biraz geri çeker.  
  
- <xref:System.Windows.Media.Animation.BounceEase>: Sıçrama efekti oluşturur.  
  
- <xref:System.Windows.Media.Animation.CircleEase>: Döngüsel işlevi kullanarak hızlandırır/yavaşlayan bir animasyon oluşturur.  
  
- <xref:System.Windows.Media.Animation.CubicEase>: Formülü kullanarak yavaşlayan hızlanan bir animasyon oluşturur *f*(*t*) = *t*<sup>3</sup>.  
  
- <xref:System.Windows.Media.Animation.ElasticEase>: Kalanına gelene kadar ve geriye salınım yapan bir spring benzer bir animasyon oluşturur.  
  
- <xref:System.Windows.Media.Animation.ExponentialEase>: Bir üstel formülünü kullanarak hızlandırır/yavaşlayan bir animasyon oluşturur.  
  
- <xref:System.Windows.Media.Animation.PowerEase>: Formülü kullanarak yavaşlayan hızlanan bir animasyon oluşturur *f*(*t*) = *t*<sup>p</sup> p olduğu için eşit<xref:System.Windows.Media.Animation.PowerEase.Power%2A>özelliği.  
  
- <xref:System.Windows.Media.Animation.QuadraticEase>: Formülü kullanarak yavaşlayan hızlanan bir animasyon oluşturur *f*(*t*) = *t*<sup>2</sup>.  
  
- <xref:System.Windows.Media.Animation.QuarticEase>: Formülü kullanarak yavaşlayan hızlanan bir animasyon oluşturur *f*(*t*) = *t*<sup>4</sup>.  
  
- <xref:System.Windows.Media.Animation.QuinticEase>: Formül kullanarak yavaşlayan hızlandırır animasyon oluşturmak *f*(*t*) = *t*<sup>5</sup>.  
  
- <xref:System.Windows.Media.Animation.SineEase>: Sinüs formülü kullanarak yavaşlayan hızlandırır animasyon oluşturur.  
  
 Animasyonlara kolaylaştırıcı bir işlev uygulamak için `EasingFunction` özelliğine animasyon uygulamak üzere kolaylaştırıcı işlevi belirtin. Aşağıdaki örnek geçerli bir <xref:System.Windows.Media.Animation.BounceEase> kolaylaştırıcı işlevi bir <xref:System.Windows.Media.Animation.DoubleAnimation> Sıçrama efekti oluşturmak için.  
  
 [!code-xaml[BounceEase_snippet#BounceEase](~/samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 Önceki örnekte, bir From/To/By için hızlandırma işlevini uygulandığı animasyon. Anahtar-çerçeve animasyonlara kolaylaştırıcı bu işlevler de uygulayabilirsiniz. Aşağıdaki örnek anahtar çerçeveler ile ilişkili kolaylaştırıcı işlevleri sözleşmeler yukarı, yavaşlatır, ardından aşağı doğru (düşüyor gibi) genişletir ve ardından Durma noktasına geri dönmeler bir dikdörtgen bir animasyon oluşturmak için nasıl kullanılacağını gösterir.  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](~/samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 Kullanabileceğiniz <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> özelliğini hızlandırma işlevini, diğer bir deyişle, davranış biçimini değiştirmek için değiştirme animasyonun nasıl ilişkilendirileceğini. Verebileceğiniz üç olası değer vardır <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseIn>: İlişkilendirme ile hızlandırma işlevini ilişkili matematik formülünü izler.  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseOut>: İlişkilendirme % 100'ü eksi kolaylaştırıcı bir işlev ile ilişkili formülün izler.  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: İlişkilendirme kullanan <xref:System.Windows.Media.Animation.EasingMode.EaseIn> animasyonun ilk yarısında ve <xref:System.Windows.Media.Animation.EasingMode.EaseOut> ikinci yarısında hiç.  
  
 Farklı değerleri aşağıdaki grafikleri gösteren <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> burada *f*(*x*) animasyon ilerleme durumunu temsil eder ve *t* saati temsil eder.  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 ![BackEase EasingMode grafikleri. ](./media/backease-graph.png "BackEase_Graph")  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 ![BounceEase EasingMode grafikleri. ](./media/bounceease-graph.png "BounceEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 ![CircleEase EasingMode grafikleri. ](./media/circleease-graph.png "CircleEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 ![CubicEase EasingMode grafikleri. ](./media/cubicease-graph.png "CubicEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 ![ElasticEase farklı gevşeme modlarının ile. ](./media/elasticease-graph.png "ElasticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 ![ExponentialEase grafiklerini farklı gevşeme modlarının. ](./media/exponentialease-graph.png "ExponentialEase_Graph")  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 ![QuarticEase farklı gevşeme modlarının ile. ](./media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 ![Farklı gevşeme modlarının grafikleriyle](./media/quadraticease-graph.png "QuadraticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 ![QuarticEase farklı gevşeme modlarının ile. ](./media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 ![QuinticEase farklı gevşeme modlarının ile. ](./media/quinticease-graph.png "QuinticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 ![Farklı EasingMode değerler için SineEase](./media/sineease-graph.png "SineEase_Graph")  
  
> [!NOTE]
>  Kullanabileceğiniz <xref:System.Windows.Media.Animation.PowerEase> aynı davranışı oluşturmak için <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, ve <xref:System.Windows.Media.Animation.QuinticEase> kullanarak <xref:System.Windows.Media.Animation.PowerEase.Power%2A> özelliği. Örneğin, kullanmak istediğiniz <xref:System.Windows.Media.Animation.PowerEase> için yedek olarak <xref:System.Windows.Media.Animation.CubicEase>, belirtin bir <xref:System.Windows.Media.Animation.PowerEase.Power%2A> 3 değeri.  
  
 Kolaylaştırıcı işlevler çalışma zamanı içinde bulunan kullanmanın yanı sıra, kendi özel kolaylaştırıcı işlevler devralarak oluşturabilirsiniz <xref:System.Windows.Media.Animation.EasingFunctionBase>. Aşağıdaki örnek, basit bir özel hızlandırma işlevini nasıl oluşturulacağını gösterir. Geçersiz kılarak hızlandırma işlevini nasıl davranacağını kendi matematiksel mantığı ekleyebileceğiniz <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> yöntemi.   
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
