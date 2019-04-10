---
title: 'İzlenecek yol: ElementHost Denetimini Kullanarak Özellikleri Eşleme'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
ms.openlocfilehash: 360f19e558f97e1807b329ad18e429fa893bbf86
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59300924"
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a><span data-ttu-id="7fd48-102">İzlenecek yol: ElementHost Denetimini Kullanarak Özellikleri Eşleme</span><span class="sxs-lookup"><span data-stu-id="7fd48-102">Walkthrough: Mapping Properties Using the ElementHost Control</span></span>

<span data-ttu-id="7fd48-103">Bu izlenecek yol size nasıl kullanılacağını gösterir <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> eşlemek için özellik [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] barındırılan karşılık gelen özelliklere özellikleri [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] öğesi.</span><span class="sxs-lookup"><span data-stu-id="7fd48-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> property to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element.</span></span>

<span data-ttu-id="7fd48-104">Bu kılavuzda gösterilen görevler aşağıdakileri içerir:</span><span class="sxs-lookup"><span data-stu-id="7fd48-104">Tasks illustrated in this walkthrough include:</span></span>

-   <span data-ttu-id="7fd48-105">Proje oluşturuluyor.</span><span class="sxs-lookup"><span data-stu-id="7fd48-105">Creating the project.</span></span>

-   <span data-ttu-id="7fd48-106">Yeni bir özellik eşlemesi tanımlama.</span><span class="sxs-lookup"><span data-stu-id="7fd48-106">Defining a new property mapping.</span></span>

-   <span data-ttu-id="7fd48-107">Varsayılan özellik eşlemesi kaldırılıyor.</span><span class="sxs-lookup"><span data-stu-id="7fd48-107">Removing a default property mapping.</span></span>

-   <span data-ttu-id="7fd48-108">Varsayılan özellik eşlemesi genişletme.</span><span class="sxs-lookup"><span data-stu-id="7fd48-108">Extending a default property mapping.</span></span>

