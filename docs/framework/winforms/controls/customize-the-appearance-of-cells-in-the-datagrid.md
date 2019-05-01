---
title: 'Nasıl yapılır: Windows Forms DataGridView Denetiminde Hücrelerin Görünüşünü Özelleştirme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: 415cf18aa4cf01b151a414dbc26609af638a7af7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011478"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="2d145-102">Nasıl yapılır: Windows Forms DataGridView Denetiminde Hücrelerin Görünüşünü Özelleştirme</span><span class="sxs-lookup"><span data-stu-id="2d145-102">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2d145-103">İşleyerek herhangi bir hücreyi görünümünü özelleştirebilirsiniz <xref:System.Windows.Forms.DataGridView> denetimin <xref:System.Windows.Forms.DataGridView.CellPainting> olay.</span><span class="sxs-lookup"><span data-stu-id="2d145-103">You can customize the appearance of any cell by handling the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellPainting> event.</span></span> <span data-ttu-id="2d145-104">Ayıklayabilmeniz için <xref:System.Windows.Forms.DataGridView> denetimin <xref:System.Drawing.Graphics> gelen <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> özelliği <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="2d145-104">You can extract the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Drawing.Graphics> from the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span></span> <span data-ttu-id="2d145-105">Bu <xref:System.Drawing.Graphics>, tüm görünümünü etkileyebilir <xref:System.Windows.Forms.DataGridView> denetimidir, ancak genellikle Environment yalnızca şu anda boyanan hücre görünümünü etkileyebilir.</span><span class="sxs-lookup"><span data-stu-id="2d145-105">With this <xref:System.Drawing.Graphics>, you can affect the appearance of the entire <xref:System.Windows.Forms.DataGridView> control, but you will usually want to affect only the appearance of the cell that is currently being painted.</span></span> <span data-ttu-id="2d145-106"><xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> Özelliği <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> boyama işlemlerinizi şu anda boyanan hücreye sınırlamak sağlar.</span><span class="sxs-lookup"><span data-stu-id="2d145-106">The <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> enables you to restrict your painting operations to the cell that is currently being painted.</span></span>  
  
 <span data-ttu-id="2d145-107">Aşağıdaki kod örneği, tüm hücreleri boyama bir `ContactName` sütun kullanarak <xref:System.Windows.Forms.DataGridView> denetimin renk şeması.</span><span class="sxs-lookup"><span data-stu-id="2d145-107">In the following code example, you will paint all the cells in a `ContactName` column using the <xref:System.Windows.Forms.DataGridView> control's color scheme.</span></span> <span data-ttu-id="2d145-108">Her hücrenin metin içeriği içinde boyanır <xref:System.Drawing.Color.Crimson%2A>, ve bir iç dikdörtgen aynı renkte çizilir <xref:System.Windows.Forms.DataGridView> denetimin <xref:System.Windows.Forms.DataGridView.GridColor%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="2d145-108">Each cell's text content is painted in <xref:System.Drawing.Color.Crimson%2A>, and an inset rectangle is drawn in the same color as the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d145-109">Örnek</span><span class="sxs-lookup"><span data-stu-id="2d145-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2d145-110">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="2d145-110">Compiling the Code</span></span>  
 <span data-ttu-id="2d145-111">Bu örnek gerektirir:</span><span class="sxs-lookup"><span data-stu-id="2d145-111">This example requires:</span></span>  
  
- <span data-ttu-id="2d145-112">A <xref:System.Windows.Forms.DataGridView> adlı Denetim `dataGridView1` ile bir `ContactName` gibi Northwind örnek veritabanındaki Müşteriler tablosunda bir sütun.</span><span class="sxs-lookup"><span data-stu-id="2d145-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a `ContactName` column such as the one in the Customers table in the Northwind sample database.</span></span>  
  
- <span data-ttu-id="2d145-113">Sistem, System.Windows.Forms ve System.Drawing derlemelerine başvurular.</span><span class="sxs-lookup"><span data-stu-id="2d145-113">References to the System, System.Windows.Forms, and System.Drawing assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d145-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="2d145-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [<span data-ttu-id="2d145-115">Windows Forms DataGridView Denetimini Özelleştirme</span><span class="sxs-lookup"><span data-stu-id="2d145-115">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
