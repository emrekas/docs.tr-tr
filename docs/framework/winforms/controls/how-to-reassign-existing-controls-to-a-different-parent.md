---
title: 'Nasıl yapılır: Mevcut denetimleri farklı bir üst öğeye yeniden atama'
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
ms.openlocfilehash: fa1bd6c0274fdf702072e062e6eeab7078375491
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600290"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a>Nasıl yapılır: Mevcut denetimleri farklı bir üst öğeye yeniden atama
Formunuzdaki yeni bir kapsayıcı denetimi için mevcut denetimleri atayabilirsiniz.  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için seçin **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için [Visual Studio IDE'yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-reassign-existing-controls-to-a-different-parent"></a>Mevcut denetimleri farklı bir üst öğeye yeniden atama  
  
1.  Üç sürükleyin <xref:System.Windows.Forms.Button> denetimler **araç kutusu** forma.  
  
     Birbirine yakın yerleştirin, ancak bunları hizalanmamış bırakın.  
  
2.  İçinde **araç kutusu**, tıklayın <xref:System.Windows.Forms.FlowLayoutPanel> denetim simgesi.  
  
     Simge, form üzerine sürükleyin değil.  
  
3.  Fare işaretçisini üç yakın <xref:System.Windows.Forms.Button> kontrol eder.  
  
     Bir artı işareti ile işaretçi <xref:System.Windows.Forms.FlowLayoutPanel> bağlı denetim simgesi.  
  
4.  ' A tıklayın ve fare düğmesini basılı tutun.  
  
5.  Fare işaretçisi ana hat çizmek için sürükleyin <xref:System.Windows.Forms.FlowLayoutPanel> denetimi.  
  
6.  Üç çevresinde anahat çizmek <xref:System.Windows.Forms.Button> kontrol eder.  
  
7.  Fare düğmesini bırakın.  
  
     Üç <xref:System.Windows.Forms.Button> denetimleri içine eklenir artık <xref:System.Windows.Forms.FlowLayoutPanel> denetimi.  
  
## <a name="see-also"></a>Ayrıca bkz.
- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Windows Forms’da Denetimleri Düzenleme](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)
- [İzlenecek yol: TableLayoutPanel kullanarak Windows Forms'da denetimleri düzenleme](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [İzlenecek yol: Dayama çizgileri kullanarak Windows Forms'da denetimleri düzenleme](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
