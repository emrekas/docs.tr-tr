---
title: 'İzlenecek yol: WPF’de Windows Forms Denetimlerini Düzenleme'
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: d2bd3a7d4b8e84542f1c5fa3dbb15f1a9753a180
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168590"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="e12c3-102">İzlenecek yol: WPF’de Windows Forms Denetimlerini Düzenleme</span><span class="sxs-lookup"><span data-stu-id="e12c3-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>
<span data-ttu-id="e12c3-103">Bu izlenecek yol size nasıl kullanılacağını gösterir [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] düzenlemek için düzen özelliklerini [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] karma uygulamada denetimleri.</span><span class="sxs-lookup"><span data-stu-id="e12c3-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in a hybrid application.</span></span>  
  
 <span data-ttu-id="e12c3-104">Bu kılavuzda gösterilen görevler aşağıdakileri içerir:</span><span class="sxs-lookup"><span data-stu-id="e12c3-104">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="e12c3-105">Proje oluşturuluyor.</span><span class="sxs-lookup"><span data-stu-id="e12c3-105">Creating the project.</span></span>  
  
-   <span data-ttu-id="e12c3-106">Varsayılan düzen ayarları kullanıyor.</span><span class="sxs-lookup"><span data-stu-id="e12c3-106">Using default layout settings.</span></span>  
  
-   <span data-ttu-id="e12c3-107">İçeriği boyutlandırma.</span><span class="sxs-lookup"><span data-stu-id="e12c3-107">Sizing to content.</span></span>  
  
-   <span data-ttu-id="e12c3-108">Konumlandırmayı mutlak kullanma.</span><span class="sxs-lookup"><span data-stu-id="e12c3-108">Using absolute positioning.</span></span>  
  
-   <span data-ttu-id="e12c3-109">Açıkça boyutunu belirtme.</span><span class="sxs-lookup"><span data-stu-id="e12c3-109">Specifying size explicitly.</span></span>  
  
-   <span data-ttu-id="e12c3-110">Düzen özelliklerini ayarlama.</span><span class="sxs-lookup"><span data-stu-id="e12c3-110">Setting layout properties.</span></span>  
  
-   <span data-ttu-id="e12c3-111">Z düzenini sınırlamaları anlama.</span><span class="sxs-lookup"><span data-stu-id="e12c3-111">Understanding z-order limitations.</span></span>  
  
-   <span data-ttu-id="e12c3-112">Yerleştirme.</span><span class="sxs-lookup"><span data-stu-id="e12c3-112">Docking.</span></span>  
  
-   <span data-ttu-id="e12c3-113">Görünürlük ayarlama.</span><span class="sxs-lookup"><span data-stu-id="e12c3-113">Setting visibility.</span></span>  
  
-   <span data-ttu-id="e12c3-114">Esnetme değil bir denetim barındırma.</span><span class="sxs-lookup"><span data-stu-id="e12c3-114">Hosting a control that does not stretch.</span></span>  
  
-   <span data-ttu-id="e12c3-115">Ölçeklendirme.</span><span class="sxs-lookup"><span data-stu-id="e12c3-115">Scaling.</span></span>  
  
-   <span data-ttu-id="e12c3-116">Döndürme.</span><span class="sxs-lookup"><span data-stu-id="e12c3-116">Rotating.</span></span>  
  
-   <span data-ttu-id="e12c3-117">Ayar doldurma ve kenar boşlukları.</span><span class="sxs-lookup"><span data-stu-id="e12c3-117">Setting padding and margins.</span></span>  
  
