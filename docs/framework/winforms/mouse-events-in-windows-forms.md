---
title: Windows Forms'ta Fare Olayları
ms.date: 03/30/2017
helpviewer_keywords:
- MouseLeave event [Windows Forms]
- events [Windows Forms], mouse
- Click event [Windows Forms], raising order
- Windows Forms controls, click events
- MouseDoubleClick event [Windows Forms]
- MouseEnter event [Windows Forms]
- MouseHover event [Windows Forms]
- MouseDown event [Windows Forms]
- MouseClick event [Windows Forms]
- MouseMove event [Windows Forms]
- mouse [Windows Forms], events
- MouseUp event
ms.assetid: 8cf0070d-793b-4876-b09e-d20d28280fab
ms.openlocfilehash: 818364ceddb03df51ed656c8ff7b69fd433ac86a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64750880"
---
# <a name="mouse-events-in-windows-forms"></a><span data-ttu-id="c7658-102">Windows Forms'ta Fare Olayları</span><span class="sxs-lookup"><span data-stu-id="c7658-102">Mouse Events in Windows Forms</span></span>

<span data-ttu-id="c7658-103">Fare girişi işlediğinizde, genellikle işaretçi ve farenin düğme durumunu fare konumunu bilmek ister.</span><span class="sxs-lookup"><span data-stu-id="c7658-103">When you handle mouse input, you usually want to know the location of the mouse pointer and the state of the mouse buttons.</span></span> <span data-ttu-id="c7658-104">Bu konu, fare olayları bu bilgiler edinme hakkında ayrıntılı bilgi sağlar ve Windows Forms denetimlerinde tetiklenen hangi fare tıklatın olayları siparişi açıklar.</span><span class="sxs-lookup"><span data-stu-id="c7658-104">This topic provides details on how to get this information from mouse events, and explains the order in which mouse click events are raised in Windows Forms controls.</span></span> <span data-ttu-id="c7658-105">Bir listesi ve açıklamaları tüm fare olayları için bkz. [nasıl Windows Forms'ta fare girdisi çalışır](how-mouse-input-works-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="c7658-105">For a list and description of all of the mouse events, see [How Mouse Input Works in Windows Forms](how-mouse-input-works-in-windows-forms.md).</span></span>  <span data-ttu-id="c7658-106">Ayrıca bkz: [olay işleyicilerine genel bakış (Windows Forms)](event-handlers-overview-windows-forms.md) ve [olaylara genel bakış (Windows Forms)](events-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="c7658-106">Also see [Event Handlers Overview (Windows Forms)](event-handlers-overview-windows-forms.md) and [Events Overview (Windows Forms)](events-overview-windows-forms.md).</span></span>

## <a name="mouse-information"></a><span data-ttu-id="c7658-107">Fare bilgileri</span><span class="sxs-lookup"><span data-stu-id="c7658-107">Mouse Information</span></span>

<span data-ttu-id="c7658-108">A <xref:System.Windows.Forms.MouseEventArgs> fare etkinliklerinin bir fare düğmesine tıklamak ve fare hareketlerini izleme ile ilgili işleyicileri gönderilir.</span><span class="sxs-lookup"><span data-stu-id="c7658-108">A <xref:System.Windows.Forms.MouseEventArgs> is sent to the handlers of mouse events related to clicking a mouse button and tracking mouse movements.</span></span> <span data-ttu-id="c7658-109"><xref:System.Windows.Forms.MouseEventArgs> Fare işaretçisi konumunu fare düğmesini basılı ve fare tekerleğini olup kaydırılan istemci koordinatlarında dahil olmak üzere fareyi geçerli durumu hakkında bilgi sağlar.</span><span class="sxs-lookup"><span data-stu-id="c7658-109"><xref:System.Windows.Forms.MouseEventArgs> provides information about the current state of the mouse, including the location of the mouse pointer in client coordinates, which mouse buttons are pressed, and whether the mouse wheel has scrolled.</span></span> <span data-ttu-id="c7658-110">Birkaç fare olayları, yalnızca bildir olanlar gibi fare işaretçisi girilen veya denetimin sınırları sol, gönderme bir <xref:System.EventArgs> olay işleyicisi ile daha fazla bilgi için.</span><span class="sxs-lookup"><span data-stu-id="c7658-110">Several mouse events, such as those that simply notify when the mouse pointer has entered or left the bounds of a control, send an <xref:System.EventArgs> to the event handler with no further information.</span></span>

<span data-ttu-id="c7658-111">Geçerli durumunu fare düğmesini veya fare işaretçisi konumunu bilmek istiyorsunuz ve bir fare olayına işleme önlemek istiyorsanız, ayrıca <xref:System.Windows.Forms.Control.MouseButtons%2A> ve <xref:System.Windows.Forms.Control.MousePosition%2A> özelliklerini <xref:System.Windows.Forms.Control> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="c7658-111">If you want to know the current state of the mouse buttons or the location of the mouse pointer, and you want to avoid handling a mouse event, you can also use the <xref:System.Windows.Forms.Control.MouseButtons%2A> and <xref:System.Windows.Forms.Control.MousePosition%2A> properties of the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="c7658-112"><xref:System.Windows.Forms.Control.MouseButtons%2A> hangi şu anda fare düğmelere basıldığında bilgileri döndürür.</span><span class="sxs-lookup"><span data-stu-id="c7658-112"><xref:System.Windows.Forms.Control.MouseButtons%2A> returns information about which mouse buttons are currently pressed.</span></span> <span data-ttu-id="c7658-113"><xref:System.Windows.Forms.Control.MousePosition%2A> Fare işaretçisi ekran koordinatlarını döndürür ve tarafından döndürülen değere eşdeğer bir gruba <xref:System.Windows.Forms.Cursor.Position%2A>.</span><span class="sxs-lookup"><span data-stu-id="c7658-113">The <xref:System.Windows.Forms.Control.MousePosition%2A> returns the screen coordinates of the mouse pointer and is equivalent to the value returned by <xref:System.Windows.Forms.Cursor.Position%2A>.</span></span>

## <a name="converting-between-screen-and-client-coordinates"></a><span data-ttu-id="c7658-114">Ekran ve istemci arasında dönüştürme koordinatları</span><span class="sxs-lookup"><span data-stu-id="c7658-114">Converting Between Screen and Client Coordinates</span></span>

<span data-ttu-id="c7658-115">Bazı fare konum bilgilerini istemci koordinatlarını ve bazı ekran koordinatlarında olduğundan, bir nokta bir koordinat sistemini dönüştürmek gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="c7658-115">Because some mouse location information is in client coordinates and some is in screen coordinates, you may need to convert a point from one coordinate system to the other.</span></span> <span data-ttu-id="c7658-116">Kolayca kullanarak bunu yapabilirsiniz <xref:System.Windows.Forms.Control.PointToClient%2A> ve <xref:System.Windows.Forms.Control.PointToScreen%2A> yöntemleri üzerinde kullanılabilir <xref:System.Windows.Forms.Control> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="c7658-116">You can do this easily by using the <xref:System.Windows.Forms.Control.PointToClient%2A> and <xref:System.Windows.Forms.Control.PointToScreen%2A> methods available on the <xref:System.Windows.Forms.Control> class.</span></span>

## <a name="standard-click-event-behavior"></a><span data-ttu-id="c7658-117">Standart tıklatma olay davranışı</span><span class="sxs-lookup"><span data-stu-id="c7658-117">Standard Click Event Behavior</span></span>

<span data-ttu-id="c7658-118">Kullanmak istediğiniz fare tıklatın doğru sırada olayları, Windows Forms denetimlerinde tetiklenen hangi tıklama olayları sırasını bilmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="c7658-118">If you want to handle mouse click events in the proper order, you need to know the order in which click events are raised in Windows Forms controls.</span></span> <span data-ttu-id="c7658-119">Bir fare düğmesi basılı olduğunda ve tek tek denetimler için aşağıdaki listede belirtilmedikçe (hangi fare düğmesi bağımsız olarak), yayımlanan olayların aynı sırayla tüm Windows Formları denetimleri Yükselt'e tıklayın.</span><span class="sxs-lookup"><span data-stu-id="c7658-119">All Windows Forms controls raise click events in the same order when a mouse button is pressed and released (regardless of which mouse button), except where noted in the following list for individual controls.</span></span> <span data-ttu-id="c7658-120">Aşağıdaki liste için tek fare düğmesini tıklatın yükseltilmiş olayların sırası gösterir:</span><span class="sxs-lookup"><span data-stu-id="c7658-120">The following list shows the order of events raised for a single mouse-button click:</span></span>

1. <span data-ttu-id="c7658-121"><xref:System.Windows.Forms.Control.MouseDown> olay.</span><span class="sxs-lookup"><span data-stu-id="c7658-121"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>

2. <span data-ttu-id="c7658-122"><xref:System.Windows.Forms.Control.Click> olay.</span><span class="sxs-lookup"><span data-stu-id="c7658-122"><xref:System.Windows.Forms.Control.Click> event.</span></span>

3. <span data-ttu-id="c7658-123"><xref:System.Windows.Forms.Control.MouseClick> olay.</span><span class="sxs-lookup"><span data-stu-id="c7658-123"><xref:System.Windows.Forms.Control.MouseClick> event.</span></span>

4. <span data-ttu-id="c7658-124"><xref:System.Windows.Forms.Control.MouseUp> olay.</span><span class="sxs-lookup"><span data-stu-id="c7658-124"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>

<span data-ttu-id="c7658-125">İçin bir fare düğmesine çift tıklayın yükseltilmiş olayların sırası aşağıda verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="c7658-125">Following is the order of events raised for a double mouse-button click:</span></span>

1. <span data-ttu-id="c7658-126"><xref:System.Windows.Forms.Control.MouseDown> olay.</span><span class="sxs-lookup"><span data-stu-id="c7658-126"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>

2. <span data-ttu-id="c7658-127"><xref:System.Windows.Forms.Control.Click> olay.</span><span class="sxs-lookup"><span data-stu-id="c7658-127"><xref:System.Windows.Forms.Control.Click> event.</span></span>

3. <span data-ttu-id="c7658-128"><xref:System.Windows.Forms.Control.MouseClick> olay.</span><span class="sxs-lookup"><span data-stu-id="c7658-128"><xref:System.Windows.Forms.Control.MouseClick> event.</span></span>

4. <span data-ttu-id="c7658-129"><xref:System.Windows.Forms.Control.MouseUp> olay.</span><span class="sxs-lookup"><span data-stu-id="c7658-129"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>

5. <span data-ttu-id="c7658-130"><xref:System.Windows.Forms.Control.MouseDown> olay.</span><span class="sxs-lookup"><span data-stu-id="c7658-130"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>

6. <span data-ttu-id="c7658-131"><xref:System.Windows.Forms.Control.DoubleClick> olay.</span><span class="sxs-lookup"><span data-stu-id="c7658-131"><xref:System.Windows.Forms.Control.DoubleClick> event.</span></span> <span data-ttu-id="c7658-132">(Bu, söz konusu denetim olup bağlı olarak değişebilir <xref:System.Windows.Forms.ControlStyles.StandardDoubleClick> stili biti ayarlanmış `true`.</span><span class="sxs-lookup"><span data-stu-id="c7658-132">(This can vary, depending on whether the control in question has the <xref:System.Windows.Forms.ControlStyles.StandardDoubleClick> style bit set to `true`.</span></span> <span data-ttu-id="c7658-133">Nasıl ayarlanacağı hakkında daha fazla bilgi için bir <xref:System.Windows.Forms.ControlStyles> bit için bkz: <xref:System.Windows.Forms.Control.SetStyle%2A> yöntemi.)</span><span class="sxs-lookup"><span data-stu-id="c7658-133">For more information about how to set a <xref:System.Windows.Forms.ControlStyles> bit, see the <xref:System.Windows.Forms.Control.SetStyle%2A> method.)</span></span>

7. <span data-ttu-id="c7658-134"><xref:System.Windows.Forms.Control.MouseDoubleClick> olay.</span><span class="sxs-lookup"><span data-stu-id="c7658-134"><xref:System.Windows.Forms.Control.MouseDoubleClick> event.</span></span>

8. <span data-ttu-id="c7658-135"><xref:System.Windows.Forms.Control.MouseUp> olay.</span><span class="sxs-lookup"><span data-stu-id="c7658-135"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>

<span data-ttu-id="c7658-136">Tıklama olayları fare düzenini gösteren bir kod örneği için bkz: [nasıl yapılır: Tanıtıcı kullanıcı girdi olaylarını Windows Forms denetimlerine](how-to-handle-user-input-events-in-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="c7658-136">For a code example that demonstrates the order of the mouse click events, see [How to: Handle User Input Events in Windows Forms Controls](how-to-handle-user-input-events-in-windows-forms-controls.md).</span></span>

### <a name="individual-controls"></a><span data-ttu-id="c7658-137">Tek denetimleri</span><span class="sxs-lookup"><span data-stu-id="c7658-137">Individual Controls</span></span>

<span data-ttu-id="c7658-138">Aşağıdaki denetimler için standart fare uymayan olay davranışı:</span><span class="sxs-lookup"><span data-stu-id="c7658-138">The following controls do not conform to the standard mouse click event behavior:</span></span>

- <span data-ttu-id="c7658-139"><xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.ComboBox>, ve <xref:System.Windows.Forms.RadioButton> denetimleri</span><span class="sxs-lookup"><span data-stu-id="c7658-139"><xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.ComboBox>, and <xref:System.Windows.Forms.RadioButton> controls</span></span>

  > [!NOTE]
  > <span data-ttu-id="c7658-140">İçin <xref:System.Windows.Forms.ComboBox> denetim daha sonra ayrıntılı olay davranış oluşur kullanıcı düzenleme alanı, düğmeyi veya bir öğe listede tıklarsa.</span><span class="sxs-lookup"><span data-stu-id="c7658-140">For the <xref:System.Windows.Forms.ComboBox> control, the event behavior detailed later occurs if the user clicks on the edit field, the button, or on an item within the list.</span></span>

  - <span data-ttu-id="c7658-141">Sol tıklama: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="c7658-141">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="c7658-142">Sağ tıklayın: Yükseltilmiş click olayı yok</span><span class="sxs-lookup"><span data-stu-id="c7658-142">Right click: No click events raised</span></span>

  - <span data-ttu-id="c7658-143">Sol çift: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="c7658-143">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="c7658-144">Çift tıklatın doğru: Yükseltilmiş click olayı yok</span><span class="sxs-lookup"><span data-stu-id="c7658-144">Right double-click: No click events raised</span></span>

- <span data-ttu-id="c7658-145"><xref:System.Windows.Forms.TextBox>, <xref:System.Windows.Forms.RichTextBox>, <xref:System.Windows.Forms.ListBox>, <xref:System.Windows.Forms.MaskedTextBox>, ve <xref:System.Windows.Forms.CheckedListBox> denetimleri</span><span class="sxs-lookup"><span data-stu-id="c7658-145"><xref:System.Windows.Forms.TextBox>, <xref:System.Windows.Forms.RichTextBox>, <xref:System.Windows.Forms.ListBox>, <xref:System.Windows.Forms.MaskedTextBox>, and <xref:System.Windows.Forms.CheckedListBox> controls</span></span>

  > [!NOTE]
  > <span data-ttu-id="c7658-146">Daha sonra ayrıntılı olay davranışı, kullanıcı bu denetimleri içinde herhangi bir yere tıkladığında gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="c7658-146">The event behavior detailed later occurs when the user clicks anywhere within these controls.</span></span>

  - <span data-ttu-id="c7658-147">Sol tıklama: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="c7658-147">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="c7658-148">Sağ tıklayın: Yükseltilmiş click olayı yok</span><span class="sxs-lookup"><span data-stu-id="c7658-148">Right click: No click events raised</span></span>

  - <span data-ttu-id="c7658-149">Sol çift: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="c7658-149">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

  - <span data-ttu-id="c7658-150">Çift tıklatın doğru: Yükseltilmiş click olayı yok</span><span class="sxs-lookup"><span data-stu-id="c7658-150">Right double-click: No click events raised</span></span>

- <span data-ttu-id="c7658-151"><xref:System.Windows.Forms.ListView> Denetimi</span><span class="sxs-lookup"><span data-stu-id="c7658-151"><xref:System.Windows.Forms.ListView> control</span></span>

  > [!NOTE]
  > <span data-ttu-id="c7658-152">Daha sonra ayrıntılı olay yalnızca kullanıcı öğelerde tıkladığında davranış <xref:System.Windows.Forms.ListView> denetimi.</span><span class="sxs-lookup"><span data-stu-id="c7658-152">The event behavior detailed later occurs only when the user clicks on the items in the <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="c7658-153">Tıklama denetimi başka bir yerde için hiçbir olay harekete geçirilir.</span><span class="sxs-lookup"><span data-stu-id="c7658-153">No events are raised for clicks anywhere else on the control.</span></span> <span data-ttu-id="c7658-154">Daha sonra açıklanan olaylarına ilaveten vardır <xref:System.Windows.Forms.ListView.BeforeLabelEdit> ve <xref:System.Windows.Forms.ListView.AfterLabelEdit> ile doğrulama kullanmak istiyorsanız, ilginizi çekebilecek olayları <xref:System.Windows.Forms.ListView> denetimi.</span><span class="sxs-lookup"><span data-stu-id="c7658-154">In addition to the events described later, there are the <xref:System.Windows.Forms.ListView.BeforeLabelEdit> and <xref:System.Windows.Forms.ListView.AfterLabelEdit> events, which may be of interest to you if you want to use validation with the <xref:System.Windows.Forms.ListView> control.</span></span>

  - <span data-ttu-id="c7658-155">Sol tıklama: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="c7658-155">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="c7658-156">Sağ tıklayın: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="c7658-156">Right click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="c7658-157">Sol çift: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="c7658-157">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

  - <span data-ttu-id="c7658-158">Sağa çift: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="c7658-158">Right double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

- <span data-ttu-id="c7658-159"><xref:System.Windows.Forms.TreeView> Denetimi</span><span class="sxs-lookup"><span data-stu-id="c7658-159"><xref:System.Windows.Forms.TreeView> control</span></span>

  > [!NOTE]
  > <span data-ttu-id="c7658-160">Daha sonra ayrıntılı olay yalnızca kullanıcı öğeleri veya öğeleri sağındaki tıkladığında davranış <xref:System.Windows.Forms.TreeView> denetimi.</span><span class="sxs-lookup"><span data-stu-id="c7658-160">The event behavior detailed later occurs only when the user clicks on the items themselves or to the right of the items in the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="c7658-161">Tıklama denetimi başka bir yerde için hiçbir olay harekete geçirilir.</span><span class="sxs-lookup"><span data-stu-id="c7658-161">No events are raised for clicks anywhere else on the control.</span></span> <span data-ttu-id="c7658-162">Açıklanana yanı sıra daha sonra vardır <xref:System.Windows.Forms.TreeView.BeforeCheck>, <xref:System.Windows.Forms.TreeView.BeforeSelect>, <xref:System.Windows.Forms.TreeView.BeforeLabelEdit>, <xref:System.Windows.Forms.TreeView.AfterSelect>, <xref:System.Windows.Forms.TreeView.AfterCheck>, ve <xref:System.Windows.Forms.TreeView.AfterLabelEdit> ile doğrulama kullanmak istiyorsanız, ilginizi çekebilecek olayları <xref:System.Windows.Forms.TreeView> denetimi .</span><span class="sxs-lookup"><span data-stu-id="c7658-162">In addition to those described later, there are the <xref:System.Windows.Forms.TreeView.BeforeCheck>, <xref:System.Windows.Forms.TreeView.BeforeSelect>, <xref:System.Windows.Forms.TreeView.BeforeLabelEdit>, <xref:System.Windows.Forms.TreeView.AfterSelect>, <xref:System.Windows.Forms.TreeView.AfterCheck>, and <xref:System.Windows.Forms.TreeView.AfterLabelEdit> events, which may be of interest to you if you want to use validation with the <xref:System.Windows.Forms.TreeView> control.</span></span>

  - <span data-ttu-id="c7658-163">Sol tıklama: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="c7658-163">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="c7658-164">Sağ tıklayın: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="c7658-164">Right click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="c7658-165">Sol çift: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="c7658-165">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

  - <span data-ttu-id="c7658-166">Sağa çift: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="c7658-166">Right double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

### <a name="painting-behavior-of-toggle-controls"></a><span data-ttu-id="c7658-167">İki durumlu denetimleri davranışını boyama</span><span class="sxs-lookup"><span data-stu-id="c7658-167">Painting Behavior of Toggle Controls</span></span>

<span data-ttu-id="c7658-168">Geçiş türetme denetimleri gibi denetimleri <xref:System.Windows.Forms.ButtonBase> sınıfı, tıklama olayları aşağıdaki farklı boyama davranış fare ile birlikte sahiptir:</span><span class="sxs-lookup"><span data-stu-id="c7658-168">Toggle controls, such as the controls deriving from the <xref:System.Windows.Forms.ButtonBase> class, have the following distinctive painting behavior in combination with mouse click events:</span></span>

1. <span data-ttu-id="c7658-169">Kullanıcı fare düğmesine bastığında.</span><span class="sxs-lookup"><span data-stu-id="c7658-169">The user presses the mouse button.</span></span>

2. <span data-ttu-id="c7658-170">Basılan durumda denetimi boyar.</span><span class="sxs-lookup"><span data-stu-id="c7658-170">The control paints in the pressed state.</span></span>

3. <span data-ttu-id="c7658-171"><xref:System.Windows.Forms.Control.MouseDown> Olayı oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="c7658-171">The <xref:System.Windows.Forms.Control.MouseDown> event is raised.</span></span>

4. <span data-ttu-id="c7658-172">Kullanıcı, fare düğmesini serbest bırakır.</span><span class="sxs-lookup"><span data-stu-id="c7658-172">The user releases the mouse button.</span></span>

5. <span data-ttu-id="c7658-173">Yükseltilmiş durumunda denetimi boyar.</span><span class="sxs-lookup"><span data-stu-id="c7658-173">The control paints in the raised state.</span></span>

6. <span data-ttu-id="c7658-174"><xref:System.Windows.Forms.Control.Click> Olayı oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="c7658-174">The <xref:System.Windows.Forms.Control.Click> event is raised.</span></span>

7. <span data-ttu-id="c7658-175"><xref:System.Windows.Forms.Control.MouseClick> Olayı oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="c7658-175">The <xref:System.Windows.Forms.Control.MouseClick> event is raised.</span></span>

8. <span data-ttu-id="c7658-176"><xref:System.Windows.Forms.Control.MouseUp> Olayı oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="c7658-176">The <xref:System.Windows.Forms.Control.MouseUp> event is raised.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="c7658-177">Kullanıcı fare düğmesini basılı durumdayken işaretçiyi iki durumlu denetimin dışına taşınırsa (fareyi hareket gibi <xref:System.Windows.Forms.Button> , basılı durumdayken denetim), iki durumlu denetimin yükseltilmiş boyama durum ve yalnızca <xref:System.Windows.Forms.Control.MouseUp> olayı oluşur.</span><span class="sxs-lookup"><span data-stu-id="c7658-177">If the user moves the pointer out of the toggle control while the mouse button is down (such as moving the mouse off the <xref:System.Windows.Forms.Button> control while it is pressed), the toggle control will paint in the raised state and only the <xref:System.Windows.Forms.Control.MouseUp> event occurs.</span></span> <span data-ttu-id="c7658-178"><xref:System.Windows.Forms.Control.Click> Veya <xref:System.Windows.Forms.Control.MouseClick> olayları, bu durumda gerçekleşmez.</span><span class="sxs-lookup"><span data-stu-id="c7658-178">The <xref:System.Windows.Forms.Control.Click> or <xref:System.Windows.Forms.Control.MouseClick> events will not occur in this situation.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7658-179">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="c7658-179">See also</span></span>

- [<span data-ttu-id="c7658-180">Bir Windows Forms Uygulamasında Fare Girdisi</span><span class="sxs-lookup"><span data-stu-id="c7658-180">Mouse Input in a Windows Forms Application</span></span>](mouse-input-in-a-windows-forms-application.md)
