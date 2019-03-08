---
title: UI Otomasyon MultipleView Denetim Düzeni Uygulama
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, MultipleView control pattern
- MultipleView control pattern
- control patterns, MultipleView
ms.assetid: 5bf1b248-ffee-48c8-9613-0b134bbe9f6a
ms.openlocfilehash: 5c875794a3d6fb0325bf282bc0f4b903aa29de07
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57674295"
---
# <a name="implementing-the-ui-automation-multipleview-control-pattern"></a><span data-ttu-id="7be8c-102">UI Otomasyon MultipleView Denetim Düzeni Uygulama</span><span class="sxs-lookup"><span data-stu-id="7be8c-102">Implementing the UI Automation MultipleView Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="7be8c-103">Bu belge yönetilen kullanmak isteyen .NET Framework için tasarlanan [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tanımlanan sınıflar <xref:System.Windows.Automation> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="7be8c-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="7be8c-104">En son bilgileri [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], bkz: [Windows Automation API: UI Otomasyonu](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="7be8c-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="7be8c-105">Bu konu, yönergeleri ve uygulama kuralları tanıtır <xref:System.Windows.Automation.Provider.IMultipleViewProvider>, olayları ve özellikleri hakkında bilgi dahil olmak üzere.</span><span class="sxs-lookup"><span data-stu-id="7be8c-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IMultipleViewProvider>, including information about events and properties.</span></span> <span data-ttu-id="7be8c-106">Ek başvurular bağlantılar konunun sonunda listelenmiştir.</span><span class="sxs-lookup"><span data-stu-id="7be8c-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="7be8c-107"><xref:System.Windows.Automation.MultipleViewPattern> Denetim düzeni sağlayın ve birden çok bilgi veya alt denetim aynı dizi temsillerini, arasında geçiş yapabilirsiniz denetimleri desteklemek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="7be8c-107">The <xref:System.Windows.Automation.MultipleViewPattern> control pattern is used to support controls that provide, and are able to switch between, multiple representations of the same set of information or child controls.</span></span>  
  
 <span data-ttu-id="7be8c-108">Birden çok görünüm sunabilir denetimleri örnekler (da içeriğini küçük resimleri, kutucukları, simgeler veya ayrıntılar gösterebilir) liste görünümü [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] grafikleri (pasta, çizgi, çubuk, hücre değerini bir formül ile), [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] belgeleri (normal, Web düzeni yazdırma düzeni, okuma düzeni, anahat) [!INCLUDE[TLA#tla_outlook](../../../includes/tlasharptla-outlook-md.md)] (yıl, ay, hafta, gün), Takvim ve [!INCLUDE[TLA#tla_wmp](../../../includes/tlasharptla-wmp-md.md)] css'li dış görünümler.</span><span class="sxs-lookup"><span data-stu-id="7be8c-108">Examples of controls that can present multiple views include the list view (which can show its contents as thumbnails, tiles, icons, or details), [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] charts (pie, line, bar, cell value with a formula), [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] documents (normal, Web layout, print layout, reading layout, outline), [!INCLUDE[TLA#tla_outlook](../../../includes/tlasharptla-outlook-md.md)] calendar (year, month, week, day), and [!INCLUDE[TLA#tla_wmp](../../../includes/tlasharptla-wmp-md.md)] skins.</span></span> <span data-ttu-id="7be8c-109">Desteklenen görünümler denetim geliştiricisi tarafından belirlenir ve her bir denetimin özgüdür.</span><span class="sxs-lookup"><span data-stu-id="7be8c-109">The supported views are determined by the control developer and are specific to each control.</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="7be8c-110">Uygulama yönergeleri ve kuralları</span><span class="sxs-lookup"><span data-stu-id="7be8c-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="7be8c-111">Birden çok görünüm denetim düzeni uygularken aşağıdaki yönergeler ve kuralları dikkat edin:</span><span class="sxs-lookup"><span data-stu-id="7be8c-111">When implementing the Multiple View control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="7be8c-112"><xref:System.Windows.Automation.Provider.IMultipleViewProvider> Ayrıca, geçerli görünüm sağlayan bir denetimi farklıysa, geçerli görünüm yöneten bir kapsayıcıda uygulanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="7be8c-112"><xref:System.Windows.Automation.Provider.IMultipleViewProvider> should also be implemented on a container that manages the current view if it is different from a control that provides the current view.</span></span> <span data-ttu-id="7be8c-113">Örneğin, görünüm denetimi için Windows Gezgini uygulamadan yönetilen Windows Explorer geçerli klasör içeriği için bir liste denetimini içerir.</span><span class="sxs-lookup"><span data-stu-id="7be8c-113">For example, Windows Explorer contains a List control for the current folder content while the view for the control is managed from the Windows Explorer application.</span></span>  
  
-   <span data-ttu-id="7be8c-114">İçeriği sıralama mümkün olan denetimi birden çok görünüm desteklemek için dikkate alınmaz.</span><span class="sxs-lookup"><span data-stu-id="7be8c-114">A control that is able to sort its content is not considered to support multiple views.</span></span>  
  
-   <span data-ttu-id="7be8c-115">Görünümler koleksiyonu örneklerinde aynı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="7be8c-115">The collection of views must be identical across instances.</span></span>  
  
-   <span data-ttu-id="7be8c-116">Görünüm adları metin okuma, Braille ve okunabilir diğer uygulamalar için uygun olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="7be8c-116">View names must be suitable for use in Text to Speech, Braille, and other human-readable applications.</span></span>  
  
<a name="Required_Members_for_IMultipleViewProvider"></a>   
## <a name="required-members-for-imultipleviewprovider"></a><span data-ttu-id="7be8c-117">Gerekli üyeleri IMultipleViewProvider için</span><span class="sxs-lookup"><span data-stu-id="7be8c-117">Required Members for IMultipleViewProvider</span></span>  
 <span data-ttu-id="7be8c-118">Aşağıdaki özellikleri ve yöntemleri IMultipleViewProvider uygulamak için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="7be8c-118">The following properties and methods are required for implementing IMultipleViewProvider.</span></span>  
  
|<span data-ttu-id="7be8c-119">Gerekli üyeleri</span><span class="sxs-lookup"><span data-stu-id="7be8c-119">Required members</span></span>|<span data-ttu-id="7be8c-120">Üye türü</span><span class="sxs-lookup"><span data-stu-id="7be8c-120">Member type</span></span>|<span data-ttu-id="7be8c-121">Notlar</span><span class="sxs-lookup"><span data-stu-id="7be8c-121">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.CurrentView%2A>|<span data-ttu-id="7be8c-122">Özellik</span><span class="sxs-lookup"><span data-stu-id="7be8c-122">Property</span></span>|<span data-ttu-id="7be8c-123">Hiçbiri</span><span class="sxs-lookup"><span data-stu-id="7be8c-123">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetSupportedViews%2A>|<span data-ttu-id="7be8c-124">Yöntem</span><span class="sxs-lookup"><span data-stu-id="7be8c-124">Method</span></span>|<span data-ttu-id="7be8c-125">Hiçbiri</span><span class="sxs-lookup"><span data-stu-id="7be8c-125">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A>|<span data-ttu-id="7be8c-126">Yöntem</span><span class="sxs-lookup"><span data-stu-id="7be8c-126">Method</span></span>|<span data-ttu-id="7be8c-127">Hiçbiri</span><span class="sxs-lookup"><span data-stu-id="7be8c-127">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A>|<span data-ttu-id="7be8c-128">Yöntem</span><span class="sxs-lookup"><span data-stu-id="7be8c-128">Method</span></span>|<span data-ttu-id="7be8c-129">Hiçbiri</span><span class="sxs-lookup"><span data-stu-id="7be8c-129">None</span></span>|  
  
 <span data-ttu-id="7be8c-130">Bu denetim düzeni ile ilişkili olay yok.</span><span class="sxs-lookup"><span data-stu-id="7be8c-130">There are no events associated with this control pattern.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="7be8c-131">Özel Durumlar</span><span class="sxs-lookup"><span data-stu-id="7be8c-131">Exceptions</span></span>  
 <span data-ttu-id="7be8c-132">Sağlayıcı, aşağıdaki özel durumlar gerekir.</span><span class="sxs-lookup"><span data-stu-id="7be8c-132">Provider must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="7be8c-133">Özel durum türü</span><span class="sxs-lookup"><span data-stu-id="7be8c-133">Exception type</span></span>|<span data-ttu-id="7be8c-134">Koşul</span><span class="sxs-lookup"><span data-stu-id="7be8c-134">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="7be8c-135">Zaman ya da <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> veya <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> desteklenen görünümler koleksiyonunun bir üyesi olmayan bir parametre ile adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="7be8c-135">When either <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> or <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> is called with a parameter that is not a member of the supported views collection.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7be8c-136">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="7be8c-136">See also</span></span>
- [<span data-ttu-id="7be8c-137">UI Otomasyonu Denetim Desenlerine Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="7be8c-137">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="7be8c-138">UI Otomasyonu Sağlayıcıda Denetim Düzenleri Desteği</span><span class="sxs-lookup"><span data-stu-id="7be8c-138">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="7be8c-139">İstemciler İçin UI Otomasyonu Denetim Düzenleri</span><span class="sxs-lookup"><span data-stu-id="7be8c-139">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="7be8c-140">UI Otomasyon Ağacına Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="7be8c-140">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [<span data-ttu-id="7be8c-141">UI Otomasyonunda Önbelleğe Almayı Kullanma</span><span class="sxs-lookup"><span data-stu-id="7be8c-141">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
