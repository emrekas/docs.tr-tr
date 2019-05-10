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
ms.openlocfilehash: c07e3cc2f5985c05271e21ea77a7c7056045a891
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64621230"
---
# <a name="how-to-print-in-windows-forms-using-print-preview"></a><span data-ttu-id="53d0b-102">Nasıl yapılır: Windows Forms'da Baskı Önizlemeyi Kullanarak Yazdırma</span><span class="sxs-lookup"><span data-stu-id="53d0b-102">How to: Print in Windows Forms Using Print Preview</span></span>
<span data-ttu-id="53d0b-103">Windows Forms'ta baskı önizlemeyi yazdırma hizmetlerine ek olarak sunmak için programlama yaygın olarak görülür.</span><span class="sxs-lookup"><span data-stu-id="53d0b-103">It is very common in Windows Forms programming to offer print preview in addition to printing services.</span></span> <span data-ttu-id="53d0b-104">Baskı Önizleme Hizmetleri uygulamanıza eklemek için kolay bir yol kullanmaktır bir <xref:System.Windows.Forms.PrintPreviewDialog> birlikte denetim <xref:System.Drawing.Printing.PrintDocument.PrintPage> dosya yazdırma için olay işleme mantığı.</span><span class="sxs-lookup"><span data-stu-id="53d0b-104">An easy way to add print preview services to your application is to use a <xref:System.Windows.Forms.PrintPreviewDialog> control in combination with the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event-handling logic for printing a file.</span></span>  
  
### <a name="to-preview-a-text-document-with-a-printpreviewdialog-control"></a><span data-ttu-id="53d0b-105">Bir metin belgesi PrintPreviewDialog denetimi ile önizlemesini görüntülemek için</span><span class="sxs-lookup"><span data-stu-id="53d0b-105">To preview a text document with a PrintPreviewDialog control</span></span>  
  
1. <span data-ttu-id="53d0b-106">Ekleme bir <xref:System.Windows.Forms.PrintPreviewDialog>, <xref:System.Drawing.Printing.PrintDocument>ve iki dizeyi formunuza.</span><span class="sxs-lookup"><span data-stu-id="53d0b-106">Add a <xref:System.Windows.Forms.PrintPreviewDialog>, <xref:System.Drawing.Printing.PrintDocument>, and two strings to your form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#1)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#1)]  
  
2. <span data-ttu-id="53d0b-107">Ayarlama <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> belge özelliğini istediğiniz yazdırma, açın ve daha önce eklediğiniz dize belgenin içeriğini okuyun.</span><span class="sxs-lookup"><span data-stu-id="53d0b-107">Set the <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> property to the document you wish to print, and open and read the document's contents to the string you added previously.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#2)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#2)]  
  
3. <span data-ttu-id="53d0b-108">İçinde belge yazdırma gibi <xref:System.Drawing.Printing.PrintDocument.PrintPage> olay işleyicisi, kullanım <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> özelliği <xref:System.Drawing.Printing.PrintPageEventArgs> sınıfı ve satırlarını her sayfada hesaplamak ve belge içeriğini işlemek için dosyanın içeriği.</span><span class="sxs-lookup"><span data-stu-id="53d0b-108">As you would for printing the document, in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class and the file contents to calculate lines per page and render the document's contents.</span></span> <span data-ttu-id="53d0b-109">Her sayfanın çekildikten sonra son sayfa olup olmadığını denetleyin ve ayarlama <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> özelliği <xref:System.Drawing.Printing.PrintPageEventArgs> uygun şekilde.</span><span class="sxs-lookup"><span data-stu-id="53d0b-109">After each page is drawn, check to see if it is the last page, and set the <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> accordingly.</span></span> <span data-ttu-id="53d0b-110"><xref:System.Drawing.Printing.PrintDocument.PrintPage> Kadar olayı yükseltildiğinde <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> olduğu `false`.</span><span class="sxs-lookup"><span data-stu-id="53d0b-110">The <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is raised until <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> is `false`.</span></span> <span data-ttu-id="53d0b-111">Belge işleme tamamlandığında, işlenmek üzere dize sıfırlayın.</span><span class="sxs-lookup"><span data-stu-id="53d0b-111">When the document has finished rendering, reset the string to be rendered.</span></span> <span data-ttu-id="53d0b-112">Ayrıca, emin <xref:System.Drawing.Printing.PrintDocument.PrintPage> olay, olay işleme yöntemi ile ilişkili.</span><span class="sxs-lookup"><span data-stu-id="53d0b-112">Also, make sure the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is associated with its event-handling method.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="53d0b-113">Uygulamanızda yazdırma uyguladıysanız zaten 2 ve 3. adımları tamamlamış olmanız.</span><span class="sxs-lookup"><span data-stu-id="53d0b-113">You may have already completed steps 2 and 3 if you have implemented printing in your application.</span></span>  
  
     <span data-ttu-id="53d0b-114">Aşağıdaki kod örneğinde, olay işleyicisi, form üzerinde kullanılan yazı tipini "testPage.txt" dosyasında yazdırmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="53d0b-114">In the following code example, the event handler is used to print the "testPage.txt" file in the same font used on the form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#3)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#3)]  
  
