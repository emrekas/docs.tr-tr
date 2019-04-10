---
title: 'Nasıl yapılır: Standart bir Denetimde Klavye Girdisini Değiştirme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyboard input [Windows Forms], modifying
- modifying keyboard input
- Windows Forms, modifying keyboard input
- keyboards [Windows Forms], keyboard input
ms.assetid: 626d3712-d866-4988-bcda-a2d5b36ec0ba
ms.openlocfilehash: 81d33234670fb8ae5445cc86a79f5c3b6a647a03
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225787"
---
# <a name="how-to-modify-keyboard-input-to-a-standard-control"></a><span data-ttu-id="9f225-102">Nasıl yapılır: Standart bir Denetimde Klavye Girdisini Değiştirme</span><span class="sxs-lookup"><span data-stu-id="9f225-102">How to: Modify Keyboard Input to a Standard Control</span></span>
<span data-ttu-id="9f225-103">Windows Forms, kullanma ve klavye girdisini değiştirme olanağı sağlar.</span><span class="sxs-lookup"><span data-stu-id="9f225-103">Windows Forms provides the ability to consume and modify keyboard input.</span></span> <span data-ttu-id="9f225-104">Bir anahtarı kullanan bir yöntem veya olay işleyicisi içindeki bir anahtar diğer yöntemleri ve olayları daha fazla ileti kuyruğu aşağı anahtar değerini alıyor musunuz böylece işlemeye ifade eder.</span><span class="sxs-lookup"><span data-stu-id="9f225-104">Consuming a key refers to handling a key within a method or event handler so that other methods and events further down the message queue do not receive the key value.</span></span> <span data-ttu-id="9f225-105">Bir anahtar değiştirme yöntemlerini ve olay işleyicileri daha fazla ileti kuyruğu aşağı farklı bir anahtar değeri alması için bunları bir anahtarın değerini değiştirmek için ifade eder.</span><span class="sxs-lookup"><span data-stu-id="9f225-105">Modifying a key refers to modifying the value of a key so that methods and event handlers further down the message queue receive a different key value.</span></span> <span data-ttu-id="9f225-106">Bu konu aşağıdaki görevlerin nasıl gerçekleştirileceğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="9f225-106">This topic shows how to accomplish these tasks.</span></span>  
  
### <a name="to-consume-a-key"></a><span data-ttu-id="9f225-107">Bir anahtar kullanmak için</span><span class="sxs-lookup"><span data-stu-id="9f225-107">To consume a key</span></span>  
  
-   <span data-ttu-id="9f225-108">İçinde bir <xref:System.Windows.Forms.Control.KeyPress> olay işleyicisini <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> özelliği <xref:System.Windows.Forms.KeyPressEventArgs> sınıfının `true`.</span><span class="sxs-lookup"><span data-stu-id="9f225-108">In a <xref:System.Windows.Forms.Control.KeyPress> event handler, set the <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> class to `true`.</span></span>  
  
     <span data-ttu-id="9f225-109">-veya-</span><span class="sxs-lookup"><span data-stu-id="9f225-109">-or-</span></span>  
  
     <span data-ttu-id="9f225-110">İçinde bir <xref:System.Windows.Forms.Control.KeyDown> olay işleyicisini <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> özelliği <xref:System.Windows.Forms.KeyEventArgs> sınıfının `true`.</span><span class="sxs-lookup"><span data-stu-id="9f225-110">In a <xref:System.Windows.Forms.Control.KeyDown> event handler, set the <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyEventArgs> class to `true`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9f225-111">Ayarı <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> özelliğinde <xref:System.Windows.Forms.Control.KeyDown> olay işleyicisi engellemez <xref:System.Windows.Forms.Control.KeyPress> ve <xref:System.Windows.Forms.Control.KeyUp> için geçerli bir tuş vuruşu gerçekleştirilen gelen olayları.</span><span class="sxs-lookup"><span data-stu-id="9f225-111">Setting the <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> property in the <xref:System.Windows.Forms.Control.KeyDown> event handler does not prevent the <xref:System.Windows.Forms.Control.KeyPress> and <xref:System.Windows.Forms.Control.KeyUp> events from being raised for the current keystroke.</span></span> <span data-ttu-id="9f225-112">Kullanım <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> bu amaç için özellik.</span><span class="sxs-lookup"><span data-stu-id="9f225-112">Use the <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> property for this purpose.</span></span>  
  
     <span data-ttu-id="9f225-113">Aşağıdaki örnek, kitabından bir `switch` inceler deyimi <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> özelliği <xref:System.Windows.Forms.KeyPressEventArgs> tarafından alınan bir <xref:System.Windows.Forms.Control.KeyPress> olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="9f225-113">The following example is an excerpt from a `switch` statement that examines the <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> received by a <xref:System.Windows.Forms.Control.KeyPress> event handler.</span></span> <span data-ttu-id="9f225-114">Bu kod, 'A' ve 'bir' karakter anahtarları kullanır.</span><span class="sxs-lookup"><span data-stu-id="9f225-114">This code consumes the 'A' and 'a' character keys.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#6)]  
  
