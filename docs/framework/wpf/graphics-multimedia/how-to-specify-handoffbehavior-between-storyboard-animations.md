---
title: 'Nasıl yapılır: Görsel Taslak Animasyonları Arasında HandoffBehavior Belirtme'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
ms.openlocfilehash: 01c652e170e27da0be9b1ab5f7659d7089aee6f8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54677763"
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a>Nasıl yapılır: Görsel Taslak Animasyonları Arasında HandoffBehavior Belirtme
Bu örnekte, görsel taslak animasyonları arasında iletim davranışı belirtmek gösterilmektedir. <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> Özelliği <xref:System.Windows.Media.Animation.BeginStoryboard> belirtir nasıl yeni bir özellik için zaten uygulanmış olan tüm mevcut vm'lere etkileşim.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, fare imleci üzerine getirdiğinde büyütün ve işaretçiyi hemen taşır, daha küçük olur iki düğme oluşturur. Bir düğmenin üzerine fare imleci hızlı bir şekilde kaldırmak, ilk tamamlanmadan önce ikinci animasyonun uygulanır. Bu arasındaki farkı gördüğünüz gibi üst üste iki animasyon <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> değerlerini <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> ve <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>. Değerini <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> değerini animasyonlar arasında daha sorunsuz bir geçiş neden örtüşen animasyonlar birleştirir <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> hemen önceki çakışan animasyonu değiştirmek yeni animasyonu neden olur.  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a>Ayrıca bkz.
- <xref:System.Windows.Media.Animation.BeginStoryboard>
- <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>
- [Animasyona Genel bakış](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [Animasyon ve zamanlama](https://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)
- [Nasıl Yapılır Konuları](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
