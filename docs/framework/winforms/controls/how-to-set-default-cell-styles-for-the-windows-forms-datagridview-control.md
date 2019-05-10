---
title: 'Nasıl yapılır: Windows Forms DataGridView Denetimi İçin Varsayılan Hücre Stillerini Ayarlama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: 1aaaca43-5340-447e-99c0-9177d9776aa1
ms.openlocfilehash: de939051b613a0622f60178a566fd19dbca53694
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64638160"
---
# <a name="how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="a0f5e-102">Nasıl yapılır: Windows Forms DataGridView Denetimi İçin Varsayılan Hücre Stillerini Ayarlama</span><span class="sxs-lookup"><span data-stu-id="a0f5e-102">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="a0f5e-103">İle <xref:System.Windows.Forms.DataGridView> denetimi tüm denetim ve özel sütunlar ve satırlar için varsayılan hücre stilleri belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a0f5e-103">With the <xref:System.Windows.Forms.DataGridView> control, you can specify default cell styles for the entire control and for specific columns and rows.</span></span> <span data-ttu-id="a0f5e-104">Bu varsayılan aşağı sütun düzeyi sonra satır düzeyinde sonra hücre düzeyi denetim düzeyden filtreleyin.</span><span class="sxs-lookup"><span data-stu-id="a0f5e-104">These defaults filter down from the control level to the column level, then to the row level, then to the cell level.</span></span> <span data-ttu-id="a0f5e-105">Belirli bir varsa <xref:System.Windows.Forms.DataGridViewCellStyle> hücre düzeyinde özelliği ayarlı değil, satır düzeyinde varsayılan özellik ayarı kullanılır.</span><span class="sxs-lookup"><span data-stu-id="a0f5e-105">If a particular <xref:System.Windows.Forms.DataGridViewCellStyle> property is not set at the cell level, the default property setting at the row level is used.</span></span> <span data-ttu-id="a0f5e-106">Özellik ayrıca satır düzeyinde ayarlanmazsa, varsayılan sütun ayarı kullanılır.</span><span class="sxs-lookup"><span data-stu-id="a0f5e-106">If the property is also not set at the row level, the default column setting is used.</span></span> <span data-ttu-id="a0f5e-107">Son olarak, özellik ayrıca, varsayılan sütun düzeyinde ayarlanmazsa @encryptor_type <xref:System.Windows.Forms.DataGridView> ayarı kullanılır.</span><span class="sxs-lookup"><span data-stu-id="a0f5e-107">Finally, if the property is also not set at the column level, the default <xref:System.Windows.Forms.DataGridView> setting is used.</span></span> <span data-ttu-id="a0f5e-108">Bu ayar, yinelenen özellik ayarları farklı düzeylere gerek kalmadan önleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a0f5e-108">With this setting, you can avoid having to duplicate the property settings at multiple levels.</span></span> <span data-ttu-id="a0f5e-109">Her düzeyde yukarıdaki düzeyleri farklı stilleri belirtmeniz yeterlidir.</span><span class="sxs-lookup"><span data-stu-id="a0f5e-109">At each level, simply specify the styles that differ from the levels above it.</span></span> <span data-ttu-id="a0f5e-110">Daha fazla bilgi için [Windows Forms DataGridView denetimindeki hücre stilleri](cell-styles-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="a0f5e-110">For more information, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="a0f5e-111">Visual Studio'da bu görevi için kapsamlı desteği yoktur.</span><span class="sxs-lookup"><span data-stu-id="a0f5e-111">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="a0f5e-112">Ayrıca bkz: [nasıl yapılır: DataGridView denetimi Tasarımcı kullanarak Windows formları için varsayılan hücre stilleri ve veri biçimleri ayarlama](default-cell-styles-datagridview.md).</span><span class="sxs-lookup"><span data-stu-id="a0f5e-112">Also see [How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer](default-cell-styles-datagridview.md).</span></span>  
  
### <a name="to-set-the-default-cell-styles-programmatically"></a><span data-ttu-id="a0f5e-113">Varsayılan hücre stilleri program üzerinden ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="a0f5e-113">To set the default cell styles programmatically</span></span>  
  
