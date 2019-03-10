---
title: 'Nasıl yapılır: MenuStrip (Windows Forms) seçenek düğmeleri görüntüleme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
ms.openlocfilehash: c64dd88915fdd17deee415b4d6c3fd088fbcfbfd
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718876"
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a><span data-ttu-id="f48bd-102">Nasıl yapılır: MenuStrip (Windows Forms) seçenek düğmeleri görüntüleme</span><span class="sxs-lookup"><span data-stu-id="f48bd-102">How to: Display Option Buttons in a MenuStrip (Windows Forms)</span></span>
<span data-ttu-id="f48bd-103">Seçenek düğmeleri, radyo düğmeleri olarak da bilinir, kullanıcılar yalnızca teker teker seçebilir dışında onay kutularını işaretleyin benzerdir.</span><span class="sxs-lookup"><span data-stu-id="f48bd-103">Option buttons, also known as radio buttons, are similar to check boxes except that users can select only one at a time.</span></span> <span data-ttu-id="f48bd-104">Ancak varsayılan olarak <xref:System.Windows.Forms.ToolStripMenuItem> sınıfı seçenek düğmesini davranışı sağlamaz, sınıfı menü öğeleri için seçenek düğmesini davranışı uygulamak için özelleştirebileceğiniz onay kutusu davranış sağlayan bir <xref:System.Windows.Forms.MenuStrip> denetimi.</span><span class="sxs-lookup"><span data-stu-id="f48bd-104">Although by default the <xref:System.Windows.Forms.ToolStripMenuItem> class does not provide option-button behavior, the class does provide check-box behavior that you can customize to implement option-button behavior for menu items in a <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="f48bd-105">Zaman <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> özelliği bir menü öğesinin `true`, kullanıcılar, bir onay işareti görünümünü değiştirmek için öğeyi tıklatabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f48bd-105">When the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property of a menu item is `true`, users can click the item to toggle the display of a check mark.</span></span> <span data-ttu-id="f48bd-106"><xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> Özelliği öğesinin geçerli durumunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="f48bd-106">The <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property indicates the current state of the item.</span></span> <span data-ttu-id="f48bd-107">Temel seçenek düğmesini davranışı uygulamak için bir öğe seçildiğinde, ayarladığınız emin olmalısınız <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> özelliği için daha önce seçilen öğe için `false`.</span><span class="sxs-lookup"><span data-stu-id="f48bd-107">To implement basic option-button behavior, you must ensure that when an item is selected, you set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property for the previously selected item to `false`.</span></span>  
  
 <span data-ttu-id="f48bd-108">Aşağıdaki yordamlarda, bunu uygulamak açıklanır ve devralınan bir sınıf ek işlevsellik <xref:System.Windows.Forms.ToolStripMenuItem> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="f48bd-108">The following procedures describe how to implement this and additional functionality in a class that inherits the <xref:System.Windows.Forms.ToolStripMenuItem> class.</span></span> <span data-ttu-id="f48bd-109">`ToolStripRadioButtonMenuItem` Sınıfı üyeleri gibi geçersiz kılmalar <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> ve <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> seçim davranışı ve seçenek düğmeleri görünümünü sağlamak için.</span><span class="sxs-lookup"><span data-stu-id="f48bd-109">The `ToolStripRadioButtonMenuItem` class overrides members such as <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> and <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> to provide the selection behavior and appearance of option buttons.</span></span> <span data-ttu-id="f48bd-110">Ayrıca, bu sınıfı geçersiz kılan <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> üst öğe seçili değilse, bir alt menüsünde Seçenekler özelliğini devre dışı.</span><span class="sxs-lookup"><span data-stu-id="f48bd-110">Additionally, this class overrides the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that options on a submenu are disabled unless the parent item is selected.</span></span>  
  
### <a name="to-implement-option-button-selection-behavior"></a><span data-ttu-id="f48bd-111">Seçenek düğmesini seçme davranışı uygulamak için</span><span class="sxs-lookup"><span data-stu-id="f48bd-111">To implement option-button selection behavior</span></span>  
  
