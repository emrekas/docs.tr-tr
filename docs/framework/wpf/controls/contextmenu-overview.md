---
title: ContextMenu Genel Bakışı
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ContextMenu
- ContextMenu controls [WPF], about ContextMenu controls
ms.assetid: 16909c42-799a-4561-91e0-7d69dcfeea91
ms.openlocfilehash: f1ef0f166908cce3f6c6e39819561a7ec3756a7b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595753"
---
# <a name="contextmenu-overview"></a><span data-ttu-id="654d6-102">ContextMenu Genel Bakışı</span><span class="sxs-lookup"><span data-stu-id="654d6-102">ContextMenu Overview</span></span>
<span data-ttu-id="654d6-103"><xref:System.Windows.Controls.ContextMenu> Sınıfı temsil eder, bağlam özgü kullanarak işlevselliği ortaya koyan öğe <xref:System.Windows.Controls.Menu>.</span><span class="sxs-lookup"><span data-stu-id="654d6-103">The <xref:System.Windows.Controls.ContextMenu> class represents the element that exposes functionality by using a context-specific <xref:System.Windows.Controls.Menu>.</span></span> <span data-ttu-id="654d6-104">Genellikle, bir kullanıcı sunan <xref:System.Windows.Controls.ContextMenu> içinde [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] fare düğmesine tıklanarak.</span><span class="sxs-lookup"><span data-stu-id="654d6-104">Typically, a user exposes the <xref:System.Windows.Controls.ContextMenu> in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] by right-clicking the mouse button.</span></span> <span data-ttu-id="654d6-105">Bu konu tanıtır <xref:System.Windows.Controls.ContextMenu> öğe ve içindeki kullanma örnekleri sağlar [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ve kod.</span><span class="sxs-lookup"><span data-stu-id="654d6-105">This topic introduces the <xref:System.Windows.Controls.ContextMenu> element and provides examples of how to use it in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] and code.</span></span>  
  
  
  
<a name="contextmenu_control"></a>   
## <a name="contextmenu-control"></a><span data-ttu-id="654d6-106">ContextMenu denetimi</span><span class="sxs-lookup"><span data-stu-id="654d6-106">ContextMenu Control</span></span>  
 <span data-ttu-id="654d6-107">A <xref:System.Windows.Controls.ContextMenu> belirli bir denetime bağlı.</span><span class="sxs-lookup"><span data-stu-id="654d6-107">A <xref:System.Windows.Controls.ContextMenu> is attached to a specific control.</span></span> <span data-ttu-id="654d6-108"><xref:System.Windows.Controls.ContextMenu> Öğesi, kullanıcıların mevcut komutları veya örneğin, belirli bir denetimle ilişkilendirilen seçenekleri belirten öğeleri listesini olanak tanır bir <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="654d6-108">The <xref:System.Windows.Controls.ContextMenu> element enables you to present users with a list of items that specify commands or options that are associated with a particular control, for example, a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="654d6-109">Kullanıcı denetim menüsünün görünür hale getirmek için sağ tıklayın.</span><span class="sxs-lookup"><span data-stu-id="654d6-109">Users right-click the control to make the menu appear.</span></span> <span data-ttu-id="654d6-110">Genellikle, tıklayarak bir <xref:System.Windows.Controls.MenuItem> bir alt açar veya bir uygulamanın bir komutu yürütür.</span><span class="sxs-lookup"><span data-stu-id="654d6-110">Typically, clicking a <xref:System.Windows.Controls.MenuItem> opens a submenu or causes an application to carry out a command.</span></span>  
  
