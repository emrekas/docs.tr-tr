---
title: 'Nasıl yapılır: Veri girişi için yeniden boyutlandırılabilir Windows formu oluşturma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- layout [Windows Forms], resizing
- forms [Windows Forms], creating resizable
- Windows Forms, resizable
ms.assetid: babdf198-404c-485d-a914-ed370c6ecd99
ms.openlocfilehash: a632b243715ee42243c184aa2aca25abb6347f9a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733330"
---
# <a name="how-to-create-a-resizable-windows-form-for-data-entry"></a>Nasıl yapılır: Veri girişi için yeniden boyutlandırılabilir Windows formu oluşturma
İyi bir düzen değişiklikleri kendi üst formunun boyutları için de yanıt verir. Kullanabileceğiniz <xref:System.Windows.Forms.TableLayoutPanel> yeniden boyutlandırabilir ve denetimleri tutarlı bir şekilde form denetiminin boyutlarını değiştikçe konumlandırmak için formun yerleşimini düzenlemeyi denetimi. <xref:System.Windows.Forms.TableLayoutPanel> Denetimidir de yararlıdır düzen değişiklikleri neden denetimlerinizi içeriğini değiştirir. Visual Studio ortamında bu yordamda bahsedilen işlem yapılabilir.  Ayrıca bkz: [izlenecek yol: Veri girişi için yeniden boyutlandırılabilir Windows formu oluşturma](https://msdn.microsoft.com/library/991eahec\(v=vs.110\)).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek nasıl kullanılacağını gösterir. bir <xref:System.Windows.Forms.TableLayoutPanel> zaman kullanıcı formu boyutlandırır iyi cevap veren bir düzen oluşturmak için denetimi. Ayrıca, yerelleştirmeye iyi cevap veren bir düzen gösterir.  
  
 [!code-cpp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/cpp/basicdataentryform.cpp#1)]
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/CS/basicdataentryform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/VB/basicdataentryform.vb#1)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnek gerektirir:  
  
-   Sistem, System.Data System.Drawing ve System.Windows.Forms derlemelere başvuruları.  
  
 Visual Basic veya Visual C# için bu örnek komut satırından derleme hakkında daha fazla bilgi için bkz: [komut satırından derleme](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) veya [oluşturma ile komut satırı csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Visual Studio bu örnekte yeni bir projeye kod yapıştırarak da oluşturabilirsiniz.  Ayrıca bkz: [nasıl yapılır: Derleme ve Visual Studio kullanarak tam bir Windows Formları kod örneği çalıştırma](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Ayrıca bkz.
- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Nasıl yapılır: Sabitleme ve TableLayoutPanel denetiminde alt denetimleri yerleştirme](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Nasıl yapılır: Yerelleştirmeye iyi cevap veren bir Windows Forms düzeni tasarlama](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
- [Microsoft Windows kullanıcı deneyimi, kullanıcı arabirimi geliştiricileri ve tasarımcıları için resmi yönergeleri. Redmond, WA: Microsoft Press, 1999. (USBN: 0-7356-0566-1)](https://www.microsoft.com/mspress/southpacific/books/book11588.htm)
