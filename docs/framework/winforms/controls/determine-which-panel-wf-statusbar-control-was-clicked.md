---
title: 'Nasıl yapılır: Windows Forms StatusBar Denetiminde Hangi Panele Tıklandığını Belirleme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], determining panel clicked
- panels [Windows Forms], determining clicked
- StatusBar control [Windows Forms], coding panel click events
- StatusBar control [Windows Forms], determining panel clicked
- PanelClick event [Windows Forms], determining panel clicked
- Panel control [Windows Forms], determining click
ms.assetid: d14c6092-04b2-4a07-8ddf-0dd11277ff5f
ms.openlocfilehash: 1c28f8eaba5c35f762d6fc57ebbddbbb71769c81
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59304291"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a><span data-ttu-id="242d3-102">Nasıl yapılır: Windows Forms StatusBar Denetiminde Hangi Panele Tıklandığını Belirleme</span><span class="sxs-lookup"><span data-stu-id="242d3-102">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="242d3-103"><xref:System.Windows.Forms.StatusStrip> Ve <xref:System.Windows.Forms.ToolStripStatusLabel> denetimleri değiştirin ve işlevsellik eklemek <xref:System.Windows.Forms.StatusBar> ve <xref:System.Windows.Forms.StatusBarPanel> denetler; ancak, <xref:System.Windows.Forms.StatusBar> ve <xref:System.Windows.Forms.StatusBarPanel> denetimleri korunur geriye dönük uyumluluk ve gelecekte kullanım için varsa, ' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="242d3-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="242d3-104">Programa [StatusBar denetimine](statusbar-control-windows-forms.md) denetim bir case deyimi içinde kullanıcının tıklamalarına yanıt verme kullanılacağı <xref:System.Windows.Forms.StatusBar.PanelClick> olay.</span><span class="sxs-lookup"><span data-stu-id="242d3-104">To program the [StatusBar Control](statusbar-control-windows-forms.md) control to respond to user clicks, use a case statement within the <xref:System.Windows.Forms.StatusBar.PanelClick> event.</span></span> <span data-ttu-id="242d3-105">Tıklandı başvuru içeren bir bağımsız değişken (paneli bağımsız) olayı içeren <xref:System.Windows.Forms.StatusBarPanel>.</span><span class="sxs-lookup"><span data-stu-id="242d3-105">The event contains an argument (the panel argument), which contains a reference to the clicked <xref:System.Windows.Forms.StatusBarPanel>.</span></span> <span data-ttu-id="242d3-106">Bu başvuruyu kullanarak dizini tıklanan paneli belirleme ve buna göre program.</span><span class="sxs-lookup"><span data-stu-id="242d3-106">Using this reference, you can determine the index of the clicked panel, and program accordingly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="242d3-107">Emin <xref:System.Windows.Forms.StatusBar> denetimin <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> özelliği `true`.</span><span class="sxs-lookup"><span data-stu-id="242d3-107">Ensure that the <xref:System.Windows.Forms.StatusBar> control's <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property is set to `true`.</span></span>  
  
### <a name="to-determine-which-panel-was-clicked"></a><span data-ttu-id="242d3-108">Hangi panele tıklandığını belirleme</span><span class="sxs-lookup"><span data-stu-id="242d3-108">To determine which panel was clicked</span></span>  
  
1. <span data-ttu-id="242d3-109">İçinde <xref:System.Windows.Forms.StatusBar.PanelClick> olay işleyicisi, kullanım bir `Select Case` (Visual Basic'te) veya `switch case` (görsel C# veya [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) deyimini olay bağımsız değişkenleri tıklandı panelinde dizinini inceleyerek hangi panele tıklandığını belirleme.</span><span class="sxs-lookup"><span data-stu-id="242d3-109">In the <xref:System.Windows.Forms.StatusBar.PanelClick> event handler, use a `Select Case` (in Visual Basic) or `switch case` (Visual C# or [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) statement to determine which panel was clicked by examining the index of the clicked panel in the event arguments.</span></span>  
  
     <span data-ttu-id="242d3-110">Aşağıdaki kod örneği form üzerindeki varlığı gerektiren bir <xref:System.Windows.Forms.StatusBar> denetimi `StatusBar1`ve iki <xref:System.Windows.Forms.StatusBarPanel> nesneleri `StatusBarPanel1` ve `StatusBarPanel2`.</span><span class="sxs-lookup"><span data-stu-id="242d3-110">The following code example requires the presence, on the form, of a <xref:System.Windows.Forms.StatusBar> control, `StatusBar1`, and two <xref:System.Windows.Forms.StatusBarPanel> objects, `StatusBarPanel1` and `StatusBarPanel2`.</span></span>  
  
    ```vb  
    Private Sub StatusBar1_PanelClick(ByVal sender As System.Object, ByVal e As System.Windows.Forms.StatusBarPanelClickEventArgs) Handles StatusBar1.PanelClick  
       Select Case StatusBar1.Panels.IndexOf(e.StatusBarPanel)  
         Case 0  
           MessageBox.Show("You have clicked Panel One.")  
         Case 1  
           MessageBox.Show("You have clicked Panel Two.")  
       End Select  
    End Sub  
    ```  
  
    ```csharp  
    private void statusBar1_PanelClick(object sender,   
    System.Windows.Forms.StatusBarPanelClickEventArgs e)  
    {  
       switch (statusBar1.Panels.IndexOf(e.StatusBarPanel))  
       {  
          case 0 :  
             MessageBox.Show("You have clicked Panel One.");  
             break;  
          case 1 :  
             MessageBox.Show("You have clicked Panel Two.");  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void statusBar1_PanelClick(System::Object ^  sender,  
          System::Windows::Forms::StatusBarPanelClickEventArgs ^  e)  
       {  
          switch (statusBar1->Panels->IndexOf(e->StatusBarPanel))  
          {  
             case 0 :  
                MessageBox::Show("You have clicked Panel One.");  
                break;  
             case 1 :  
                MessageBox::Show("You have clicked Panel Two.");  
                break;  
          }  
       }  
    ```  
  
     <span data-ttu-id="242d3-111">(Visual C# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) formun oluşturucuda olay işleyicisi kaydetmek için aşağıdaki kodu yerleştirin.</span><span class="sxs-lookup"><span data-stu-id="242d3-111">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.statusBar1.PanelClick += new   
       System.Windows.Forms.StatusBarPanelClickEventHandler   
       (this.statusBar1_PanelClick);  
    ```  
  
    ```cpp  
    this->statusBar1->PanelClick += gcnew  
       System::Windows::Forms::StatusBarPanelClickEventHandler  
       (this, &Form1::statusBar1_PanelClick);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="242d3-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="242d3-112">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="242d3-113">Nasıl yapılır: Durum Çubuğu Panellerinin Boyutunu Ayarlama</span><span class="sxs-lookup"><span data-stu-id="242d3-113">How to: Set the Size of Status-Bar Panels</span></span>](how-to-set-the-size-of-status-bar-panels.md)
- [<span data-ttu-id="242d3-114">İzlenecek yol: Çalışma Zamanında Durum Çubuğu Bilgilerini Güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="242d3-114">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)
- [<span data-ttu-id="242d3-115">StatusBar Denetimine Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="242d3-115">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)
