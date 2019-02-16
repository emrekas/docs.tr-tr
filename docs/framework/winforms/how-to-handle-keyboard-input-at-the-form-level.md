---
title: 'Nasıl yapılır: Klavye girdisini Form düzeyinde işleme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboard input [Windows Forms], at form level
- Windows Forms, handling keyboard input
- keyboards [Windows Forms], form-level input
ms.assetid: d7f8b390-dc91-42d2-ae0f-2ffa388127ad
ms.openlocfilehash: bf8c0f37d8a55e37680ea20bf071b02725a201ff
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/16/2019
ms.locfileid: "56332799"
---
# <a name="how-to-handle-keyboard-input-at-the-form-level"></a><span data-ttu-id="9b486-102">Nasıl yapılır: Klavye girdisini Form düzeyinde işleme</span><span class="sxs-lookup"><span data-stu-id="9b486-102">How to: Handle Keyboard Input at the Form Level</span></span>
<span data-ttu-id="9b486-103">Windows Forms Denetim iletileri ulaşmadan önce klavye iletileri form düzeyinde işleme yeteneği sağlar.</span><span class="sxs-lookup"><span data-stu-id="9b486-103">Windows Forms provides the ability to handle keyboard messages at the form level, before the messages reach a control.</span></span> <span data-ttu-id="9b486-104">Bu konu, bu görevi nasıl gerçekleştireceğinizi gösterir.</span><span class="sxs-lookup"><span data-stu-id="9b486-104">This topic shows how to accomplish this task.</span></span>  
  
### <a name="to-handle-a-keyboard-message-at-the-form-level"></a><span data-ttu-id="9b486-105">Bir klavye iletisi form düzeyinde işlemek için</span><span class="sxs-lookup"><span data-stu-id="9b486-105">To handle a keyboard message at the form level</span></span>  
  
-   <span data-ttu-id="9b486-106">İşlemek <xref:System.Windows.Forms.Control.KeyPress> veya <xref:System.Windows.Forms.Control.KeyDown> olay başlangıç formu ve kümesi <xref:System.Windows.Forms.Form.KeyPreview%2A> özellik formun `true` böylece form üzerinde herhangi bir denetim ulaşmadan önce klavye iletiler form tarafından alınır.</span><span class="sxs-lookup"><span data-stu-id="9b486-106">Handle the <xref:System.Windows.Forms.Control.KeyPress> or <xref:System.Windows.Forms.Control.KeyDown> event of the startup form, and set the <xref:System.Windows.Forms.Form.KeyPreview%2A> property of the form to `true` so that keyboard messages are received by the form before they reach any controls on the form.</span></span> <span data-ttu-id="9b486-107">Aşağıdaki kod örneği tanıtıcıları <xref:System.Windows.Forms.Control.KeyPress> tüm sayı tuşları algılama ve '1', '4' ve '7' kullanan olay.</span><span class="sxs-lookup"><span data-stu-id="9b486-107">The following code example handles the <xref:System.Windows.Forms.Control.KeyPress> event by detecting all of the number keys and consuming '1', '4', and '7'.</span></span>  
  
     [!code-cpp[System.Windows.Forms.KeyboardInputForm#10](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/cpp/form1.cpp#10)]
     [!code-csharp[System.Windows.Forms.KeyboardInputForm#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/CS/form1.cs#10)]
     [!code-vb[System.Windows.Forms.KeyboardInputForm#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/VB/form1.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="9b486-108">Örnek</span><span class="sxs-lookup"><span data-stu-id="9b486-108">Example</span></span>  
 <span data-ttu-id="9b486-109">Aşağıdaki kod örneği, yukarıdaki örnek için tüm uygulamasıdır.</span><span class="sxs-lookup"><span data-stu-id="9b486-109">The following code example is the entire application for the above example.</span></span> <span data-ttu-id="9b486-110">Uygulama içeren bir <xref:System.Windows.Forms.TextBox> odağı Taşı olanak tanıyan çeşitli diğer denetimler birlikte <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="9b486-110">The application includes a <xref:System.Windows.Forms.TextBox> along with several other controls that allow you to move focus from the <xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="9b486-111"><xref:System.Windows.Forms.Control.KeyPress> Ana olay <xref:System.Windows.Forms.Form> '1', '4' ve '7', tüketir ve <xref:System.Windows.Forms.Control.KeyPress> olayı <xref:System.Windows.Forms.TextBox> '2', '5' ve '8' kalan anahtarlar görüntülenirken kullanır.</span><span class="sxs-lookup"><span data-stu-id="9b486-111">The <xref:System.Windows.Forms.Control.KeyPress> event of the main <xref:System.Windows.Forms.Form> consumes '1', '4', and '7', and the <xref:System.Windows.Forms.Control.KeyPress> event of the <xref:System.Windows.Forms.TextBox> consumes '2', '5', and '8' while displaying the remaining keys.</span></span> <span data-ttu-id="9b486-112">Karşılaştırma <xref:System.Windows.Forms.MessageBox> sayı anahtar biraz bastığınızda çıkış <xref:System.Windows.Forms.TextBox> ile odaklı <xref:System.Windows.Forms.MessageBox> diğer denetimlerden birini odak modundayken bir sayı tuşuna bastığınızda çıktı.</span><span class="sxs-lookup"><span data-stu-id="9b486-112">Compare the <xref:System.Windows.Forms.MessageBox> output when you press a number key while the <xref:System.Windows.Forms.TextBox> has focus with the <xref:System.Windows.Forms.MessageBox> output when you press a number key while focus is on one of the other controls.</span></span>  
  
 [!code-cpp[System.Windows.Forms.KeyBoardInputForm#0](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.KeyBoardInputForm#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.KeyBoardInputForm#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9b486-113">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="9b486-113">Compiling the Code</span></span>  
 <span data-ttu-id="9b486-114">Bu örnek gerektirir:</span><span class="sxs-lookup"><span data-stu-id="9b486-114">This example requires:</span></span>  
  
-   <span data-ttu-id="9b486-115">Sistem, System.Drawing ve System.Windows.Forms öğelerini derlemelerine başvurular.</span><span class="sxs-lookup"><span data-stu-id="9b486-115">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="9b486-116">Visual Basic veya Visual C# için bu örnek komut satırından derleme hakkında daha fazla bilgi için bkz: [komut satırından derleme](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) veya [oluşturma ile komut satırı csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="9b486-116">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="9b486-117">Visual Studio bu örnekte yeni bir projeye kod yapıştırarak da oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9b486-117">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  

## <a name="see-also"></a><span data-ttu-id="9b486-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="9b486-118">See also</span></span>
- [<span data-ttu-id="9b486-119">Bir Windows Forms Uygulamasında Klavye Girdisi</span><span class="sxs-lookup"><span data-stu-id="9b486-119">Keyboard Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)