1. <span data-ttu-id="a0f5e-114">Özelliklerini ayarlama <xref:System.Windows.Forms.DataGridViewCellStyle> üzerinden alınan <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> özelliği.</span><span class="sxs-lookup"><span data-stu-id="a0f5e-114">Set the properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> retrieved through the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#141](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#141)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#141](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#141)]  
  
2. <span data-ttu-id="a0f5e-115">Oluşturma ve başlatma yeni <xref:System.Windows.Forms.DataGridViewCellStyle> birden çok satır ve sütun tarafından kullanılmak üzere nesneleri.</span><span class="sxs-lookup"><span data-stu-id="a0f5e-115">Create and initialize new <xref:System.Windows.Forms.DataGridViewCellStyle> objects for use by multiple rows and columns.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#142](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#142)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#142](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#142)]  
  
3. <span data-ttu-id="a0f5e-116">Ayarlama `DefaultCellStyle` belirli satırlar ve sütunlar özelliği.</span><span class="sxs-lookup"><span data-stu-id="a0f5e-116">Set the `DefaultCellStyle` property of specific rows and columns.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#143](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#143)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#143](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#143)]  
  
## <a name="example"></a><span data-ttu-id="a0f5e-117">Örnek</span><span class="sxs-lookup"><span data-stu-id="a0f5e-117">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#140)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#140)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a0f5e-118">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="a0f5e-118">Compiling the Code</span></span>  
 <span data-ttu-id="a0f5e-119">Bu örnek gerektirir:</span><span class="sxs-lookup"><span data-stu-id="a0f5e-119">This example requires:</span></span>  
  
- <span data-ttu-id="a0f5e-120">A <xref:System.Windows.Forms.DataGridView> adlı Denetim `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="a0f5e-120">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="a0f5e-121">Başvurular <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, ve <xref:System.Windows.Forms?displayProperty=nameWithType> derlemeler.</span><span class="sxs-lookup"><span data-stu-id="a0f5e-121">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a0f5e-122">Güçlü Programlama</span><span class="sxs-lookup"><span data-stu-id="a0f5e-122">Robust Programming</span></span>  
 <span data-ttu-id="a0f5e-123">Çok büyük veri kümeleriyle çalışırken maksimum ölçeklenebilirlik elde etmek için paylaşmalıdır <xref:System.Windows.Forms.DataGridViewCellStyle> birden çok satır, sütun veya ayrı ayrı ayrı ayrı öğeler stil özelliklerini ayarlama yerine aynı stilleri kullanıp hücreleri nesneleri.</span><span class="sxs-lookup"><span data-stu-id="a0f5e-123">To achieve maximum scalability when you work with very large data sets, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles, rather than set the style properties for individual elements separately.</span></span> <span data-ttu-id="a0f5e-124">Ayrıca, paylaşılan satırlar oluşturmak ve bunları kullanarak erişim <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> özelliği.</span><span class="sxs-lookup"><span data-stu-id="a0f5e-124">Additionally, you should create shared rows and access them by using the <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="a0f5e-125">Daha fazla bilgi için [Windows Forms DataGridView denetimini ölçeklendirme için en iyi yöntemler](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="a0f5e-125">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0f5e-126">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="a0f5e-126">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- [<span data-ttu-id="a0f5e-127">Windows Forms DataGridView Denetimindeki Temel Biçim ve Stiller</span><span class="sxs-lookup"><span data-stu-id="a0f5e-127">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="a0f5e-128">Windows Forms DataGridView Denetimindeki Hücre Stilleri</span><span class="sxs-lookup"><span data-stu-id="a0f5e-128">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="a0f5e-129">Windows Forms DataGridView Denetimini Ölçeklendirme için En İyi Yöntemler</span><span class="sxs-lookup"><span data-stu-id="a0f5e-129">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="a0f5e-130">Nasıl yapılır: Windows Forms DataGridView denetimi için alternatif satır stillerini ayarlama</span><span class="sxs-lookup"><span data-stu-id="a0f5e-130">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)
