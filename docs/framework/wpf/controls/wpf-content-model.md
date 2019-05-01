---
title: WPF İçerik Modeli
ms.date: 03/30/2017
helpviewer_keywords:
- UIElement class [WPF], displaying content
- content model [WPF], controls
- controls [WPF], displaying text
- content display [WPF], controls
- controls [WPF], formatting text
- displaying content [WPF]
- arbitrary content classes [WPF], content model
- ContentControl class [WPF], displaying content
ms.assetid: 214da5ef-547a-4cf8-9b07-4aa8a0e52cdd
ms.openlocfilehash: 4f866e0366a7781c287b3ebae7b668c2b296a5cc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62023939"
---
# <a name="wpf-content-model"></a><span data-ttu-id="a94bb-102">WPF İçerik Modeli</span><span class="sxs-lookup"><span data-stu-id="a94bb-102">WPF Content Model</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="a94bb-103">birçok denetimleri ve farklı içerik türlerini görüntülemek için birincil amacı olan denetim-like türleri sağlayan bir sunu platformudur.</span><span class="sxs-lookup"><span data-stu-id="a94bb-103">is a presentation platform that provides many controls and control-like types whose primary purpose is to display different types of content.</span></span> <span data-ttu-id="a94bb-104">Hangi denetimi kullanmak için veya türetmek için hangi denetimi belirlemek için belirli bir denetimi en iyi görüntüleyebilirsiniz nesne türlerini anlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="a94bb-104">To determine which control to use or which control to derive from, you should understand the kinds of objects a particular control can best display.</span></span>  
  
 <span data-ttu-id="a94bb-105">İçerik modeli için bu konuda özetlenir [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] denetimi ve denetim-like türleri.</span><span class="sxs-lookup"><span data-stu-id="a94bb-105">This topic summarizes the content model for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control and control-like types.</span></span> <span data-ttu-id="a94bb-106">İçerik modeli, hangi içerik denetimi kullanılabileceğini anlatmaktadır.</span><span class="sxs-lookup"><span data-stu-id="a94bb-106">The content model describes what content can be used in a control.</span></span> <span data-ttu-id="a94bb-107">Bu konu, ayrıca her bir içerik modeli için içerik özellikleri listeler.</span><span class="sxs-lookup"><span data-stu-id="a94bb-107">This topic also lists the content properties for each content model.</span></span> <span data-ttu-id="a94bb-108">İçerik özelliği bir nesnenin içeriğini depolamak için kullanılan bir özelliktir.</span><span class="sxs-lookup"><span data-stu-id="a94bb-108">A content property is a property that is used to store the content of the object.</span></span>  

<a name="classes_that_contain_arbitrary_content"></a>   
## <a name="classes-that-contain-arbitrary-content"></a><span data-ttu-id="a94bb-109">Rasgele içerik içeren sınıflar</span><span class="sxs-lookup"><span data-stu-id="a94bb-109">Classes That Contain Arbitrary Content</span></span>  
 <span data-ttu-id="a94bb-110">Bazı denetimler, dize gibi herhangi bir türde bir nesne içerebilir bir <xref:System.DateTime> nesnesi veya bir <xref:System.Windows.UIElement> ek öğeler için diğer bir deyişle bir kapsayıcı.</span><span class="sxs-lookup"><span data-stu-id="a94bb-110">Some controls can contain an object of any type, such as a string, a <xref:System.DateTime> object, or a <xref:System.Windows.UIElement> that is a container for additional items.</span></span> <span data-ttu-id="a94bb-111">Örneğin, bir <xref:System.Windows.Controls.Button> görüntü ve metin; içerebilir veya <xref:System.Windows.Controls.CheckBox> değerini içerebilir <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a94bb-111">For example, a <xref:System.Windows.Controls.Button> can contain an image and some text; or a <xref:System.Windows.Controls.CheckBox> can contain the value of <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span></span>  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="a94bb-112">rasgele içerik içerebilir dört sınıfları içerir.</span><span class="sxs-lookup"><span data-stu-id="a94bb-112">has four classes that can contain arbitrary content.</span></span> <span data-ttu-id="a94bb-113">Devralma sınıfları aşağıdaki tabloda listelenmektedir <xref:System.Windows.Controls.Control>.</span><span class="sxs-lookup"><span data-stu-id="a94bb-113">The following table lists the classes, which inherit from <xref:System.Windows.Controls.Control>.</span></span>  
  
