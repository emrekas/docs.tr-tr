---
title: 'Nasıl yapılır: Windows Forms DataGridView Denetiminde Sütunların Sırasını Değiştirme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], changing order
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], changing column order
ms.assetid: 5e9ac3bc-b0f0-48cb-a3d5-b005af905395
ms.openlocfilehash: 90d262e738f092215e88e38e31169d74059e4401
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228802"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="cdb32-102">Nasıl yapılır: Windows Forms DataGridView Denetiminde Sütunların Sırasını Değiştirme</span><span class="sxs-lookup"><span data-stu-id="cdb32-102">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="cdb32-103">Kullandığınızda, bir <xref:System.Windows.Forms.DataGridView> bir veri kaynağından verileri görüntülemek için veri kaynağı şemasındaki bazen sütunları görüntülemek istediğiniz sırayla görünmez.</span><span class="sxs-lookup"><span data-stu-id="cdb32-103">When you use a <xref:System.Windows.Forms.DataGridView> to display data from a data source, the columns in the data source's schema sometimes do not appear in the order you would like to display them.</span></span> <span data-ttu-id="cdb32-104">Görüntülenen sütunların sırasını kullanarak değiştirebileceğiniz <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A> özelliği <xref:System.Windows.Forms.DataGridViewColumn> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="cdb32-104">You can change the displayed order of the columns by using the <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A> property of the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
 <span data-ttu-id="cdb32-105">Aşağıdaki kod örneği Northwind örnek veritabanındaki Müşteriler tablosunu bağlama zaman otomatik olarak oluşturulan sütunların bazıları yeniden konumlandırır.</span><span class="sxs-lookup"><span data-stu-id="cdb32-105">The following code example repositions some of the columns automatically generated when binding to the Customers table in the Northwind sample database.</span></span> <span data-ttu-id="cdb32-106">Bağlama hakkında daha fazla bilgi için <xref:System.Windows.Forms.DataGridView> denetlemek için bir veritabanı tablosu, bkz: [nasıl yapılır: Veri bağlama Windows Forms DataGridView denetiminde](how-to-bind-data-to-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="cdb32-106">For more information about how to bind the <xref:System.Windows.Forms.DataGridView> control to a database table, see [How to: Bind Data to the Windows Forms DataGridView Control](how-to-bind-data-to-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="cdb32-107">Visual Studio'da bu görevi için desteği yoktur.</span><span class="sxs-lookup"><span data-stu-id="cdb32-107">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="cdb32-108">Ayrıca bkz: [nasıl yapılır: Tasarımcı kullanarak Windows Forms DataGridView denetiminde sütunların sırasını değiştirme](change-the-order-of-columns-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="cdb32-108">Also see [How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer](change-the-order-of-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdb32-109">Örnek</span><span class="sxs-lookup"><span data-stu-id="cdb32-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#040](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#040)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#040](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#040)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cdb32-110">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="cdb32-110">Compiling the Code</span></span>  
 <span data-ttu-id="cdb32-111">Bu örnek gerektirir:</span><span class="sxs-lookup"><span data-stu-id="cdb32-111">This example requires:</span></span>  
  
-   <span data-ttu-id="cdb32-112">A <xref:System.Windows.Forms.DataGridView> adlı Denetim `customersDataGridView` bağlanan belirtilen sütun adları içeren bir tablo gibi `Customers` Northwind örnek veritabanındaki tablo.</span><span class="sxs-lookup"><span data-stu-id="cdb32-112">A <xref:System.Windows.Forms.DataGridView> control named `customersDataGridView` that is bound to a table with the indicated column names, such as the `Customers` table in the Northwind sample database.</span></span>  
  
-   <span data-ttu-id="cdb32-113">Başvurular <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType>, ve <xref:System.Xml?displayProperty=nameWithType> derlemeler.</span><span class="sxs-lookup"><span data-stu-id="cdb32-113">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType>, and <xref:System.Xml?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdb32-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="cdb32-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="cdb32-115">Windows Forms DataGridView Denetiminde Verileri Görüntüleme</span><span class="sxs-lookup"><span data-stu-id="cdb32-115">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="cdb32-116">Nasıl yapılır: Windows Forms DataGridView Denetimine Veri Bağlama</span><span class="sxs-lookup"><span data-stu-id="cdb32-116">How to: Bind Data to the Windows Forms DataGridView Control</span></span>](how-to-bind-data-to-the-windows-forms-datagridview-control.md)
