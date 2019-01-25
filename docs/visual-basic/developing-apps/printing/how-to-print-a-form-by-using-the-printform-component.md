---
title: 'Nasıl yapılır: (Visual Basic) PrintForm bileşenini kullanarak Form yazdırma'
ms.date: 07/20/2015
helpviewer_keywords:
- Form [Visual Basic], printing
ms.assetid: df963bf6-3ee1-49f4-8b2e-1d95d1beb0be
ms.openlocfilehash: 0a1a62627390c8839625862b9d43d61fc07ebf12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521575"
---
# <a name="how-to-print-a-form-by-using-the-printform-component-visual-basic"></a>Nasıl yapılır: (Visual Basic) PrintForm bileşenini kullanarak Form yazdırma
<xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> Bileşeni ekranda kullanmadan göründüğü gibi hızlı bir şekilde bir form görüntüsü baskı sağlar bir <xref:System.Drawing.Printing.PrintDocument> bileşeni. Aşağıdaki yordamlar bir yazıcı, bir yazdırma önizleme penceresi ve kapsüllenmiş PostScript'i dosya form yazdırma işlemini göstermektedir.  
  
 PowerPack denetimleri artık Visual Studio'ya dahil, ancak bunları indirebilirsiniz [İndirme Merkezi](https://www.microsoft.com/en-us/download/details.aspx?id=25169).  
  
### <a name="to-print-a-form-to-the-default-printer"></a>Varsayılan yazıcı için bir form yazdırma  
  
1.  İçinde **araç kutusu**, tıklayın **Visual Basic PowerPacks** sekmesini ve ardından sürükleyin <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> forma bileşen.  
  
     <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> Bileşen, bileşen tepsisine eklenir.  
  
2.  İçinde **özellikleri** penceresinde <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> özelliğini <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.  
  
3.  Uygun olay işleyicisine aşağıdaki kodu ekleyin (örneğin, `Click` için olay işleyicisi bir **yazdırma**`Button`).  
  
    ```  
    PrintForm1.Print()  
    ```  
  
### <a name="to-display-a-form-in-a-print-preview-window"></a>Bir formu bir baskı önizlemeyi penceresinde görüntülemek için  
  
1.  İçinde **araç kutusu**, tıklayın **Visual Basic PowerPacks** sekmesini ve ardından sürükleyin <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> forma bileşen.  
  
     <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> Bileşen, bileşen tepsisine eklenir.  
  
2.  İçinde **özellikleri** penceresinde <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> özelliğini <xref:System.Drawing.Printing.PrintAction.PrintToPreview>.  
  
3.  Uygun olay işleyicisine aşağıdaki kodu ekleyin (örneğin, `Click` için olay işleyicisi bir **yazdırma**`Button`).  
  
    ```  
    PrintForm1.Print()  
    ```  
  
### <a name="to-print-a-form-to-a-file"></a>Bir formu bir dosyaya yazdırmak için  
  
1.  İçinde **araç kutusu**, tıklayın **Visual Basic PowerPacks** sekmesini ve ardından sürükleyin <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> forma bileşen.  
  
     <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> Bileşen, bileşen tepsisine eklenir.  
  
2.  İçinde **özellikleri** penceresinde <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> özelliğini <xref:System.Drawing.Printing.PrintAction.PrintToFile>.  
  
3.  İsteğe bağlı olarak <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A> tam yol ve dosya adı için gereken hedef dosyayı özelliği ve türü.  
  
     Bu adımı atlarsanız, kullanıcının bir dosya adı için çalışma zamanında istenir.  
  
4.  Uygun olay işleyicisine aşağıdaki kodu ekleyin (örneğin, `Click` için olay işleyicisi bir **yazdırma**`Button`).  
  
    ```  
    PrintForm1.Print()  
    ```  
  
## <a name="see-also"></a>Ayrıca bkz.
- <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>
- <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A>
- [Nasıl yapılır: Formun İstemci Alanını Yazdırma](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)
- [Nasıl yapılır: Formun İstemci Alanlarını ve Diğerlerini Yazdırma](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)
- [Nasıl yapılır: Kaydırılabilir Form Yazdırma](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)
- [PrintForm Bileşeni](../../../visual-basic/developing-apps/printing/printform-component.md)