|<span data-ttu-id="a94bb-114">Rasgele içerik içeren sınıfı</span><span class="sxs-lookup"><span data-stu-id="a94bb-114">Class that contains arbitrary content</span></span>|<span data-ttu-id="a94bb-115">İçerik</span><span class="sxs-lookup"><span data-stu-id="a94bb-115">Content</span></span>|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="a94bb-116">Tek bir rasgele nesne.</span><span class="sxs-lookup"><span data-stu-id="a94bb-116">A single arbitrary object.</span></span>|  
|<xref:System.Windows.Controls.HeaderedContentControl>|<span data-ttu-id="a94bb-117">Üstbilgi ve ikisi için de rasgele nesne olan tek bir öğe.</span><span class="sxs-lookup"><span data-stu-id="a94bb-117">A header and a single item, both of which are arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.ItemsControl>|<span data-ttu-id="a94bb-118">Rastgele nesneleri koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="a94bb-118">A collection of arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|<span data-ttu-id="a94bb-119">Üstbilgi ve tümü isteğe bağlı nesneleri olan öğelerin bir koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="a94bb-119">A header and a collection of items, all of which are arbitrary objects.</span></span>|  
  
 <span data-ttu-id="a94bb-120">Bu sınıflardan devralmasına denetimleri, aynı içerik türünü içerir ve içerik aynı şekilde davranma.</span><span class="sxs-lookup"><span data-stu-id="a94bb-120">Controls that inherit from these classes can contain the same type of content and treat the content in the same way.</span></span> <span data-ttu-id="a94bb-121">Aşağıdaki resimde, bir görüntü içeren her bir içerik modeli ve bazı metinler denetiminden gösterilmektedir:</span><span class="sxs-lookup"><span data-stu-id="a94bb-121">The following illustration shows one control from each content model that contains an image and some text:</span></span>  
  
 ![İçerik modeli her birinden dört farklı denetim gösteren ekran görüntüsü.](./media/wpf-content-model/control-content-model-image-text.png)  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a><span data-ttu-id="a94bb-123">Tek bir rasgele nesne içeren denetimler</span><span class="sxs-lookup"><span data-stu-id="a94bb-123">Controls That Contain a Single Arbitrary Object</span></span>  
 <span data-ttu-id="a94bb-124"><xref:System.Windows.Controls.ContentControl> Sınıfı, rastgele içeriği tek bir parçasını içerir.</span><span class="sxs-lookup"><span data-stu-id="a94bb-124">The <xref:System.Windows.Controls.ContentControl> class contains a single piece of arbitrary content.</span></span> <span data-ttu-id="a94bb-125">İçerik özelliği olan <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="a94bb-125">Its content property is <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="a94bb-126">Aşağıdaki denetimler devralınacak <xref:System.Windows.Controls.ContentControl> ve kendi içerik modelini kullanın:</span><span class="sxs-lookup"><span data-stu-id="a94bb-126">The following controls inherit from <xref:System.Windows.Controls.ContentControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Button>  
  
- <xref:System.Windows.Controls.Primitives.ButtonBase>  
  
- <xref:System.Windows.Controls.CheckBox>  
  
- <xref:System.Windows.Controls.ComboBoxItem>  
  
- <xref:System.Windows.Controls.ContentControl>  
  
- <xref:System.Windows.Controls.Frame>  
  
- <xref:System.Windows.Controls.GridViewColumnHeader>  
  
- <xref:System.Windows.Controls.GroupItem>  
  
- <xref:System.Windows.Controls.Label>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Navigation.NavigationWindow>  
  
- <xref:System.Windows.Controls.RadioButton>  
  
- <xref:System.Windows.Controls.Primitives.RepeatButton>  
  
- <xref:System.Windows.Controls.ScrollViewer>  
  
- <xref:System.Windows.Controls.Primitives.StatusBarItem>  
  
- <xref:System.Windows.Controls.Primitives.ToggleButton>  
  
- <xref:System.Windows.Controls.ToolTip>  
  
- <xref:System.Windows.Controls.UserControl>  
  