4. <span data-ttu-id="53d0b-115">Ayarlama <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A> özelliği <xref:System.Windows.Forms.PrintPreviewDialog> denetimini <xref:System.Drawing.Printing.PrintDocument> formdaki bileşen.</span><span class="sxs-lookup"><span data-stu-id="53d0b-115">Set the <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintPreviewDialog> control to the <xref:System.Drawing.Printing.PrintDocument> component on the form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#5)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#5)]  
  
5. <span data-ttu-id="53d0b-116">Çağrı <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodunda <xref:System.Windows.Forms.PrintPreviewDialog> denetimi.</span><span class="sxs-lookup"><span data-stu-id="53d0b-116">Call the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method on the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="53d0b-117">Genellikle çağıracak <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> gelen <xref:System.Windows.Forms.Control.Click> düğmesinin olay işleme yöntemi.</span><span class="sxs-lookup"><span data-stu-id="53d0b-117">You would typically call <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> from the <xref:System.Windows.Forms.Control.Click> event-handling method of a button.</span></span> <span data-ttu-id="53d0b-118">Çağırma <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> başlatır <xref:System.Drawing.Printing.PrintDocument.PrintPage> olay ve için çıktıyı işlemeden <xref:System.Windows.Forms.PrintPreviewDialog> denetimi.</span><span class="sxs-lookup"><span data-stu-id="53d0b-118">Calling <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> raises the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event and renders the output to the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="53d0b-119">Kullanıcı iletişim kutusundaki yazdırma simgesine tıkladığında <xref:System.Drawing.Printing.PrintDocument.PrintPage> olayı oluşturulur yeniden Önizleme iletişim kutusu yerine yazıcıya çıktı gönderme.</span><span class="sxs-lookup"><span data-stu-id="53d0b-119">When the user clicks the print icon on the dialog, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is raised again, sending the output to the printer instead of the preview dialog.</span></span> <span data-ttu-id="53d0b-120">Dizenin sonunda, işleme sürecini adım 3'teki sıfırlama nedeni budur.</span><span class="sxs-lookup"><span data-stu-id="53d0b-120">This is why the string is reset at the end of the rendering process in step 3.</span></span>  
  
     <span data-ttu-id="53d0b-121">Aşağıdaki örnekte gösterildiği kod <xref:System.Windows.Forms.Control.Click> form üzerindeki bir düğme için olay işleme yöntemi.</span><span class="sxs-lookup"><span data-stu-id="53d0b-121">The following code example shows the <xref:System.Windows.Forms.Control.Click> event-handling method for a button on the form.</span></span> <span data-ttu-id="53d0b-122">Bu olay işleme yöntemi belge okuma ve yazdırma önizleme iletişim kutusu göstermek için yöntemleri çağırır.</span><span class="sxs-lookup"><span data-stu-id="53d0b-122">This event-handling method calls the methods to read the document and show the print preview dialog.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#4)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="53d0b-123">Örnek</span><span class="sxs-lookup"><span data-stu-id="53d0b-123">Example</span></span>  
 [!code-csharp[System.Drawing.Printing.PrintPreviewExample#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#0)]
 [!code-vb[System.Drawing.Printing.PrintPreviewExample#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="53d0b-124">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="53d0b-124">Compiling the Code</span></span>  
 <span data-ttu-id="53d0b-125">Bu örnek gerektirir:</span><span class="sxs-lookup"><span data-stu-id="53d0b-125">This example requires:</span></span>  
  
- <span data-ttu-id="53d0b-126">Sistem, System.Windows.Forms, System.Drawing derlemelere başvurular.</span><span class="sxs-lookup"><span data-stu-id="53d0b-126">References to the System, System.Windows.Forms, System.Drawing assemblies.</span></span>  
  
- <span data-ttu-id="53d0b-127">Visual Basic veya Visual C# için bu örnek komut satırından derleme hakkında daha fazla bilgi için bkz: [komut satırından derleme](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) veya [oluşturma ile komut satırı csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="53d0b-127">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="53d0b-128">Visual Studio bu örnekte yeni bir projeye kod yapıştırarak da oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="53d0b-128">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53d0b-129">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="53d0b-129">See also</span></span>

- [<span data-ttu-id="53d0b-130">Nasıl yapılır: Windows Forms'ta çok sayfalı metin dosyası yazdırma</span><span class="sxs-lookup"><span data-stu-id="53d0b-130">How to: Print a Multi-Page Text File in Windows Forms</span></span>](how-to-print-a-multi-page-text-file-in-windows-forms.md)
- [<span data-ttu-id="53d0b-131">Windows Forms Yazdırma Desteği</span><span class="sxs-lookup"><span data-stu-id="53d0b-131">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
- [<span data-ttu-id="53d0b-132">Windows Forms'ta Daha Güvenli Yazdırma</span><span class="sxs-lookup"><span data-stu-id="53d0b-132">More Secure Printing in Windows Forms</span></span>](../more-secure-printing-in-windows-forms.md)
