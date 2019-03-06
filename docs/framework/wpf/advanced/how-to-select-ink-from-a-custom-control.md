---
title: 'Nasıl yapılır: Özel Denetimden Mürekkep Seçme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ink selection
- ink [WPF], selecting from custom control
- custom controls [WPF], ink selection
ms.assetid: 5f3a45c6-6d40-4017-9b47-933f134ceba3
ms.openlocfilehash: 8517041fd9a1864abfb32851314a2926ddab5a3e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363789"
---
# <a name="how-to-select-ink-from-a-custom-control"></a><span data-ttu-id="74e2c-102">Nasıl yapılır: Özel Denetimden Mürekkep Seçme</span><span class="sxs-lookup"><span data-stu-id="74e2c-102">How to: Select Ink from a Custom Control</span></span>
<span data-ttu-id="74e2c-103">Ekleyerek bir <xref:System.Windows.Ink.IncrementalLassoHitTester> özel denetiminizi kullanıcı benzer şekilde, Serbest Şekil aracı ile mürekkep seçebilmeniz için Denetim etkinleştirebilirsiniz <xref:System.Windows.Controls.InkCanvas> mürekkebi seçer.</span><span class="sxs-lookup"><span data-stu-id="74e2c-103">By adding an <xref:System.Windows.Ink.IncrementalLassoHitTester> to your custom control, you can enable your control so that a user can select ink with a lasso tool, similar to the way the <xref:System.Windows.Controls.InkCanvas> selects ink with a lasso.</span></span>  
  
 <span data-ttu-id="74e2c-104">Bu örnekte, mürekkep özellikli bir özel denetim oluşturma konusunda bilgi sahibi olduğunuz varsayılır.</span><span class="sxs-lookup"><span data-stu-id="74e2c-104">This example assumes you are familiar with creating an ink-enabled custom control.</span></span>  <span data-ttu-id="74e2c-105">Mürekkep giriş kabul eden özel bir denetim oluşturmak için bkz: [mürekkep giriş denetimi oluşturma](creating-an-ink-input-control.md).</span><span class="sxs-lookup"><span data-stu-id="74e2c-105">To create a custom control that accepts ink input, see [Creating an Ink Input Control](creating-an-ink-input-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="74e2c-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="74e2c-106">Example</span></span>  
 <span data-ttu-id="74e2c-107">Kullanıcı bir Serbest Şekil çizdiğinde <xref:System.Windows.Ink.IncrementalLassoHitTester> kullanıcı Serbest Şekil tamamlandıktan sonra hangi strokes Serbest Şekil yolunun sınırları içinde olacak tahmin eder.</span><span class="sxs-lookup"><span data-stu-id="74e2c-107">When the user draws a lasso, the <xref:System.Windows.Ink.IncrementalLassoHitTester> predicts which strokes will be within the lasso path's boundaries after the user completes the lasso.</span></span>  <span data-ttu-id="74e2c-108">Serbest Şekil yolunun sınırları içinde olacak şekilde belirlenir strokes, seçili olarak düşünülebilir.</span><span class="sxs-lookup"><span data-stu-id="74e2c-108">Strokes that are determined to be within the lasso path's boundaries can be thought of as being selected.</span></span>  <span data-ttu-id="74e2c-109">Seçili vuruşların seçilmemiş olabilir.</span><span class="sxs-lookup"><span data-stu-id="74e2c-109">Selected strokes can also become unselected.</span></span>  <span data-ttu-id="74e2c-110">Örneğin, kullanıcı Serbest Şekil çizim sırasında yön tersine döner <xref:System.Windows.Ink.IncrementalLassoHitTester> bazı vuruşları seçimden.</span><span class="sxs-lookup"><span data-stu-id="74e2c-110">For example, if the user reverses direction while drawing the lasso, the <xref:System.Windows.Ink.IncrementalLassoHitTester> may unselect some strokes.</span></span>  
  
 <span data-ttu-id="74e2c-111"><xref:System.Windows.Ink.IncrementalLassoHitTester> Başlatır <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> özel denetiminizin kullanıcı, serbest şekil çizme sırasında yanıt vermesini sağlayan olay.</span><span class="sxs-lookup"><span data-stu-id="74e2c-111">The <xref:System.Windows.Ink.IncrementalLassoHitTester> raises the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> event, which enables your custom control to respond while the user is drawing the lasso.</span></span>  <span data-ttu-id="74e2c-112">Örneğin, kullanıcının seçer ve bunları seçili olanları kaldırdığında vuruşlarının görünümünü değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="74e2c-112">For example, you can change the appearance of strokes as the user selects and unselects them.</span></span>  
  
## <a name="managing-the-ink-mode"></a><span data-ttu-id="74e2c-113">Mürekkep modunu yönetme</span><span class="sxs-lookup"><span data-stu-id="74e2c-113">Managing the Ink Mode</span></span>  
 <span data-ttu-id="74e2c-114">Serbest Şekil, denetim üzerinde mürekkep farklı görünürse kullanıcıya yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="74e2c-114">It is helpful to the user if the lasso appears differently than the ink on your control.</span></span> <span data-ttu-id="74e2c-115">Bunu gerçekleştirmek için özel denetiminizi kullanıcı yazma ya da mürekkep seçme izlemek gerekir.</span><span class="sxs-lookup"><span data-stu-id="74e2c-115">To accomplish this, your custom control must keep track of whether the user is writing or selecting ink.</span></span> <span data-ttu-id="74e2c-116">İki değer içeren bir numaralandırmayı bildirmek için bunu yapmanın en kolay yolu olan: bir kullanıcı mürekkep ve kullanıcı mürekkep seçtiğini gösteren yazma belirtmek için.</span><span class="sxs-lookup"><span data-stu-id="74e2c-116">The easiest way to do this is to declare an enumeration with two values: one to indicate that the user is writing ink and one to indicate that the user is selecting ink.</span></span>  
  
 [!code-csharp[HowToSelectInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#2)]
 [!code-vb[HowToSelectInk#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#2)]  
  
 <span data-ttu-id="74e2c-117">Ardından, iki ekleyin <xref:System.Windows.Ink.DrawingAttributes> sınıfa: bir kullanıcının kullanıcı mürekkep seçtiğinde kullanacağıma mürekkep yazarken kullanılacak.</span><span class="sxs-lookup"><span data-stu-id="74e2c-117">Next, add two <xref:System.Windows.Ink.DrawingAttributes> to the class: one to use when the user writes ink, one to use when the user selects ink.</span></span>  <span data-ttu-id="74e2c-118">Oluşturucuda başlatmak <xref:System.Windows.Ink.DrawingAttributes> ve her iki <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> aynı olay işleyicisi olayları.</span><span class="sxs-lookup"><span data-stu-id="74e2c-118">In the constructor, initialize the <xref:System.Windows.Ink.DrawingAttributes> and attach both <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> events to the same event handler.</span></span> <span data-ttu-id="74e2c-119">Ardından <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> özelliği <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> mürekkep <xref:System.Windows.Ink.DrawingAttributes>.</span><span class="sxs-lookup"><span data-stu-id="74e2c-119">Then set the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> property of the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the ink <xref:System.Windows.Ink.DrawingAttributes>.</span></span>  
  
 [!code-csharp[HowToSelectInk#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#3)]
 [!code-vb[HowToSelectInk#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#3)]  
[!code-csharp[HowToSelectInk#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#4)]
[!code-vb[HowToSelectInk#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#4)]  
  
 <span data-ttu-id="74e2c-120">Seçim modunu kullanıma sunduğu özellik ekleyin.</span><span class="sxs-lookup"><span data-stu-id="74e2c-120">Add a property that exposes the selection mode.</span></span> <span data-ttu-id="74e2c-121">Kullanıcı seçim modu değiştiğinde ayarlamak <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> özelliği <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> uygun <xref:System.Windows.Ink.DrawingAttributes> nesnesi ve ardından yeniden <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> özelliğini <xref:System.Windows.Controls.InkPresenter>.</span><span class="sxs-lookup"><span data-stu-id="74e2c-121">When the user changes the selection mode, set the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> property of the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the appropriate <xref:System.Windows.Ink.DrawingAttributes> object and then reattach the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> Property to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
 [!code-csharp[HowToSelectInk#5](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#5)]
 [!code-vb[HowToSelectInk#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#5)]  
  
 <span data-ttu-id="74e2c-122">Kullanıma sunma <xref:System.Windows.Ink.DrawingAttributes> özellikleri, böylece uygulamalar mürekkep ve seçim vuruşlarını görünümünü belirleyebilir.</span><span class="sxs-lookup"><span data-stu-id="74e2c-122">Expose the <xref:System.Windows.Ink.DrawingAttributes> as properties so applications can determine the appearance of the ink strokes and selection strokes.</span></span>  
  
 [!code-csharp[HowToSelectInk#6](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#6)]
 [!code-vb[HowToSelectInk#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#6)]  
  
 <span data-ttu-id="74e2c-123">Özelliği bir <xref:System.Windows.Ink.DrawingAttributes> değişiklikleri, nesne <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> iliştirilmesi gerekir <xref:System.Windows.Controls.InkPresenter>.</span><span class="sxs-lookup"><span data-stu-id="74e2c-123">When a property of a <xref:System.Windows.Ink.DrawingAttributes> object changes, the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> must be reattached to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  <span data-ttu-id="74e2c-124">İçin olay işleyicisinde <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> olay ekleyemediği <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> için <xref:System.Windows.Controls.InkPresenter>.</span><span class="sxs-lookup"><span data-stu-id="74e2c-124">In the event handler for the <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> event, reattach the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
 [!code-csharp[HowToSelectInk#7](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#7)]
 [!code-vb[HowToSelectInk#7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#7)]  
  
## <a name="using-the-incrementallassohittester"></a><span data-ttu-id="74e2c-125">IncrementalLassoHitTester kullanma</span><span class="sxs-lookup"><span data-stu-id="74e2c-125">Using the IncrementalLassoHitTester</span></span>  
 <span data-ttu-id="74e2c-126">Oluşturma ve başlatma bir <xref:System.Windows.Ink.StrokeCollection> , seçili vuruşların içerir.</span><span class="sxs-lookup"><span data-stu-id="74e2c-126">Create and initialize a <xref:System.Windows.Ink.StrokeCollection> that contains the selected strokes.</span></span>  
  
 [!code-csharp[HowToSelectInk#8](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#8)]
 [!code-vb[HowToSelectInk#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#8)]  
  
 <span data-ttu-id="74e2c-127">Kullanıcı bir fırça çizmek başladığında mürekkep veya Serbest Şekil seçili vuruşların seçimini kaldırın.</span><span class="sxs-lookup"><span data-stu-id="74e2c-127">When the user starts to draw a stroke, either ink or the lasso, unselect any selected strokes.</span></span> <span data-ttu-id="74e2c-128">Ardından, kullanıcı, bir serbest şekil çizme, oluşturun bir <xref:System.Windows.Ink.IncrementalLassoHitTester> çağırarak <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A>, abone <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> olay ve arama <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A>.</span><span class="sxs-lookup"><span data-stu-id="74e2c-128">Then, if the user is drawing a lasso, create an <xref:System.Windows.Ink.IncrementalLassoHitTester> by calling <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A>, subscribe to the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> event, and call <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A>.</span></span> <span data-ttu-id="74e2c-129">Bu kodu ayrı bir yöntem olabilir ve çağrılır <xref:System.Windows.UIElement.OnStylusDown%2A> ve <xref:System.Windows.UIElement.OnMouseDown%2A> yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="74e2c-129">This code can be a separate method and called from the <xref:System.Windows.UIElement.OnStylusDown%2A> and <xref:System.Windows.UIElement.OnMouseDown%2A> methods.</span></span>  
  
 [!code-csharp[HowToSelectInk#9](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#9)]
 [!code-vb[HowToSelectInk#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#9)]  
  
 <span data-ttu-id="74e2c-130">Ekran kalemi işaret ekleme <xref:System.Windows.Ink.IncrementalLassoHitTester> sırada kullanıcının Serbest Şekil çizer.</span><span class="sxs-lookup"><span data-stu-id="74e2c-130">Add the stylus points to the <xref:System.Windows.Ink.IncrementalLassoHitTester> while the user draws the lasso.</span></span>  <span data-ttu-id="74e2c-131">Aşağıdaki yöntemi çağırın <xref:System.Windows.UIElement.OnStylusMove%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, <xref:System.Windows.UIElement.OnMouseMove%2A>, ve <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="74e2c-131">Call the following method from the <xref:System.Windows.UIElement.OnStylusMove%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, <xref:System.Windows.UIElement.OnMouseMove%2A>, and <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> methods.</span></span>  
  
 [!code-csharp[HowToSelectInk#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#10)]
 [!code-vb[HowToSelectInk#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#10)]  
  
 <span data-ttu-id="74e2c-132">Tanıtıcı <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=nameWithType> kullanıcı seçer ve vuruş seçili olanları kaldırdığında geldiğinde olay.</span><span class="sxs-lookup"><span data-stu-id="74e2c-132">Handle the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=nameWithType> event to respond when the user selects and unselects strokes.</span></span>  <span data-ttu-id="74e2c-133"><xref:System.Windows.Ink.LassoSelectionChangedEventArgs> Sınıfında <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A> ve <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A> vuruşları özellikleri seçili olan ve seçili, sırasıyla.</span><span class="sxs-lookup"><span data-stu-id="74e2c-133">The <xref:System.Windows.Ink.LassoSelectionChangedEventArgs> class has the <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A> and <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A> properties that get the strokes that were selected and unselected, respectively.</span></span>  
  
 [!code-csharp[HowToSelectInk#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#11)]
 [!code-vb[HowToSelectInk#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#11)]  
  
 <span data-ttu-id="74e2c-134">Kullanıcı serbest şekil çizme tamamlandığında, aboneliğinizi <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> olay ve arama <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A>.</span><span class="sxs-lookup"><span data-stu-id="74e2c-134">When the user finishes drawing the lasso, unsubscribe from the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> event and call <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A>.</span></span>  
  
 [!code-csharp[HowToSelectInk#12](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#12)]
 [!code-vb[HowToSelectInk#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#12)]  
  
## <a name="putting-it-all-together"></a><span data-ttu-id="74e2c-135">Hepsini birleştirme.</span><span class="sxs-lookup"><span data-stu-id="74e2c-135">Putting it All Together.</span></span>  
 <span data-ttu-id="74e2c-136">Aşağıdaki örnek, kullanıcının mürekkebi seçmesini sağlayan özel bir denetimdir.</span><span class="sxs-lookup"><span data-stu-id="74e2c-136">The following example is a custom control that enables a user to select ink with a lasso.</span></span>  
  
 [!code-csharp[HowToSelectInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#1)]
 [!code-vb[HowToSelectInk#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="74e2c-137">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="74e2c-137">See also</span></span>
- <xref:System.Windows.Ink.IncrementalLassoHitTester>
- <xref:System.Windows.Ink.StrokeCollection>
- <xref:System.Windows.Input.StylusPointCollection>
- [<span data-ttu-id="74e2c-138">Mürekkep Giriş Denetimi Oluşturma</span><span class="sxs-lookup"><span data-stu-id="74e2c-138">Creating an Ink Input Control</span></span>](creating-an-ink-input-control.md)