- <xref:System.Windows.Window>  
  
 <span data-ttu-id="a94bb-127">Aşağıdaki resimde dört düğme gösterilmektedir <xref:System.Windows.Controls.ContentControl.Content%2A> bir dize olarak ayarlanmış bir <xref:System.DateTime> nesnesi bir <xref:System.Windows.Shapes.Rectangle>ve <xref:System.Windows.Controls.Panel> içeren bir <xref:System.Windows.Shapes.Ellipse> ve <xref:System.Windows.Controls.TextBlock>:</span><span class="sxs-lookup"><span data-stu-id="a94bb-127">The following illustration shows four buttons whose <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a string, a <xref:System.DateTime> object, a <xref:System.Windows.Shapes.Rectangle>, and a <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>:</span></span>  
  
 ![Farklı içerik türleri ile dört düğme gösteren ekran görüntüsü.](./media/wpf-content-model/control-content-model-buttons.png)  
  
 <span data-ttu-id="a94bb-129">Ayarlama örneği için <xref:System.Windows.Controls.ContentControl.Content%2A> özelliği bkz <xref:System.Windows.Controls.ContentControl>.</span><span class="sxs-lookup"><span data-stu-id="a94bb-129">For an example of how to set the <xref:System.Windows.Controls.ContentControl.Content%2A> property, see <xref:System.Windows.Controls.ContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a><span data-ttu-id="a94bb-130">Üst bilgi ve tek bir rasgele nesne içeren denetimler</span><span class="sxs-lookup"><span data-stu-id="a94bb-130">Controls That Contain a Header and a Single Arbitrary Object</span></span>  
 <span data-ttu-id="a94bb-131"><xref:System.Windows.Controls.HeaderedContentControl> Sınıfının devraldığı <xref:System.Windows.Controls.ContentControl> ve bir üst bilgisiyle içeriğini görüntüler.</span><span class="sxs-lookup"><span data-stu-id="a94bb-131">The <xref:System.Windows.Controls.HeaderedContentControl> class inherits from <xref:System.Windows.Controls.ContentControl> and displays content with a header.</span></span> <span data-ttu-id="a94bb-132">İçerik özelliği devralan <xref:System.Windows.Controls.ContentControl.Content%2A>, gelen <xref:System.Windows.Controls.ContentControl> tanımlar <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> tür özelliği <xref:System.Object>; bu nedenle, her ikisi de rastgele bir nesne olabilir.</span><span class="sxs-lookup"><span data-stu-id="a94bb-132">It inherits the content property, <xref:System.Windows.Controls.ContentControl.Content%2A>, from <xref:System.Windows.Controls.ContentControl> and defines the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> property that is of type <xref:System.Object>; therefore, both can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="a94bb-133">Aşağıdaki denetimler devralınacak <xref:System.Windows.Controls.HeaderedContentControl> ve kendi içerik modelini kullanın:</span><span class="sxs-lookup"><span data-stu-id="a94bb-133">The following controls inherit from <xref:System.Windows.Controls.HeaderedContentControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Expander>  
  
- <xref:System.Windows.Controls.GroupBox>  
  
