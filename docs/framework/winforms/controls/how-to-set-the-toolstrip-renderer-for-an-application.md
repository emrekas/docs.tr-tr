---
title: 'Nasıl yapılır: Bir uygulama için ToolStrip oluşturucusunu ayarlama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Renderer property [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], customizing
ms.assetid: 46acef3e-9844-4ae8-9a2e-3006fe99cadf
ms.openlocfilehash: 1b07f9f7ef8e06263ea3aaa5626e6ab5cba1d82c
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2019
ms.locfileid: "56260874"
---
# <a name="how-to-set-the-toolstrip-renderer-for-an-application"></a><span data-ttu-id="330dc-102">Nasıl yapılır: Bir uygulama için ToolStrip oluşturucusunu ayarlama</span><span class="sxs-lookup"><span data-stu-id="330dc-102">How to: Set the ToolStrip Renderer for an Application</span></span>
<span data-ttu-id="330dc-103">Görünümünü özelleştirebilirsiniz, <xref:System.Windows.Forms.ToolStrip> denetimleri tek tek veya tüm <xref:System.Windows.Forms.ToolStrip> denetimleri, uygulamanızda.</span><span class="sxs-lookup"><span data-stu-id="330dc-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> controls individually or for all the <xref:System.Windows.Forms.ToolStrip> controls in your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="330dc-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="330dc-104">Example</span></span>  
 <span data-ttu-id="330dc-105">Aşağıdaki kod örneği için özel Oluşturucu seçmeli olarak uygulamak gösterilmiştir bir <xref:System.Windows.Forms.ToolStrip> denetimi ve bir <xref:System.Windows.Forms.MenuStrip> denetimi.</span><span class="sxs-lookup"><span data-stu-id="330dc-105">The following code example demonstrates how to selectively apply a custom renderer to a <xref:System.Windows.Forms.ToolStrip> control and a <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="330dc-106">Bu kod örneği kullanmak için derlemek ve uygulamayı çalıştırın ve ardından gelen özel Perforator kapsamını seçin <xref:System.Windows.Forms.ComboBox> denetimi.</span><span class="sxs-lookup"><span data-stu-id="330dc-106">To use this code example, compile and run the application, and then select the scope of the custom rending from the <xref:System.Windows.Forms.ComboBox> control.</span></span> <span data-ttu-id="330dc-107">Tıklayın **Uygula** Oluşturucu ayarlamak için.</span><span class="sxs-lookup"><span data-stu-id="330dc-107">Click **Apply** to set the renderer.</span></span>  
  
 <span data-ttu-id="330dc-108">Özel menü öğesi işleme görmek için seçin <xref:System.Windows.Forms.MenuStrip> seçeneğini <xref:System.Windows.Forms.ComboBox> tıklayın, Denetim **Uygula**ve ardından açın **dosya** menü öğesi.</span><span class="sxs-lookup"><span data-stu-id="330dc-108">To see custom menu item rendering, select the <xref:System.Windows.Forms.MenuStrip> option from the <xref:System.Windows.Forms.ComboBox> control, click **Apply**, and then open the **File** menu item.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#70](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#70)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#70](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#70)]  
  
 <span data-ttu-id="330dc-109">Ayarlama <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> özel Oluşturucu tümüne uygulamak için özellik <xref:System.Windows.Forms.ToolStrip> denetimleri, uygulamanızda.</span><span class="sxs-lookup"><span data-stu-id="330dc-109">Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to apply a custom renderer to all the <xref:System.Windows.Forms.ToolStrip> controls in your application.</span></span>  
  
 <span data-ttu-id="330dc-110">Ayarlama <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> özel Oluşturucu için bireysel uygulamak için özellik <xref:System.Windows.Forms.ToolStrip> denetimi.</span><span class="sxs-lookup"><span data-stu-id="330dc-110">Set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to apply a custom renderer to an individual <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="330dc-111">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="330dc-111">Compiling the Code</span></span>  
 <span data-ttu-id="330dc-112">Bu örnek gerektirir:</span><span class="sxs-lookup"><span data-stu-id="330dc-112">This example requires:</span></span>  
  
-   <span data-ttu-id="330dc-113">System.Windows.Forms System.Design ve System.Drawing derlemelerine başvurular.</span><span class="sxs-lookup"><span data-stu-id="330dc-113">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="330dc-114">Visual Basic veya Visual C# için bu örnek komut satırından derleme hakkında daha fazla bilgi için bkz: [komut satırından derleme](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) veya [oluşturma ile komut satırı csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="330dc-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="330dc-115">Visual Studio bu örnekte yeni bir projeye kod yapıştırarak da oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="330dc-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="330dc-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="330dc-116">See also</span></span>
- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- [<span data-ttu-id="330dc-117">ToolStrip Denetimi</span><span class="sxs-lookup"><span data-stu-id="330dc-117">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
