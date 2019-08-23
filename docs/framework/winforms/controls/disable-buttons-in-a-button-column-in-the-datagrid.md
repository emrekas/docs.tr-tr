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
ms.openlocfilehash: b8bb503186e41c682b0685e4c9c4bf0bb3adcbe8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967390"
---
# <a name="how-to-disable-buttons-in-a-button-column-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="7ec54-102">Nasıl yapılır: Windows Forms DataGridView Denetimindeki Bir Düğme Sütununda Düğmeleri Devre Dışı Bırakma</span><span class="sxs-lookup"><span data-stu-id="7ec54-102">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="7ec54-103">Denetim, bir düğme <xref:System.Windows.Forms.DataGridViewButtonCell> gibi bir kullanıcı arabirimi (UI) ile hücreleri görüntülemek için sınıfını içerir. <xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="7ec54-103">The <xref:System.Windows.Forms.DataGridView> control includes the <xref:System.Windows.Forms.DataGridViewButtonCell> class for displaying cells with a user interface (UI) like a button.</span></span> <span data-ttu-id="7ec54-104">Ancak, <xref:System.Windows.Forms.DataGridViewButtonCell> hücre tarafından görünen düğmenin görünümünü devre dışı bırakmak için bir yol sağlamaz.</span><span class="sxs-lookup"><span data-stu-id="7ec54-104">However, <xref:System.Windows.Forms.DataGridViewButtonCell> does not provide a way to disable the appearance of the button displayed by the cell.</span></span>  
  
 <span data-ttu-id="7ec54-105">Aşağıdaki kod örneği, devre dışı görünebilen düğmeleri <xref:System.Windows.Forms.DataGridViewButtonCell> göstermek için sınıfının nasıl özelleştirileceğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="7ec54-105">The following code example demonstrates how to customize the <xref:System.Windows.Forms.DataGridViewButtonCell> class to display buttons that can appear disabled.</span></span> <span data-ttu-id="7ec54-106">Örnek, `DataGridViewDisableButtonCell`' den <xref:System.Windows.Forms.DataGridViewButtonCell>türetilen yeni bir hücre türü tanımlar.</span><span class="sxs-lookup"><span data-stu-id="7ec54-106">The example defines a new cell type, `DataGridViewDisableButtonCell`, that derives from <xref:System.Windows.Forms.DataGridViewButtonCell>.</span></span> <span data-ttu-id="7ec54-107">Bu hücre türü, hücrede devre `Enabled` dışı bir düğme çizmek için olarak `false` ayarlanabilir yeni bir özellik sağlar.</span><span class="sxs-lookup"><span data-stu-id="7ec54-107">This cell type provides a new `Enabled` property that can be set to `false` to draw a disabled button in the cell.</span></span> <span data-ttu-id="7ec54-108">Örnek ayrıca, nesneleri görüntüleyen `DataGridViewDisableButtonColumn` `DataGridViewDisableButtonCell` yeni bir sütun türü tanımlar.</span><span class="sxs-lookup"><span data-stu-id="7ec54-108">The example also defines a new column type, `DataGridViewDisableButtonColumn`, that displays `DataGridViewDisableButtonCell` objects.</span></span> <span data-ttu-id="7ec54-109">Bu yeni hücreyi ve sütun türünü göstermek için, <xref:System.Windows.Forms.DataGridViewCheckBoxCell> üst öğede <xref:System.Windows.Forms.DataGridView> her birinin geçerli değeri, aynı satırdaki `Enabled` öğesinin `DataGridViewDisableButtonCell` özelliğinin veya `false`olduğunu `true` belirler.</span><span class="sxs-lookup"><span data-stu-id="7ec54-109">To demonstrate this new cell and column type, the current value of each <xref:System.Windows.Forms.DataGridViewCheckBoxCell> in the parent <xref:System.Windows.Forms.DataGridView> determines whether the `Enabled` property of the `DataGridViewDisableButtonCell` in the same row is `true` or `false`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7ec54-110">Türetilmiş sınıfa türeten <xref:System.Windows.Forms.DataGridViewCell> veya <xref:System.Windows.Forms.DataGridViewColumn> yeni özellikler eklediğinizde, kopyalama işlemleri sırasında yeni özellikleri kopyalamak için `Clone` yöntemi geçersiz kıldığınızdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="7ec54-110">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="7ec54-111">Ayrıca temel sınıfın özelliklerini yeni hücreye veya sütuna `Clone` kopyalamak için temel sınıfın yöntemini çağırmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="7ec54-111">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ec54-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="7ec54-112">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView.DisabledButtons#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.DisabledButtons#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7ec54-113">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="7ec54-113">Compiling the Code</span></span>  
 <span data-ttu-id="7ec54-114">Bu örnek şunları gerektirir:</span><span class="sxs-lookup"><span data-stu-id="7ec54-114">This example requires:</span></span>  
  
- <span data-ttu-id="7ec54-115">System, System. Drawing, System. Windows. Forms ve System. Windows. Forms. VisualStyles derlemelerine başvurular.</span><span class="sxs-lookup"><span data-stu-id="7ec54-115">References to the System, System.Drawing, System.Windows.Forms and System.Windows.Forms.VisualStyles assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ec54-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="7ec54-116">See also</span></span>

- [<span data-ttu-id="7ec54-117">Windows Forms DataGridView Denetimini Özelleştirme</span><span class="sxs-lookup"><span data-stu-id="7ec54-117">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="7ec54-118">DataGridView Denetimi Mimarisi</span><span class="sxs-lookup"><span data-stu-id="7ec54-118">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
- [<span data-ttu-id="7ec54-119">Windows Forms DataGridView Denetiminde Sütun Türleri</span><span class="sxs-lookup"><span data-stu-id="7ec54-119">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