- <xref:System.Windows.Controls.TabItem>  
  
 <span data-ttu-id="a94bb-134">Aşağıdaki iki resimde <xref:System.Windows.Controls.TabItem> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="a94bb-134">The following illustration shows two <xref:System.Windows.Controls.TabItem> objects.</span></span> <span data-ttu-id="a94bb-135">İlk <xref:System.Windows.Controls.TabItem> sahip <xref:System.Windows.UIElement> olarak nesneleri <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> ve <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="a94bb-135">The first <xref:System.Windows.Controls.TabItem> has <xref:System.Windows.UIElement> objects as the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="a94bb-136"><xref:System.Windows.Controls.HeaderedContentControl.Header%2A> Ayarlanmış bir <xref:System.Windows.Controls.StackPanel> içeren bir <xref:System.Windows.Shapes.Ellipse> ve <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="a94bb-136">The <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="a94bb-137"><xref:System.Windows.Controls.ContentControl.Content%2A> Ayarlanmış bir <xref:System.Windows.Controls.StackPanel> içeren bir <xref:System.Windows.Controls.TextBlock> ve <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="a94bb-137">The <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains a <xref:System.Windows.Controls.TextBlock> and a <xref:System.Windows.Controls.Label>.</span></span> <span data-ttu-id="a94bb-138">İkinci <xref:System.Windows.Controls.TabItem> cinsinden bir dize olan <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> ve <xref:System.Windows.Controls.TextBlock> içinde <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="a94bb-138">The second <xref:System.Windows.Controls.TabItem> has a string in the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and a <xref:System.Windows.Controls.TextBlock> in the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span>  
  
 ![Farklı üst bilgi özelliği kullanan TabControl.](./media/wpf-content-model/control-content-model-tab.png)  
  
 <span data-ttu-id="a94bb-140">Nasıl oluşturulacağına dair bir örnek <xref:System.Windows.Controls.TabItem> nesneleri bkz <xref:System.Windows.Controls.HeaderedContentControl>.</span><span class="sxs-lookup"><span data-stu-id="a94bb-140">For an example of how to create <xref:System.Windows.Controls.TabItem> objects, see <xref:System.Windows.Controls.HeaderedContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a><span data-ttu-id="a94bb-141">Rastgele nesnelerinin bir koleksiyonunu içeren denetimler</span><span class="sxs-lookup"><span data-stu-id="a94bb-141">Controls That Contain a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="a94bb-142"><xref:System.Windows.Controls.ItemsControl> Sınıfının devraldığı <xref:System.Windows.Controls.Control> ve dizeler, nesneler veya diğer öğeleri gibi birden çok öğe içerebilir.</span><span class="sxs-lookup"><span data-stu-id="a94bb-142">The <xref:System.Windows.Controls.ItemsControl> class inherits from <xref:System.Windows.Controls.Control> and can contain multiple items, such as strings, objects, or other elements.</span></span> <span data-ttu-id="a94bb-143">İçerik özellikleri olan <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> ve <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span><span class="sxs-lookup"><span data-stu-id="a94bb-143">Its content properties are <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> and <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span></span> <span data-ttu-id="a94bb-144"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> genellikle doldurmak için kullanılan <xref:System.Windows.Controls.ItemsControl> veri koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="a94bb-144"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> is typically used to populate the <xref:System.Windows.Controls.ItemsControl> with a data collection.</span></span> <span data-ttu-id="a94bb-145">Doldurmak için bir koleksiyon kullanmak istemiyorsanız <xref:System.Windows.Controls.ItemsControl>, kullanarak öğeleri ekleyebilirsiniz <xref:System.Windows.Controls.ItemsControl.Items%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="a94bb-145">If you do not want to use a collection to populate the <xref:System.Windows.Controls.ItemsControl>, you can add items by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="a94bb-146">Aşağıdaki denetimler devralınacak <xref:System.Windows.Controls.ItemsControl> ve kendi içerik modelini kullanın:</span><span class="sxs-lookup"><span data-stu-id="a94bb-146">The following controls inherit from <xref:System.Windows.Controls.ItemsControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Menu>  
  
- <xref:System.Windows.Controls.Primitives.MenuBase>  
  
- <xref:System.Windows.Controls.ContextMenu>  
  
- <xref:System.Windows.Controls.ComboBox>  
  
- <xref:System.Windows.Controls.ItemsControl>  
  
- <xref:System.Windows.Controls.ListBox>  
  
- <xref:System.Windows.Controls.ListView>  
  
- <xref:System.Windows.Controls.TabControl>  
  
- <xref:System.Windows.Controls.TreeView>  
  
- <xref:System.Windows.Controls.Primitives.Selector>  
  
- <xref:System.Windows.Controls.Primitives.StatusBar>  
  
 <span data-ttu-id="a94bb-147">Aşağıdaki çizimde gösterildiği bir <xref:System.Windows.Controls.ListBox> , bu tür öğeleri içerir:</span><span class="sxs-lookup"><span data-stu-id="a94bb-147">The following illustration shows a <xref:System.Windows.Controls.ListBox> that contains these types of items:</span></span>  
  
- <span data-ttu-id="a94bb-148">Bir dize.</span><span class="sxs-lookup"><span data-stu-id="a94bb-148">A string.</span></span>  
  
- <span data-ttu-id="a94bb-149">A <xref:System.DateTime> nesne.</span><span class="sxs-lookup"><span data-stu-id="a94bb-149">A <xref:System.DateTime> object.</span></span>  
  
- <span data-ttu-id="a94bb-150">A <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="a94bb-150">A <xref:System.Windows.UIElement>.</span></span>  
  
