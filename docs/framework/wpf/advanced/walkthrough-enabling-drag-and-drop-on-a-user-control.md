---
title: 'İzlenecek yol: Sürükleme ve bırakmayı kullanıcı denetiminde etkinleştirme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthrough [WPF], drag-and-drop
- drag-and-drop [WPF], walkthrough
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
ms.openlocfilehash: 9ffaab4115edec1fc0115b27b8904970854f79d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600680"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a><span data-ttu-id="4cd31-102">İzlenecek yol: Sürükleme ve bırakmayı kullanıcı denetiminde etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="4cd31-102">Walkthrough: Enabling Drag and Drop on a User Control</span></span>

<span data-ttu-id="4cd31-103">Bu izlenecek yol, sürükle ve bırak veri aktarımı katılabilen özel bir kullanıcı denetimi oluşturmak gösterilmiştir [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4cd31-103">This walkthrough demonstrates how to create a custom user control that can participate in drag-and-drop data transfer in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>

<span data-ttu-id="4cd31-104">Bu kılavuzda, özel bir WPF oluşturacağınız <xref:System.Windows.Controls.UserControl> temsil eden bir daire şeklinde.</span><span class="sxs-lookup"><span data-stu-id="4cd31-104">In this walkthrough, you will create a custom WPF <xref:System.Windows.Controls.UserControl> that represents a circle shape.</span></span> <span data-ttu-id="4cd31-105">Sürükle ve bırak aracılığıyla veri aktarımı etkinleştirmeyi denetimi işlevselliğini uygular.</span><span class="sxs-lookup"><span data-stu-id="4cd31-105">You will implement functionality on the control to enable data transfer through drag-and-drop.</span></span> <span data-ttu-id="4cd31-106">Örneğin, başka bir daire denetimden sürüklerseniz, dolgu rengi veri daire kaynaktan hedefe kopyalanır.</span><span class="sxs-lookup"><span data-stu-id="4cd31-106">For example, if you drag from one Circle control to another, the Fill color data is copied from the source Circle to the target.</span></span> <span data-ttu-id="4cd31-107">İçin bir daire denetiminden sürüklerseniz bir <xref:System.Windows.Controls.TextBox>, dolgu rengi dize gösterimini kopyalanır <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4cd31-107">If you drag from a Circle control to a <xref:System.Windows.Controls.TextBox>, the string representation of the Fill color is copied to the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="4cd31-108">Ayrıca iki panel denetimleri içeren küçük bir uygulama oluşturacak ve bir <xref:System.Windows.Controls.TextBox> sürükle ve bırak işlevselliğini test etmek için.</span><span class="sxs-lookup"><span data-stu-id="4cd31-108">You will also create a small application that contains two panel controls and a <xref:System.Windows.Controls.TextBox> to test the drag-and-drop functionality.</span></span> <span data-ttu-id="4cd31-109">Paneller, taşıyabilir veya daireler bir panelin alt öğeleri koleksiyondan kopyalayabilirsiniz sağlayacak bırakılan daire veriyi işlemek sağlayan bir kod yazacaksınız.</span><span class="sxs-lookup"><span data-stu-id="4cd31-109">You will write code that enables the panels to process dropped Circle data, which will enable you to move or copy Circles from the Children collection of one panel to the other.</span></span>

<span data-ttu-id="4cd31-110">Bu izlenecek yol aşağıdaki görevleri gösterir:</span><span class="sxs-lookup"><span data-stu-id="4cd31-110">This walkthrough illustrates the following tasks:</span></span>

-   <span data-ttu-id="4cd31-111">Özel bir kullanıcı denetimi oluşturun.</span><span class="sxs-lookup"><span data-stu-id="4cd31-111">Create a custom user control.</span></span>

-   <span data-ttu-id="4cd31-112">Bir sürükleme kaynağı olması kullanıcı denetimi etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="4cd31-112">Enable the user control to be a drag source.</span></span>

-   <span data-ttu-id="4cd31-113">Bir bırakma hedefi olarak kullanıcı denetimini etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="4cd31-113">Enable the user control to be a drop target.</span></span>

-   <span data-ttu-id="4cd31-114">Kullanıcı denetimi bırakılan veri almak bir panel etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="4cd31-114">Enable a panel to receive data dropped from the user control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4cd31-115">Önkoşullar</span><span class="sxs-lookup"><span data-stu-id="4cd31-115">Prerequisites</span></span>

<span data-ttu-id="4cd31-116">Bu izlenecek yolu tamamlamak için Visual Studio ihtiyacınız vardır.</span><span class="sxs-lookup"><span data-stu-id="4cd31-116">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="4cd31-117">Uygulama projesini oluşturun</span><span class="sxs-lookup"><span data-stu-id="4cd31-117">Create the Application Project</span></span>
 <span data-ttu-id="4cd31-118">Bu bölümde, bir ana sayfa ile iki panel içerir uygulama altyapısı oluşturacak ve bir <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4cd31-118">In this section, you will create the application infrastructure, which includes a main page with two panels and a <xref:System.Windows.Controls.TextBox>.</span></span>

1.  <span data-ttu-id="4cd31-119">Visual Basic veya Visual C# adlı yeni bir WPF uygulaması projesi oluşturma `DragDropExample`.</span><span class="sxs-lookup"><span data-stu-id="4cd31-119">Create a new WPF Application project in Visual Basic or Visual C# named `DragDropExample`.</span></span> <span data-ttu-id="4cd31-120">Daha fazla bilgi için [nasıl yapılır: Yeni bir WPF uygulaması projesi oluşturma](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span><span class="sxs-lookup"><span data-stu-id="4cd31-120">For more information, see [How to: Create a New WPF Application Project](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span>

2.  <span data-ttu-id="4cd31-121">Open MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="4cd31-121">Open MainWindow.xaml.</span></span>

3.  <span data-ttu-id="4cd31-122">Açılış ve kapanış arasında aşağıdaki işaretlemeyi ekleyin <xref:System.Windows.Controls.Grid> etiketler.</span><span class="sxs-lookup"><span data-stu-id="4cd31-122">Add the following markup between the opening and closing <xref:System.Windows.Controls.Grid> tags.</span></span>

     <span data-ttu-id="4cd31-123">Bu işaretleme, kullanıcı arabirimi test uygulaması oluşturur.</span><span class="sxs-lookup"><span data-stu-id="4cd31-123">This markup creates the user interface for the test application.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]

## <a name="add-a-new-user-control-to-the-project"></a><span data-ttu-id="4cd31-124">Projeye yeni bir kullanıcı denetimi Ekle</span><span class="sxs-lookup"><span data-stu-id="4cd31-124">Add a New User Control to the Project</span></span>
 <span data-ttu-id="4cd31-125">Bu bölümde, projeye yeni bir kullanıcı denetimi ekleyeceksiniz.</span><span class="sxs-lookup"><span data-stu-id="4cd31-125">In this section, you will add a new user control to the project.</span></span>

