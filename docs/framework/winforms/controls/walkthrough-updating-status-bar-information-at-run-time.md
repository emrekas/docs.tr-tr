---
title: 'İzlenecek yol: Çalışma Zamanında Durum Çubuğu Bilgilerini Güncelleştirme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], updating at run time
- status bars [Windows Forms], refreshing panels
- StatusBar control [Windows Forms], refreshing panels
- panels [Windows Forms], refreshing status bar
ms.assetid: cc2abb06-c082-49f7-a5a3-2fd1bbcb58d1
ms.openlocfilehash: 7beae9bb886c7c79d4d97375887bfecb0c2a40c1
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59333320"
---
# <a name="walkthrough-updating-status-bar-information-at-run-time"></a><span data-ttu-id="fac38-102">İzlenecek yol: Çalışma Zamanında Durum Çubuğu Bilgilerini Güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="fac38-102">Walkthrough: Updating Status Bar Information at Run Time</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="fac38-103"><xref:System.Windows.Forms.StatusStrip> Ve <xref:System.Windows.Forms.ToolStripStatusLabel> denetimleri değiştirin ve işlevsellik eklemek <xref:System.Windows.Forms.StatusBar> ve <xref:System.Windows.Forms.StatusBarPanel> denetler; ancak, <xref:System.Windows.Forms.StatusBar> ve <xref:System.Windows.Forms.StatusBarPanel> denetimleri korunur geriye dönük uyumluluk ve gelecekte kullanım için varsa, ' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="fac38-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="fac38-104">Genellikle, bir program, çalışma zamanında dinamik olarak güncelleştirmek için uygulama durumunu veya başka bir kullanıcı etkileşimi değişikliklere göre durum çubuğu panellerinin içeriğini çağırır.</span><span class="sxs-lookup"><span data-stu-id="fac38-104">Often, a program will call for you to update the contents of status bar panels dynamically at run time, based on changes to application state or other user interaction.</span></span> <span data-ttu-id="fac38-105">Bu anahtarları CAPS LOCK, NUM LOCK veya SCROLL LOCK gibi etkinleştirildiğini kullanıcılar sinyal ya da tarih veya saat kullanışlı bir başvuru olarak sağlamak için ortak bir yoludur.</span><span class="sxs-lookup"><span data-stu-id="fac38-105">This is a common way to signal users that keys such as the CAPS LOCK, NUM LOCK, or SCROLL LOCK are enabled, or to provide the date or a clock as a convenient reference.</span></span>  
  
 <span data-ttu-id="fac38-106">Aşağıdaki örnekte, bir örneğini kullanacağınız <xref:System.Windows.Forms.StatusBarPanel> saat barındırmak için sınıf.</span><span class="sxs-lookup"><span data-stu-id="fac38-106">In the following example, you will use an instance of the <xref:System.Windows.Forms.StatusBarPanel> class to host a clock.</span></span>  
  
### <a name="to-get-the-status-bar-ready-for-updating"></a><span data-ttu-id="fac38-107">Durum çubuğu güncelleştirmek için hazır hale getirmek için</span><span class="sxs-lookup"><span data-stu-id="fac38-107">To get the status bar ready for updating</span></span>  
  
1. <span data-ttu-id="fac38-108">Yeni bir Windows formu oluşturun.</span><span class="sxs-lookup"><span data-stu-id="fac38-108">Create a new Windows form.</span></span>  
  