- <span data-ttu-id="a94bb-151">A <xref:System.Windows.Controls.Panel> içeren bir <xref:System.Windows.Shapes.Ellipse> ve <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="a94bb-151">A <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 ![Dört tür içerikle ListBox gösteren ekran görüntüsü.](./media/wpf-content-model/control-content-model-listbox.png)  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a><span data-ttu-id="a94bb-153">Üst bilgi ve rastgele nesnelerinin bir koleksiyonunu içeren denetimler</span><span class="sxs-lookup"><span data-stu-id="a94bb-153">Controls That Contain a Header and a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="a94bb-154"><xref:System.Windows.Controls.HeaderedItemsControl> Sınıfının devraldığı <xref:System.Windows.Controls.ItemsControl> ve dizeler, nesneler veya diğer öğeleri ve bir üst bilgisi gibi birden çok öğe içerebilir.</span><span class="sxs-lookup"><span data-stu-id="a94bb-154">The <xref:System.Windows.Controls.HeaderedItemsControl> class inherits from <xref:System.Windows.Controls.ItemsControl> and can contain multiple items, such as strings, objects, or other elements, and a header.</span></span> <span data-ttu-id="a94bb-155">Devralır <xref:System.Windows.Controls.ItemsControl> içerik özellikleri, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, ve <xref:System.Windows.Controls.ItemsControl.Items%2A>, ve tanımladığı <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> özelliği rastgele bir nesne olabilir.</span><span class="sxs-lookup"><span data-stu-id="a94bb-155">It inherits the <xref:System.Windows.Controls.ItemsControl> content properties, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, and <xref:System.Windows.Controls.ItemsControl.Items%2A>, and it defines the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property that can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="a94bb-156">Aşağıdaki denetimler devralınacak <xref:System.Windows.Controls.HeaderedItemsControl> ve kendi içerik modelini kullanın:</span><span class="sxs-lookup"><span data-stu-id="a94bb-156">The following controls inherit from <xref:System.Windows.Controls.HeaderedItemsControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.MenuItem>  
  
- <xref:System.Windows.Controls.ToolBar>  
  
- <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>   
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a><span data-ttu-id="a94bb-157">UIElement nesnelerinin bir koleksiyonunu içeren sınıflar</span><span class="sxs-lookup"><span data-stu-id="a94bb-157">Classes That Contain a Collection of UIElement Objects</span></span>  
 <span data-ttu-id="a94bb-158"><xref:System.Windows.Controls.Panel> Sınıfı yerleştirir ve alt düzenler <xref:System.Windows.UIElement> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="a94bb-158">The <xref:System.Windows.Controls.Panel> class positions and arranges child <xref:System.Windows.UIElement> objects.</span></span> <span data-ttu-id="a94bb-159">İçerik özelliği olan <xref:System.Windows.Controls.Panel.Children%2A>.</span><span class="sxs-lookup"><span data-stu-id="a94bb-159">Its content property is <xref:System.Windows.Controls.Panel.Children%2A>.</span></span>  
  
 <span data-ttu-id="a94bb-160">Aşağıdaki sınıflar devralınacak <xref:System.Windows.Controls.Panel> sınıfı ve kendi içerik modelini kullanın:</span><span class="sxs-lookup"><span data-stu-id="a94bb-160">The following classes inherit from the <xref:System.Windows.Controls.Panel> class and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Canvas>  
  
- <xref:System.Windows.Controls.DockPanel>  
  
- <xref:System.Windows.Controls.Grid>  
  
- <xref:System.Windows.Controls.Primitives.TabPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
  
- <xref:System.Windows.Controls.Primitives.UniformGrid>  
  
- <xref:System.Windows.Controls.StackPanel>  
  
- <xref:System.Windows.Controls.VirtualizingPanel>  
  