1.  <span data-ttu-id="4cd31-126">Proje menüsünde **kullanıcı denetimi Ekle**.</span><span class="sxs-lookup"><span data-stu-id="4cd31-126">On the Project menu, select **Add User Control**.</span></span>

2.  <span data-ttu-id="4cd31-127">İçinde **Yeni Öğe Ekle** iletişim kutusunda, ada değiştirin `Circle.xaml`, tıklatıp **Ekle**.</span><span class="sxs-lookup"><span data-stu-id="4cd31-127">In the **Add New Item** dialog box, change the name to `Circle.xaml`, and click **Add**.</span></span>

     <span data-ttu-id="4cd31-128">Circle.XAML ve kendi arka plan kod projesine eklenir.</span><span class="sxs-lookup"><span data-stu-id="4cd31-128">Circle.xaml and its code-behind is added to the project.</span></span>

3.  <span data-ttu-id="4cd31-129">Circle.xaml açın.</span><span class="sxs-lookup"><span data-stu-id="4cd31-129">Open Circle.xaml.</span></span>

     <span data-ttu-id="4cd31-130">Bu dosya kullanıcı denetiminin kullanıcı arabirimi öğeleri içerir.</span><span class="sxs-lookup"><span data-stu-id="4cd31-130">This file will contain the user interface elements of the user control.</span></span>