2. <span data-ttu-id="fac38-109">Ekleme bir <xref:System.Windows.Forms.StatusBar> form denetimi.</span><span class="sxs-lookup"><span data-stu-id="fac38-109">Add a <xref:System.Windows.Forms.StatusBar> control to your form.</span></span> <span data-ttu-id="fac38-110">Ayrıntılar için bkz [nasıl yapılır: Windows Forms'a denetimler ekleme](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="fac38-110">For details, see [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
3. <span data-ttu-id="fac38-111">Bir durum çubuğu paneline eklemek, <xref:System.Windows.Forms.StatusBar> denetimi.</span><span class="sxs-lookup"><span data-stu-id="fac38-111">Add a status bar panel to your <xref:System.Windows.Forms.StatusBar> control.</span></span> <span data-ttu-id="fac38-112">Ayrıntılar için bkz [nasıl yapılır: Bir StatusBar denetimine panel ekleme](how-to-add-panels-to-a-statusbar-control.md).</span><span class="sxs-lookup"><span data-stu-id="fac38-112">For details, see [How to: Add Panels to a StatusBar Control](how-to-add-panels-to-a-statusbar-control.md).</span></span>  
  
4. <span data-ttu-id="fac38-113">İçin <xref:System.Windows.Forms.StatusBar> formunuza, eklediğiniz denetimi ayarlama <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> özelliğini `true`.</span><span class="sxs-lookup"><span data-stu-id="fac38-113">For the <xref:System.Windows.Forms.StatusBar> control you added to your form, set the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true`.</span></span>  
  
5. <span data-ttu-id="fac38-114">Bir Windows Forms ekleme <xref:System.Windows.Forms.Timer> forma bileşen.</span><span class="sxs-lookup"><span data-stu-id="fac38-114">Add a Windows Forms <xref:System.Windows.Forms.Timer> component to the form.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fac38-115">Windows Forms <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> bileşeni, bir Windows Forms ortamı için tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="fac38-115">The Windows Forms <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="fac38-116">Bir sunucu ortamı için uygun olan bir zamanlayıcı gerekirse bkz [sunucu tabanlı zamanlayıcılar giriş](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="fac38-116">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
6. <span data-ttu-id="fac38-117">Ayarlama <xref:System.Windows.Forms.Timer.Enabled%2A> özelliğini `true`.</span><span class="sxs-lookup"><span data-stu-id="fac38-117">Set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true`.</span></span>  
  
7. <span data-ttu-id="fac38-118">Ayarlama <xref:System.Windows.Forms.Timer.Interval%2A> özelliği <xref:System.Windows.Forms.Timer> 30000 için.</span><span class="sxs-lookup"><span data-stu-id="fac38-118">Set the <xref:System.Windows.Forms.Timer.Interval%2A> property of the <xref:System.Windows.Forms.Timer> to 30000.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fac38-119"><xref:System.Windows.Forms.Timer.Interval%2A> Özelliği <xref:System.Windows.Forms.Timer> bileşeni doğru bir zaman görüntülenen saat yansıtılmasını sağlamak üzere 30 saniye (30.000 milisaniye cinsinden) ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="fac38-119">The <xref:System.Windows.Forms.Timer.Interval%2A> property of the <xref:System.Windows.Forms.Timer> component is set to 30 seconds (30,000 milliseconds) to ensure that an accurate time is reflected in the time displayed.</span></span>  
  
### <a name="to-implement-the-timer-to-update-the-status-bar"></a><span data-ttu-id="fac38-120">Durum çubuğunu güncellemek için Zamanlayıcıyı uygulamak için</span><span class="sxs-lookup"><span data-stu-id="fac38-120">To implement the timer to update the status bar</span></span>  
  
1. <span data-ttu-id="fac38-121">Olay işleyicisi aşağıdaki kodu ekleyin <xref:System.Windows.Forms.Timer> panelini güncelleştirmek için bileşen <xref:System.Windows.Forms.StatusBar> denetimi.</span><span class="sxs-lookup"><span data-stu-id="fac38-121">Insert the following code into the event handler of the <xref:System.Windows.Forms.Timer> component to update the panel of the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
    ```vb  
    Private Sub Timer1_Tick(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
       StatusBar1.Panels(0).Text = Now.ToShortTimeString  
    End Sub  
    ```  
  
    ```csharp  
    private void timer1_Tick(object sender, System.EventArgs e)  
    {  
       statusBar1.Panels[0].Text = DateTime.Now.ToShortTimeString();  
    }  
    ```  
  
    ```cpp  
    private:  
      System::Void timer1_Tick(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        statusBar1->Panels[0]->Text =  
          DateTime::Now.ToShortTimeString();  
      }  
    ```  
  
     <span data-ttu-id="fac38-122">Bu noktada, uygulamayı çalıştırmak ve durum çubuğu panelinde çalıştıran saat gözlemek hazır olursunuz.</span><span class="sxs-lookup"><span data-stu-id="fac38-122">At this point, you are ready to run the application and observe the clock running in the status bar panel.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="fac38-123">Uygulamayı test etmek için</span><span class="sxs-lookup"><span data-stu-id="fac38-123">To test the application</span></span>  
  
1. <span data-ttu-id="fac38-124">Uygulamada hata ayıklamak ve çalıştırmak için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="fac38-124">Debug the application and press F5 to run it.</span></span> <span data-ttu-id="fac38-125">Hata ayıklama hakkında daha fazla ayrıntı için bkz. [Visual Studio'da hata ayıklama](/visualstudio/debugger/debugging-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="fac38-125">For details about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fac38-126">Yaklaşık olarak 30 durum çubuğunda görüntülenecek saniye saat sürer.</span><span class="sxs-lookup"><span data-stu-id="fac38-126">It will take approximately 30 seconds for the clock to appear in the status bar.</span></span> <span data-ttu-id="fac38-127">Olası en doğru zamanı elde etmek için budur.</span><span class="sxs-lookup"><span data-stu-id="fac38-127">This is to get the most accurate time possible.</span></span> <span data-ttu-id="fac38-128">Buna karşılık, daha kısa süre içinde görünen saati hale getirmek için değerini azaltabilirsiniz <xref:System.Windows.Forms.Timer.Interval%2A> ayarlanan önceki yordamdaki adım 7'deki özelliği.</span><span class="sxs-lookup"><span data-stu-id="fac38-128">Conversely, to make the clock appear sooner, you can reduce the value of the <xref:System.Windows.Forms.Timer.Interval%2A> property you set in step 7 in the previous procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fac38-129">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="fac38-129">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="fac38-130">Nasıl yapılır: Bir StatusBar Denetimine Panel Ekleme</span><span class="sxs-lookup"><span data-stu-id="fac38-130">How to: Add Panels to a StatusBar Control</span></span>](how-to-add-panels-to-a-statusbar-control.md)
- [<span data-ttu-id="fac38-131">Nasıl yapılır: Windows Forms StatusBar Denetiminde Hangi Panele Tıklandığını Belirleme</span><span class="sxs-lookup"><span data-stu-id="fac38-131">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)
- [<span data-ttu-id="fac38-132">StatusBar Denetimine Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="fac38-132">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)
