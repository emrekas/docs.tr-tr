---
title: 'Nasıl yapılır: Mevcut Denetimleri Farklı bir Üst Öğeye Yeniden Atama'
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
ms.openlocfilehash: 2639322707c1c7e378f6d389a1dec80fd619841c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59328224"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a>Nasıl yapılır: Mevcut Denetimleri Farklı bir Üst Öğeye Yeniden Atama
Formunuzdaki yeni bir kapsayıcı denetimi için mevcut denetimleri atayabilirsiniz.  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için seçin **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için [Visual Studio IDE'yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-reassign-existing-controls-to-a-different-parent"></a>Mevcut denetimleri farklı bir üst öğeye yeniden atama  
  
1. Üç sürükleyin <xref:System.Windows.Forms.Button> denetimler **araç kutusu** forma.  
  
     Birbirine yakın yerleştirin, ancak bunları hizalanmamış bırakın.  
  
2. İçinde **araç kutusu**, tıklayın <xref:System.Windows.Forms.FlowLayoutPanel> denetim simgesi.  
  
     Simge, form üzerine sürükleyin değil.  
  
3. Fare işaretçisini üç yakın <xref:System.Windows.Forms.Button> kontrol eder.  
  
     Bir artı işareti ile işaretçi <xref:System.Windows.Forms.FlowLayoutPanel> bağlı denetim simgesi.  
  
4. ' A tıklayın ve fare düğmesini basılı tutun.  
  
5. Fare işaretçisi ana hat çizmek için sürükleyin <xref:System.Windows.Forms.FlowLayoutPanel> denetimi.  
  
6. Üç çevresinde anahat çizmek <xref:System.Windows.Forms.Button> kontrol eder.  
  
7. Fare düğmesini bırakın.  
  
     Üç <xref:System.Windows.Forms.Button> denetimleri içine eklenir artık <xref:System.Windows.Forms.FlowLayoutPanel> denetimi.  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Windows Forms’da Denetimleri Düzenleme](arranging-controls-on-windows-forms.md)
- [İzlenecek yol: TableLayoutPanel kullanarak Windows Forms'da denetimleri düzenleme](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [İzlenecek yol: Dayama çizgileri kullanarak Windows Forms'da denetimleri düzenleme](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
