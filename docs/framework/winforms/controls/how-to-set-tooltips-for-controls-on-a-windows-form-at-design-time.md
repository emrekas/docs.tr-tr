---
title: 'Nasıl yapılır: Tasarım zamanında bir Windows formundaki denetimler için ToolTips ayarlama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: ebefe596728b5cabd9d24720d8c39f13c8836bd8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54609414"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a>Nasıl yapılır: Tasarım zamanında bir Windows formundaki denetimler için ToolTips ayarlama
Ayarlayabileceğiniz bir <xref:System.Windows.Forms.ToolTip> kodda veya Windows Forms Tasarımcısı'nda bir dize. Hakkında daha fazla bilgi için <xref:System.Windows.Forms.ToolTip> bileşeni Bkz [ToolTip bileşenine genel bakış](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md).  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için seçin **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için [Visual Studio IDE'yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-a-tooltip-programmatically"></a>Bir araç ipucu program üzerinden ayarlamak için  
  
1.  Araç İpucu görüntüleyen denetimi ekleyin.  
  
2.  Kullanım <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> yöntemi <xref:System.Windows.Forms.ToolTip> bileşeni.  
  
    ```vb  
    ' In this example, Button1 is the control to display the ToolTip.  
    ToolTip1.SetToolTip(Button1, "Save changes")  
    ```  
  
    ```csharp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1.SetToolTip(button1, "Save changes");  
    ```  
  
    ```cpp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1->SetToolTip(button1, "Save changes");  
    ```  
  
### <a name="to-set-a-tooltip-in-the-designer"></a>Tasarımcıda bir araç ipucu ayarlamak için  
  
1.  Ekleme bir <xref:System.Windows.Forms.ToolTip> forma bileşen.  
  
2.  Araç ipucunu görüntülemek veya forma ekler denetimi seçin.  
  
3.  İçinde **özellikleri** penceresinde **ToolTip1 araç ipucu** uygun bir metin dizesi değeri.  

### <a name="to-remove-a-tooltip-programmatically"></a>Bir araç ipucu programlı bir şekilde kaldırmak için  
  
1.  Kullanım <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> yöntemi <xref:System.Windows.Forms.ToolTip> bileşeni.  
  
    ```vb  
    ' In this example, Button1 is the control displaying the ToolTip.  
    ToolTip1.SetToolTip(Button1, Nothing)  
    ```  
  
    ```csharp  
    // In this example, button1 is the control displaying the ToolTip.  
    toolTip1.SetToolTip(button1, null);  
    ```  
  
    ```cpp  
    // In this example, button1 is the control displaying the ToolTip.  
    toolTip1->SetToolTip(button1, NULL);  
    ```  
  
### <a name="to-remove-a-tooltip-in-the-designer"></a>Tasarımcıda bir araç ipucu kaldırmak için  
  
1.  Araç İpucu görüntüleyen bir denetimi seçin.  
  
2.  İçinde **özellikleri** penceresi, metni silmek **ToolTip1 araç ipucu**.  

## <a name="see-also"></a>Ayrıca bkz.
- [ToolTip Bileşenine Genel Bakış](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)
- [Nasıl yapılır: Windows Forms ToolTip bileşeninin gecikmesini değiştirme](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [ToolTip Bileşeni](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)
