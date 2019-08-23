---
title: 'Nasıl yapılır: Windows Forms DataGridView Denetiminde Kenarlık ve Kılavuz Çizgi Stillerini Değiştirme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gridlines [Windows Forms], changing styles
- data grids [Windows Forms], changing gridline styles
- DataGridView control [Windows Forms], border styles
- data grids [Windows Forms], changing border styles
- DataGridView control [Windows Forms], gridline styles
ms.assetid: 2f413c7a-4025-4171-8e3a-66ef908ea583
ms.openlocfilehash: ebeca5f933eac4da2bf3d4f300866fd2ff52b32a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917668"
---
# <a name="how-to-change-the-border-and-gridline-styles-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="3d09c-102">Nasıl yapılır: Windows Forms DataGridView Denetiminde Kenarlık ve Kılavuz Çizgi Stillerini Değiştirme</span><span class="sxs-lookup"><span data-stu-id="3d09c-102">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="3d09c-103"><xref:System.Windows.Forms.DataGridView> Denetim ile, Kullanıcı deneyimini geliştirmek için denetimin kenarlığının ve kılavuz çizgilerinin görünümünü özelleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3d09c-103">With the <xref:System.Windows.Forms.DataGridView> control, you can customize the appearance of the control's border and gridlines to improve the user experience.</span></span> <span data-ttu-id="3d09c-104">Denetim içindeki hücrelerin kenarlık stillerine ek olarak kılavuz çizgisi rengini ve denetim kenarlığı stilini değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3d09c-104">You can modify the gridline color and the control border style in addition to the border styles for the cells within the control.</span></span> <span data-ttu-id="3d09c-105">Ayrıca, normal hücreler, satır üst bilgisi hücreleri ve sütun üst bilgisi hücreleri için farklı hücre kenarlık stilleri uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3d09c-105">You can also apply different cell border styles for ordinary cells, row header cells, and column header cells.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3d09c-106">Kılavuz çizgisi rengi yalnızca <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle> sabit <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal> <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> listesinin,<xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> ve değerleri ile numaralandırma değeriilekullanılır.<xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single></span><span class="sxs-lookup"><span data-stu-id="3d09c-106">The gridline color is used only with the <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>, and <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> values of the <xref:System.Windows.Forms.DataGridViewCellBorderStyle> enumeration and the <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> value of the <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> enumeration.</span></span> <span data-ttu-id="3d09c-107">Bu Numaralandırmaların diğer değerleri, işletim sistemi tarafından belirtilen renkleri kullanır.</span><span class="sxs-lookup"><span data-stu-id="3d09c-107">The other values of these enumerations use colors specified by the operating system.</span></span> <span data-ttu-id="3d09c-108">Ayrıca, Windows XP ve Windows Server 2003 ailesinde <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> yöntemi <xref:System.Windows.Forms.DataGridView.GridColor%2A> aracılığıyla görsel stiller etkinleştirildiğinde Özellik değeri kullanılmaz.</span><span class="sxs-lookup"><span data-stu-id="3d09c-108">Additionally, when visual styles are enabled on Windows XP and the Windows Server 2003 family through the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method, the <xref:System.Windows.Forms.DataGridView.GridColor%2A> property value is not used.</span></span>  
  
### <a name="to-change-the-gridline-color-programmatically"></a><span data-ttu-id="3d09c-109">Kılavuz çizgisi rengini programlı olarak değiştirmek için</span><span class="sxs-lookup"><span data-stu-id="3d09c-109">To change the gridline color programmatically</span></span>  
  
- <span data-ttu-id="3d09c-110"><xref:System.Windows.Forms.DataGridView.GridColor%2A> Özelliği ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="3d09c-110">Set the <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#031)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#031)]  
  
### <a name="to-change-the-border-style-of-the-entire-datagridview-control-programmatically"></a><span data-ttu-id="3d09c-111">Tüm DataGridView denetiminin kenarlık stilini programlı olarak değiştirme</span><span class="sxs-lookup"><span data-stu-id="3d09c-111">To change the border style of the entire DataGridView control programmatically</span></span>  
  
- <span data-ttu-id="3d09c-112"><xref:System.Windows.Forms.DataGridView.BorderStyle%2A> Özelliğini <xref:System.Windows.Forms.BorderStyle> sabit listesi değerlerinden birine ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="3d09c-112">Set the <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> property to one of the <xref:System.Windows.Forms.BorderStyle> enumeration values.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#032)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#032)]  
  
### <a name="to-change-the-border-styles-for-datagridview-cells-programmatically"></a><span data-ttu-id="3d09c-113">DataGridView hücrelerinin kenarlık stillerini programlı olarak değiştirmek için</span><span class="sxs-lookup"><span data-stu-id="3d09c-113">To change the border styles for DataGridView cells programmatically</span></span>  
  
- <span data-ttu-id="3d09c-114"><xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A> ,<xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>Ve özelliklerini<xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="3d09c-114">Set the <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>, and <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#033)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#033)]  
  
## <a name="example"></a><span data-ttu-id="3d09c-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="3d09c-115">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#030)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#030)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3d09c-116">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="3d09c-116">Compiling the Code</span></span>  
 <span data-ttu-id="3d09c-117">Bu örnek şunları gerektirir:</span><span class="sxs-lookup"><span data-stu-id="3d09c-117">This example requires:</span></span>  
  
- <span data-ttu-id="3d09c-118"><xref:System.Windows.Forms.DataGridView> Adlı`dataGridView1`bir denetim.</span><span class="sxs-lookup"><span data-stu-id="3d09c-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="3d09c-119"><xref:System?displayProperty=nameWithType> ,<xref:System.Windows.Forms?displayProperty=nameWithType>Ve derlemelerinin<xref:System.Drawing?displayProperty=nameWithType> başvuruları.</span><span class="sxs-lookup"><span data-stu-id="3d09c-119">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d09c-120">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="3d09c-120">See also</span></span>

- <xref:System.Windows.Forms.BorderStyle>
- <xref:System.Windows.Forms.DataGridView.BorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.GridColor%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellBorderStyle>
- <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>
- [<span data-ttu-id="3d09c-121">Windows Forms DataGridView Denetimindeki Temel Biçim ve Stiller</span><span class="sxs-lookup"><span data-stu-id="3d09c-121">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