<a name="creating_contextmenus"></a>   
## <a name="creating-contextmenus"></a><span data-ttu-id="654d6-111">ContextMenus oluşturma</span><span class="sxs-lookup"><span data-stu-id="654d6-111">Creating ContextMenus</span></span>  
 <span data-ttu-id="654d6-112">Aşağıdaki örnekler nasıl oluşturulacağını gösterir. bir <xref:System.Windows.Controls.ContextMenu> menülerinde ile.</span><span class="sxs-lookup"><span data-stu-id="654d6-112">The following examples show how to create a <xref:System.Windows.Controls.ContextMenu> with submenus.</span></span> <span data-ttu-id="654d6-113"><xref:System.Windows.Controls.ContextMenu> Denetimleri için düğme denetimleri eklenir.</span><span class="sxs-lookup"><span data-stu-id="654d6-113">The <xref:System.Windows.Controls.ContextMenu> controls are attached to button controls.</span></span>  
  
 [!code-xaml[ContextMenu#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>   
## <a name="applying-styles-to-a-contextmenu"></a><span data-ttu-id="654d6-114">Uygulama bir ContextMenu stilleri</span><span class="sxs-lookup"><span data-stu-id="654d6-114">Applying Styles to a ContextMenu</span></span>  
 <span data-ttu-id="654d6-115">Bir denetimi kullanarak <xref:System.Windows.Style>, önemli ölçüde görünümünü ve davranışını değiştirebilirsiniz bir <xref:System.Windows.Controls.ContextMenu> özel denetim yazmadan.</span><span class="sxs-lookup"><span data-stu-id="654d6-115">By using a control <xref:System.Windows.Style>, you can dramatically change the appearance and behavior of a <xref:System.Windows.Controls.ContextMenu> without writing a custom control.</span></span> <span data-ttu-id="654d6-116">Görsel özelliklerini ayarlamaktan ek olarak, stilleri bir denetimin bölümleri de uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="654d6-116">In addition to setting visual properties, you can also apply styles to parts of a control.</span></span> <span data-ttu-id="654d6-117">Örneğin, özelliklerini kullanarak denetim bölümlerini davranışını değiştirebilirsiniz veya bölümleri ekleyin veya düzenini değiştirebilirsiniz bir <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="654d6-117">For example, you can change the behavior of parts of the control by using properties, or you can add parts to, or change the layout of, a <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="654d6-118">Aşağıdaki örnekler stil eklemek için çeşitli yollar <xref:System.Windows.Controls.ContextMenu> kontrol eder.</span><span class="sxs-lookup"><span data-stu-id="654d6-118">The following examples show several ways to add styles to <xref:System.Windows.Controls.ContextMenu> controls.</span></span>  
  
 <span data-ttu-id="654d6-119">İlk örnek adlı bir stil tanımlar `SimpleSysResources`, geçerli sistem ayarlarını, stili kullanmayı gösterir.</span><span class="sxs-lookup"><span data-stu-id="654d6-119">The first example defines a style called `SimpleSysResources`, which shows how to use the current system settings in your style.</span></span> <span data-ttu-id="654d6-120">Örnek atar <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> olarak <xref:System.Windows.Controls.Control.Background%2A> renk ve <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> olarak <xref:System.Windows.Controls.Control.Foreground%2A> rengini <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="654d6-120">The example assigns <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> as the <xref:System.Windows.Controls.Control.Background%2A> color and <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> as the <xref:System.Windows.Controls.Control.Foreground%2A> color of the <xref:System.Windows.Controls.ContextMenu>.</span></span>  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=   
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=   
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 <span data-ttu-id="654d6-121">Aşağıdaki örnekte <xref:System.Windows.Trigger> görünümünü değiştirmek için öğenin bir <xref:System.Windows.Controls.Menu> üzerinde gerçekleşen olaylara yanıt olarak <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="654d6-121">The following example uses the <xref:System.Windows.Trigger> element to change the appearance of a <xref:System.Windows.Controls.Menu> in response to events that are raised on the <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="654d6-122">Ne zaman bir kullanıcı hareket fare görünümünü menüye <xref:System.Windows.Controls.ContextMenu> öğelerini değişiklikler.</span><span class="sxs-lookup"><span data-stu-id="654d6-122">When a user moves the mouse over the menu, the appearance of the <xref:System.Windows.Controls.ContextMenu> items changes.</span></span>  
  
```xaml  
<Style x:Key="Triggers" TargetType="{x:Type MenuItem}">  
  <Style.Triggers>  
    <Trigger Property="MenuItem.IsMouseOver" Value="true">  
      <Setter Property = "FontSize" Value="16"/>  
      <Setter Property = "FontStyle" Value="Italic"/>  
      <Setter Property = "Foreground" Value="Red"/>  
    </Trigger>  
  </Style.Triggers>  
</Style>  
```  
  
## <a name="see-also"></a><span data-ttu-id="654d6-123">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="654d6-123">See also</span></span>
- <xref:System.Windows.Controls.ContextMenu>
- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.Menu>
- <xref:System.Windows.Controls.MenuItem>
- [<span data-ttu-id="654d6-124">ContextMenu</span><span class="sxs-lookup"><span data-stu-id="654d6-124">ContextMenu</span></span>](../../../../docs/framework/wpf/controls/contextmenu.md)
- [<span data-ttu-id="654d6-125">ContextMenu Stilleri ve Şablonları</span><span class="sxs-lookup"><span data-stu-id="654d6-125">ContextMenu Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/contextmenu-styles-and-templates.md)
- [<span data-ttu-id="654d6-126">WPF denetimleri Galerisi örneği</span><span class="sxs-lookup"><span data-stu-id="654d6-126">WPF Controls Gallery Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160053)
