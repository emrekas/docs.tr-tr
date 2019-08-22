---
title: 'Nasıl yapılır: Tasarımcı Kullanarak ToolBar Düğmesi için Simge Tanımlama'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
ms.openlocfilehash: 49e93f12bebbf409e6b3a06634556b9103c85f44
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666200"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a><span data-ttu-id="33376-102">Nasıl yapılır: Tasarımcı Kullanarak ToolBar Düğmesi için Simge Tanımlama</span><span class="sxs-lookup"><span data-stu-id="33376-102">How to: Define an Icon for a ToolBar Button Using the Designer</span></span>

> [!NOTE]
> <span data-ttu-id="33376-103">Denetim yerini alır ve <xref:System.Windows.Forms.ToolBar> <xref:System.Windows.Forms.ToolBar> denetime işlevsellik ekler; ancak, isterseniz denetim hem geri uyumluluk hem de gelecekteki kullanım için korunur. <xref:System.Windows.Forms.ToolStrip></span><span class="sxs-lookup"><span data-stu-id="33376-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>

<span data-ttu-id="33376-104"><xref:System.Windows.Forms.ToolBar>düğmeler, kullanıcılar tarafından kolay bir şekilde tanımlanması için simgeleri içinde görüntüleyebilir.</span><span class="sxs-lookup"><span data-stu-id="33376-104"><xref:System.Windows.Forms.ToolBar> buttons are able to display icons within them for easy identification by users.</span></span> <span data-ttu-id="33376-105">Bu, <xref:System.Windows.Forms.ImageList> bileşene görüntü eklenerek ve <xref:System.Windows.Forms.ToolBar> denetimi ile ilişkilendirerek elde edilir.</span><span class="sxs-lookup"><span data-stu-id="33376-105">This is achieved through adding images to the <xref:System.Windows.Forms.ImageList> component and associating it with the <xref:System.Windows.Forms.ToolBar> control.</span></span>

<span data-ttu-id="33376-106">Aşağıdaki yordam, bir <xref:System.Windows.Forms.ToolBar> denetim ve <xref:System.Windows.Forms.ImageList> bileşen içeren bir form ile **Windows uygulama** projesi gerektirir.</span><span class="sxs-lookup"><span data-stu-id="33376-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ToolBar> control and an <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="33376-107">Böyle bir projeyi ayarlama hakkında daha fazla bilgi için bkz [. nasıl yapılır: Windows Forms bir uygulama projesi](/visualstudio/ide/step-1-create-a-windows-forms-application-project) oluşturun ve [şunları yapın: Windows Forms](how-to-add-controls-to-windows-forms.md)denetimleri ekleyin.</span><span class="sxs-lookup"><span data-stu-id="33376-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a><span data-ttu-id="33376-108">Tasarım zamanında bir araç çubuğu düğmesine simge ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="33376-108">To set an icon for a toolbar button at design time</span></span>

1. <span data-ttu-id="33376-109"><xref:System.Windows.Forms.ImageList> Bileşene resim ekleyin.</span><span class="sxs-lookup"><span data-stu-id="33376-109">Add images to the <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="33376-110">Daha fazla bilgi için [nasıl yapılır: Tasarımcı](how-to-add-or-remove-imagelist-images-with-the-designer.md)ile ImageList görüntüleri ekleyin veya kaldırın.</span><span class="sxs-lookup"><span data-stu-id="33376-110">For more information, see [How to: Add or Remove ImageList Images with the Designer](how-to-add-or-remove-imagelist-images-with-the-designer.md).</span></span>

2. <span data-ttu-id="33376-111"><xref:System.Windows.Forms.ToolBar> Formunuzdaki denetimi seçin.</span><span class="sxs-lookup"><span data-stu-id="33376-111">Select the <xref:System.Windows.Forms.ToolBar> control on your form.</span></span>

3. <span data-ttu-id="33376-112">**Özellikler** penceresinde, <xref:System.Windows.Forms.ToolBar> denetimin <xref:System.Windows.Forms.ToolBar.ImageList%2A> özelliğini <xref:System.Windows.Forms.ImageList> bileşen olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="33376-112">In the **Properties** window, set the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.ImageList%2A> property to the <xref:System.Windows.Forms.ImageList> component.</span></span>

4. <span data-ttu-id="33376-113">![](./media/visual-studio-ellipsis-button.png)Seçmek için <xref:System.Windows.Forms.ToolBar> <xref:System.Windows.Forms.ToolBar.Buttons%2A> denetimin özelliğine tıklayın ve sonra ToolBarButton koleksiyon düzenleyicisini açmak için üç nokta (Visual Studio 'nun Özellikler penceresi) düğmesine tıklayın.</span><span class="sxs-lookup"><span data-stu-id="33376-113">Click the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.Buttons%2A> property to select it, and click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to open the **ToolBarButton Collection Editor**.</span></span>

5. <span data-ttu-id="33376-114"><xref:System.Windows.Forms.ToolBar> Denetime düğme eklemek için **Ekle** düğmesini kullanın.</span><span class="sxs-lookup"><span data-stu-id="33376-114">Use the **Add** button to add buttons to the <xref:System.Windows.Forms.ToolBar> control.</span></span>

6. <span data-ttu-id="33376-115">**ToolBarButton koleksiyon düzenleyicisinin**sağ tarafındaki bölmede görüntülenen <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> **Özellikler** penceresinde, her bir araç çubuğu düğmesinin özelliğini listedeki değerlerden birine, bu düğmeye eklediğiniz görüntülerden çizmiş olacak şekilde ayarlayın. <xref:System.Windows.Forms.ImageList> bileşen.</span><span class="sxs-lookup"><span data-stu-id="33376-115">In the **Properties** window that appears in the pane on the right side of the **ToolBarButton Collection Editor**, set the <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> property of each toolbar button to one of the values in the list, which is drawn from the images you added to the <xref:System.Windows.Forms.ImageList> component.</span></span>

## <a name="see-also"></a><span data-ttu-id="33376-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="33376-116">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="33376-117">Nasıl yapılır: Araç çubuğu düğmeleri için tetikleyici menü olayları</span><span class="sxs-lookup"><span data-stu-id="33376-117">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="33376-118">ToolBar Denetimi</span><span class="sxs-lookup"><span data-stu-id="33376-118">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
- [<span data-ttu-id="33376-119">ImageList Bileşeni</span><span class="sxs-lookup"><span data-stu-id="33376-119">ImageList Component</span></span>](imagelist-component-windows-forms.md)