4.  <span data-ttu-id="4cd31-131">Kök aşağıdaki işaretlemeyi ekleyin <xref:System.Windows.Controls.Grid> mavi bir daire olarak kullanıcı arabirimini sahip basit bir kullanıcı denetimi oluşturmak için.</span><span class="sxs-lookup"><span data-stu-id="4cd31-131">Add the following markup to the root <xref:System.Windows.Controls.Grid> to create a simple user control that has a blue circle as its UI.</span></span>

     [!code-xaml[DragDropWalkthrough#EllipseXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]

5.  <span data-ttu-id="4cd31-132">Circle.xaml.cs veya Circle.xaml.vb açın.</span><span class="sxs-lookup"><span data-stu-id="4cd31-132">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

6.  <span data-ttu-id="4cd31-133">C# ' ta bir kopya Oluşturucu oluşturmak için varsayılan oluşturucu sonra aşağıdaki kodu ekleyin.</span><span class="sxs-lookup"><span data-stu-id="4cd31-133">In C#, add the following code after the default constructor to create a copy constructor.</span></span> <span data-ttu-id="4cd31-134">Visual Basic'te, bir kopya oluşturucu ve bir varsayılan oluşturucu oluşturmak için aşağıdaki kodu ekleyin.</span><span class="sxs-lookup"><span data-stu-id="4cd31-134">In Visual Basic, add the following code to create both a default constructor and a copy constructor.</span></span>

     <span data-ttu-id="4cd31-135">Kopyalanacak kullanıcı denetimi izin vermek üzere arka plan kod dosyasında bir kopya Oluşturucu yöntemi ekleyin.</span><span class="sxs-lookup"><span data-stu-id="4cd31-135">In order to allow the user control to be copied, you add a copy constructor method in the code-behind file.</span></span> <span data-ttu-id="4cd31-136">Basitleştirilmiş daire kullanıcı denetiminde yalnızca dolgu ve boyutunu kopyalayacağınız kullanıcı denetimi.</span><span class="sxs-lookup"><span data-stu-id="4cd31-136">In the simplified Circle user control, you will only copy the Fill and the size of the of the user control.</span></span>

     [!code-csharp[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]

## <a name="add-the-user-control-to-the-main-window"></a><span data-ttu-id="4cd31-137">Kullanıcı denetiminin ana penceresine ekleme</span><span class="sxs-lookup"><span data-stu-id="4cd31-137">Add the user control to the main window</span></span>

1.  <span data-ttu-id="4cd31-138">Open MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="4cd31-138">Open MainWindow.xaml.</span></span>

2.  <span data-ttu-id="4cd31-139">Aşağıdaki XAML açılış ekleme <xref:System.Windows.Window> bir XML ad alanı başvurusu geçerli uygulamaya etiket.</span><span class="sxs-lookup"><span data-stu-id="4cd31-139">Add the following XAML to the opening <xref:System.Windows.Window> tag to create an XML namespace reference to the current application.</span></span>

    ```
    xmlns:local="clr-namespace:DragDropExample"
    ```

3.  <span data-ttu-id="4cd31-140">İlk <xref:System.Windows.Controls.StackPanel>, ilk panelindeki daire kullanıcı denetimi iki örneğini oluşturmak için aşağıdaki XAML ekleyin.</span><span class="sxs-lookup"><span data-stu-id="4cd31-140">In the first <xref:System.Windows.Controls.StackPanel>, add the following XAML to create two instances of the Circle user control in the first panel.</span></span>

     [!code-xaml[DragDropWalkthrough#CirclesXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]

     <span data-ttu-id="4cd31-141">Tam XAML paneli aşağıdaki gibi görünür.</span><span class="sxs-lookup"><span data-stu-id="4cd31-141">The full XAML for the panel looks like the following.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]

## <a name="implement-drag-source-events-in-the-user-control"></a><span data-ttu-id="4cd31-142">Kullanıcı denetiminde sürükleme kaynağı olayları uygulama</span><span class="sxs-lookup"><span data-stu-id="4cd31-142">Implement Drag Source Events in the User Control</span></span>
 <span data-ttu-id="4cd31-143">Bu bölümde, geçersiz kılar <xref:System.Windows.UIElement.OnMouseMove%2A> yöntemi ve sürükle ve bırak işlemi Başlat.</span><span class="sxs-lookup"><span data-stu-id="4cd31-143">In this section, you will override the <xref:System.Windows.UIElement.OnMouseMove%2A> method and initiate the drag-and-drop operation.</span></span>

 <span data-ttu-id="4cd31-144">Bir sürükleme başladıysanız (fare taşınır ve bir fare düğmesi basılı), verileri içine aktarılacak paket oluşturur bir <xref:System.Windows.DataObject>.</span><span class="sxs-lookup"><span data-stu-id="4cd31-144">If a drag is started (a mouse button is pressed and the mouse is moved), you will package the data to be transferred into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="4cd31-145">Bu durumda, daire denetim, üç veri öğeleri paket oluşturur; Dolgu rengini, yükseklik çift temsili ve kendisini bir kopyasını bir dize açıklaması.</span><span class="sxs-lookup"><span data-stu-id="4cd31-145">In this case, the Circle control will package three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

### <a name="to-initiate-a-drag-and-drop-operation"></a><span data-ttu-id="4cd31-146">Bir Sürükle ve bırak işlemi başlatmak için</span><span class="sxs-lookup"><span data-stu-id="4cd31-146">To initiate a drag-and-drop operation</span></span>

1.  <span data-ttu-id="4cd31-147">Circle.xaml.cs veya Circle.xaml.vb açın.</span><span class="sxs-lookup"><span data-stu-id="4cd31-147">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2.  <span data-ttu-id="4cd31-148">Aşağıdaki <xref:System.Windows.UIElement.OnMouseMove%2A> sınıf için işleme sağlamak için geçersiz kılma <xref:System.Windows.UIElement.MouseMove> olay.</span><span class="sxs-lookup"><span data-stu-id="4cd31-148">Add the following <xref:System.Windows.UIElement.OnMouseMove%2A> override to provide class handling for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]

     <span data-ttu-id="4cd31-149">Bu <xref:System.Windows.UIElement.OnMouseMove%2A> geçersiz kılma aşağıdaki görevleri gerçekleştirir:</span><span class="sxs-lookup"><span data-stu-id="4cd31-149">This <xref:System.Windows.UIElement.OnMouseMove%2A> override performs the following tasks:</span></span>

    -   <span data-ttu-id="4cd31-150">Fareyi hareket ederken, farenin sol düğmesine basıldığında olup olmadığını denetler.</span><span class="sxs-lookup"><span data-stu-id="4cd31-150">Checks whether the left mouse button is pressed while the mouse is moving.</span></span>

    -   <span data-ttu-id="4cd31-151">Daire verileri paketleri bir <xref:System.Windows.DataObject>.</span><span class="sxs-lookup"><span data-stu-id="4cd31-151">Packages the Circle data into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="4cd31-152">Bu durumda, daire denetim, üç veri öğeleri paketleri; Dolgu rengini, yükseklik çift temsili ve kendisini bir kopyasını bir dize açıklaması.</span><span class="sxs-lookup"><span data-stu-id="4cd31-152">In this case, the Circle control packages three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

    -   <span data-ttu-id="4cd31-153">Statik çağırır <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> sürükle ve bırak işlemi başlatmak için yöntem.</span><span class="sxs-lookup"><span data-stu-id="4cd31-153">Calls the static <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> method to initiate the drag-and-drop operation.</span></span> <span data-ttu-id="4cd31-154">Şu üç parametreyi için geçirdiğiniz <xref:System.Windows.DragDrop.DoDragDrop%2A> yöntemi:</span><span class="sxs-lookup"><span data-stu-id="4cd31-154">You pass the following three parameters to the <xref:System.Windows.DragDrop.DoDragDrop%2A> method:</span></span>

        -   <span data-ttu-id="4cd31-155">`dragSource` – Bu denetimi bir başvuru.</span><span class="sxs-lookup"><span data-stu-id="4cd31-155">`dragSource` – A reference to this control.</span></span>

        -   <span data-ttu-id="4cd31-156">`data` – <xref:System.Windows.DataObject> Önceki kod içinde oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="4cd31-156">`data` – The <xref:System.Windows.DataObject> created in the previous code.</span></span>

        -   <span data-ttu-id="4cd31-157">`allowedEffects` – Olan izin verilen sürükle ve bırak işlemleri <xref:System.Windows.DragDropEffects.Copy> veya <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="4cd31-157">`allowedEffects` – The allowed drag-and-drop operations, which are <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3.  <span data-ttu-id="4cd31-158">Tuşuna **F5** oluşturun ve uygulamayı çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="4cd31-158">Press **F5** to build and run the application.</span></span>

4.  <span data-ttu-id="4cd31-159">Daire denetimlerden birini tıklatın ve başka bir daire, panellerin üzerine sürükleyin ve <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4cd31-159">Click one of the Circle controls and drag it over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="4cd31-160">Üzerine sürüklerken <xref:System.Windows.Controls.TextBox>, taşıma belirtecek şekilde imleç değişir.</span><span class="sxs-lookup"><span data-stu-id="4cd31-160">When dragging over the <xref:System.Windows.Controls.TextBox>, the cursor changes to indicate a move.</span></span>

5.  <span data-ttu-id="4cd31-161">Bir dairenin üzerine sürüklerken <xref:System.Windows.Controls.TextBox>, basın **Ctrl** anahtarı.</span><span class="sxs-lookup"><span data-stu-id="4cd31-161">While dragging a Circle over the <xref:System.Windows.Controls.TextBox>, press the **Ctrl** key.</span></span> <span data-ttu-id="4cd31-162">Nasıl bir kopyasını belirtmek için imleç değiştiğine dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="4cd31-162">Notice how the cursor changes to indicate a copy.</span></span>

6.  <span data-ttu-id="4cd31-163">Bir dairenin üzerine sürükleyip <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4cd31-163">Drag and drop a Circle onto the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="4cd31-164">Dairenin dolgu rengi dize gösterimini eklenir <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4cd31-164">The string representation of the Circle’s fill color is appended to the <xref:System.Windows.Controls.TextBox>.</span></span>

     <span data-ttu-id="4cd31-165">![Dize gösterimini dairenin dolgu rengi](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop_ColorString")</span><span class="sxs-lookup"><span data-stu-id="4cd31-165">![String representation of Circle's fill color](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop_ColorString")</span></span>

<span data-ttu-id="4cd31-166">Varsayılan olarak, imleç bir Sürükle ve bırak işlemi sırasında veri bırakarak hangi etkisi olmayacak göstermek için değiştirir.</span><span class="sxs-lookup"><span data-stu-id="4cd31-166">By default, the cursor will change during a drag-and-drop operation to indicate what effect dropping the data will have.</span></span> <span data-ttu-id="4cd31-167">Kullanıcıya verilen işleyerek geri bildirim özelleştirebilirsiniz <xref:System.Windows.UIElement.GiveFeedback> olay ve farklı bir imleç ayarlama.</span><span class="sxs-lookup"><span data-stu-id="4cd31-167">You can customize the feedback given to the user by handling the <xref:System.Windows.UIElement.GiveFeedback> event and setting a different cursor.</span></span>

## <a name="give-feedback-to-the-user"></a><span data-ttu-id="4cd31-168">Kullanıcıya geri bildirimde bulunun</span><span class="sxs-lookup"><span data-stu-id="4cd31-168">Give feedback to the user</span></span>

1.  <span data-ttu-id="4cd31-169">Circle.xaml.cs veya Circle.xaml.vb açın.</span><span class="sxs-lookup"><span data-stu-id="4cd31-169">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2.  <span data-ttu-id="4cd31-170">Aşağıdaki <xref:System.Windows.UIElement.OnGiveFeedback%2A> sınıf için işleme sağlamak için geçersiz kılma <xref:System.Windows.UIElement.GiveFeedback> olay.</span><span class="sxs-lookup"><span data-stu-id="4cd31-170">Add the following <xref:System.Windows.UIElement.OnGiveFeedback%2A> override to provide class handling for the <xref:System.Windows.UIElement.GiveFeedback> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]

     <span data-ttu-id="4cd31-171">Bu <xref:System.Windows.UIElement.OnGiveFeedback%2A> geçersiz kılma aşağıdaki görevleri gerçekleştirir:</span><span class="sxs-lookup"><span data-stu-id="4cd31-171">This <xref:System.Windows.UIElement.OnGiveFeedback%2A> override performs the following tasks:</span></span>

    -   <span data-ttu-id="4cd31-172">Denetler <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> bırakma hedef ayarlanan değerlerle <xref:System.Windows.UIElement.DragOver> olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="4cd31-172">Checks the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> values that are set in the drop target's <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

    -   <span data-ttu-id="4cd31-173">Temel özel bir imleç ayarlar <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> değeri.</span><span class="sxs-lookup"><span data-stu-id="4cd31-173">Sets a custom cursor based on the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> value.</span></span> <span data-ttu-id="4cd31-174">İmleç, verileri bırakmayı hangi etkisi hakkında kullanıcıya görsel geribildirim vermek için tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="4cd31-174">The cursor is intended to give visual feedback to the user about what effect dropping the data will have.</span></span>

3.  <span data-ttu-id="4cd31-175">Tuşuna **F5** oluşturun ve uygulamayı çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="4cd31-175">Press **F5** to build and run the application.</span></span>

4.  <span data-ttu-id="4cd31-176">Bir dairenin denetimleri başka bir daire, panellerin üzerine sürükleyin ve <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4cd31-176">Drag one of the Circle controls over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="4cd31-177">İmleçler artık, belirttiğiniz özel işaretçiler olduğunu fark <xref:System.Windows.UIElement.OnGiveFeedback%2A> geçersiz kılar.</span><span class="sxs-lookup"><span data-stu-id="4cd31-177">Notice that the cursors are now the custom cursors that you specified in the <xref:System.Windows.UIElement.OnGiveFeedback%2A> override.</span></span>

     <span data-ttu-id="4cd31-178">![Sürükle ve bırak ile özel işaretçiler](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span><span class="sxs-lookup"><span data-stu-id="4cd31-178">![Drag and drop with custom cursors](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span></span>

5.  <span data-ttu-id="4cd31-179">Metni seçin `green` gelen <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4cd31-179">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

6.  <span data-ttu-id="4cd31-180">Sürükleme `green` bir daire denetime metin.</span><span class="sxs-lookup"><span data-stu-id="4cd31-180">Drag the `green` text to a Circle control.</span></span> <span data-ttu-id="4cd31-181">Sürükle ve bırak işlemi etkilerini belirtmek için gösterilen varsayılan imleçler dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="4cd31-181">Notice that the default cursors are shown to indicate the effects of the drag-and-drop operation.</span></span> <span data-ttu-id="4cd31-182">Geri bildirim imleci her zaman sürükleme kaynağı tarafından ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="4cd31-182">The feedback cursor is always set by the drag source.</span></span>

## <a name="implement-drop-target-events-in-the-user-control"></a><span data-ttu-id="4cd31-183">Bırakma hedefi olayları kullanıcı denetimi uygulayın</span><span class="sxs-lookup"><span data-stu-id="4cd31-183">Implement Drop Target Events in the User Control</span></span>
 <span data-ttu-id="4cd31-184">Bu bölümde, kullanıcı denetiminin bir bırakma hedefi, kullanıcı etkinleştirme yöntemleri bir bırakma hedefi olarak denetlemek ve üzerinde bırakılan veri işlem geçersiz kılma olduğunu belirtin.</span><span class="sxs-lookup"><span data-stu-id="4cd31-184">In this section, you will specify that the user control is a drop target, override the methods that enable the user control to be a drop target, and process the data that is dropped on it.</span></span>

### <a name="to-enable-the-user-control-to-be-a-drop-target"></a><span data-ttu-id="4cd31-185">Bir bırakma hedefi olarak kullanıcı denetimini etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="4cd31-185">To enable the user control to be a drop target</span></span>

1.  <span data-ttu-id="4cd31-186">Circle.xaml açın.</span><span class="sxs-lookup"><span data-stu-id="4cd31-186">Open Circle.xaml.</span></span>

2.  <span data-ttu-id="4cd31-187">Açılışında <xref:System.Windows.Controls.UserControl> etiketinde, ekleyin <xref:System.Windows.UIElement.AllowDrop%2A> özelliği ve değerini `true`.</span><span class="sxs-lookup"><span data-stu-id="4cd31-187">In the opening <xref:System.Windows.Controls.UserControl> tag, add the <xref:System.Windows.UIElement.AllowDrop%2A> property and set it to `true`.</span></span>

     [!code-xaml[DragDropWalkthrough#UCTagXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]

<span data-ttu-id="4cd31-188"><xref:System.Windows.UIElement.OnDrop%2A> Yöntemi çağrılır <xref:System.Windows.UIElement.AllowDrop%2A> özelliği `true` ve daire kullanıcı denetiminde sürükleme kaynağından bırakıldı.</span><span class="sxs-lookup"><span data-stu-id="4cd31-188">The <xref:System.Windows.UIElement.OnDrop%2A> method is called when the <xref:System.Windows.UIElement.AllowDrop%2A> property is set to `true` and data from the drag source is dropped on the Circle user control.</span></span> <span data-ttu-id="4cd31-189">Bu yöntemde, bırakılmış verileri işleme ve veri dairenin uygulayın.</span><span class="sxs-lookup"><span data-stu-id="4cd31-189">In this method, you will process the data that was dropped and apply the data to the Circle.</span></span>

### <a name="to-process-the-dropped-data"></a><span data-ttu-id="4cd31-190">Bırakılan veri işlemek için</span><span class="sxs-lookup"><span data-stu-id="4cd31-190">To process the dropped data</span></span>

1.  <span data-ttu-id="4cd31-191">Circle.xaml.cs veya Circle.xaml.vb açın.</span><span class="sxs-lookup"><span data-stu-id="4cd31-191">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2.  <span data-ttu-id="4cd31-192">Aşağıdaki <xref:System.Windows.UIElement.OnDrop%2A> sınıf için işleme sağlamak için geçersiz kılma <xref:System.Windows.UIElement.Drop> olay.</span><span class="sxs-lookup"><span data-stu-id="4cd31-192">Add the following <xref:System.Windows.UIElement.OnDrop%2A> override to provide class handling for the <xref:System.Windows.UIElement.Drop> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]

     <span data-ttu-id="4cd31-193">Bu <xref:System.Windows.UIElement.OnDrop%2A> geçersiz kılma aşağıdaki görevleri gerçekleştirir:</span><span class="sxs-lookup"><span data-stu-id="4cd31-193">This <xref:System.Windows.UIElement.OnDrop%2A> override performs the following tasks:</span></span>

    -   <span data-ttu-id="4cd31-194">Kullanan <xref:System.Windows.DataObject.GetDataPresent%2A> sürüklenen verileri bir dize nesnesi içerip içermediğini denetlemek için yöntem.</span><span class="sxs-lookup"><span data-stu-id="4cd31-194">Uses the <xref:System.Windows.DataObject.GetDataPresent%2A> method to check if the dragged data contains a string object.</span></span>

    -   <span data-ttu-id="4cd31-195">Kullanan <xref:System.Windows.DataObject.GetData%2A> varsa, dize verilerini ayıklamak için yöntemi.</span><span class="sxs-lookup"><span data-stu-id="4cd31-195">Uses the <xref:System.Windows.DataObject.GetData%2A> method to extract the string data if it is present.</span></span>

    -   <span data-ttu-id="4cd31-196">Kullanan bir <xref:System.Windows.Media.BrushConverter> dizeye dönüştürülecek denemek için bir <xref:System.Windows.Media.Brush>.</span><span class="sxs-lookup"><span data-stu-id="4cd31-196">Uses a <xref:System.Windows.Media.BrushConverter> to try to convert the string to a <xref:System.Windows.Media.Brush>.</span></span>

    -   <span data-ttu-id="4cd31-197">Dönüştürme başarılı ise fırçaya uygulanır <xref:System.Windows.Shapes.Shape.Fill%2A> , <xref:System.Windows.Shapes.Ellipse> daire denetimin kullanıcı Arabirimi sağlar.</span><span class="sxs-lookup"><span data-stu-id="4cd31-197">If the conversion is successful, applies the brush to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle control.</span></span>

    -   <span data-ttu-id="4cd31-198">İşaretleri <xref:System.Windows.UIElement.Drop> işlenmiş olarak olay.</span><span class="sxs-lookup"><span data-stu-id="4cd31-198">Marks the <xref:System.Windows.UIElement.Drop> event as handled.</span></span> <span data-ttu-id="4cd31-199">Bırakma olayını daire kullanıcı denetimi, işlenen Bu etkinliğin diğer öğeleri öğrenmek için işlenmiş olarak işaretlemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="4cd31-199">You should mark the drop event as handled so that other elements that receive this event know that the Circle user control handled it.</span></span>

3.  <span data-ttu-id="4cd31-200">Tuşuna **F5** oluşturun ve uygulamayı çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="4cd31-200">Press **F5** to build and run the application.</span></span>

4.  <span data-ttu-id="4cd31-201">Metni seçin `green` içinde <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4cd31-201">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5.  <span data-ttu-id="4cd31-202">Bir daire denetime metin sürükleyin ve bırakın.</span><span class="sxs-lookup"><span data-stu-id="4cd31-202">Drag the text to a Circle control and drop it.</span></span> <span data-ttu-id="4cd31-203">Mavi yeşil daire değişiklikleri.</span><span class="sxs-lookup"><span data-stu-id="4cd31-203">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="4cd31-204">![Bir dize dönüştürmek için bir fırça](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span><span class="sxs-lookup"><span data-stu-id="4cd31-204">![Convert a string to a brush](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span></span>

6.  <span data-ttu-id="4cd31-205">Bir metin yazın `green` içinde <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4cd31-205">Type the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7.  <span data-ttu-id="4cd31-206">Metni seçin `gre` içinde <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4cd31-206">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

8.  <span data-ttu-id="4cd31-207">Bir daire denetimine sürükleyin ve bırakın.</span><span class="sxs-lookup"><span data-stu-id="4cd31-207">Drag it to a Circle control and drop it.</span></span> <span data-ttu-id="4cd31-208">Açılan izin verilir, ancak dairenin rengi, çünkü değiştirmez belirtmek için imleç değiştiğine dikkat edin `gre` geçerli bir renk değil.</span><span class="sxs-lookup"><span data-stu-id="4cd31-208">Notice that the cursor changes to indicate that the drop is allowed, but the color of the Circle does not change because `gre` is not a valid color.</span></span>

9. <span data-ttu-id="4cd31-209">Yeşil daire denetiminden sürükleyip mavi daire denetimi.</span><span class="sxs-lookup"><span data-stu-id="4cd31-209">Drag from the green Circle control and drop on the blue Circle control.</span></span> <span data-ttu-id="4cd31-210">Mavi yeşil daire değişiklikleri.</span><span class="sxs-lookup"><span data-stu-id="4cd31-210">The Circle changes from blue to green.</span></span> <span data-ttu-id="4cd31-211">Hangi imleç gösterilir bağlıdır dikkat edin <xref:System.Windows.Controls.TextBox> veya daire sürükleme kaynağı.</span><span class="sxs-lookup"><span data-stu-id="4cd31-211">Notice that which cursor is shown depends on whether the <xref:System.Windows.Controls.TextBox> or the Circle is the drag source.</span></span>

<span data-ttu-id="4cd31-212">Ayarı <xref:System.Windows.UIElement.AllowDrop%2A> özelliğini `true` ve bırakılan verilerin işlenmesi tüm bir bırakma hedefi olarak bir öğeyi etkinleştirmek için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="4cd31-212">Setting the <xref:System.Windows.UIElement.AllowDrop%2A> property to `true` and processing the dropped data is all that is required to enable an element to be a drop target.</span></span> <span data-ttu-id="4cd31-213">Ancak, daha iyi bir kullanıcı deneyimi sağlamak için ayrıca işleyeceğini <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, ve <xref:System.Windows.UIElement.DragOver> olayları.</span><span class="sxs-lookup"><span data-stu-id="4cd31-213">However, to provide a better user experience, you should also handle the <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, and <xref:System.Windows.UIElement.DragOver> events.</span></span> <span data-ttu-id="4cd31-214">Bu olayları, denetimleri gerçekleştirir ve veri kesilmeden önce kullanıcıya ek geri bildirim sağlayın.</span><span class="sxs-lookup"><span data-stu-id="4cd31-214">In these events, you can perform checks and provide additional feedback to the user before the data is dropped.</span></span>

<span data-ttu-id="4cd31-215">Veri daire kullanıcı denetime sürüklendiğinde denetimin sürüklenen veri işleme olup olmadığını sürükleme kaynağı bildirmelisiniz.</span><span class="sxs-lookup"><span data-stu-id="4cd31-215">When data is dragged over the Circle user control, the control should notify the drag source whether it can process the data that is being dragged.</span></span> <span data-ttu-id="4cd31-216">Denetim verileri işlemek nasıl emin değilseniz açılan reddeder.</span><span class="sxs-lookup"><span data-stu-id="4cd31-216">If the control does not know how to process the data, it should refuse the drop.</span></span> <span data-ttu-id="4cd31-217">Bunu yapmak için işleyecek <xref:System.Windows.UIElement.DragOver> olay ve kümesi <xref:System.Windows.DragEventArgs.Effects%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="4cd31-217">To do this, you will handle the <xref:System.Windows.UIElement.DragOver> event and set the <xref:System.Windows.DragEventArgs.Effects%2A> property.</span></span>

### <a name="to-verify-that-the-data-drop-is-allowed"></a><span data-ttu-id="4cd31-218">Veri bırakma izin verildiğini doğrulamak için</span><span class="sxs-lookup"><span data-stu-id="4cd31-218">To verify that the data drop is allowed</span></span>

1.  <span data-ttu-id="4cd31-219">Circle.xaml.cs veya Circle.xaml.vb açın.</span><span class="sxs-lookup"><span data-stu-id="4cd31-219">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2.  <span data-ttu-id="4cd31-220">Aşağıdaki <xref:System.Windows.UIElement.OnDragOver%2A> sınıf için işleme sağlamak için geçersiz kılma <xref:System.Windows.UIElement.DragOver> olay.</span><span class="sxs-lookup"><span data-stu-id="4cd31-220">Add the following <xref:System.Windows.UIElement.OnDragOver%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragOver> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]

     <span data-ttu-id="4cd31-221">Bu <xref:System.Windows.UIElement.OnDragOver%2A> geçersiz kılma aşağıdaki görevleri gerçekleştirir:</span><span class="sxs-lookup"><span data-stu-id="4cd31-221">This <xref:System.Windows.UIElement.OnDragOver%2A> override performs the following tasks:</span></span>

    -   <span data-ttu-id="4cd31-222">Kümeleri <xref:System.Windows.DragEventArgs.Effects%2A> özelliğini <xref:System.Windows.DragDropEffects.None>.</span><span class="sxs-lookup"><span data-stu-id="4cd31-222">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.None>.</span></span>

    -   <span data-ttu-id="4cd31-223">Gerçekleştirilir aynı denetimleri gerçekleştirir <xref:System.Windows.UIElement.OnDrop%2A> daire kullanıcı denetimi sürüklenen verileri işleyebildiğinden olup olmadığını belirlemek için yöntemi.</span><span class="sxs-lookup"><span data-stu-id="4cd31-223">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the Circle user control can process the dragged data.</span></span>

    -   <span data-ttu-id="4cd31-224">Kullanıcı denetimi verileri işleyebildiğinden, ayarlar <xref:System.Windows.DragEventArgs.Effects%2A> özelliğini <xref:System.Windows.DragDropEffects.Copy> veya <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="4cd31-224">If the user control can process the data, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3.  <span data-ttu-id="4cd31-225">Tuşuna **F5** oluşturun ve uygulamayı çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="4cd31-225">Press **F5** to build and run the application.</span></span>

4.  <span data-ttu-id="4cd31-226">Metni seçin `gre` içinde <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4cd31-226">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5.  <span data-ttu-id="4cd31-227">Metin bir daire denetimi sürükleyin.</span><span class="sxs-lookup"><span data-stu-id="4cd31-227">Drag the text to a Circle control.</span></span> <span data-ttu-id="4cd31-228">İmleç açılan olduğundan izin verilmiyor belirtmek için hemen değiştiğine dikkat edin `gre` geçerli bir renk değil.</span><span class="sxs-lookup"><span data-stu-id="4cd31-228">Notice that the cursor now changes to indicate that the drop is not allowed because `gre` is not a valid color.</span></span>

 <span data-ttu-id="4cd31-229">Kullanıcı deneyimini daha fazla bırakma işlemi önizlemesini uygulayarak da geliştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4cd31-229">You can further enhance the user experience by applying a preview of the drop operation.</span></span> <span data-ttu-id="4cd31-230">Daire kullanıcı denetimi için geçersiz kılar <xref:System.Windows.UIElement.OnDragEnter%2A> ve <xref:System.Windows.UIElement.OnDragLeave%2A> yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="4cd31-230">For the Circle user control, you will override the <xref:System.Windows.UIElement.OnDragEnter%2A> and <xref:System.Windows.UIElement.OnDragLeave%2A> methods.</span></span> <span data-ttu-id="4cd31-231">Ne zaman veri sürüklediğiniz geçerli arka plan denetimin üzerine <xref:System.Windows.Shapes.Shape.Fill%2A> bir yer tutucu değişkende kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="4cd31-231">When the data is dragged over the control, the current background <xref:System.Windows.Shapes.Shape.Fill%2A> is saved in a placeholder variable.</span></span> <span data-ttu-id="4cd31-232">Dize ardından fırçaya dönüştürülür ve uygulanan <xref:System.Windows.Shapes.Ellipse> dairenin sağlayan kullanıcı Arabirimi.</span><span class="sxs-lookup"><span data-stu-id="4cd31-232">The string is then converted to a brush and applied to the <xref:System.Windows.Shapes.Ellipse> that provides the Circle's UI.</span></span> <span data-ttu-id="4cd31-233">Veri daire dışında ' bırakılan olmadan, özgün sürüklediyseniz <xref:System.Windows.Shapes.Shape.Fill%2A> değeri dairenin yeniden uygulanır.</span><span class="sxs-lookup"><span data-stu-id="4cd31-233">If the data is dragged out of the Circle without being dropped, the original <xref:System.Windows.Shapes.Shape.Fill%2A> value is re-applied to the Circle.</span></span>

### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a><span data-ttu-id="4cd31-234">Sürükle ve bırak işlemi etkilerini önizlemesini görüntülemek için</span><span class="sxs-lookup"><span data-stu-id="4cd31-234">To preview the effects of the drag-and-drop operation</span></span>

1.  <span data-ttu-id="4cd31-235">Circle.xaml.cs veya Circle.xaml.vb açın.</span><span class="sxs-lookup"><span data-stu-id="4cd31-235">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2.  <span data-ttu-id="4cd31-236">Özel bir daire sınıfında bildirmek <xref:System.Windows.Media.Brush> adlı değişken `_previousFill` ve kendisine başlatma `null`.</span><span class="sxs-lookup"><span data-stu-id="4cd31-236">In the Circle class, declare a private <xref:System.Windows.Media.Brush> variable named `_previousFill` and initialize it to `null`.</span></span>

     [!code-csharp[DragDropWalkthrough#Brush](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]

3.  <span data-ttu-id="4cd31-237">Aşağıdaki <xref:System.Windows.UIElement.OnDragEnter%2A> sınıf için işleme sağlamak için geçersiz kılma <xref:System.Windows.UIElement.DragEnter> olay.</span><span class="sxs-lookup"><span data-stu-id="4cd31-237">Add the following <xref:System.Windows.UIElement.OnDragEnter%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragEnter> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]

     <span data-ttu-id="4cd31-238">Bu <xref:System.Windows.UIElement.OnDragEnter%2A> geçersiz kılma aşağıdaki görevleri gerçekleştirir:</span><span class="sxs-lookup"><span data-stu-id="4cd31-238">This <xref:System.Windows.UIElement.OnDragEnter%2A> override performs the following tasks:</span></span>

    -   <span data-ttu-id="4cd31-239">Kaydeder <xref:System.Windows.Shapes.Shape.Fill%2A> özelliği <xref:System.Windows.Shapes.Ellipse> içinde `_previousFill` değişkeni.</span><span class="sxs-lookup"><span data-stu-id="4cd31-239">Saves the <xref:System.Windows.Shapes.Shape.Fill%2A> property of the <xref:System.Windows.Shapes.Ellipse> in the `_previousFill` variable.</span></span>

    -   <span data-ttu-id="4cd31-240">Gerçekleştirilir aynı denetimleri gerçekleştirir <xref:System.Windows.UIElement.OnDrop%2A> verileri için dönüştürülüp dönüştürülemeyeceğini belirlemek için yöntemi bir <xref:System.Windows.Media.Brush>.</span><span class="sxs-lookup"><span data-stu-id="4cd31-240">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the data can be converted to a <xref:System.Windows.Media.Brush>.</span></span>

    -   <span data-ttu-id="4cd31-241">Geçerli bir veri dönüştürülürse <xref:System.Windows.Media.Brush>, uygular <xref:System.Windows.Shapes.Shape.Fill%2A> , <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="4cd31-241">If the data is converted to a valid <xref:System.Windows.Media.Brush>, applies it to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse>.</span></span>

4.  <span data-ttu-id="4cd31-242">Aşağıdaki <xref:System.Windows.UIElement.OnDragLeave%2A> sınıf için işleme sağlamak için geçersiz kılma <xref:System.Windows.UIElement.DragLeave> olay.</span><span class="sxs-lookup"><span data-stu-id="4cd31-242">Add the following <xref:System.Windows.UIElement.OnDragLeave%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragLeave> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]

     <span data-ttu-id="4cd31-243">Bu <xref:System.Windows.UIElement.OnDragLeave%2A> geçersiz kılma aşağıdaki görevleri gerçekleştirir:</span><span class="sxs-lookup"><span data-stu-id="4cd31-243">This <xref:System.Windows.UIElement.OnDragLeave%2A> override performs the following tasks:</span></span>

    -   <span data-ttu-id="4cd31-244">Geçerli <xref:System.Windows.Media.Brush> kaydedilmiş `_previousFill` değişkenini <xref:System.Windows.Shapes.Shape.Fill%2A> , <xref:System.Windows.Shapes.Ellipse> daire kullanıcı denetiminin kullanıcı Arabirimi sağlar.</span><span class="sxs-lookup"><span data-stu-id="4cd31-244">Applies the <xref:System.Windows.Media.Brush> saved in the `_previousFill` variable to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle user control.</span></span>

5.  <span data-ttu-id="4cd31-245">Tuşuna **F5** oluşturun ve uygulamayı çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="4cd31-245">Press **F5** to build and run the application.</span></span>

6.  <span data-ttu-id="4cd31-246">Metni seçin `green` içinde <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4cd31-246">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7.  <span data-ttu-id="4cd31-247">Metin, sürükleyip bırakarak olmadan bir daire denetimin üzerine sürükleyin.</span><span class="sxs-lookup"><span data-stu-id="4cd31-247">Drag the text over a Circle control without dropping it.</span></span> <span data-ttu-id="4cd31-248">Mavi yeşil daire değişiklikleri.</span><span class="sxs-lookup"><span data-stu-id="4cd31-248">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="4cd31-249">![Bir sürükleme etkilerini önizleme&#45;ve&#45;bırakma işlemi](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span><span class="sxs-lookup"><span data-stu-id="4cd31-249">![Preview the effects of a drag&#45;and&#45;drop operation](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span></span>

8.  <span data-ttu-id="4cd31-250">Metin daire denetim uzağa sürükleyin.</span><span class="sxs-lookup"><span data-stu-id="4cd31-250">Drag the text away from the Circle control.</span></span> <span data-ttu-id="4cd31-251">Mavi yeşil arka daireye dönüşür.</span><span class="sxs-lookup"><span data-stu-id="4cd31-251">The Circle changes from green back to blue.</span></span>

## <a name="enable-a-panel-to-receive-dropped-data"></a><span data-ttu-id="4cd31-252">Bırakılan veri almak bir Panel etkinleştir</span><span class="sxs-lookup"><span data-stu-id="4cd31-252">Enable a Panel to Receive Dropped Data</span></span>

<span data-ttu-id="4cd31-253">Bu bölümde, sürüklenen daire veriler için bırakma hedefleri olarak davranmak üzere daire kullanıcı denetimleri barındıran paneller etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="4cd31-253">In this section, you enable the panels that host the Circle user controls to act as drop targets for dragged Circle data.</span></span> <span data-ttu-id="4cd31-254">Bir daire bir panelden diğerine taşımak için ya da basılı tutarak bir daire denetimin bir kopyasını yapmak sağlayan kodu gerçekleştireceksiniz **Ctrl** tuşunu sürükleyip bırakarak bir daire.</span><span class="sxs-lookup"><span data-stu-id="4cd31-254">You will implement code that enables you to move a Circle from one panel to another, or to make a copy of a Circle control by holding down the **Ctrl** key while dragging and dropping a Circle.</span></span>

1.  <span data-ttu-id="4cd31-255">Open MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="4cd31-255">Open MainWindow.xaml.</span></span>

2.  <span data-ttu-id="4cd31-256">Her birinde aşağıdaki XAML gösterildiği <xref:System.Windows.Controls.StackPanel> denetimler eklemek için işleyiciler <xref:System.Windows.UIElement.DragOver> ve <xref:System.Windows.UIElement.Drop> olayları.</span><span class="sxs-lookup"><span data-stu-id="4cd31-256">As shown in the following XAML, in each of the <xref:System.Windows.Controls.StackPanel> controls, add handlers for the <xref:System.Windows.UIElement.DragOver> and <xref:System.Windows.UIElement.Drop> events.</span></span> <span data-ttu-id="4cd31-257">Adı <xref:System.Windows.UIElement.DragOver> olay işleyicisi `panel_DragOver`ve ad <xref:System.Windows.UIElement.Drop> olay işleyicisi `panel_Drop`.</span><span class="sxs-lookup"><span data-stu-id="4cd31-257">Name the <xref:System.Windows.UIElement.DragOver> event handler, `panel_DragOver`, and name the <xref:System.Windows.UIElement.Drop> event handler, `panel_Drop`.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]

3.  <span data-ttu-id="4cd31-258">MainWindows.xaml.cs veya MainWindow.xaml.vb açın.</span><span class="sxs-lookup"><span data-stu-id="4cd31-258">Open MainWindows.xaml.cs or MainWindow.xaml.vb.</span></span>

4.  <span data-ttu-id="4cd31-259">İçin aşağıdaki kodu ekleyin <xref:System.Windows.UIElement.DragOver> olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="4cd31-259">Add the following code for the <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]

     <span data-ttu-id="4cd31-260">Bu <xref:System.Windows.UIElement.DragOver> olay işleyicisi aşağıdaki görevleri gerçekleştirir:</span><span class="sxs-lookup"><span data-stu-id="4cd31-260">This <xref:System.Windows.UIElement.DragOver> event handler performs the following tasks:</span></span>

    -   <span data-ttu-id="4cd31-261">Sürüklenen veri içinde paketlendi "Nesne" veri içerip içermediğini denetler <xref:System.Windows.DataObject> daire kullanıcı denetimi tarafından ve çağrısına geçirilen <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span><span class="sxs-lookup"><span data-stu-id="4cd31-261">Checks that the dragged data contains the "Object" data that was packaged in the <xref:System.Windows.DataObject> by the Circle user control and passed in the call to <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span></span>

    -   <span data-ttu-id="4cd31-262">"Nesne" veri yoksa, denetimleri olup **Ctrl** tuşuna basıldığında.</span><span class="sxs-lookup"><span data-stu-id="4cd31-262">If the "Object" data is present, checks whether the **Ctrl** key is pressed.</span></span>

    -   <span data-ttu-id="4cd31-263">Varsa **Ctrl** tuşuna basıldığında, ayarlar <xref:System.Windows.DragEventArgs.Effects%2A> özelliğini <xref:System.Windows.DragDropEffects.Copy>.</span><span class="sxs-lookup"><span data-stu-id="4cd31-263">If the **Ctrl** key is pressed, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy>.</span></span> <span data-ttu-id="4cd31-264">Aksi takdirde, ayarlama <xref:System.Windows.DragEventArgs.Effects%2A> özelliğini <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="4cd31-264">Otherwise, set the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Move>.</span></span>

5.  <span data-ttu-id="4cd31-265">İçin aşağıdaki kodu ekleyin <xref:System.Windows.UIElement.Drop> olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="4cd31-265">Add the following code for the <xref:System.Windows.UIElement.Drop> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]

     <span data-ttu-id="4cd31-266">Bu <xref:System.Windows.UIElement.Drop> olay işleyicisi aşağıdaki görevleri gerçekleştirir:</span><span class="sxs-lookup"><span data-stu-id="4cd31-266">This <xref:System.Windows.UIElement.Drop> event handler performs the following tasks:</span></span>

    -   <span data-ttu-id="4cd31-267">Denetler olmadığını <xref:System.Windows.UIElement.Drop> olay zaten işlenir.</span><span class="sxs-lookup"><span data-stu-id="4cd31-267">Checks whether the <xref:System.Windows.UIElement.Drop> event has already been handled.</span></span> <span data-ttu-id="4cd31-268">Başka bir daire kesilirse, örneğin, yuvarlak tanıtıcıları <xref:System.Windows.UIElement.Drop> olay istemediğiniz ayrıca işlemek için daire içeren paneli.</span><span class="sxs-lookup"><span data-stu-id="4cd31-268">For instance, if a Circle is dropped on another Circle which handles the <xref:System.Windows.UIElement.Drop> event, you do not want the panel that contains the Circle to also handle it.</span></span>

    -   <span data-ttu-id="4cd31-269">Varsa <xref:System.Windows.UIElement.Drop> olay işlenmez, denetimleri olup **Ctrl** tuşuna basıldığında.</span><span class="sxs-lookup"><span data-stu-id="4cd31-269">If the <xref:System.Windows.UIElement.Drop> event is not handled, checks whether the **Ctrl** key is pressed.</span></span>

    -   <span data-ttu-id="4cd31-270">Varsa **Ctrl** anahtar bilgisi basıldığında <xref:System.Windows.UIElement.Drop> olduğunda, dairenin kopyasını hale denetlemek ve ekleyin <xref:System.Windows.Controls.Panel.Children%2A> koleksiyonunu <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="4cd31-270">If the **Ctrl** key is pressed when the <xref:System.Windows.UIElement.Drop> happens, makes a copy of the Circle control and add it to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.StackPanel>.</span></span>

    -   <span data-ttu-id="4cd31-271">Varsa **Ctrl** değil tuşuna basıldığında, gelen daire taşır <xref:System.Windows.Controls.Panel.Children%2A> kendi üst paneline koleksiyonunu <xref:System.Windows.Controls.Panel.Children%2A> bırakılmış paneli koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="4cd31-271">If the **Ctrl** key is not pressed, moves the Circle from the <xref:System.Windows.Controls.Panel.Children%2A> collection of its parent panel to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the panel that it was dropped on.</span></span>

    -   <span data-ttu-id="4cd31-272">Kümeleri <xref:System.Windows.DragEventArgs.Effects%2A> bildirmek için özellik <xref:System.Windows.DragDrop.DoDragDrop%2A> yöntemi olup olmadığını taşıma veya kopyalama işlemi gerçekleştirildi.</span><span class="sxs-lookup"><span data-stu-id="4cd31-272">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to notify the <xref:System.Windows.DragDrop.DoDragDrop%2A> method whether a move or copy operation was performed.</span></span>

6.  <span data-ttu-id="4cd31-273">Tuşuna **F5** oluşturun ve uygulamayı çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="4cd31-273">Press **F5** to build and run the application.</span></span>

7.  <span data-ttu-id="4cd31-274">Metni seçin `green` gelen <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4cd31-274">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

8.  <span data-ttu-id="4cd31-275">Metin bir daire denetimin üzerine sürükleyin ve bırakın.</span><span class="sxs-lookup"><span data-stu-id="4cd31-275">Drag the text over a Circle control and drop it.</span></span>

9. <span data-ttu-id="4cd31-276">Bir daire denetimi sol panelden sağ bölmenin sürükleyip bırakın.</span><span class="sxs-lookup"><span data-stu-id="4cd31-276">Drag a Circle control from the left panel to the right panel and drop it.</span></span> <span data-ttu-id="4cd31-277">Daire kaldırılır <xref:System.Windows.Controls.Panel.Children%2A> sol panelde koleksiyonunu ve sağ alt koleksiyona eklenir.</span><span class="sxs-lookup"><span data-stu-id="4cd31-277">The Circle is removed from the <xref:System.Windows.Controls.Panel.Children%2A> collection of the left panel and added to the Children collection of the right panel.</span></span>

10. <span data-ttu-id="4cd31-278">Bulunduğu diğer panele panelindeki daire denetimi sürükleyin ve tuşlarına basarak ederken bırakma **Ctrl** anahtarı.</span><span class="sxs-lookup"><span data-stu-id="4cd31-278">Drag a Circle control from the panel it is in to the other panel and drop it while pressing the **Ctrl** key.</span></span> <span data-ttu-id="4cd31-279">Daire kopyalanır ve kopyayı eklendiğinden <xref:System.Windows.Controls.Panel.Children%2A> alma panelini koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="4cd31-279">The Circle is copied and the copy is added to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the receiving panel.</span></span>

     <span data-ttu-id="4cd31-280">![Bir daire CTRL tuşunu basılı tutarak sürükleyerek](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span><span class="sxs-lookup"><span data-stu-id="4cd31-280">![Dragging a Circle while pressing the CTRL key](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span></span>

## <a name="see-also"></a><span data-ttu-id="4cd31-281">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="4cd31-281">See also</span></span>

- [<span data-ttu-id="4cd31-282">Sürükleme ve Bırakmaya Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="4cd31-282">Drag and Drop Overview</span></span>](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)