- <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
- <xref:System.Windows.Controls.WrapPanel>  
  
 <span data-ttu-id="a94bb-161">Daha fazla bilgi için [panellere genel bakış](panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a94bb-161">For more information, see [Panels Overview](panels-overview.md).</span></span>  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>   
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a><span data-ttu-id="a94bb-162">UIElement'i görünümünü etkileyen sınıfları</span><span class="sxs-lookup"><span data-stu-id="a94bb-162">Classes That Affect the Appearance of a UIElement</span></span>  
 <span data-ttu-id="a94bb-163"><xref:System.Windows.Controls.Decorator> Görsel efektler üzerine veya çevresine tek bir alt sınıfı uygulanır <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="a94bb-163">The <xref:System.Windows.Controls.Decorator> class applies visual effects onto or around a single child <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="a94bb-164">İçerik özelliği olan <xref:System.Windows.Controls.Decorator.Child%2A>.</span><span class="sxs-lookup"><span data-stu-id="a94bb-164">Its content property is <xref:System.Windows.Controls.Decorator.Child%2A>.</span></span> <span data-ttu-id="a94bb-165">Aşağıdaki sınıflar devralınacak <xref:System.Windows.Controls.Decorator> ve kendi içerik modelini kullanın:</span><span class="sxs-lookup"><span data-stu-id="a94bb-165">The following classes inherit from <xref:System.Windows.Controls.Decorator> and use its content model:</span></span>  
  
- <xref:System.Windows.Documents.AdornerDecorator>  
  
- <xref:System.Windows.Controls.Border>  
  
- <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
- <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
- <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
- <xref:System.Windows.Controls.InkPresenter>  
  
- <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
- <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
- <xref:System.Windows.Controls.Viewbox>  
  
 <span data-ttu-id="a94bb-166">Aşağıdaki çizimde gösterildiği bir <xref:System.Windows.Controls.TextBox> olan (ile donatılmış) bir <xref:System.Windows.Controls.Border> çevresinde.</span><span class="sxs-lookup"><span data-stu-id="a94bb-166">The following illustration shows a <xref:System.Windows.Controls.TextBox> that has (is decorated with) a <xref:System.Windows.Controls.Border> around it.</span></span>  
  
 <span data-ttu-id="a94bb-167">![TextBox siyah kenarlığa sahip](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span><span class="sxs-lookup"><span data-stu-id="a94bb-167">![TextBox with black border](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span></span>  
<span data-ttu-id="a94bb-168">Bir kenarlığa sahip bir TextBlock</span><span class="sxs-lookup"><span data-stu-id="a94bb-168">TextBlock that has a Border</span></span>  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>   
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a><span data-ttu-id="a94bb-169">UIElement'i hakkında görsel geri bildirim sağlayan sınıflar</span><span class="sxs-lookup"><span data-stu-id="a94bb-169">Classes That Provide Visual Feedback About a UIElement</span></span>  
 <span data-ttu-id="a94bb-170"><xref:System.Windows.Documents.Adorner> Sınıfı, bir kullanıcı için görsel ipuçları sağlar.</span><span class="sxs-lookup"><span data-stu-id="a94bb-170">The <xref:System.Windows.Documents.Adorner> class provides visual cues to a user.</span></span> <span data-ttu-id="a94bb-171">Örneğin, bir <xref:System.Windows.Documents.Adorner> işlevsel tanıtıcıları öğeleri ekleyin ya da bir denetimi hakkındaki durum bilgilerini sağlamak için.</span><span class="sxs-lookup"><span data-stu-id="a94bb-171">For example, use an <xref:System.Windows.Documents.Adorner> to add functional handles to elements or provide state information about a control.</span></span> <span data-ttu-id="a94bb-172"><xref:System.Windows.Documents.Adorner> Sınıf kendi donatıcıları oluşturabilmesi bir çerçeve sağlar.</span><span class="sxs-lookup"><span data-stu-id="a94bb-172">The <xref:System.Windows.Documents.Adorner> class provides a framework so that you can create your own adorners.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="a94bb-173">uygulanan tüm donatıcıları sağlamaz.</span><span class="sxs-lookup"><span data-stu-id="a94bb-173">does not provide any implemented adorners.</span></span> <span data-ttu-id="a94bb-174">Daha fazla bilgi için [Donatıcılara Genel Bakış](adorners-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a94bb-174">For more information, see [Adorners Overview](adorners-overview.md).</span></span>  
  
<a name="classes_that_enable_users_to_enter_text"></a>   
## <a name="classes-that-enable-users-to-enter-text"></a><span data-ttu-id="a94bb-175">Kullanıcıların metin girmesine olanak tanıyan sınıflar</span><span class="sxs-lookup"><span data-stu-id="a94bb-175">Classes That Enable Users to Enter Text</span></span>  
 <span data-ttu-id="a94bb-176">WPF metin girmesini sağlayan üç birincil denetim sağlar.</span><span class="sxs-lookup"><span data-stu-id="a94bb-176">WPF provides three primary controls that enable users to enter text.</span></span> <span data-ttu-id="a94bb-177">Her denetim farklı metni görüntüler.</span><span class="sxs-lookup"><span data-stu-id="a94bb-177">Each control displays the text differently.</span></span> <span data-ttu-id="a94bb-178">Aşağıdaki tabloda bu üç metin ile ilgili denetimleri, metin ve denetimin metni içeren özelliklerini görüntülediğinizde yeteneklerini listeler.</span><span class="sxs-lookup"><span data-stu-id="a94bb-178">The following table lists these three text-related controls, their capabilities when they display text, and their properties that contain the control's text.</span></span>  
  
|<span data-ttu-id="a94bb-179">Denetim</span><span class="sxs-lookup"><span data-stu-id="a94bb-179">Control</span></span>|<span data-ttu-id="a94bb-180">Metin olarak görüntülenir</span><span class="sxs-lookup"><span data-stu-id="a94bb-180">Text is displayed as</span></span>|<span data-ttu-id="a94bb-181">İçerik özelliği</span><span class="sxs-lookup"><span data-stu-id="a94bb-181">Content property</span></span>|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|<span data-ttu-id="a94bb-182">Düz metin</span><span class="sxs-lookup"><span data-stu-id="a94bb-182">Plain text</span></span>|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|<span data-ttu-id="a94bb-183">Biçimlendirilmiş metin</span><span class="sxs-lookup"><span data-stu-id="a94bb-183">Formatted text</span></span>|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|<span data-ttu-id="a94bb-184">Gizli metin (karakterler maskelenir)</span><span class="sxs-lookup"><span data-stu-id="a94bb-184">Hidden text (characters are masked)</span></span>|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>   
## <a name="classes-that-display-your-text"></a><span data-ttu-id="a94bb-185">Metninizi görüntüleme sınıfları</span><span class="sxs-lookup"><span data-stu-id="a94bb-185">Classes That Display Your Text</span></span>  
 <span data-ttu-id="a94bb-186">Düz veya biçimlendirilmiş metni görüntülemek için çeşitli sınıflar kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="a94bb-186">Several classes can be used to display plain or formatted text.</span></span> <span data-ttu-id="a94bb-187">Kullanabileceğiniz <xref:System.Windows.Controls.TextBlock> küçük miktarda metni görüntülemek için.</span><span class="sxs-lookup"><span data-stu-id="a94bb-187">You can use <xref:System.Windows.Controls.TextBlock> to display small amounts of text.</span></span> <span data-ttu-id="a94bb-188">Büyük miktarda metni görüntülemek istiyorsanız, kullanın <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, veya <xref:System.Windows.Controls.FlowDocumentScrollViewer> kontrol eder.</span><span class="sxs-lookup"><span data-stu-id="a94bb-188">If you want to display large amounts of text, use the <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, or <xref:System.Windows.Controls.FlowDocumentScrollViewer> controls.</span></span>  
  
 <span data-ttu-id="a94bb-189"><xref:System.Windows.Controls.TextBlock> İçerik iki özelliğe sahiptir: <xref:System.Windows.Controls.TextBlock.Text%2A> ve <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span><span class="sxs-lookup"><span data-stu-id="a94bb-189">The <xref:System.Windows.Controls.TextBlock> has two content properties: <xref:System.Windows.Controls.TextBlock.Text%2A> and <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span></span> <span data-ttu-id="a94bb-190">Tutarlı biçimlendirme kullanan metni görüntülemek istediğinizde <xref:System.Windows.Controls.TextBlock.Text%2A> özelliği olan genellikle en iyi seçimdir.</span><span class="sxs-lookup"><span data-stu-id="a94bb-190">When you want to display text that uses consistent formatting, the <xref:System.Windows.Controls.TextBlock.Text%2A> property is often your best choice.</span></span> <span data-ttu-id="a94bb-191">Farklı biçimlendirme boyunda metinde kullanmayı planlıyorsanız, kullanmak <xref:System.Windows.Controls.TextBlock.Inlines%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="a94bb-191">If you plan to use different formatting throughout the text, use the <xref:System.Windows.Controls.TextBlock.Inlines%2A> property.</span></span> <span data-ttu-id="a94bb-192"><xref:System.Windows.Controls.TextBlock.Inlines%2A> Özelliktir koleksiyonu <xref:System.Windows.Documents.Inline> metnin nasıl biçimlendirileceğini belirten nesneleri.</span><span class="sxs-lookup"><span data-stu-id="a94bb-192">The <xref:System.Windows.Controls.TextBlock.Inlines%2A> property is a collection of <xref:System.Windows.Documents.Inline> objects, which specify how to format text.</span></span>  
  
 <span data-ttu-id="a94bb-193">İçerik özelliği için aşağıdaki tabloda <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, ve <xref:System.Windows.Controls.FlowDocumentScrollViewer> sınıfları.</span><span class="sxs-lookup"><span data-stu-id="a94bb-193">The following table lists the content property for <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, and <xref:System.Windows.Controls.FlowDocumentScrollViewer> classes.</span></span>  
  
|<span data-ttu-id="a94bb-194">Denetim</span><span class="sxs-lookup"><span data-stu-id="a94bb-194">Control</span></span>|<span data-ttu-id="a94bb-195">İçerik özelliği</span><span class="sxs-lookup"><span data-stu-id="a94bb-195">Content property</span></span>|<span data-ttu-id="a94bb-196">İçerik özelliği türü</span><span class="sxs-lookup"><span data-stu-id="a94bb-196">Content property type</span></span>|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|<span data-ttu-id="a94bb-197">Belge</span><span class="sxs-lookup"><span data-stu-id="a94bb-197">Document</span></span>|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|<span data-ttu-id="a94bb-198">Belge</span><span class="sxs-lookup"><span data-stu-id="a94bb-198">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|<span data-ttu-id="a94bb-199">Belge</span><span class="sxs-lookup"><span data-stu-id="a94bb-199">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
  
 <span data-ttu-id="a94bb-200"><xref:System.Windows.Documents.FlowDocument> Uygulayan <xref:System.Windows.Documents.IDocumentPaginatorSource> arabirim; bu nedenle, tüm üç sınıf sürebilir bir <xref:System.Windows.Documents.FlowDocument> içeriği.</span><span class="sxs-lookup"><span data-stu-id="a94bb-200">The <xref:System.Windows.Documents.FlowDocument> implements the <xref:System.Windows.Documents.IDocumentPaginatorSource> interface; therefore, all three classes can take a <xref:System.Windows.Documents.FlowDocument> as content.</span></span>  
  
<a name="classes_that_format_text"></a>   
## <a name="classes-that-format-your-text"></a><span data-ttu-id="a94bb-201">Metninizi biçimlendirmek sınıfları</span><span class="sxs-lookup"><span data-stu-id="a94bb-201">Classes That Format Your Text</span></span>  
 <span data-ttu-id="a94bb-202"><xref:System.Windows.Documents.TextElement> ve ilişkili sınıflarının metni biçimlendirmek izin verir.</span><span class="sxs-lookup"><span data-stu-id="a94bb-202"><xref:System.Windows.Documents.TextElement> and its related classes allow you to format text.</span></span> <span data-ttu-id="a94bb-203"><xref:System.Windows.Documents.TextElement> nesneler içerir ve metni biçimlendirebilir <xref:System.Windows.Controls.TextBlock> ve <xref:System.Windows.Documents.FlowDocument> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="a94bb-203"><xref:System.Windows.Documents.TextElement> objects contain and format text in <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Documents.FlowDocument> objects.</span></span> <span data-ttu-id="a94bb-204">İki birincil türlerini <xref:System.Windows.Documents.TextElement> nesneler <xref:System.Windows.Documents.Block> öğeleri ve <xref:System.Windows.Documents.Inline> öğeleri.</span><span class="sxs-lookup"><span data-stu-id="a94bb-204">The two primary types of <xref:System.Windows.Documents.TextElement> objects are <xref:System.Windows.Documents.Block> elements and <xref:System.Windows.Documents.Inline> elements.</span></span> <span data-ttu-id="a94bb-205">A <xref:System.Windows.Documents.Block> öğesi, paragraf ya da liste gibi bir metin bloğu temsil eder.</span><span class="sxs-lookup"><span data-stu-id="a94bb-205">A <xref:System.Windows.Documents.Block> element represents a block of text, such as a paragraph or list.</span></span> <span data-ttu-id="a94bb-206">Bir <xref:System.Windows.Documents.Inline> öğesi bir blok içinde metnin bir bölümünü temsil eder.</span><span class="sxs-lookup"><span data-stu-id="a94bb-206">An <xref:System.Windows.Documents.Inline> element represents a portion of text in a block.</span></span> <span data-ttu-id="a94bb-207">Birçok <xref:System.Windows.Documents.Inline> sınıfları için bunlar uygulandığı metin biçimlendirme belirtin.</span><span class="sxs-lookup"><span data-stu-id="a94bb-207">Many <xref:System.Windows.Documents.Inline> classes specify formatting for the text to which they are applied.</span></span> <span data-ttu-id="a94bb-208">Her <xref:System.Windows.Documents.TextElement> kendi içerik modeli vardır.</span><span class="sxs-lookup"><span data-stu-id="a94bb-208">Each <xref:System.Windows.Documents.TextElement> has its own content model.</span></span> <span data-ttu-id="a94bb-209">Daha fazla bilgi için [TextElement içerik modeline genel bakış](../advanced/textelement-content-model-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a94bb-209">For more information, see the [TextElement Content Model Overview](../advanced/textelement-content-model-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a94bb-210">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="a94bb-210">See also</span></span>

- [<span data-ttu-id="a94bb-211">Gelişmiş</span><span class="sxs-lookup"><span data-stu-id="a94bb-211">Advanced</span></span>](../advanced/index.md)
