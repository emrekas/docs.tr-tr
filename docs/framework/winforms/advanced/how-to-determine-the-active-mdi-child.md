---
title: 'Nasıl yapılır: Etkin MDI Alt Öğesini Belirleme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- MDI [Windows Forms], child windows
- child forms
- MDI [Windows Forms], activating forms
- MDI [Windows Forms], locating focus
ms.assetid: 33880ec3-0207-4c2b-a616-ff140443cc0f
ms.openlocfilehash: 81cb9b55f53c152e755ada1803e4ba5731498627
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229478"
---
# <a name="how-to-determine-the-active-mdi-child"></a><span data-ttu-id="39b2e-102">Nasıl yapılır: Etkin MDI Alt Öğesini Belirleme</span><span class="sxs-lookup"><span data-stu-id="39b2e-102">How to: Determine the Active MDI Child</span></span>
<span data-ttu-id="39b2e-103">Bazı durumlarda, çalışan bir komut odaklanmış etkin alt form üzerinde denetim sağlamak isteyeceksiniz.</span><span class="sxs-lookup"><span data-stu-id="39b2e-103">On occasion, you will want to provide a command that operates on the control that has focus on the currently active child form.</span></span> <span data-ttu-id="39b2e-104">Örneğin, alt formun metin kutusunda seçili metni panoya kopyalamak istediğiniz varsayalım.</span><span class="sxs-lookup"><span data-stu-id="39b2e-104">For example, suppose you want to copy selected text from the child form's text box to the Clipboard.</span></span> <span data-ttu-id="39b2e-105">Seçili metni panoya kullanmaya kopyalayan bir yordam oluşturacak <xref:System.Windows.Forms.Control.Click> Standart Düzen menüsünde kopyalama menü öğesinin olay.</span><span class="sxs-lookup"><span data-stu-id="39b2e-105">You would create a procedure that copies selected text to the Clipboard using the <xref:System.Windows.Forms.Control.Click> event of the Copy menu item on the standard Edit menu.</span></span>  
  
 <span data-ttu-id="39b2e-106">Bir MDI uygulaması aynı alt formunun birçok örneği olduğundan yordamı kullanmak için hangi form bilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="39b2e-106">Because an MDI application can have many instances of the same child form, the procedure needs to know which form to use.</span></span> <span data-ttu-id="39b2e-107">Doğru biçimde belirtmek için kullanın <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> odaklı veya, en çok kullanılan etkin alt formun döndüren özellik.</span><span class="sxs-lookup"><span data-stu-id="39b2e-107">To specify the correct form, use the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, which returns the child form that has the focus or that was most recently active.</span></span>  
  
 <span data-ttu-id="39b2e-108">Bir form üzerinde bazı denetimler vardır, ayrıca hangi denetimi etkinse belirtmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="39b2e-108">When you have several controls on a form, you also need to specify which control is active.</span></span> <span data-ttu-id="39b2e-109">Gibi <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> özelliği <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> özelliği etkin alt form üzerinde denetim odağa sahip döndürür.</span><span class="sxs-lookup"><span data-stu-id="39b2e-109">Like the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, the <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> property returns the control with the focus on the active child form.</span></span> <span data-ttu-id="39b2e-110">Aşağıdaki yordam bir alt form menüsünden bir MDI formu veya araç çubuğu düğmesi menüsünde çağrılabilen bir kopyalama yordam gösterir.</span><span class="sxs-lookup"><span data-stu-id="39b2e-110">The procedure below illustrates a copy procedure that can be called from a child form menu, a menu on the MDI form, or a toolbar button.</span></span>  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a><span data-ttu-id="39b2e-111">(Metni panoya kopyalamak için) etkin MDI alt belirlemek için</span><span class="sxs-lookup"><span data-stu-id="39b2e-111">To determine the active MDI child (to copy its text to the Clipboard)</span></span>  
  
1.  <span data-ttu-id="39b2e-112">Bir yöntem içinde etkin denetim etkin alt formun metnini panoya kopyalayın.</span><span class="sxs-lookup"><span data-stu-id="39b2e-112">Within a method, copy the text of the active control of the active child form to the Clipboard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="39b2e-113">Bu örnek MDI üst formu olduğunu varsayar (`Form1`) içeren bir veya daha fazla MDI alt pencereleri olan bir <xref:System.Windows.Forms.RichTextBox> denetimi.</span><span class="sxs-lookup"><span data-stu-id="39b2e-113">This example assumes there is an MDI parent form (`Form1`) that has one or more MDI child windows containing a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="39b2e-114">Daha fazla bilgi için [MDI üst formları oluşturma](how-to-create-mdi-parent-forms.md).</span><span class="sxs-lookup"><span data-stu-id="39b2e-114">For more information, see [Creating MDI Parent Forms](how-to-create-mdi-parent-forms.md).</span></span>  
  
    ```vb  
    Public Sub mniCopy_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniCopy.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Dim theBox As RichTextBox = _  
            TryCast(activeChild.ActiveControl, RichTextBox)  
  
          If (Not theBox Is Nothing) Then  
             'Put selected text on Clipboard.  
             Clipboard.SetDataObject(theBox.SelectedText)  
          Else  
             MessageBox.Show("You need to select a RichTextBox.")  
          End If  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void mniCopy_Click (object sender, System.EventArgs e)  
    {  
       // Determine the active child form.  
       Form activeChild = this.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {    
          try  
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Put the selected text on the Clipboard.  
                Clipboard.SetDataObject(theBox.SelectedText);  
  
             }  
          }  
          catch  
          {  
             MessageBox.Show("You need to select a RichTextBox.");  
          }  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="39b2e-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="39b2e-115">See also</span></span>

- [<span data-ttu-id="39b2e-116">Çoklu Belge Arabirimi (MDI) Uygulamaları</span><span class="sxs-lookup"><span data-stu-id="39b2e-116">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="39b2e-117">Nasıl yapılır: MDI Üst Formları Oluşturma</span><span class="sxs-lookup"><span data-stu-id="39b2e-117">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="39b2e-118">Nasıl yapılır: MDI Alt Formları Oluşturma</span><span class="sxs-lookup"><span data-stu-id="39b2e-118">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="39b2e-119">Nasıl yapılır: Etkin MDI Alt Öğesine Veri Gönderme</span><span class="sxs-lookup"><span data-stu-id="39b2e-119">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="39b2e-120">Nasıl yapılır: MDI Alt Formlarını Düzenleme</span><span class="sxs-lookup"><span data-stu-id="39b2e-120">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
