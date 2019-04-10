---
title: 'Nasıl yapılır: Tasarımcı Kullanarak Windows Forms Panel Denetimi ile Denetimleri Gruplandırma'
ms.date: 03/30/2017
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
ms.openlocfilehash: 1a3fcac56df1328c12d7a5dcb542138afdb486f5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214838"
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a>Nasıl yapılır: Tasarımcı Kullanarak Windows Forms Panel Denetimi ile Denetimleri Gruplandırma
Windows Forms <xref:System.Windows.Forms.Panel> denetimleri başka denetimler gruplandırmak için kullanılır. Grup denetimleri için üç neden vardır. NET kullanıcı arabirimi için ilgili form öğelerinin gruplandırma visual biridir; başka bir program, radyo düğmeleri örneğin gruplandırmadır; Tasarım zamanında bir birim olarak denetimleri taşımak için son olur.  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için seçin **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için [Visual Studio IDE'yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-a-group-of-controls"></a>Denetimlerin bir grup oluşturmak için  
  
1.  Sürükleme bir <xref:System.Windows.Forms.Panel> denetimi **Windows Forms** forma araç kutusu sekmesi.  
  
2.  Her bir panel içinde çizim paneli, diğer denetimleri ekleyin.  
  
     Bir panelinde eklemek istediğiniz mevcut denetimleri varsa, tüm denetimler seçip onları seçin panoya Kes <xref:System.Windows.Forms.Panel> denetlemek ve bunları paneline yapıştırın. Ayrıca bunları paneline sürükleyebilirsiniz.  
  
3.  (İsteğe bağlı) Bir panel için bir kenarlık eklemek istiyorsanız, kendi <xref:System.Windows.Forms.BorderStyle> özelliği. Üç seçeneğiniz vardır: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, ve <xref:System.Windows.Forms.BorderStyle.None>.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Panel Denetimi](panel-control-windows-forms.md)
- [Panel Denetimine Genel Bakış](panel-control-overview-windows-forms.md)
- [Nasıl yapılır: Bir Panelin Arka Planını Ayarlama](how-to-set-the-background-of-a-windows-forms-panel.md)
