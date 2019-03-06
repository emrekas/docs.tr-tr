---
title: ContextMenu Stilleri ve Şablonları
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], ContextMenu
- parts [WPF], ContextMenu
- ContextMenu [WPF], styles and templates
- styles [WPF], ContextMenu
- ControlTemplate [WPF], ContextMenu
- states [WPF], ContextMenu
ms.assetid: 342d1f17-c406-4f94-8f55-867c5f3ea511
ms.openlocfilehash: be26156d74f3a3509bf150e5611512172f08a14e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369074"
---
# <a name="contextmenu-styles-and-templates"></a><span data-ttu-id="d55bb-102">ContextMenu Stilleri ve Şablonları</span><span class="sxs-lookup"><span data-stu-id="d55bb-102">ContextMenu Styles and Templates</span></span>
<span data-ttu-id="d55bb-103">Bu konu için şablonları ve stilleri açıklar <xref:System.Windows.Controls.ContextMenu> denetimi.</span><span class="sxs-lookup"><span data-stu-id="d55bb-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ContextMenu> control.</span></span> <span data-ttu-id="d55bb-104">Varsayılan değiştirebileceğiniz <xref:System.Windows.Controls.ControlTemplate> denetim benzersiz bir görünüm sağlamak için.</span><span class="sxs-lookup"><span data-stu-id="d55bb-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="d55bb-105">Daha fazla bilgi için [ControlTemplate oluşturarak varolan denetimin görünümünü özelleştirme](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="d55bb-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="contextmenu-parts"></a><span data-ttu-id="d55bb-106">ContextMenu bölümleri</span><span class="sxs-lookup"><span data-stu-id="d55bb-106">ContextMenu Parts</span></span>  
 <span data-ttu-id="d55bb-107"><xref:System.Windows.Controls.ContextMenu> Denetim herhangi bir adlandırılmış bölümü yok.</span><span class="sxs-lookup"><span data-stu-id="d55bb-107">The <xref:System.Windows.Controls.ContextMenu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="d55bb-108">Oluştururken bir <xref:System.Windows.Controls.ControlTemplate> için bir <xref:System.Windows.Controls.ContextMenu>, şablonunuzu içerebilir bir <xref:System.Windows.Controls.ItemsPresenter> içinde bir <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="d55bb-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ContextMenu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="d55bb-109">( <xref:System.Windows.Controls.ItemsPresenter> Her öğe görüntüler <xref:System.Windows.Controls.ContextMenu>; <xref:System.Windows.Controls.ScrollViewer> denetimi içinde kaydırma sağlar).</span><span class="sxs-lookup"><span data-stu-id="d55bb-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ContextMenu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="d55bb-110">Varsa <xref:System.Windows.Controls.ItemsPresenter> doğrudan alt öğesi değil <xref:System.Windows.Controls.ScrollViewer>, size gereken <xref:System.Windows.Controls.ItemsPresenter> adı `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="d55bb-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="contextmenu-states"></a><span data-ttu-id="d55bb-111">ContextMenu durumları</span><span class="sxs-lookup"><span data-stu-id="d55bb-111">ContextMenu States</span></span>  
 <span data-ttu-id="d55bb-112">Görsel durumlar için aşağıdaki tabloda <xref:System.Windows.Controls.ContextMenu> denetimi.</span><span class="sxs-lookup"><span data-stu-id="d55bb-112">The following table lists the visual states for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
|<span data-ttu-id="d55bb-113">VisualState adı</span><span class="sxs-lookup"><span data-stu-id="d55bb-113">VisualState Name</span></span>|<span data-ttu-id="d55bb-114">Visualstategroup'u adı</span><span class="sxs-lookup"><span data-stu-id="d55bb-114">VisualStateGroup Name</span></span>|<span data-ttu-id="d55bb-115">Açıklama</span><span class="sxs-lookup"><span data-stu-id="d55bb-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d55bb-116">Geçerli</span><span class="sxs-lookup"><span data-stu-id="d55bb-116">Valid</span></span>|<span data-ttu-id="d55bb-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d55bb-117">ValidationStates</span></span>|<span data-ttu-id="d55bb-118">Denetimi kullanan <xref:System.Windows.Controls.Validation> sınıfı ve <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> ekli özelliği `false`.</span><span class="sxs-lookup"><span data-stu-id="d55bb-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="d55bb-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="d55bb-119">InvalidFocused</span></span>|<span data-ttu-id="d55bb-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d55bb-120">ValidationStates</span></span>|<span data-ttu-id="d55bb-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Ekli özelliği `true` olan denetim odağa sahip.</span><span class="sxs-lookup"><span data-stu-id="d55bb-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="d55bb-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="d55bb-122">InvalidUnfocused</span></span>|<span data-ttu-id="d55bb-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d55bb-123">ValidationStates</span></span>|<span data-ttu-id="d55bb-124"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Ekli özelliği `true` olan denetim odağa sahip değil.</span><span class="sxs-lookup"><span data-stu-id="d55bb-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="contextmenu-controltemplate-example"></a><span data-ttu-id="d55bb-125">ContextMenu ControlTemplate Örneği</span><span class="sxs-lookup"><span data-stu-id="d55bb-125">ContextMenu ControlTemplate Example</span></span>  
 <span data-ttu-id="d55bb-126">Aşağıdaki örnek nasıl tanımlanacağını gösterir bir <xref:System.Windows.Controls.ControlTemplate> için <xref:System.Windows.Controls.ContextMenu> denetimi.</span><span class="sxs-lookup"><span data-stu-id="d55bb-126">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 <span data-ttu-id="d55bb-127"><xref:System.Windows.Controls.ControlTemplate> Aşağıdaki kaynakları kullanır.</span><span class="sxs-lookup"><span data-stu-id="d55bb-127">The <xref:System.Windows.Controls.ControlTemplate> uses the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="d55bb-128">Tam bir örnek için bkz. [ControlTemplates örneği ile stillendirme](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="d55bb-128">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d55bb-129">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d55bb-129">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="d55bb-130">Denetim Stilleri ve Şablonları</span><span class="sxs-lookup"><span data-stu-id="d55bb-130">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="d55bb-131">Denetim Özelleştirme</span><span class="sxs-lookup"><span data-stu-id="d55bb-131">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="d55bb-132">Stil ve Şablon Oluşturma</span><span class="sxs-lookup"><span data-stu-id="d55bb-132">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="d55bb-133">ControlTemplate Oluşturarak Varolan Denetimin Görünümünü Özelleştirme</span><span class="sxs-lookup"><span data-stu-id="d55bb-133">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
