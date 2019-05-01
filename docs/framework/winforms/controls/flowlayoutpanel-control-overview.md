---
title: FlowLayoutPanel Denetimine Genel Bakış
ms.date: 03/30/2017
f1_keywords:
- FlowLayoutPanel
helpviewer_keywords:
- forms [Windows Forms], dynamic layout
- layout [Windows Forms], dynamic
- Windows Forms, dynamic layout
- FlowLayoutPanel control [Windows Forms], about FlowLayoutPanel control
ms.assetid: 3883e024-f5a0-456d-9c27-b4dfa1cc9045
ms.openlocfilehash: 260146cd901fe2b80a73c01060ccd55958cd169e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011326"
---
# <a name="flowlayoutpanel-control-overview"></a><span data-ttu-id="79885-102">FlowLayoutPanel Denetimine Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="79885-102">FlowLayoutPanel Control Overview</span></span>
<span data-ttu-id="79885-103"><xref:System.Windows.Forms.FlowLayoutPanel> Denetim akışı yatay veya dikey yönde içeriği düzenler.</span><span class="sxs-lookup"><span data-stu-id="79885-103">The <xref:System.Windows.Forms.FlowLayoutPanel> control arranges its contents in a horizontal or vertical flow direction.</span></span> <span data-ttu-id="79885-104">Denetimin içeriği sonraki bir satır veya sonraki bir sütun sarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="79885-104">You can wrap the control's contents from one row to the next, or from one column to the next.</span></span> <span data-ttu-id="79885-105">Alternatif olarak, içeriği kaydırmayı yerine bölebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="79885-105">Alternately, you can clip instead of wrap its contents.</span></span>  
  
 <span data-ttu-id="79885-106">Akış yönü değerini ayarlayarak belirtebilirsiniz <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="79885-106">You can specify the flow direction by setting the value of the <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> property.</span></span> <span data-ttu-id="79885-107"><xref:System.Windows.Forms.FlowLayoutPanel> Denetimi doğru şekilde akış yönünü sağdan sola (RTL) düzeni tersine çevirir.</span><span class="sxs-lookup"><span data-stu-id="79885-107">The <xref:System.Windows.Forms.FlowLayoutPanel> control correctly reverses its flow direction in Right-to-Left (RTL) layouts.</span></span> <span data-ttu-id="79885-108">Belirtebilirsiniz olmadığını <xref:System.Windows.Forms.FlowLayoutPanel> denetimin içeriği sarmalanmış veya değerini ayarlayarak kırpılarak <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="79885-108">You can also specify whether the <xref:System.Windows.Forms.FlowLayoutPanel> control's contents are wrapped or clipped by setting the value of the <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A> property.</span></span>  
  
 <span data-ttu-id="79885-109"><xref:System.Windows.Forms.FlowLayoutPanel> Ayarladığınızda boyutları için içeriği otomatik olarak Denetim <xref:System.Windows.Forms.Control.AutoSize%2A> özelliğini `true`.</span><span class="sxs-lookup"><span data-stu-id="79885-109">The <xref:System.Windows.Forms.FlowLayoutPanel> control automatically sizes to its contents when you set the <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span> <span data-ttu-id="79885-110">Ayrıca sağlar bir **FlowBreak** özelliğini, alt denetimlerini.</span><span class="sxs-lookup"><span data-stu-id="79885-110">It also provides a **FlowBreak** property to its child controls.</span></span> <span data-ttu-id="79885-111">FlowBreak özelliğin değerini ayarlamak `true` neden <xref:System.Windows.Forms.FlowLayoutPanel> sonraki satır veya sütun kaydırılır ve geçerli akış yönü denetimlerinde düzenlemeyi durdurmak için denetimi.</span><span class="sxs-lookup"><span data-stu-id="79885-111">Setting the value of the FlowBreak property to `true` causes the <xref:System.Windows.Forms.FlowLayoutPanel> control to stop laying out controls in the current flow direction and wrap to the next row or column.</span></span>  
  
 <span data-ttu-id="79885-112">Herhangi bir Windows Forms denetimini bir alt öğesi olabilir <xref:System.Windows.Forms.FlowLayoutPanel> denetim, diğer örnekleri dahil <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="79885-112">Any Windows Forms control can be a child of the <xref:System.Windows.Forms.FlowLayoutPanel> control, including other instances of <xref:System.Windows.Forms.FlowLayoutPanel>.</span></span> <span data-ttu-id="79885-113">Bu özellik sayesinde, çalışma zamanında formunuzun boyutlarına uyum karmaşık düzenler oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="79885-113">With this capability, you can construct sophisticated layouts that adapt to your form's dimensions at run time.</span></span>  
  
 <span data-ttu-id="79885-114">Ayrıca bkz: [izlenecek yol: FlowLayoutPanel kullanarak Windows Forms'da denetimleri düzenleme](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).</span><span class="sxs-lookup"><span data-stu-id="79885-114">Also see [Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79885-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="79885-115">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="79885-116">FlowLayoutPanel Denetimi</span><span class="sxs-lookup"><span data-stu-id="79885-116">FlowLayoutPanel Control</span></span>](flowlayoutpanel-control-windows-forms.md)
