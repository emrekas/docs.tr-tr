---
title: 'Nasıl yapılır: Bir TableLayoutPanel Denetimindeki Satırları ve Sütunları Yayma'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
ms.openlocfilehash: a215b2b4e05bab5c81d2779d4b67d5b9d57b6ba5
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039696"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a><span data-ttu-id="34396-102">Nasıl yapılır: Bir TableLayoutPanel Denetimindeki Satırları ve Sütunları Yayma</span><span class="sxs-lookup"><span data-stu-id="34396-102">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>
<span data-ttu-id="34396-103">Bir <xref:System.Windows.Forms.TableLayoutPanel> denetimdeki denetimler bitişik satır ve sütunlara yayılabilir.</span><span class="sxs-lookup"><span data-stu-id="34396-103">Controls in a <xref:System.Windows.Forms.TableLayoutPanel> control can span adjacent rows and columns.</span></span>

## <a name="to-span-columns-and-rows"></a><span data-ttu-id="34396-104">Sütunları ve satırları yayma</span><span class="sxs-lookup"><span data-stu-id="34396-104">To span columns and rows</span></span>

1. <span data-ttu-id="34396-105"><xref:System.Windows.Forms.TableLayoutPanel> **Araç kutusu** ' ndan formunuza bir denetim sürükleyin.</span><span class="sxs-lookup"><span data-stu-id="34396-105">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="34396-106"><xref:System.Windows.Forms.Button> **Araç kutusundan** denetimin<xref:System.Windows.Forms.TableLayoutPanel> sol üst hücresine bir denetim sürükleyin.</span><span class="sxs-lookup"><span data-stu-id="34396-106">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

3. <span data-ttu-id="34396-107">Denetimin ColumnSpan özelliğini **2**olarak ayarlayın. <xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="34396-107">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **2**.</span></span> <span data-ttu-id="34396-108"><xref:System.Windows.Forms.Button> Denetimin birinci ve ikinci sütunları yaydığına unutmayın.</span><span class="sxs-lookup"><span data-stu-id="34396-108">Note that the <xref:System.Windows.Forms.Button> control spans the first and second columns.</span></span>

4. <span data-ttu-id="34396-109">Denetimin RowSpan özelliğini **2**olarak ayarlayın. <xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="34396-109">Set the <xref:System.Windows.Forms.Button> control's **RowSpan** property to **2**.</span></span> <span data-ttu-id="34396-110"><xref:System.Windows.Forms.Button> Denetimin birinci ve ikinci satırları yaydığına unutmayın.</span><span class="sxs-lookup"><span data-stu-id="34396-110">Note that the <xref:System.Windows.Forms.Button> control spans the first and second rows.</span></span>

5. <span data-ttu-id="34396-111">Denetimin ColumnSpan özelliğini **1**olarak ayarlayın. <xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="34396-111">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **1**.</span></span> <span data-ttu-id="34396-112"><xref:System.Windows.Forms.Button> Denetimin ilk sütuna taşındığını ve birinci ve ikinci satırlara yayıldığına unutmayın.</span><span class="sxs-lookup"><span data-stu-id="34396-112">Note that the <xref:System.Windows.Forms.Button> control moves into the first column and spans the first and second rows.</span></span>

## <a name="see-also"></a><span data-ttu-id="34396-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="34396-113">See also</span></span>

- [<span data-ttu-id="34396-114">TableLayoutPanel Denetimi</span><span class="sxs-lookup"><span data-stu-id="34396-114">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
