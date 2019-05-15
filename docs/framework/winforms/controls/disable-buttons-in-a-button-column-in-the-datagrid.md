---
title: 'Nasıl yapılır: Windows Forms DataGridView Denetimindeki Bir Düğme Sütununda Düğmeleri Devre Dışı Bırakma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], disabling buttons
- buttons [Windows Forms], disabling in button columns
- DataGridView control [Windows Forms], disabling button cells
ms.assetid: 5c344d01-013a-4a6b-8f8d-62ec9321d81e
ms.openlocfilehash: 7d6223e4d75524044e701ea4cf34dcc7487ccd25
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591792"
---
# <a name="how-to-disable-buttons-in-a-button-column-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="d884d-102">Nasıl yapılır: Windows Forms DataGridView Denetimindeki Bir Düğme Sütununda Düğmeleri Devre Dışı Bırakma</span><span class="sxs-lookup"><span data-stu-id="d884d-102">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d884d-103"><xref:System.Windows.Forms.DataGridView> Denetimi içeren <xref:System.Windows.Forms.DataGridViewButtonCell> hücre bir düğme gibi bir kullanıcı arabirimi (UI) görüntülemek için sınıf.</span><span class="sxs-lookup"><span data-stu-id="d884d-103">The <xref:System.Windows.Forms.DataGridView> control includes the <xref:System.Windows.Forms.DataGridViewButtonCell> class for displaying cells with a user interface (UI) like a button.</span></span> <span data-ttu-id="d884d-104">Ancak, <xref:System.Windows.Forms.DataGridViewButtonCell> hücrenin tarafından görüntülenen düğmesinin devre dışı bırakmak için bir yöntem sağlamaz.</span><span class="sxs-lookup"><span data-stu-id="d884d-104">However, <xref:System.Windows.Forms.DataGridViewButtonCell> does not provide a way to disable the appearance of the button displayed by the cell.</span></span>  
  
 <span data-ttu-id="d884d-105">Aşağıdaki kod örneğinde nasıl özelleştirileceğini gösterir <xref:System.Windows.Forms.DataGridViewButtonCell> devre dışı görünebilen düğmeleri görüntülemek için sınıf.</span><span class="sxs-lookup"><span data-stu-id="d884d-105">The following code example demonstrates how to customize the <xref:System.Windows.Forms.DataGridViewButtonCell> class to display buttons that can appear disabled.</span></span> <span data-ttu-id="d884d-106">Örnek yeni bir hücre türü tanımlar `DataGridViewDisableButtonCell`, türetilen <xref:System.Windows.Forms.DataGridViewButtonCell>.</span><span class="sxs-lookup"><span data-stu-id="d884d-106">The example defines a new cell type, `DataGridViewDisableButtonCell`, that derives from <xref:System.Windows.Forms.DataGridViewButtonCell>.</span></span> <span data-ttu-id="d884d-107">Bu hücre türü yeni bir sağlar `Enabled` ayarlanabilir özelliği `false` hücrede devre dışı bırakılmış bir düğme çizmek için.</span><span class="sxs-lookup"><span data-stu-id="d884d-107">This cell type provides a new `Enabled` property that can be set to `false` to draw a disabled button in the cell.</span></span> <span data-ttu-id="d884d-108">Örnek ayrıca yeni bir sütun türü tanımlar `DataGridViewDisableButtonColumn`, görüntüleyen `DataGridViewDisableButtonCell` nesneleri.</span><span class="sxs-lookup"><span data-stu-id="d884d-108">The example also defines a new column type, `DataGridViewDisableButtonColumn`, that displays `DataGridViewDisableButtonCell` objects.</span></span> <span data-ttu-id="d884d-109">Göstermek için bu yeni hücreyi ve sütun türü, her geçerli değerini <xref:System.Windows.Forms.DataGridViewCheckBoxCell> üst <xref:System.Windows.Forms.DataGridView> belirler olmadığını `Enabled` özelliği `DataGridViewDisableButtonCell` aynı sırada `true` veya `false`.</span><span class="sxs-lookup"><span data-stu-id="d884d-109">To demonstrate this new cell and column type, the current value of each <xref:System.Windows.Forms.DataGridViewCheckBoxCell> in the parent <xref:System.Windows.Forms.DataGridView> determines whether the `Enabled` property of the `DataGridViewDisableButtonCell` in the same row is `true` or `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d884d-110">Olduğunda, türetilen <xref:System.Windows.Forms.DataGridViewCell> veya <xref:System.Windows.Forms.DataGridViewColumn> ve türetilmiş sınıf için yeni özellikler eklemek için geçersiz kılmak mutlaka `Clone` kopyalama işlemleri sırasında yeni özellikleri kopyalamak için yöntemi.</span><span class="sxs-lookup"><span data-stu-id="d884d-110">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="d884d-111">Ayrıca temel sınıfın çağırmalıdır `Clone` yöntemi, böylece yeni hücresinde veya sütununda için temel sınıf özelliklerini kopyalanır.</span><span class="sxs-lookup"><span data-stu-id="d884d-111">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d884d-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="d884d-112">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView.DisabledButtons#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.DisabledButtons#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d884d-113">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="d884d-113">Compiling the Code</span></span>  
 <span data-ttu-id="d884d-114">Bu örnek gerektirir:</span><span class="sxs-lookup"><span data-stu-id="d884d-114">This example requires:</span></span>  
  
- <span data-ttu-id="d884d-115">Sistem, System.Drawing, System.Windows.Forms ve System.Windows.Forms.VisualStyles derlemelerine başvurular.</span><span class="sxs-lookup"><span data-stu-id="d884d-115">References to the System, System.Drawing, System.Windows.Forms and System.Windows.Forms.VisualStyles assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d884d-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d884d-116">See also</span></span>

- [<span data-ttu-id="d884d-117">Windows Forms DataGridView Denetimini Özelleştirme</span><span class="sxs-lookup"><span data-stu-id="d884d-117">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d884d-118">DataGridView Denetimi Mimarisi</span><span class="sxs-lookup"><span data-stu-id="d884d-118">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
- [<span data-ttu-id="d884d-119">Windows Forms DataGridView Denetiminde Sütun Türleri</span><span class="sxs-lookup"><span data-stu-id="d884d-119">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
