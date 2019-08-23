---
title: 'Nasıl yapılır: Windows Forms CheckBox Tıklamalarına Yanıt Verme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Click event [Windows Forms], CheckBox control
- CheckBox control [Windows Forms], Click events
- events [Windows Forms], Click events
- double-clicks
- check boxes [Windows Forms], responding to events
ms.assetid: c39f901e-8899-43b6-aa31-939cbf7089fb
ms.openlocfilehash: 7ff6b2aad9ef0775547af57f11af28839e69637c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914975"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a><span data-ttu-id="b8c7a-102">Nasıl yapılır: Windows Forms CheckBox Tıklamalarına Yanıt Verme</span><span class="sxs-lookup"><span data-stu-id="b8c7a-102">How to: Respond to Windows Forms CheckBox Clicks</span></span>
<span data-ttu-id="b8c7a-103">Kullanıcı Windows Forms <xref:System.Windows.Forms.CheckBox> denetimine <xref:System.Windows.Forms.Control.Click> tıkladığında olay oluşur.</span><span class="sxs-lookup"><span data-stu-id="b8c7a-103">Whenever a user clicks a Windows Forms <xref:System.Windows.Forms.CheckBox> control, the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span> <span data-ttu-id="b8c7a-104">Onay kutusunun durumuna bağlı olarak, uygulamanızı bazı eylemler gerçekleştirecek şekilde programlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b8c7a-104">You can program your application to perform some action depending upon the state of the check box.</span></span>  
  
### <a name="to-respond-to-checkbox-clicks"></a><span data-ttu-id="b8c7a-105">Onay kutusu tıklamalarına yanıt vermek için</span><span class="sxs-lookup"><span data-stu-id="b8c7a-105">To respond to CheckBox clicks</span></span>  
  
1. <span data-ttu-id="b8c7a-106">Olay işleyicisinde, denetimin durumunu öğrenmek için <xref:System.Windows.Forms.CheckBox.Checked%2A> özelliğini kullanın ve gerekli tüm eylemleri gerçekleştirin. <xref:System.Windows.Forms.Control.Click></span><span class="sxs-lookup"><span data-stu-id="b8c7a-106">In the <xref:System.Windows.Forms.Control.Click> event handler, use the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine the control's state, and perform any necessary action.</span></span>  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       ' The CheckBox control's Text property is changed each time the   
       ' control is clicked, indicating a checked or unchecked state.  
       If CheckBox1.Checked = True Then  
          CheckBox1.Text = "Checked"  
       Else  
          CheckBox1.Text = "Unchecked"  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       // The CheckBox control's Text property is changed each time the   
       // control is clicked, indicating a checked or unchecked state.  
       if (checkBox1.Checked)  
       {  
          checkBox1.Text = "Checked";  
       }  
       else  
       {  
          checkBox1.Text = "Unchecked";  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if (checkBox1->Checked)  
          {  
             checkBox1->Text = "Checked";  
          }  
          else  
          {  
             checkBox1->Text = "Unchecked";  
          }  
       }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="b8c7a-107">Kullanıcı <xref:System.Windows.Forms.CheckBox> denetime çift tıkladenerse, her tıklama ayrı olarak işlenir; diğer bir deyişle <xref:System.Windows.Forms.CheckBox> , denetim çift tıklama olayını desteklemez.</span><span class="sxs-lookup"><span data-stu-id="b8c7a-107">If the user attempts to double-click the <xref:System.Windows.Forms.CheckBox> control, each click will be processed separately; that is, the <xref:System.Windows.Forms.CheckBox> control does not support the double-click event.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="b8c7a-108">Özellik (varsayılan )<xref:System.Windows.Forms.CheckBox> olduğunda, tıklandığında otomatik olarak seçilir veya temizlenir. `true` <xref:System.Windows.Forms.CheckBox.AutoCheck%2A></span><span class="sxs-lookup"><span data-stu-id="b8c7a-108">When the <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> property is `true` (the default), the <xref:System.Windows.Forms.CheckBox> is automatically selected or cleared when it is clicked.</span></span> <span data-ttu-id="b8c7a-109">Aksi takdirde, <xref:System.Windows.Forms.CheckBox.Checked%2A> <xref:System.Windows.Forms.Control.Click> olay gerçekleştiğinde özelliği el ile ayarlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="b8c7a-109">Otherwise, you must manually set the <xref:System.Windows.Forms.CheckBox.Checked%2A> property when the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span>  
  
     <span data-ttu-id="b8c7a-110">Ayrıca, <xref:System.Windows.Forms.CheckBox> bir eylem kursu tespit etmek için denetimi de kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b8c7a-110">You can also use the <xref:System.Windows.Forms.CheckBox> control to determine a course of action.</span></span>  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a><span data-ttu-id="b8c7a-111">Bir onay kutusu tıklandığında bir eylem kursu belirleme</span><span class="sxs-lookup"><span data-stu-id="b8c7a-111">To determine a course of action when a check box is clicked</span></span>  
  
