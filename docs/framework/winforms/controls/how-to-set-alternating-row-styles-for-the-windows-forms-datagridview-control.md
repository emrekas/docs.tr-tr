---
title: 'Nasıl yapılır: Windows Forms DataGridView denetimi için alternatif satır stillerini ayarlama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], row styles
- data grids [Windows Forms], row styles
- rows [Windows Forms], data grids
ms.assetid: 699ef759-458c-426d-ac87-7c7e71b018ae
ms.openlocfilehash: eea77b7601b7dc81b92f7b08806f3f00b494aecd
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56583894"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="5a928-102">Nasıl yapılır: Windows Forms DataGridView denetimi için alternatif satır stillerini ayarlama</span><span class="sxs-lookup"><span data-stu-id="5a928-102">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="5a928-103">Tablo verileri genellikle kullanıcılara büyük defter benzeri biçimde değişen satırları farklı arka plan renkleri sahip olduğu sunulur.</span><span class="sxs-lookup"><span data-stu-id="5a928-103">Tabular data is often presented to users in a ledger-like format where alternating rows have different background colors.</span></span> <span data-ttu-id="5a928-104">Bu biçim, özellikle fazla sayıda sütun sahip geniş tabloların ile her bir satırdaki hücreleri olduğunu bildirir kullanıcıların kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="5a928-104">This format makes it easier for users to tell which cells are in each row, especially with wide tables that have many columns.</span></span>  
  
 <span data-ttu-id="5a928-105">İle <xref:System.Windows.Forms.DataGridView> denetimi için alternatif satırlar tam stil bilgilerini belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5a928-105">With the <xref:System.Windows.Forms.DataGridView> control, you can specify complete style information for alternating rows.</span></span> <span data-ttu-id="5a928-106">Ön plan rengini ve değişen satırları ayırt etmek için yazı tipini, arka plan rengi, ek olarak bu etkinleştirir stil özellikleri kullanmak ister.</span><span class="sxs-lookup"><span data-stu-id="5a928-106">This enables you use style characteristics like foreground color and font, in addition to background color, to differentiate alternating rows.</span></span>  
  
 <span data-ttu-id="5a928-107">Visual Studio'da bu görevi için desteği yoktur.</span><span class="sxs-lookup"><span data-stu-id="5a928-107">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="5a928-108">Ayrıca bkz: [nasıl yapılır: Windows Forms DataGridView Tasarımcısı'nı kullanarak denetimi için alternatif satır stillerini ayarlama](set-alternating-row-styles-for-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="5a928-108">Also see [How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer](set-alternating-row-styles-for-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-set-alternating-row-styles-programmatically"></a><span data-ttu-id="5a928-109">Ayarlamak için alternatif satır stillerini program aracılığıyla</span><span class="sxs-lookup"><span data-stu-id="5a928-109">To set alternating row styles programmatically</span></span>  
  
-   <span data-ttu-id="5a928-110">Özelliklerini ayarlama <xref:System.Windows.Forms.DataGridViewCellStyle> tarafından döndürülen nesne <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> ve <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> özelliklerini <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="5a928-110">Set the properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> objects returned by the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> and <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> properties of the <xref:System.Windows.Forms.DataGridView>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#068](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#068)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#068](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#068)]  
  
    > [!NOTE]
    >  <span data-ttu-id="5a928-111">Stilleri kullanarak belirtilen <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> ve <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> belirtilen sütun stillerini geçersiz kılma özellikleri ve <xref:System.Windows.Forms.DataGridView> düzey, ancak tek satır ve hücre düzeyinde ayarlanan stilleri tarafından geçersiz kılınır.</span><span class="sxs-lookup"><span data-stu-id="5a928-111">The styles specified using the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> and <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> properties override the styles specified on the column and <xref:System.Windows.Forms.DataGridView> level, but are overridden by the styles set on the individual row and cell level.</span></span> <span data-ttu-id="5a928-112">Daha fazla bilgi için [Windows Forms DataGridView denetimindeki hücre stilleri](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="5a928-112">For more information, see [Cell Styles in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5a928-113">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="5a928-113">Compiling the Code</span></span>  
 <span data-ttu-id="5a928-114">Bu örnek gerektirir:</span><span class="sxs-lookup"><span data-stu-id="5a928-114">This example requires:</span></span>  
  
-   <span data-ttu-id="5a928-115">A <xref:System.Windows.Forms.DataGridView> adlı Denetim `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="5a928-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="5a928-116">Başvurular <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, ve <xref:System.Windows.Forms?displayProperty=nameWithType> derlemeler.</span><span class="sxs-lookup"><span data-stu-id="5a928-116">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="5a928-117">Güçlü Programlama</span><span class="sxs-lookup"><span data-stu-id="5a928-117">Robust Programming</span></span>  
 <span data-ttu-id="5a928-118">En yüksek ölçeklenebilirlik için paylaşmalıdır <xref:System.Windows.Forms.DataGridViewCellStyle> nesneleri birden çok satırları, sütunları veya hücreleri stil özellikleri her öğe için ayrı olarak ayarlamak yerine aynı stili kullanın.</span><span class="sxs-lookup"><span data-stu-id="5a928-118">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles, rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="5a928-119">Daha fazla bilgi için [Windows Forms DataGridView denetimini ölçeklendirme için en iyi yöntemler](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="5a928-119">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a928-120">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="5a928-120">See also</span></span>
- <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [<span data-ttu-id="5a928-121">Windows Forms DataGridView Denetimindeki Temel Biçim ve Stiller</span><span class="sxs-lookup"><span data-stu-id="5a928-121">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="5a928-122">Windows Forms DataGridView Denetimindeki Hücre Stilleri</span><span class="sxs-lookup"><span data-stu-id="5a928-122">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="5a928-123">Windows Forms DataGridView Denetimini Ölçeklendirme için En İyi Yöntemler</span><span class="sxs-lookup"><span data-stu-id="5a928-123">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="5a928-124">Nasıl yapılır: Windows Forms DataGridView denetiminde yazı tipi ve renk stillerini ayarlama</span><span class="sxs-lookup"><span data-stu-id="5a928-124">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)