<span data-ttu-id="7fd48-109">Bu izlenecek yolda gösterilen görevler tam kod listesi için bkz. [ElementHost denetimi örneğini kullanarak eşleme özelliklerini](https://go.microsoft.com/fwlink/?LinkID=160018).</span><span class="sxs-lookup"><span data-stu-id="7fd48-109">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the ElementHost Control Sample](https://go.microsoft.com/fwlink/?LinkID=160018).</span></span>

<span data-ttu-id="7fd48-110">Bitirdiğiniz zaman, eşlemek mümkün olmayacak [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] karşılık gelen özellikleri [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] barındırılan bir öğedeki özellikleri.</span><span class="sxs-lookup"><span data-stu-id="7fd48-110">When you are finished, you will be able to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties on a hosted element.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7fd48-111">Önkoşullar</span><span class="sxs-lookup"><span data-stu-id="7fd48-111">Prerequisites</span></span>

<span data-ttu-id="7fd48-112">Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:</span><span class="sxs-lookup"><span data-stu-id="7fd48-112">You need the following components to complete this walkthrough:</span></span>

-   <span data-ttu-id="7fd48-113">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="7fd48-113">Visual Studio 2017</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="7fd48-114">Projeyi Oluşturma</span><span class="sxs-lookup"><span data-stu-id="7fd48-114">Creating the Project</span></span>

### <a name="to-create-the-project"></a><span data-ttu-id="7fd48-115">Proje oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="7fd48-115">To create the project</span></span>

1. <span data-ttu-id="7fd48-116">Oluşturma bir **Windows Forms uygulaması** adlı proje `PropertyMappingWithElementHost`.</span><span class="sxs-lookup"><span data-stu-id="7fd48-116">Create a **Windows Forms App** project named `PropertyMappingWithElementHost`.</span></span>

2. <span data-ttu-id="7fd48-117">İçinde **Çözüm Gezgini**, aşağıdaki başvuruları ekleyin [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] derlemeler.</span><span class="sxs-lookup"><span data-stu-id="7fd48-117">In **Solution Explorer**, add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies.</span></span>

    -   <span data-ttu-id="7fd48-118">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="7fd48-118">PresentationCore</span></span>

    -   <span data-ttu-id="7fd48-119">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="7fd48-119">PresentationFramework</span></span>

    -   <span data-ttu-id="7fd48-120">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="7fd48-120">WindowsBase</span></span>

    -   <span data-ttu-id="7fd48-121">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="7fd48-121">WindowsFormsIntegration</span></span>

3. <span data-ttu-id="7fd48-122">Üstüne aşağıdaki kodu kopyalayın `Form1` kod dosyası.</span><span class="sxs-lookup"><span data-stu-id="7fd48-122">Copy the following code into the top of the `Form1` code file.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#10](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]

4. <span data-ttu-id="7fd48-123">Açık `Form1` Windows Forms Tasarımcısı'nda.</span><span class="sxs-lookup"><span data-stu-id="7fd48-123">Open `Form1` in the Windows Forms Designer.</span></span> <span data-ttu-id="7fd48-124">Bir olay işleyicisi eklemek için formu <xref:System.Windows.Forms.Form.Load> olay.</span><span class="sxs-lookup"><span data-stu-id="7fd48-124">Double-click the form to add an event handler for the <xref:System.Windows.Forms.Form.Load> event.</span></span>

5. <span data-ttu-id="7fd48-125">Windows Forms Tasarımcısı'na dönün ve form için bir olay işleyicisi ekleme <xref:System.Windows.Forms.Control.Resize> olay.</span><span class="sxs-lookup"><span data-stu-id="7fd48-125">Return to the Windows Forms Designer and add an event handler for the form's <xref:System.Windows.Forms.Control.Resize> event.</span></span> <span data-ttu-id="7fd48-126">Daha fazla bilgi için [nasıl yapılır: Tasarımcıyı kullanarak olay işleyicileri oluşturma](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="7fd48-126">For more information, see [How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span></span>

6. <span data-ttu-id="7fd48-127">Bildirme bir <xref:System.Windows.Forms.Integration.ElementHost> alanındaki `Form1` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="7fd48-127">Declare an <xref:System.Windows.Forms.Integration.ElementHost> field in the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#16](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]

## <a name="defining-new-property-mappings"></a><span data-ttu-id="7fd48-128">Yeni Özellik eşlemeleri tanımlama</span><span class="sxs-lookup"><span data-stu-id="7fd48-128">Defining New Property Mappings</span></span>

<span data-ttu-id="7fd48-129"><xref:System.Windows.Forms.Integration.ElementHost> Denetim birkaç varsayılan özellik eşlemeleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="7fd48-129">The <xref:System.Windows.Forms.Integration.ElementHost> control provides several default property mappings.</span></span> <span data-ttu-id="7fd48-130">Çağırarak yeni bir özellik eşlemesi Ekle <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> metodunda <xref:System.Windows.Forms.Integration.ElementHost> denetimin <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="7fd48-130">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-define-new-property-mappings"></a><span data-ttu-id="7fd48-131">Yeni Özellik eşlemeleri tanımlamak için</span><span class="sxs-lookup"><span data-stu-id="7fd48-131">To define new property mappings</span></span>

1. <span data-ttu-id="7fd48-132">Tanımı aşağıdaki kodu kopyalayarak `Form1` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="7fd48-132">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]

     <span data-ttu-id="7fd48-133">`AddMarginMapping` Yöntemi ekler için yeni bir eşleme <xref:System.Windows.Forms.Control.Margin%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="7fd48-133">The `AddMarginMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span>

     <span data-ttu-id="7fd48-134">`OnMarginChange` Yöntemi çevirir <xref:System.Windows.Forms.Control.Margin%2A> özelliğini [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="7fd48-134">The `OnMarginChange` method translates the <xref:System.Windows.Forms.Control.Margin%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> property.</span></span>

2. <span data-ttu-id="7fd48-135">Tanımı aşağıdaki kodu kopyalayarak `Form1` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="7fd48-135">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]

     <span data-ttu-id="7fd48-136">`AddRegionMapping` Yöntemi ekler için yeni bir eşleme <xref:System.Windows.Forms.Control.Region%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="7fd48-136">The `AddRegionMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Region%2A> property.</span></span>

     <span data-ttu-id="7fd48-137">`OnRegionChange` Yöntemi çevirir <xref:System.Windows.Forms.Control.Region%2A> özelliğini [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="7fd48-137">The `OnRegionChange` method translates the <xref:System.Windows.Forms.Control.Region%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> property.</span></span>

     <span data-ttu-id="7fd48-138">`Form1_Resize` Yöntemi işler formun <xref:System.Windows.Forms.Control.Resize> olay ve kırpma bölgesinin barındırılan uyacak şekilde boyutları.</span><span class="sxs-lookup"><span data-stu-id="7fd48-138">The `Form1_Resize` method handles the form's <xref:System.Windows.Forms.Control.Resize> event and sizes the clipping region to fit the hosted element.</span></span>

## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="7fd48-139">Varsayılan özellik eşlemesi kaldırılıyor</span><span class="sxs-lookup"><span data-stu-id="7fd48-139">Removing a Default Property Mapping</span></span>

<span data-ttu-id="7fd48-140">Çağırarak varsayılan özellik eşlemesini kaldırma <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> metodunda <xref:System.Windows.Forms.Integration.ElementHost> denetimin <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="7fd48-140">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="7fd48-141">Varsayılan özellik eşlemesini kaldırmak için</span><span class="sxs-lookup"><span data-stu-id="7fd48-141">To remove a default property mapping</span></span>

-   <span data-ttu-id="7fd48-142">Tanımı aşağıdaki kodu kopyalayarak `Form1` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="7fd48-142">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]

     <span data-ttu-id="7fd48-143">`RemoveCursorMapping` Yöntemi için varsayılan eşlemeyi siler <xref:System.Windows.Forms.Control.Cursor%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="7fd48-143">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.Forms.Control.Cursor%2A> property.</span></span>

## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="7fd48-144">Varsayılan özellik eşlemesi genişletme</span><span class="sxs-lookup"><span data-stu-id="7fd48-144">Extending a Default Property Mapping</span></span>

<span data-ttu-id="7fd48-145">Varsayılan özellik eşlemesini ve ayrıca kendi eşleme ile genişletmek kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7fd48-145">You can use a default property mapping and also extend it with your own mapping.</span></span>

### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="7fd48-146">Varsayılan özellik eşlemesi genişletmek için</span><span class="sxs-lookup"><span data-stu-id="7fd48-146">To extend a default property mapping</span></span>

-   <span data-ttu-id="7fd48-147">Tanımı aşağıdaki kodu kopyalayarak `Form1` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="7fd48-147">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]

     <span data-ttu-id="7fd48-148">`ExtendBackColorMapping` Yöntemi, varolan bir özel özellik translator ekler <xref:System.Windows.Forms.Control.BackColor%2A> özellik eşlemesi.</span><span class="sxs-lookup"><span data-stu-id="7fd48-148">The `ExtendBackColorMapping` method adds a custom property translator to the existing <xref:System.Windows.Forms.Control.BackColor%2A> property mapping.</span></span>

     <span data-ttu-id="7fd48-149">`OnBackColorChange` Yöntemi barındırılan denetim için belirli bir görüntünün atar <xref:System.Windows.Controls.Control.Background%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="7fd48-149">The `OnBackColorChange` method assigns a specific image to the hosted control's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="7fd48-150">`OnBackColorChange` Yöntemi, varsayılan özellik eşlemesi uygulandıktan sonra çağrılır.</span><span class="sxs-lookup"><span data-stu-id="7fd48-150">The `OnBackColorChange` method is called after the default property mapping is applied.</span></span>

## <a name="initialize-your-property-mappings"></a><span data-ttu-id="7fd48-151">Özellik eşlemelerinizin Başlat</span><span class="sxs-lookup"><span data-stu-id="7fd48-151">Initialize your property mappings</span></span>

1. <span data-ttu-id="7fd48-152">Tanımı aşağıdaki kodu kopyalayarak `Form1` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="7fd48-152">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]

     <span data-ttu-id="7fd48-153">`Form1_Load` Yöntemi tanıtıcıları <xref:System.Windows.Forms.Form.Load> olay ve aşağıdaki başlatmaya gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="7fd48-153">The `Form1_Load` method handles the <xref:System.Windows.Forms.Form.Load> event and performs the following initialization.</span></span>

    -   <span data-ttu-id="7fd48-154">Oluşturur bir [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> öğesi.</span><span class="sxs-lookup"><span data-stu-id="7fd48-154">Creates a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> element.</span></span>

    -   <span data-ttu-id="7fd48-155">Özellik eşlemelerini ayarlamak için daha önce izlenecek içinde tanımlanan yöntemleri çağırır.</span><span class="sxs-lookup"><span data-stu-id="7fd48-155">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>

    -   <span data-ttu-id="7fd48-156">Eşlenen özelliklere başlangıç değerleri atar.</span><span class="sxs-lookup"><span data-stu-id="7fd48-156">Assigns initial values to the mapped properties.</span></span>

2. <span data-ttu-id="7fd48-157">Derleme ve uygulamayı çalıştırmak için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="7fd48-157">Press F5 to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="7fd48-158">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="7fd48-158">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="7fd48-159">Windows Forms ve WPF Özelliğini Eşleme</span><span class="sxs-lookup"><span data-stu-id="7fd48-159">Windows Forms and WPF Property Mapping</span></span>](windows-forms-and-wpf-property-mapping.md)
- [<span data-ttu-id="7fd48-160">Visual Studio’da XAML tasarlama</span><span class="sxs-lookup"><span data-stu-id="7fd48-160">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="7fd48-161">İzlenecek yol: WPF Bileşik Denetimini Windows Forms İçinde Barındırma</span><span class="sxs-lookup"><span data-stu-id="7fd48-161">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)