1.  <span data-ttu-id="f48bd-112">Başlatma <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> özelliğini `true` öğe seçimini etkinleştirmek için.</span><span class="sxs-lookup"><span data-stu-id="f48bd-112">Initialize the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true` to enable item selection.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#110](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]  
  
2.  <span data-ttu-id="f48bd-113">Geçersiz kılma <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> yöntemi yeni bir öğe seçildiğinde daha önce seçilen öğenin seçimini temizleyin.</span><span class="sxs-lookup"><span data-stu-id="f48bd-113">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> method to clear the selection of the previously selected item when a new item is selected.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#120](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]  
  
3.  <span data-ttu-id="f48bd-114">Geçersiz kılma <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> yöntemi zaten seçildi bir öğe sonuçlandığını emin olmak için değil seçimi temizleyin.</span><span class="sxs-lookup"><span data-stu-id="f48bd-114">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> method to ensure that clicking an item that has already been selected will not clear the selection.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#130](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]  
  
### <a name="to-modify-the-appearance-of-the-option-button-items"></a><span data-ttu-id="f48bd-115">Seçenek düğmesini öğelerin görünümünü değiştirmek için</span><span class="sxs-lookup"><span data-stu-id="f48bd-115">To modify the appearance of the option-button items</span></span>  
  
1.  <span data-ttu-id="f48bd-116">Geçersiz kılma <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> yöntemini kullanarak varsayılan onay işareti ile bir düğmeyi değiştirin <xref:System.Windows.Forms.RadioButtonRenderer> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="f48bd-116">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method to replace the default check-mark with an option button by using the <xref:System.Windows.Forms.RadioButtonRenderer> class.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#140](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]  
  
2.  <span data-ttu-id="f48bd-117">Geçersiz kılma <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, ve <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> fare durumunu izlemek ve emin olmak için yöntemleri <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> yöntemi doğru seçenek düğmesini durumu boyar.</span><span class="sxs-lookup"><span data-stu-id="f48bd-117">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, and <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> methods to track the state of the mouse and ensure that the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method paints the correct option-button state.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#150](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]  
  
### <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a><span data-ttu-id="f48bd-118">Üst öğe seçilmediğinde alt menü seçenekleri devre dışı bırakmak için</span><span class="sxs-lookup"><span data-stu-id="f48bd-118">To disable options on a submenu when the parent item is not selected</span></span>  
  
1.  <span data-ttu-id="f48bd-119">Geçersiz kılma <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> özelliği, böylece her ikisi de sahip bir üst öğesi varsa öğe devre dışı bir <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> değerini `true` ve <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> değerini `false`.</span><span class="sxs-lookup"><span data-stu-id="f48bd-119">Override the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that the item is disabled when it has a parent item with both a <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> value of `true` and a <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> value of `false`.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#160](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]  
  
2.  <span data-ttu-id="f48bd-120">Geçersiz kılma <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> abone olmak için yöntem <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> olay üst öğesi.</span><span class="sxs-lookup"><span data-stu-id="f48bd-120">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> method to subscribe to the <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event of the parent item.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#170](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]  
  
3.  <span data-ttu-id="f48bd-121">Üst öğenin işleyicisinde <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> olay öğe ekranı ile yeni etkin durumu güncelleştirmek için geçersiz.</span><span class="sxs-lookup"><span data-stu-id="f48bd-121">In the handler for the parent-item <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event, invalidate the item to update the display with the new enabled state.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#180](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]  
  
## <a name="example"></a><span data-ttu-id="f48bd-122">Örnek</span><span class="sxs-lookup"><span data-stu-id="f48bd-122">Example</span></span>  
 <span data-ttu-id="f48bd-123">Aşağıdaki kod örneği eksiksiz `ToolStripRadioButtonMenuItem` sınıfı ve <xref:System.Windows.Forms.Form> sınıfı ve `Program` seçenek düğmesini davranışını göstermek için sınıf.</span><span class="sxs-lookup"><span data-stu-id="f48bd-123">The following code example provides the complete `ToolStripRadioButtonMenuItem` class, and a <xref:System.Windows.Forms.Form> class and `Program` class to demonstrate the option-button behavior.</span></span>  
  
 [!code-csharp[ToolStripRadioButtonMenuItem#000](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
 [!code-vb[ToolStripRadioButtonMenuItem#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f48bd-124">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="f48bd-124">Compiling the Code</span></span>  
 <span data-ttu-id="f48bd-125">Bu örnek gerektirir:</span><span class="sxs-lookup"><span data-stu-id="f48bd-125">This example requires:</span></span>  
  
-   <span data-ttu-id="f48bd-126">Sistem, System.Drawing ve System.Windows.Forms derlemelere başvuruları.</span><span class="sxs-lookup"><span data-stu-id="f48bd-126">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f48bd-127">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="f48bd-127">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RadioButtonRenderer>
- [<span data-ttu-id="f48bd-128">MenuStrip Denetimi</span><span class="sxs-lookup"><span data-stu-id="f48bd-128">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
- [<span data-ttu-id="f48bd-129">Nasıl yapılır: Özel ToolStripRenderer uygulama</span><span class="sxs-lookup"><span data-stu-id="f48bd-129">How to: Implement a Custom ToolStripRenderer</span></span>](how-to-implement-a-custom-toolstriprenderer.md)