### <a name="to-modify-a-standard-character-key"></a><span data-ttu-id="9f225-115">Bir standart karakter anahtarı değiştirmek için</span><span class="sxs-lookup"><span data-stu-id="9f225-115">To modify a standard character key</span></span>  
  
-   <span data-ttu-id="9f225-116">İçinde bir <xref:System.Windows.Forms.Control.KeyPress> olay işleyicisini <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> özelliği <xref:System.Windows.Forms.KeyPressEventArgs> yeni karakter anahtar değerine sınıfı.</span><span class="sxs-lookup"><span data-stu-id="9f225-116">In a <xref:System.Windows.Forms.Control.KeyPress> event handler, set the <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> class to the value of the new character key.</span></span>  
  
     <span data-ttu-id="9f225-117">Aşağıdaki örnek, kitabından bir `switch` değiştirir 'A', ' B' deyimi ve 'a', ' b'.</span><span class="sxs-lookup"><span data-stu-id="9f225-117">The following example is an excerpt from a `switch` statement that modifies 'B' to 'A' and 'b' to 'a'.</span></span> <span data-ttu-id="9f225-118">Unutmayın <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> özelliği <xref:System.Windows.Forms.KeyPressEventArgs> parametrenin ayarlanmış `false`, böylece yeni bir anahtar değeri diğer yöntemler ve olaylar ileti sırasına yayılır.</span><span class="sxs-lookup"><span data-stu-id="9f225-118">Note that the <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> parameter is set to `false`, so that the new key value is propagated to other methods and events in the message queue.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#7)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#7)]  
  
### <a name="to-modify-a-noncharacter-key"></a><span data-ttu-id="9f225-119">Karakter olmayan bir anahtarı değiştirmek için</span><span class="sxs-lookup"><span data-stu-id="9f225-119">To modify a noncharacter key</span></span>  
  
