---
title: 'Nasıl yapılır: Windows Forms DataGridView denetiminde sanal modu uygulama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode
- DataGridView control [Windows Forms], large data sets
ms.assetid: 98236267-f08e-4918-bcf9-77acf050a3ca
ms.openlocfilehash: 7ece3dd8c5f0e56c335c85d72030f1b9aa56e33b
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2019
ms.locfileid: "56260991"
---
# <a name="how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="3f2d3-102">Nasıl yapılır: Windows Forms DataGridView denetiminde sanal modu uygulama</span><span class="sxs-lookup"><span data-stu-id="3f2d3-102">How to: Implement Virtual Mode in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="3f2d3-103">Aşağıdaki kod örneği, veri kullanımının büyük kümelerini yönetmek gösterilmiştir bir <xref:System.Windows.Forms.DataGridView> denetimini kendi <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> özelliğini `true`.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-103">The following code example demonstrates how to manage large sets of data using a <xref:System.Windows.Forms.DataGridView> control with its <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property set to `true`.</span></span>  
  
 <span data-ttu-id="3f2d3-104">Bu kod örneği tam bir açıklaması için bkz. [izlenecek yol: Sanal modu uygulama içinde Windows Forms DataGridView denetiminde](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="3f2d3-104">For a complete explanation of this code example, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f2d3-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="3f2d3-105">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#000](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#000)]
 [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3f2d3-106">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="3f2d3-106">Compiling the Code</span></span>  
 <span data-ttu-id="3f2d3-107">Bu örnek gerektirir:</span><span class="sxs-lookup"><span data-stu-id="3f2d3-107">This example requires:</span></span>  
  
-   <span data-ttu-id="3f2d3-108">Sistem ve System.Windows.Forms öğelerini derlemelerine başvurular.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-108">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="3f2d3-109">Visual Basic veya Visual C# için bu örnek komut satırından derleme hakkında daha fazla bilgi için bkz: [komut satırından derleme](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) veya [oluşturma ile komut satırı csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="3f2d3-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="3f2d3-110">Visual Studio bu örnekte yeni bir projeye kod yapıştırarak da oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f2d3-111">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="3f2d3-111">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [<span data-ttu-id="3f2d3-112">İzlenecek yol: Windows Forms DataGridView denetiminde sanal modu uygulama</span><span class="sxs-lookup"><span data-stu-id="3f2d3-112">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)
- [<span data-ttu-id="3f2d3-113">Windows Forms DataGridView Denetiminde Performans Ayarlaması</span><span class="sxs-lookup"><span data-stu-id="3f2d3-113">Performance Tuning in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="3f2d3-114">Windows Forms DataGridView Denetiminde Sanal Mod</span><span class="sxs-lookup"><span data-stu-id="3f2d3-114">Virtual Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)
