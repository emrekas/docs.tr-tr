---
title: 'Nasıl yapılır: Etkin MDI Alt Öğesine Veri Gönderme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- child forms
- MDI [Windows Forms], sending data to forms
- Clipboard [Windows Forms], pasting
- Clipboard [Windows Forms], getting data from
ms.assetid: 1047d2fe-1235-46db-aad9-563aea1d743b
ms.openlocfilehash: 0ffe87d55f7325f77bd33bdbf5d5fbab9f321f93
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203333"
---
# <a name="how-to-send-data-to-the-active-mdi-child"></a><span data-ttu-id="5ac68-102">Nasıl yapılır: Etkin MDI Alt Öğesine Veri Gönderme</span><span class="sxs-lookup"><span data-stu-id="5ac68-102">How to: Send Data to the Active MDI Child</span></span>
<span data-ttu-id="5ac68-103">Genellikle, bağlamında [Çok Belgeli Arabirim (MDI) uygulamaları](multiple-document-interface-mdi-applications.md), ne zaman kullanıcı Pano'dan veri bir MDI uygulaması yapıştırır gibi etkin alt pencerenin veri göndermek ihtiyacınız olacak.</span><span class="sxs-lookup"><span data-stu-id="5ac68-103">Often, within the context of [Multiple-Document Interface (MDI) Applications](multiple-document-interface-mdi-applications.md), you will need to send data to the active child window, such as when the user pastes data from the Clipboard into an MDI application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ac68-104">Hangi alt pencerenin odaklanmış doğrulama ve içeriği panoya gönderme hakkında daha fazla bilgi için bkz. [etkin MDI alt belirleme](how-to-determine-the-active-mdi-child.md).</span><span class="sxs-lookup"><span data-stu-id="5ac68-104">For information about verifying which child window has focus and sending its contents to the Clipboard, see [Determining the Active MDI Child](how-to-determine-the-active-mdi-child.md).</span></span>  
  
### <a name="to-send-data-to-the-active-mdi-child-window-from-the-clipboard"></a><span data-ttu-id="5ac68-105">Etkin MDI alt penceresine panodan veri göndermesini</span><span class="sxs-lookup"><span data-stu-id="5ac68-105">To send data to the active MDI child window from the Clipboard</span></span>  
  
1.  <span data-ttu-id="5ac68-106">Bir yöntem içinde etkin alt formunun etkin denetimi için metni panoya kopyalayın.</span><span class="sxs-lookup"><span data-stu-id="5ac68-106">Within a method, copy the text on the Clipboard to the active control of the active child form.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5ac68-107">Bu örnek MDI üst formu olduğunu varsayar (`Form1`) içeren bir veya daha fazla MDI alt pencereleri olan bir <xref:System.Windows.Forms.RichTextBox> denetimi.</span><span class="sxs-lookup"><span data-stu-id="5ac68-107">This example assumes there is an MDI parent form (`Form1`) that has one or more MDI child windows containing a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="5ac68-108">Daha fazla bilgi için [MDI üst formları oluşturma](how-to-create-mdi-parent-forms.md).</span><span class="sxs-lookup"><span data-stu-id="5ac68-108">For more information, see [Creating MDI Parent Forms](how-to-create-mdi-parent-forms.md).</span></span>  
  
    ```vb  
    Public Sub mniPaste_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniPaste.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ParentForm.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Try  
             Dim theBox As RichTextBox = Ctype(activeChild.ActiveControl, RichTextBox)  
             If (Not theBox Is Nothing) Then  
                ' Create a new instance of the DataObject interface.  
                Dim data As IDataObject = Clipboard.GetDataObject()  
                ' If the data is text, then set the text of the   
                ' RichTextBox to the text in the clipboard.  
                If (data.GetDataPresent(DataFormats.Text)) Then  
                   theBox.SelectedText = data.GetData(DataFormats.Text).ToString()  
                End If  
             End If  
          Catch  
             MessageBox.Show("You need to select a RichTextBox.")  
          End Try  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void mniPaste_Click (object sender, System.EventArgs e)  
    {  
      // Determine the active child form.  
       Form activeChild = this.ParentForm.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {  
          try   
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Create a new instance of the DataObject interface.  
                IDataObject data = Clipboard.GetDataObject();  
                // If the data is text, then set the text of the   
                // RichTextBox to the text in the clipboard.  
                if (data.GetDataPresent(DataFormats.Text))  
                {  
                   theBox.SelectedText = data.GetData(DataFormats.Text).ToString();                 
                }  
             }  
          }  
          catch   
          {  
             MessageBox.Show("You need to select a RichTextBox.");  
          }  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5ac68-109">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="5ac68-109">See also</span></span>

- [<span data-ttu-id="5ac68-110">Çoklu Belge Arabirimi (MDI) Uygulamaları</span><span class="sxs-lookup"><span data-stu-id="5ac68-110">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="5ac68-111">Nasıl yapılır: MDI Üst Formları Oluşturma</span><span class="sxs-lookup"><span data-stu-id="5ac68-111">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="5ac68-112">Nasıl yapılır: MDI Alt Formları Oluşturma</span><span class="sxs-lookup"><span data-stu-id="5ac68-112">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="5ac68-113">Nasıl yapılır: Etkin MDI Alt Öğesini Belirleme</span><span class="sxs-lookup"><span data-stu-id="5ac68-113">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="5ac68-114">Nasıl yapılır: MDI Alt Formlarını Düzenleme</span><span class="sxs-lookup"><span data-stu-id="5ac68-114">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
