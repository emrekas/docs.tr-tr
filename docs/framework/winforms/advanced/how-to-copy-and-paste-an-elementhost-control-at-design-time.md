---
title: 'Nasıl yapılır: Tasarım Zamanında bir ElementHost Denetimini Kopyalayıp Yapıştırma'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: dfe5244e0c5b61fdf6d940dd16d8c280f013b12c
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666176"
---
# <a name="how-to-copy-and-paste-an-elementhost-control"></a>Nasıl yapılır: ElementHost denetimini kopyalayıp yapıştırma

Bu yordamda, Visual Studio 'da bir Windows formunda Windows Presentation Foundation (WPF) denetiminin nasıl kopyalanacağı gösterilmektedir.

1. Visual Studio 'da Windows Forms projesine yeni bir WPF <xref:System.Windows.Controls.UserControl> ekleyin. Denetim türü için varsayılan adı kullanın, `UserControl1.xaml`. Daha fazla bilgi için bkz [. İzlenecek yol: Tasarım zamanında](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)Windows Forms yeni WPF içeriği oluşturuluyor.

2. **Özellikler** penceresinde <xref:System.Windows.FrameworkElement.Width%2A> , ve <xref:System.Windows.FrameworkElement.Height%2A> özelliklerinin `UserControl1` değerini **200**olarak ayarlayın.

3. <xref:System.Windows.Controls.Control.Background%2A> Özelliğin değerini **mavi**olarak ayarlayın.

4. Projeyi oluşturun.

5. Windows Form Tasarımcısı `Form1` açın.

6. **Araç kutusundan**form `UserControl1` üzerine bir örneğini sürükleyin.

   Bir örneği `UserControl1` adlı <xref:System.Windows.Forms.Integration.ElementHost> Yeni`elementHost1`bir denetimde barındırılır.

7. Seçili olarak, panoya kopyalamak için **CTRL**+C tuşlarına basın. `elementHost1`

8. Form üzerine kopyalanmış denetimi yapıştırmak için **CTRL**+**V** tuşlarına basın.

   Formunda adlı <xref:System.Windows.Forms.Integration.ElementHost> `elementHost2` yeni bir denetim oluşturulur.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Geçiş ve Birlikte Çalışabilirlik](../../wpf/advanced/migration-and-interoperability.md)
- [WPF Denetimlerini Kullanma](using-wpf-controls.md)
- [Visual Studio’da XAML tasarlama](/visualstudio/designers/designing-xaml-in-visual-studio)
