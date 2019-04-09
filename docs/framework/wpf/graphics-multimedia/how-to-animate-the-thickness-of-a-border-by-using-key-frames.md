---
title: 'Nasıl yapılır: Anahtar Çerçeveler Kullanarak Kenarlık Kalınlığına Animasyon Ekleme'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
ms.openlocfilehash: 0c5dc61ac1a4cc3f2aba83ac3a4a71084b553a2a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59087366"
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a>Nasıl yapılır: Anahtar Çerçeveler Kullanarak Kenarlık Kalınlığına Animasyon Ekleme
Bu örnek, animasyon ekleme işlemi gösterilmektedir <xref:System.Windows.Controls.Control.BorderThickness%2A> özelliği bir <xref:System.Windows.Controls.Border>.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> animasyon uygulamak için sınıfı <xref:System.Windows.Controls.Control.BorderThickness%2A> özelliği bir <xref:System.Windows.Controls.Border>. Bu animasyonu üç anahtar çerçeveler şu şekilde kullanılır:  
  
1.  İlk yarım saniye boyunca bir örneği kullanan <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> kenarlık kalınlığı aşamalı olarak artırmak için sınıf. Örnekte <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> değerler arasında düzgün ve doğrusal bir artış oluşturmak için.  
  
2.  Sonraki sonunda yarım saniye kullanan bir örneğini <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> aniden kenarlık kalınlığı artırmak için sınıf. Bu gibi ayrı anahtar çerçeveler türetilen <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> ani atlama, değerleri arasında oluşturur, bu animasyonu hareketini düzensiz olur.  
  
3.  Son iki saniye boyunca bir örneği kullanan <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> kenarlık kalınlığı azaltmak için sınıf. Eğri anahtar çercevesi olanlar gibi türetilen <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> değerlerine göre değerleri arasında bir değişken geçiş oluşturmak <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> özelliği. Bu anahtar çerçeve animasyonu yavaş başlar ve zaman diliminin sonuna doğru katlanarak hızlandırır.  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 Tam bir örnek için bkz. [ana kare animasyon örnek](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>
- [Anahtar-Çerçeve Animasyonlara Genel Bakış](key-frame-animations-overview.md)
- [Anahtar Çerçeve ile İlgili Nasıl Yapılır Konuları](key-frame-animation-how-to-topics.md)
- [BorderThickness Değerine Animasyon Ekleme](../controls/how-to-animate-a-borderthickness-value.md)