-   <span data-ttu-id="9f225-120">Geçersiz bir <xref:System.Windows.Forms.Control> Windows iletileri işleyen yöntem WM_KEYDOWN veya WM_SYSKEYDOWN ileti algılayın ve ayarlama <xref:System.Windows.Forms.Message.WParam%2A> özelliği <xref:System.Windows.Forms.Message> parametresi <xref:System.Windows.Forms.Keys> yeni karakter olmayan anahtar gösteren bir değer.</span><span class="sxs-lookup"><span data-stu-id="9f225-120">Override a <xref:System.Windows.Forms.Control> method that processes Windows messages, detect the WM_KEYDOWN or WM_SYSKEYDOWN message, and set the <xref:System.Windows.Forms.Message.WParam%2A> property of the <xref:System.Windows.Forms.Message> parameter to the <xref:System.Windows.Forms.Keys> value that represents the new noncharacter key.</span></span>  
  
     <span data-ttu-id="9f225-121">Aşağıdaki kod örneğinde nasıl geçersiz kılınacağını gösterir <xref:System.Windows.Forms.Control.PreProcessMessage%2A> yöntemi F9 F1 anahtarlarıyla algılamak ve tüm F3 tuşuna F1 değiştirmek için bir denetim.</span><span class="sxs-lookup"><span data-stu-id="9f225-121">The following code example demonstrates how to override the <xref:System.Windows.Forms.Control.PreProcessMessage%2A> method of a control to detect keys F1 through F9 and modify any F3 key press to F1.</span></span> <span data-ttu-id="9f225-122">Daha fazla bilgi için <xref:System.Windows.Forms.Control> klavye iletileri izlemesine kılabilirsiniz yöntemlerini [bir Windows Forms uygulamasında kullanıcı girişi](user-input-in-a-windows-forms-application.md) ve [nasıl klavye girişi çalışır](how-keyboard-input-works.md).</span><span class="sxs-lookup"><span data-stu-id="9f225-122">For more information on <xref:System.Windows.Forms.Control> methods that you can override to intercept keyboard messages, see [User Input in a Windows Forms Application](user-input-in-a-windows-forms-application.md) and [How Keyboard Input Works](how-keyboard-input-works.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#12)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="9f225-123">Örnek</span><span class="sxs-lookup"><span data-stu-id="9f225-123">Example</span></span>  
 <span data-ttu-id="9f225-124">Aşağıdaki kod örneği, önceki bölümlerde kod örnekleri için tam uygulamasıdır.</span><span class="sxs-lookup"><span data-stu-id="9f225-124">The following code example is the complete application for the code examples in the previous sections.</span></span> <span data-ttu-id="9f225-125">Öğesinden türetilen özel bir denetim uygulamanın kullandığı <xref:System.Windows.Forms.TextBox> kullanma ve klavye girdisini değiştirme sınıfı.</span><span class="sxs-lookup"><span data-stu-id="9f225-125">The application uses a custom control derived from the <xref:System.Windows.Forms.TextBox> class to consume and modify keyboard input.</span></span>  
  
 [!code-csharp[System.Windows.Forms.KeyBoardInput#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.KeyBoardInput#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9f225-126">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="9f225-126">Compiling the Code</span></span>  
 <span data-ttu-id="9f225-127">Bu örnek gerektirir:</span><span class="sxs-lookup"><span data-stu-id="9f225-127">This example requires:</span></span>  
  
-   <span data-ttu-id="9f225-128">Sistem, System.Drawing ve System.Windows.Forms öğelerini derlemelerine başvurular.</span><span class="sxs-lookup"><span data-stu-id="9f225-128">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="9f225-129">Visual Basic veya Visual C# için bu örnek komut satırından derleme hakkında daha fazla bilgi için bkz: [komut satırından derleme](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) veya [oluşturma ile komut satırı csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="9f225-129">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="9f225-130">Visual Studio bu örnekte yeni bir projeye kod yapıştırarak da oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9f225-130">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f225-131">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="9f225-131">See also</span></span>

- [<span data-ttu-id="9f225-132">Bir Windows Forms Uygulamasında Klavye Girdisi</span><span class="sxs-lookup"><span data-stu-id="9f225-132">Keyboard Input in a Windows Forms Application</span></span>](keyboard-input-in-a-windows-forms-application.md)
- [<span data-ttu-id="9f225-133">Bir Windows Forms Uygulamasında Kullanıcı Girdisi</span><span class="sxs-lookup"><span data-stu-id="9f225-133">User Input in a Windows Forms Application</span></span>](user-input-in-a-windows-forms-application.md)
- [<span data-ttu-id="9f225-134">Klavye Girdisi Nasıl Çalışır</span><span class="sxs-lookup"><span data-stu-id="9f225-134">How Keyboard Input Works</span></span>](how-keyboard-input-works.md)
