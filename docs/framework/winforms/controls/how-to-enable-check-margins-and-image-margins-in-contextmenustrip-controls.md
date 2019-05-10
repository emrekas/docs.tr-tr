---
title: 'Nasıl yapılır: ContextMenuStrip Denetimlerinde Denetim Kenar Boşluklarını ve Resim Kenar Boşluklarını Etkinleştirme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ShowCheckMargin property [Windows Forms]
- ShowImageMargin property [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: eb584e71-59da-4012-aaca-dbe1c7c7a156
ms.openlocfilehash: dd926a3311ab6fd181dc0acc7e2573c60d2536bb
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651720"
---
# <a name="how-to-enable-check-margins-and-image-margins-in-contextmenustrip-controls"></a><span data-ttu-id="65526-102">Nasıl yapılır: ContextMenuStrip Denetimlerinde Denetim Kenar Boşluklarını ve Resim Kenar Boşluklarını Etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="65526-102">How to: Enable Check Margins and Image Margins in ContextMenuStrip Controls</span></span>
<span data-ttu-id="65526-103">Özelleştirebileceğiniz <xref:System.Windows.Forms.ToolStripMenuItem> nesneler, <xref:System.Windows.Forms.MenuStrip> denetimiyle onay işaretleri ve özel görüntüler.</span><span class="sxs-lookup"><span data-stu-id="65526-103">You can customize the <xref:System.Windows.Forms.ToolStripMenuItem> objects in your <xref:System.Windows.Forms.MenuStrip> control with check marks and custom images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65526-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="65526-104">Example</span></span>  
 <span data-ttu-id="65526-105">Aşağıdaki kod örneği, onay işaretleri ve özel görüntüleri menü öğelerinin nasıl oluşturulacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="65526-105">The following code example demonstrates how to create menu items that have check marks and custom images.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#60)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#60)]  
  
 <span data-ttu-id="65526-106">Ayarlama <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A?displayProperty=nameWithType> ve <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A?displayProperty=nameWithType> onay işaretleri ve özel görüntüler, menü öğelerinde görüntülenirken belirtmek için özellikleri.</span><span class="sxs-lookup"><span data-stu-id="65526-106">Set the <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A?displayProperty=nameWithType> properties to specify when check marks and custom images appear in your menu items.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="65526-107">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="65526-107">Compiling the Code</span></span>  
 <span data-ttu-id="65526-108">Bu örnek gerektirir:</span><span class="sxs-lookup"><span data-stu-id="65526-108">This example requires:</span></span>  
  
- <span data-ttu-id="65526-109">System.Windows.Forms System.Design ve System.Drawing derlemelerine başvurular.</span><span class="sxs-lookup"><span data-stu-id="65526-109">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="65526-110">Visual Basic veya Visual C# için bu örnek komut satırından derleme hakkında daha fazla bilgi için bkz: [komut satırından derleme](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) veya [oluşturma ile komut satırı csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="65526-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="65526-111">Visual Studio bu örnekte yeni bir projeye kod yapıştırarak da oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="65526-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65526-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="65526-112">See also</span></span>

- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripDropDownMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="65526-113">ToolStrip Denetimi</span><span class="sxs-lookup"><span data-stu-id="65526-113">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
