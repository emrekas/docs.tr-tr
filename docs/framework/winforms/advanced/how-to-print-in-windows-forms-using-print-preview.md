---
title: "Nasıl yapılır: Windows Forms'da Baskı Önizlemeyi Kullanarak Yazdırma"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- printing [Windows Forms], using print preview
- printing [Windows Forms], with print preview
- print preview
ms.assetid: 4a16f7e2-ae10-4485-b0ae-3d558334d0fe
ms.openlocfilehash: db9269978f3a77920778ab120a6ace11d6dd111c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781257"
---
# <a name="how-to-print-in-windows-forms-using-print-preview"></a>Nasıl yapılır: Windows Forms'da Baskı Önizlemeyi Kullanarak Yazdırma
Windows Forms'ta baskı önizlemeyi yazdırma hizmetlerine ek olarak sunmak için programlama yaygın olarak görülür. Baskı Önizleme Hizmetleri uygulamanıza eklemek için kolay bir yol kullanmaktır bir <xref:System.Windows.Forms.PrintPreviewDialog> birlikte denetim <xref:System.Drawing.Printing.PrintDocument.PrintPage> dosya yazdırma için olay işleme mantığı.  
  
### <a name="to-preview-a-text-document-with-a-printpreviewdialog-control"></a>Bir metin belgesi PrintPreviewDialog denetimi ile önizlemesini görüntülemek için  
  
1. Ekleme bir <xref:System.Windows.Forms.PrintPreviewDialog>, <xref:System.Drawing.Printing.PrintDocument>ve iki dizeyi formunuza.  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#1)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#1)]  
  
2. Ayarlama <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> belge özelliğini istediğiniz yazdırma, açın ve daha önce eklediğiniz dize belgenin içeriğini okuyun.  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#2)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#2)]  
  
3. İçinde belge yazdırma gibi <xref:System.Drawing.Printing.PrintDocument.PrintPage> olay işleyicisi, kullanım <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> özelliği <xref:System.Drawing.Printing.PrintPageEventArgs> sınıfı ve satırlarını her sayfada hesaplamak ve belge içeriğini işlemek için dosyanın içeriği. Her sayfanın çekildikten sonra son sayfa olup olmadığını denetleyin ve ayarlama <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> özelliği <xref:System.Drawing.Printing.PrintPageEventArgs> uygun şekilde. <xref:System.Drawing.Printing.PrintDocument.PrintPage> Kadar olayı yükseltildiğinde <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> olduğu `false`. Belge işleme tamamlandığında, işlenmek üzere dize sıfırlayın. Ayrıca, emin <xref:System.Drawing.Printing.PrintDocument.PrintPage> olay, olay işleme yöntemi ile ilişkili.  
  
    > [!NOTE]
    >  Uygulamanızda yazdırma uyguladıysanız zaten 2 ve 3. adımları tamamlamış olmanız.  
  
     Aşağıdaki kod örneğinde, olay işleyicisi, form üzerinde kullanılan yazı tipini "testPage.txt" dosyasında yazdırmak için kullanılır.  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#3)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#3)]  
  
4. Ayarlama <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A> özelliği <xref:System.Windows.Forms.PrintPreviewDialog> denetimini <xref:System.Drawing.Printing.PrintDocument> formdaki bileşen.  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#5)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#5)]  
  
5. Çağrı <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodunda <xref:System.Windows.Forms.PrintPreviewDialog> denetimi. Genellikle çağıracak <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> gelen <xref:System.Windows.Forms.Control.Click> düğmesinin olay işleme yöntemi. Çağırma <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> başlatır <xref:System.Drawing.Printing.PrintDocument.PrintPage> olay ve için çıktıyı işlemeden <xref:System.Windows.Forms.PrintPreviewDialog> denetimi. Kullanıcı iletişim kutusundaki yazdırma simgesine tıkladığında <xref:System.Drawing.Printing.PrintDocument.PrintPage> olayı oluşturulur yeniden Önizleme iletişim kutusu yerine yazıcıya çıktı gönderme. Dizenin sonunda, işleme sürecini adım 3'teki sıfırlama nedeni budur.  
  
     Aşağıdaki örnekte gösterildiği kod <xref:System.Windows.Forms.Control.Click> form üzerindeki bir düğme için olay işleme yöntemi. Bu olay işleme yöntemi belge okuma ve yazdırma önizleme iletişim kutusu göstermek için yöntemleri çağırır.  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#4)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#4)]  
  
## <a name="example"></a>Örnek  
 [!code-csharp[System.Drawing.Printing.PrintPreviewExample#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#0)]
 [!code-vb[System.Drawing.Printing.PrintPreviewExample#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnek gerektirir:  
  
- Sistem, System.Windows.Forms, System.Drawing derlemelere başvurular.  
  
- Visual Basic veya Visual C# için bu örnek komut satırından derleme hakkında daha fazla bilgi için bkz: [komut satırından derleme](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) veya [oluşturma ile komut satırı csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Visual Studio bu örnekte yeni bir projeye kod yapıştırarak da oluşturabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: Windows Forms'ta çok sayfalı metin dosyası yazdırma](how-to-print-a-multi-page-text-file-in-windows-forms.md)
- [Windows Forms Yazdırma Desteği](windows-forms-print-support.md)
- [Windows Forms'ta Daha Güvenli Yazdırma](../more-secure-printing-in-windows-forms.md)