-   <span data-ttu-id="e12c3-118">Dinamik düzen kapsayıcıları kullanma.</span><span class="sxs-lookup"><span data-stu-id="e12c3-118">Using dynamic layout containers.</span></span>  
  
 <span data-ttu-id="e12c3-119">Bu izlenecek yolda gösterilen görevler tam kod listesi için bkz. [WPF Örneği'nde Windows Forms denetimlerini düzenleme](https://go.microsoft.com/fwlink/?LinkID=159971).</span><span class="sxs-lookup"><span data-stu-id="e12c3-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159971).</span></span>  
  
 <span data-ttu-id="e12c3-120">İşlemi tamamladığınızda, bir anlayışa sahip [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] düzen özellikleri [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-tabanlı uygulamaları.</span><span class="sxs-lookup"><span data-stu-id="e12c3-120">When you are finished, you will have an understanding of [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e12c3-121">Önkoşullar</span><span class="sxs-lookup"><span data-stu-id="e12c3-121">Prerequisites</span></span>  

<span data-ttu-id="e12c3-122">Bu izlenecek yolu tamamlamak için Visual Studio ihtiyacınız vardır.</span><span class="sxs-lookup"><span data-stu-id="e12c3-122">You need Visual Studio to complete this walkthrough.</span></span>
  
## <a name="creating-the-project"></a><span data-ttu-id="e12c3-123">Projeyi Oluşturma</span><span class="sxs-lookup"><span data-stu-id="e12c3-123">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="e12c3-124">Oluşturma ve projesi kurun</span><span class="sxs-lookup"><span data-stu-id="e12c3-124">To create and set up the project</span></span>  
  
1.  <span data-ttu-id="e12c3-125">Adlı bir WPF uygulaması projesi oluşturmak `WpfLayoutHostingWf`.</span><span class="sxs-lookup"><span data-stu-id="e12c3-125">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>  
  
2.  <span data-ttu-id="e12c3-126">Çözüm Gezgini'nde, aşağıdaki derlemelere başvurular ekleyin.</span><span class="sxs-lookup"><span data-stu-id="e12c3-126">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="e12c3-127">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="e12c3-127">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="e12c3-128">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="e12c3-128">System.Windows.Forms</span></span>  
  
    -   <span data-ttu-id="e12c3-129">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="e12c3-129">System.Drawing</span></span>  
  
3.  <span data-ttu-id="e12c3-130">MainWindow.xaml XAML görünümünde açmak için çift tıklayın.</span><span class="sxs-lookup"><span data-stu-id="e12c3-130">Double-click MainWindow.xaml to open it in XAML view.</span></span>  
  
4.  <span data-ttu-id="e12c3-131">İçinde <xref:System.Windows.Window> öğesi, aşağıdaki [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ad alanı eşlemesi.</span><span class="sxs-lookup"><span data-stu-id="e12c3-131">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespace mapping.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  <span data-ttu-id="e12c3-132">İçinde <xref:System.Windows.Controls.Grid> öğe kümesi <xref:System.Windows.Controls.Grid.ShowGridLines%2A> özelliğini `true` ve beş satır ve üç sütun tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="e12c3-132">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## <a name="using-default-layout-settings"></a><span data-ttu-id="e12c3-133">Varsayılan düzen ayarlarını kullanma</span><span class="sxs-lookup"><span data-stu-id="e12c3-133">Using Default Layout Settings</span></span>  
 <span data-ttu-id="e12c3-134">Varsayılan olarak, <xref:System.Windows.Forms.Integration.WindowsFormsHost> öğesi barındırılan düzenini işler [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] denetimi.</span><span class="sxs-lookup"><span data-stu-id="e12c3-134">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
#### <a name="to-use-default-layout-settings"></a><span data-ttu-id="e12c3-135">Varsayılan düzen ayarlarını kullanmak için</span><span class="sxs-lookup"><span data-stu-id="e12c3-135">To use default layout settings</span></span>  
  
1.  <span data-ttu-id="e12c3-136">İçine aşağıdaki XAML kopyalama <xref:System.Windows.Controls.Grid> öğesi.</span><span class="sxs-lookup"><span data-stu-id="e12c3-136">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2.  <span data-ttu-id="e12c3-137">Derleme ve uygulamayı çalıştırmak için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="e12c3-137">Press F5 to build and run the application.</span></span> <span data-ttu-id="e12c3-138">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Button?displayProperty=nameWithType> Denetimi görünür <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="e12c3-138">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="e12c3-139">Barındırılan denetim içeriğine göre boyutlandırılır ve <xref:System.Windows.Forms.Integration.WindowsFormsHost> öğesi boyutta denetimden uyum sağlamak için.</span><span class="sxs-lookup"><span data-stu-id="e12c3-139">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>  
  
## <a name="sizing-to-content"></a><span data-ttu-id="e12c3-140">İçerik boyutu</span><span class="sxs-lookup"><span data-stu-id="e12c3-140">Sizing to Content</span></span>  
 <span data-ttu-id="e12c3-141"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Öğesini denetimden içeriği düzgün görüntülenmesi için boyutlandırılır sağlar.</span><span class="sxs-lookup"><span data-stu-id="e12c3-141">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>  
  
#### <a name="to-size-to-content"></a><span data-ttu-id="e12c3-142">İçerik boyutu</span><span class="sxs-lookup"><span data-stu-id="e12c3-142">To size to content</span></span>  
  
1.  <span data-ttu-id="e12c3-143">İçine aşağıdaki XAML kopyalama <xref:System.Windows.Controls.Grid> öğesi.</span><span class="sxs-lookup"><span data-stu-id="e12c3-143">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2.  <span data-ttu-id="e12c3-144">Derleme ve uygulamayı çalıştırmak için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="e12c3-144">Press F5 to build and run the application.</span></span> <span data-ttu-id="e12c3-145">İki yeni düğme denetimleri düzgün bir şekilde, daha büyük yazı tipi boyutu ve uzun metin dizesini görüntülemek için boyutlandırılır ve <xref:System.Windows.Forms.Integration.WindowsFormsHost> öğeleri barındırılan denetimlerin sığması için yeniden boyutlandırılır.</span><span class="sxs-lookup"><span data-stu-id="e12c3-145">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>  
  
## <a name="using-absolute-positioning"></a><span data-ttu-id="e12c3-146">Mutlak konumlandırmayı kullanma</span><span class="sxs-lookup"><span data-stu-id="e12c3-146">Using Absolute Positioning</span></span>  
 <span data-ttu-id="e12c3-147">Mutlak konumlandırma yerleştirmek için kullanabileceğiniz <xref:System.Windows.Forms.Integration.WindowsFormsHost> öğesini herhangi bir kullanıcı arabirimi (UI).</span><span class="sxs-lookup"><span data-stu-id="e12c3-147">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>  
  
#### <a name="to-use-absolute-positioning"></a><span data-ttu-id="e12c3-148">Mutlak konumlandırma kullanmak için</span><span class="sxs-lookup"><span data-stu-id="e12c3-148">To use absolute positioning</span></span>  
  
1.  <span data-ttu-id="e12c3-149">İçine aşağıdaki XAML kopyalama <xref:System.Windows.Controls.Grid> öğesi.</span><span class="sxs-lookup"><span data-stu-id="e12c3-149">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2.  <span data-ttu-id="e12c3-150">Derleme ve uygulamayı çalıştırmak için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="e12c3-150">Press F5 to build and run the application.</span></span> <span data-ttu-id="e12c3-151"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Öğe, kılavuz hücresi üst tarafındaki 20 piksel ve 20 piksel soldan yerleştirilir.</span><span class="sxs-lookup"><span data-stu-id="e12c3-151">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>  
  
## <a name="specifying-size-explicitly"></a><span data-ttu-id="e12c3-152">Açıkça boyutunu belirtme</span><span class="sxs-lookup"><span data-stu-id="e12c3-152">Specifying Size Explicitly</span></span>  
 <span data-ttu-id="e12c3-153">Boyutunu belirtebilirsiniz <xref:System.Windows.Forms.Integration.WindowsFormsHost> öğesini kullanarak <xref:System.Windows.FrameworkElement.Width%2A> ve <xref:System.Windows.FrameworkElement.Height%2A> özellikleri.</span><span class="sxs-lookup"><span data-stu-id="e12c3-153">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>  
  
#### <a name="to-specify-size-explicitly"></a><span data-ttu-id="e12c3-154">Boyutu açıkça belirtmek için</span><span class="sxs-lookup"><span data-stu-id="e12c3-154">To specify size explicitly</span></span>  
  
1.  <span data-ttu-id="e12c3-155">İçine aşağıdaki XAML kopyalama <xref:System.Windows.Controls.Grid> öğesi.</span><span class="sxs-lookup"><span data-stu-id="e12c3-155">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2.  <span data-ttu-id="e12c3-156">Derleme ve uygulamayı çalıştırmak için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="e12c3-156">Press F5 to build and run the application.</span></span> <span data-ttu-id="e12c3-157"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Öğesi varsayılan düzen ayarlarından daha küçük olan bir boyutu 50 piksel genişliğinde ve 70 piksel yüksekliğinde, ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="e12c3-157">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="e12c3-158">İçeriği [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] denetimi uygun şekilde düzenlenmeyecek.</span><span class="sxs-lookup"><span data-stu-id="e12c3-158">The content of the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is rearranged accordingly.</span></span>  
  
## <a name="setting-layout-properties"></a><span data-ttu-id="e12c3-159">Düzen özelliklerini ayarlama</span><span class="sxs-lookup"><span data-stu-id="e12c3-159">Setting Layout Properties</span></span>  
 <span data-ttu-id="e12c3-160">Her zaman düzen ile ilgili özellikleri ayarlamak üzerinde barındırılan denetim özelliklerini kullanarak <xref:System.Windows.Forms.Integration.WindowsFormsHost> öğesi.</span><span class="sxs-lookup"><span data-stu-id="e12c3-160">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="e12c3-161">Doğrudan barındırılan denetimde düzen özelliklerini ayarlama, istenmeyen sonuçlar verir.</span><span class="sxs-lookup"><span data-stu-id="e12c3-161">Setting layout properties directly on the hosted control will yield unintended results.</span></span>  
  
 <span data-ttu-id="e12c3-162">Düzen ilgili özellikler barındırılan denetimi ayarını [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hiçbir etkisi olmaz.</span><span class="sxs-lookup"><span data-stu-id="e12c3-162">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>  
  
#### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a><span data-ttu-id="e12c3-163">Üzerinde barındırılan denetim özelliklerini ayarlama etkilere bakın</span><span class="sxs-lookup"><span data-stu-id="e12c3-163">To see the effects of setting properties on the hosted control</span></span>  
  
1.  <span data-ttu-id="e12c3-164">İçine aşağıdaki XAML kopyalama <xref:System.Windows.Controls.Grid> öğesi.</span><span class="sxs-lookup"><span data-stu-id="e12c3-164">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2.  <span data-ttu-id="e12c3-165">Çözüm Gezgini içinde MainWindow.xaml çift tıklayın.</span><span class="sxs-lookup"><span data-stu-id="e12c3-165">In Solution Explorer, double-click MainWindow.xaml.</span></span> <span data-ttu-id="e12c3-166">vb veya MainWindow.xaml.cs Kod Düzenleyicisi'nde açın.</span><span class="sxs-lookup"><span data-stu-id="e12c3-166">vb or MainWindow.xaml.cs to open it in the Code Editor.</span></span>  
  
3.  <span data-ttu-id="e12c3-167">Aşağıdaki kodu kopyalayın `MainWindow` sınıf tanımını.</span><span class="sxs-lookup"><span data-stu-id="e12c3-167">Copy the following code into the `MainWindow` class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4.  <span data-ttu-id="e12c3-168">Derleme ve uygulamayı çalıştırmak için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="e12c3-168">Press F5 to build and run the application.</span></span>

5.  <span data-ttu-id="e12c3-169">Tıklayın **me tıklayın** düğmesi.</span><span class="sxs-lookup"><span data-stu-id="e12c3-169">Click the **Click me** button.</span></span> <span data-ttu-id="e12c3-170">`button1_Click` Olay işleyicisi kümeleri <xref:System.Windows.Forms.Control.Top%2A> ve <xref:System.Windows.Forms.Control.Left%2A> barındırılan denetim özellikleri.</span><span class="sxs-lookup"><span data-stu-id="e12c3-170">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="e12c3-171">Bu içinde konumlandırılmasına denetimden neden <xref:System.Windows.Forms.Integration.WindowsFormsHost> öğesi.</span><span class="sxs-lookup"><span data-stu-id="e12c3-171">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="e12c3-172">Konak aynı ekran alanını korur, ancak denetimden kırpılır.</span><span class="sxs-lookup"><span data-stu-id="e12c3-172">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="e12c3-173">Bunun yerine barındırılan denetimi her zaman dolması gerektiğini <xref:System.Windows.Forms.Integration.WindowsFormsHost> öğesi.</span><span class="sxs-lookup"><span data-stu-id="e12c3-173">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

## <a name="understanding-z-order-limitations"></a><span data-ttu-id="e12c3-174">Z düzenini sınırlamaları anlama</span><span class="sxs-lookup"><span data-stu-id="e12c3-174">Understanding Z-Order Limitations</span></span>
 <span data-ttu-id="e12c3-175">Görünür <xref:System.Windows.Forms.Integration.WindowsFormsHost> öğeleri her zaman diğer WPF öğeleri üzerine çizilmiş ve z-düzeni tarafından etkilenmez.</span><span class="sxs-lookup"><span data-stu-id="e12c3-175">Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other WPF elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="e12c3-176">Bu z düzenini davranışını görmek için aşağıdakileri yapın:</span><span class="sxs-lookup"><span data-stu-id="e12c3-176">To see this z-order behavior, do the following:</span></span>

1.  <span data-ttu-id="e12c3-177">İçine aşağıdaki XAML kopyalama <xref:System.Windows.Controls.Grid> öğesi.</span><span class="sxs-lookup"><span data-stu-id="e12c3-177">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2.  <span data-ttu-id="e12c3-178">Derleme ve uygulamayı çalıştırmak için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="e12c3-178">Press F5 to build and run the application.</span></span> <span data-ttu-id="e12c3-179"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Öğesi etiketi öğenin boyanır.</span><span class="sxs-lookup"><span data-stu-id="e12c3-179">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>

## <a name="docking"></a><span data-ttu-id="e12c3-180">Yerleştirme</span><span class="sxs-lookup"><span data-stu-id="e12c3-180">Docking</span></span>
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> <span data-ttu-id="e12c3-181">öğesinin desteklediği [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] yerleştirme.</span><span class="sxs-lookup"><span data-stu-id="e12c3-181">element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="e12c3-182">Ayarlama <xref:System.Windows.Controls.DockPanel.Dock%2A> ekli özellik barındırılan denetimi sabitlemek için bir <xref:System.Windows.Controls.DockPanel> öğesi.</span><span class="sxs-lookup"><span data-stu-id="e12c3-182">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>

#### <a name="to-dock-a-hosted-control"></a><span data-ttu-id="e12c3-183">Barındırılan bir denetim sabitlemek için</span><span class="sxs-lookup"><span data-stu-id="e12c3-183">To dock a hosted control</span></span>

1.  <span data-ttu-id="e12c3-184">İçine aşağıdaki XAML kopyalama <xref:System.Windows.Controls.Grid> öğesi.</span><span class="sxs-lookup"><span data-stu-id="e12c3-184">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2.  <span data-ttu-id="e12c3-185">Derleme ve uygulamayı çalıştırmak için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="e12c3-185">Press F5 to build and run the application.</span></span> <span data-ttu-id="e12c3-186"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Öğesi sağ tarafına yerleştirilmiş <xref:System.Windows.Controls.DockPanel> öğesi.</span><span class="sxs-lookup"><span data-stu-id="e12c3-186">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>

## <a name="setting-visibility"></a><span data-ttu-id="e12c3-187">Görünürlük ayarlama</span><span class="sxs-lookup"><span data-stu-id="e12c3-187">Setting Visibility</span></span>
 <span data-ttu-id="e12c3-188">Yapabileceğiniz, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] denetiminizi görünmez veya ayarlayarak Daralt <xref:System.Windows.UIElement.Visibility%2A> özelliği <xref:System.Windows.Forms.Integration.WindowsFormsHost> öğesi.</span><span class="sxs-lookup"><span data-stu-id="e12c3-188">You can make your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="e12c3-189">Bir denetim görünmez olduğunda görüntülenmez, ancak düzen yer kaplar.</span><span class="sxs-lookup"><span data-stu-id="e12c3-189">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="e12c3-190">Bir denetim daraltıldığında görüntülenmez veya Düzen boşluk kaplamaz.</span><span class="sxs-lookup"><span data-stu-id="e12c3-190">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>

#### <a name="to-set-the-visibility-of-a-hosted-control"></a><span data-ttu-id="e12c3-191">Barındırılan bir denetim görünürlüğünü ayarlamak için</span><span class="sxs-lookup"><span data-stu-id="e12c3-191">To set the visibility of a hosted control</span></span>

1.  <span data-ttu-id="e12c3-192">İçine aşağıdaki XAML kopyalama <xref:System.Windows.Controls.Grid> öğesi.</span><span class="sxs-lookup"><span data-stu-id="e12c3-192">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2.  <span data-ttu-id="e12c3-193">MainWindow.xaml.vb veya MainWindow.xaml.cs seçeneğinde, sınıf tanımının içine aşağıdaki kodu kopyalayın.</span><span class="sxs-lookup"><span data-stu-id="e12c3-193">In MainWindow.xaml.vb or MainWindow.xaml.cs, copy the following code into the class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3.  <span data-ttu-id="e12c3-194">Derleme ve uygulamayı çalıştırmak için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="e12c3-194">Press F5 to build and run the application.</span></span>

4.  <span data-ttu-id="e12c3-195">Tıklayın **görünmez yapmak için tıklatın** düğmesini <xref:System.Windows.Forms.Integration.WindowsFormsHost> öğe görünmez.</span><span class="sxs-lookup"><span data-stu-id="e12c3-195">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>

5.  <span data-ttu-id="e12c3-196">Tıklayın **daraltmak için tıklatın** gizlemek için düğme <xref:System.Windows.Forms.Integration.WindowsFormsHost> düzenini öğesinden tamamen.</span><span class="sxs-lookup"><span data-stu-id="e12c3-196">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="e12c3-197">Zaman [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] denetimi daraltıldığında, çevreleyen öğeler alanı kaplaması için düzenlenir.</span><span class="sxs-lookup"><span data-stu-id="e12c3-197">When the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>

## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="e12c3-198">Esnetme değil bir denetimi barındırma</span><span class="sxs-lookup"><span data-stu-id="e12c3-198">Hosting a Control That Does Not Stretch</span></span>
 <span data-ttu-id="e12c3-199">Bazı [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] denetimleri sabit bir boyuta sahiptir ve düzendeki kullanılabilir alanı dolduracak şekilde uzatılır değil.</span><span class="sxs-lookup"><span data-stu-id="e12c3-199">Some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="e12c3-200">Örneğin, <xref:System.Windows.Forms.MonthCalendar> denetimi, bir ay sabit boşluk görüntüler.</span><span class="sxs-lookup"><span data-stu-id="e12c3-200">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>

#### <a name="to-host-a-control-that-does-not-stretch"></a><span data-ttu-id="e12c3-201">Esnetme değil bir denetimi barındırma</span><span class="sxs-lookup"><span data-stu-id="e12c3-201">To host a control that does not stretch</span></span>

1.  <span data-ttu-id="e12c3-202">İçine aşağıdaki XAML kopyalama <xref:System.Windows.Controls.Grid> öğesi.</span><span class="sxs-lookup"><span data-stu-id="e12c3-202">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2.  <span data-ttu-id="e12c3-203">Derleme ve uygulamayı çalıştırmak için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="e12c3-203">Press F5 to build and run the application.</span></span> <span data-ttu-id="e12c3-204"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Öğe, kılavuz satırı içinde ortalanır, ancak bunu kullanılabilir alanı dolduracak şekilde genişletilir değil.</span><span class="sxs-lookup"><span data-stu-id="e12c3-204">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="e12c3-205">Pencerenin yeterince büyük ise, iki veya daha fazla aylık barındırılan tarafından görüntülenen görebilirsiniz <xref:System.Windows.Forms.MonthCalendar> denetimidir, ancak bu satırda ortalanır.</span><span class="sxs-lookup"><span data-stu-id="e12c3-205">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="e12c3-206">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Yerleşim altyapısı kullanılabilir alanı dolduracak şekilde boyutlandırılmalıdır olamaz öğeleri ortalar.</span><span class="sxs-lookup"><span data-stu-id="e12c3-206">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>

## <a name="scaling"></a><span data-ttu-id="e12c3-207">Ölçeklendirme</span><span class="sxs-lookup"><span data-stu-id="e12c3-207">Scaling</span></span>
 <span data-ttu-id="e12c3-208">WPF öğesinin aksine, çoğu Windows Forms denetimlerini sürekli olarak ölçeklenebilir değildir.</span><span class="sxs-lookup"><span data-stu-id="e12c3-208">Unlike WPF elements, most Windows Forms controls are not continuously scalable.</span></span> <span data-ttu-id="e12c3-209">Özel bir ölçekleme sağlamak için geçersiz kılma <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="e12c3-209">To provide custom scaling, you override the <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> method.</span></span>

#### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a><span data-ttu-id="e12c3-210">Barındırılan bir denetimin varsayılan davranışını kullanarak ölçeklendirme</span><span class="sxs-lookup"><span data-stu-id="e12c3-210">To scale a hosted control by using the default behavior</span></span>

1.  <span data-ttu-id="e12c3-211">İçine aşağıdaki XAML kopyalama <xref:System.Windows.Controls.Grid> öğesi.</span><span class="sxs-lookup"><span data-stu-id="e12c3-211">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2.  <span data-ttu-id="e12c3-212">Derleme ve uygulamayı çalıştırmak için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="e12c3-212">Press F5 to build and run the application.</span></span> <span data-ttu-id="e12c3-213">Barındırılan denetim ve çevreleyen öğeleri 0,5 faktörüyle ölçeklenir.</span><span class="sxs-lookup"><span data-stu-id="e12c3-213">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="e12c3-214">Ancak, barındırılan denetim yazı tipi ölçeklenmez.</span><span class="sxs-lookup"><span data-stu-id="e12c3-214">However, the hosted control's font is not scaled.</span></span>

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a><span data-ttu-id="e12c3-215">Döndürme</span><span class="sxs-lookup"><span data-stu-id="e12c3-215">Rotating</span></span>
 <span data-ttu-id="e12c3-216">WPF öğesinin aksine, Windows Forms denetimleri döndürmeyi desteklemez.</span><span class="sxs-lookup"><span data-stu-id="e12c3-216">Unlike WPF elements, Windows Forms controls do not support rotation.</span></span> <span data-ttu-id="e12c3-217"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Öğesi döndürme dönüşümü uygulandığı zaman diğer WPF öğelerle döndürülmez.</span><span class="sxs-lookup"><span data-stu-id="e12c3-217">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other WPF elements when a rotation transformation is applied.</span></span> <span data-ttu-id="e12c3-218">180 derece harekete geçirirse dışındaki herhangi bir dönüş değeri <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> olay.</span><span class="sxs-lookup"><span data-stu-id="e12c3-218">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>

#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a><span data-ttu-id="e12c3-219">Döndürme karma uygulamada etkisini görmek için</span><span class="sxs-lookup"><span data-stu-id="e12c3-219">To see the effect of rotation in a hybrid application</span></span>

1.  <span data-ttu-id="e12c3-220">İçine aşağıdaki XAML kopyalama <xref:System.Windows.Controls.Grid> öğesi.</span><span class="sxs-lookup"><span data-stu-id="e12c3-220">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2.  <span data-ttu-id="e12c3-221">Derleme ve uygulamayı çalıştırmak için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="e12c3-221">Press F5 to build and run the application.</span></span> <span data-ttu-id="e12c3-222">Barındırılan denetim değil döndürülür, ancak çevreleyen öğeleri 180 derece açının tarafından döndürülür.</span><span class="sxs-lookup"><span data-stu-id="e12c3-222">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="e12c3-223">Öğeleri görmek için pencereyi boyutlandırmak olabilir.</span><span class="sxs-lookup"><span data-stu-id="e12c3-223">You may have to resize the window to see the elements.</span></span>

## <a name="setting-padding-and-margins"></a><span data-ttu-id="e12c3-224">Ayar doldurma ve kenar boşlukları</span><span class="sxs-lookup"><span data-stu-id="e12c3-224">Setting Padding and Margins</span></span>
 <span data-ttu-id="e12c3-225">Doldurma ve kenar boşlukları [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Düzen doldurma ve kenar boşlukları benzer [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e12c3-225">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="e12c3-226">Ayarlamanız yeterlidir <xref:System.Windows.Controls.Control.Padding%2A> ve <xref:System.Windows.FrameworkElement.Margin%2A> özellikleri <xref:System.Windows.Forms.Integration.WindowsFormsHost> öğesi.</span><span class="sxs-lookup"><span data-stu-id="e12c3-226">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

#### <a name="to-set-padding-and-margins-for-a-hosted-control"></a><span data-ttu-id="e12c3-227">Doldurma ve barındırılan denetim kenar boşluklarını ayarlama</span><span class="sxs-lookup"><span data-stu-id="e12c3-227">To set padding and margins for a hosted control</span></span>

1.  <span data-ttu-id="e12c3-228">İçine aşağıdaki XAML kopyalama <xref:System.Windows.Controls.Grid> öğesi.</span><span class="sxs-lookup"><span data-stu-id="e12c3-228">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2.  <span data-ttu-id="e12c3-229">Derleme ve uygulamayı çalıştırmak için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="e12c3-229">Press F5 to build and run the application.</span></span> <span data-ttu-id="e12c3-230">Doldurma ve kenar boşluğu ayarlar uygulanır barındırılan [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] uygulanacağı de aynı şekilde denetimleri [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e12c3-230">The padding and margin settings are applied to the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in the same way they would be applied in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="e12c3-231">Dinamik düzen kapsayıcılarını kullanma</span><span class="sxs-lookup"><span data-stu-id="e12c3-231">Using Dynamic Layout Containers</span></span>
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <span data-ttu-id="e12c3-232">iki dinamik düzen kapsayıcılar sağlayarak <xref:System.Windows.Forms.FlowLayoutPanel> ve <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="e12c3-232">provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="e12c3-233">Bu kapsayıcıları da kullanabilirsiniz [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] düzenler.</span><span class="sxs-lookup"><span data-stu-id="e12c3-233">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>

#### <a name="to-use-a-dynamic-layout-container"></a><span data-ttu-id="e12c3-234">Dinamik düzen kapsayıcısı kullanmak için</span><span class="sxs-lookup"><span data-stu-id="e12c3-234">To use a dynamic layout container</span></span>

1.  <span data-ttu-id="e12c3-235">İçine aşağıdaki XAML kopyalama <xref:System.Windows.Controls.Grid> öğesi.</span><span class="sxs-lookup"><span data-stu-id="e12c3-235">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2.  <span data-ttu-id="e12c3-236">MainWindow.xaml.vb veya MainWindow.xaml.cs içinde sınıf tanımının içine aşağıdaki kodu kopyalayın.</span><span class="sxs-lookup"><span data-stu-id="e12c3-236">In MainWindow.xaml.vb or MainWindow.xaml.cs copy the following code into the class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3.  <span data-ttu-id="e12c3-237">Bir çağrı ekleyin `InitializeFlowLayoutPanel` oluşturucuda yöntemi.</span><span class="sxs-lookup"><span data-stu-id="e12c3-237">Add a call to the `InitializeFlowLayoutPanel` method in the constructor.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4.  <span data-ttu-id="e12c3-238">Derleme ve uygulamayı çalıştırmak için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="e12c3-238">Press F5 to build and run the application.</span></span> <span data-ttu-id="e12c3-239"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Öğesi doldurur <xref:System.Windows.Controls.DockPanel>, ve <xref:System.Windows.Forms.FlowLayoutPanel> varsayılan, alt denetimlerini düzenler <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span><span class="sxs-lookup"><span data-stu-id="e12c3-239">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e12c3-240">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="e12c3-240">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="e12c3-241">Visual Studio’da XAML tasarlama</span><span class="sxs-lookup"><span data-stu-id="e12c3-241">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="e12c3-242">WindowsFormsHost Öğesi için Düzen Konusunda Dikkat Edilmesi Gereken Noktalar</span><span class="sxs-lookup"><span data-stu-id="e12c3-242">Layout Considerations for the WindowsFormsHost Element</span></span>](layout-considerations-for-the-windowsformshost-element.md)
- [<span data-ttu-id="e12c3-243">Düzenleme Windows Forms denetimleri örneği</span><span class="sxs-lookup"><span data-stu-id="e12c3-243">Arranging Windows Forms Controls in WPF Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159971)
- [<span data-ttu-id="e12c3-244">İzlenecek yol: WPF'de Windows Forms Bileşik Denetimini Barındırma</span><span class="sxs-lookup"><span data-stu-id="e12c3-244">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="e12c3-245">İzlenecek yol: WPF Bileşik Denetimini Windows Forms İçinde Barındırma</span><span class="sxs-lookup"><span data-stu-id="e12c3-245">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