1. <span data-ttu-id="b8c7a-112">Bir eylem kursu belirleme <xref:System.Windows.Forms.CheckBox.CheckState%2A> özelliğinin değerini sorgulamak için Case ifadesini kullanın.</span><span class="sxs-lookup"><span data-stu-id="b8c7a-112">Use a case statement to query the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property to determine a course of action.</span></span> <span data-ttu-id="b8c7a-113">Özelliği olarak `true`ayarlandığında ,<xref:System.Windows.Forms.CheckBox.CheckState%2A> özelliği denetlenen kutuyu, işaretlenmekte olan kutuyu veya kutunun soluk olarak görüntülendiği üçüncü bir belirsiz durumu temsil eden üç olası değeri döndürebilir <xref:System.Windows.Forms.CheckBox.ThreeState%2A> seçeneğin kullanılamadığını belirten görünüm.</span><span class="sxs-lookup"><span data-stu-id="b8c7a-113">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property may return three possible values, which represent the box being checked, the box being unchecked, or a third indeterminate state in which the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       Select Case CheckBox1.CheckState  
          Case CheckState.Checked  
             ' Code for checked state.  
          Case CheckState.Unchecked  
             ' Code for unchecked state.  
          Case CheckState.Indeterminate  
             ' Code for indeterminate state.  
       End Select   
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       switch(checkBox1.CheckState)  
       {  
          case CheckState.Checked:  
             // Code for checked state.  
             break;  
          case CheckState.Unchecked:  
             // Code for unchecked state.  
             break;  
          case CheckState.Indeterminate:  
             // Code for indeterminate state.  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          switch(checkBox1->CheckState) {  
             case CheckState::Checked:  
                // Code for checked state.  
                break;  
             case CheckState::Unchecked:  
                // Code for unchecked state.  
                break;  
             case CheckState::Indeterminate:  
                // Code for indeterminate state.  
                break;  
          }  
       }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="b8c7a-114"><xref:System.Windows.Forms.CheckBox.ThreeState%2A> Özelliği olarak `true`ayarlandığında, <xref:System.Windows.Forms.CheckBox.Checked%2A> özelliği hem hem de `true` <xref:System.Windows.Forms.CheckState.Checked> için döndürür .<xref:System.Windows.Forms.CheckState.Indeterminate></span><span class="sxs-lookup"><span data-stu-id="b8c7a-114">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns `true` for both <xref:System.Windows.Forms.CheckState.Checked> and <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8c7a-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="b8c7a-115">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="b8c7a-116">CheckBox Denetimine Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="b8c7a-116">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="b8c7a-117">Nasıl yapılır: Seçenekleri Windows Forms onay kutusu denetimleriyle ayarlama</span><span class="sxs-lookup"><span data-stu-id="b8c7a-117">How to: Set Options with Windows Forms CheckBox Controls</span></span>](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [<span data-ttu-id="b8c7a-118">CheckBox Denetimi</span><span class="sxs-lookup"><span data-stu-id="b8c7a-118">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
