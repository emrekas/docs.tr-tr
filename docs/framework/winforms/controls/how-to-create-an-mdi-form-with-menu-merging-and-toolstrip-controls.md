---
title: 'Nasıl yapılır: Menü birleştirme ve ToolStrip denetimleri içeren MDI formu oluşturma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 64992ed9-44af-4baf-b45f-863e6ab35711
ms.openlocfilehash: 6cbab3c588aa74809a7aef80ae6ffc4c3772069f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646022"
---
# <a name="how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="387e3-102">Nasıl yapılır: Menü birleştirme ve ToolStrip denetimleri içeren MDI formu oluşturma</span><span class="sxs-lookup"><span data-stu-id="387e3-102">How to: Create an MDI Form with Menu Merging and ToolStrip Controls</span></span>
<span data-ttu-id="387e3-103"><xref:System.Windows.Forms?displayProperty=nameWithType> Ad alanı birden çok belge arabirimi (MDI) uygulamaları destekler ve <xref:System.Windows.Forms.MenuStrip> denetimi, menü birleştirmeyi destekler.</span><span class="sxs-lookup"><span data-stu-id="387e3-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="387e3-104">MDI formları aynı zamanda <xref:System.Windows.Forms.ToolStrip> kontrol eder.</span><span class="sxs-lookup"><span data-stu-id="387e3-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="387e3-105">Visual Studio'da bu özellik için kapsamlı desteği yoktur.</span><span class="sxs-lookup"><span data-stu-id="387e3-105">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="387e3-106">Ayrıca bkz: [izlenecek yol: Menü birleştirme ve ToolStrip denetimleri içeren MDI formu oluşturma](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="387e3-106">Also see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="387e3-107">Örnek</span><span class="sxs-lookup"><span data-stu-id="387e3-107">Example</span></span>  
 <span data-ttu-id="387e3-108">Aşağıdaki kod örneğinde nasıl kullanılacağını gösterir <xref:System.Windows.Forms.ToolStripPanel> denetimleriyle MDI formu.</span><span class="sxs-lookup"><span data-stu-id="387e3-108">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="387e3-109">Formu ile alt menülerini birleştirme menüsünü de destekler.</span><span class="sxs-lookup"><span data-stu-id="387e3-109">The form also supports menu merging with child menus.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="387e3-110">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="387e3-110">Compiling the Code</span></span>  
 <span data-ttu-id="387e3-111">Bu kod örneği gerektirir:</span><span class="sxs-lookup"><span data-stu-id="387e3-111">This code example requires:</span></span>  
  
-   <span data-ttu-id="387e3-112">System.Drawing ve System.Windows.Forms öğelerini derlemelerine başvurular.</span><span class="sxs-lookup"><span data-stu-id="387e3-112">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="387e3-113">Visual Basic veya Visual C# için bu örnek komut satırından derleme hakkında daha fazla bilgi için bkz: [komut satırından derleme](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) veya [oluşturma ile komut satırı csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="387e3-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="387e3-114">Visual Studio bu örnekte yeni bir projeye kod yapıştırarak da oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="387e3-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="387e3-115">Ayrıca bkz [nasıl yapılır: Derleme ve Visual Studio kullanarak tam bir Windows Formları kod örneği çalıştırma](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="387e3-115">Also sssee [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="387e3-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="387e3-116">See also</span></span>
- [<span data-ttu-id="387e3-117">ToolStrip Denetimi</span><span class="sxs-lookup"><span data-stu-id="387e3-117">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
