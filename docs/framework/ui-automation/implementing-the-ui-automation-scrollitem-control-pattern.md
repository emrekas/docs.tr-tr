---
title: UI Otomasyon ScrollItem Denetim Düzeni Uygulama
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Scroll Item
- UI Automation, Scroll Item control pattern
- Scroll Item control pattern
ms.assetid: 903bab5c-80c1-44d7-bdc2-0a418893b987
ms.openlocfilehash: c0bb852fa6c117ae8eb2644a0be75f20367b2054
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61983313"
---
# <a name="implementing-the-ui-automation-scrollitem-control-pattern"></a><span data-ttu-id="4f61b-102">UI Otomasyon ScrollItem Denetim Düzeni Uygulama</span><span class="sxs-lookup"><span data-stu-id="4f61b-102">Implementing the UI Automation ScrollItem Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="4f61b-103">Bu belge yönetilen kullanmak isteyen .NET Framework için tasarlanan [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tanımlanan sınıflar <xref:System.Windows.Automation> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="4f61b-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="4f61b-104">En son bilgileri [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], bkz: [Windows Automation API: UI Otomasyonu](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="4f61b-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="4f61b-105">Bu konu, yönergeleri ve uygulama kuralları tanıtır <xref:System.Windows.Automation.Provider.IScrollItemProvider>, özellikler, yöntemler ve olaylar hakkında bilgiler dahil olmak üzere.</span><span class="sxs-lookup"><span data-stu-id="4f61b-105">This topic introduces guidelines and conventions for implementing the <xref:System.Windows.Automation.Provider.IScrollItemProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="4f61b-106">Ek başvurular bağlantılar konunun sonunda listelenmiştir.</span><span class="sxs-lookup"><span data-stu-id="4f61b-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="4f61b-107"><xref:System.Windows.Automation.ScrollItemPattern> Denetim düzeni uygulama kapsayıcılarının tek alt denetimler desteklemek için kullanılan <xref:System.Windows.Automation.Provider.IScrollProvider>.</span><span class="sxs-lookup"><span data-stu-id="4f61b-107">The <xref:System.Windows.Automation.ScrollItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IScrollProvider>.</span></span> <span data-ttu-id="4f61b-108">Bu denetim düzeni, bir iletişim kanalı arasındaki bir alt denetimin ve alt denetim görüntülemek için Görünüm penceresi içinde şu anda görünür içeriğe (veya bölge) kapsayıcı değiştirebilirsiniz emin olmak için kendi kapsayıcı görevi görür.</span><span class="sxs-lookup"><span data-stu-id="4f61b-108">This control pattern acts as a communication channel between a child control and its container to ensure that the container can change the currently visible content (or region) within its viewport to display the child control.</span></span> <span data-ttu-id="4f61b-109">Bu denetim düzeni uygulama denetimleri örnekleri için bkz: [denetim düzeni eşlemesi için UI Otomasyonu istemcileri](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="4f61b-109">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="4f61b-110">Uygulama yönergeleri ve kuralları</span><span class="sxs-lookup"><span data-stu-id="4f61b-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="4f61b-111">Kaydırma öğesi denetim düzeni uygularken aşağıdaki yönergeler ve kuralları dikkat edin:</span><span class="sxs-lookup"><span data-stu-id="4f61b-111">When implementing the Scroll Item control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="4f61b-112">Bir pencere veya Tuval denetimi içinde bulunan öğeleri IScrollItemProvider arabirim uygulamak için gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="4f61b-112">Items contained within a Window or Canvas control are not required to implement the IScrollItemProvider interface.</span></span> <span data-ttu-id="4f61b-113">Alternatif olarak, ancak bunlar için geçerli bir konum açığa çıkarmalıdır <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>.</span><span class="sxs-lookup"><span data-stu-id="4f61b-113">As an alternative, however, they must expose a valid location for the <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>.</span></span> <span data-ttu-id="4f61b-114">Bunu kullanmak UI otomasyon istemci uygulaması sağlayacak <xref:System.Windows.Automation.ScrollPattern> denetim alt öğeyi görüntülemek için kapsayıcı üzerindeki deseni yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="4f61b-114">This will allow a UI Automation client application to use the <xref:System.Windows.Automation.ScrollPattern> control pattern methods on the container to display the child item.</span></span>  
  
<a name="Required_Members_for_IScrollItemProvider"></a>   
## <a name="required-members-for-iscrollitemprovider"></a><span data-ttu-id="4f61b-115">Gerekli üyeleri IScrollItemProvider için</span><span class="sxs-lookup"><span data-stu-id="4f61b-115">Required Members for IScrollItemProvider</span></span>  
 <span data-ttu-id="4f61b-116">Aşağıdaki yöntem IScrollProvider arabirim uygulamak için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="4f61b-116">The following method is required for implementing the IScrollProvider interface.</span></span>  
  
|<span data-ttu-id="4f61b-117">Gerekli üyeleri</span><span class="sxs-lookup"><span data-stu-id="4f61b-117">Required members</span></span>|<span data-ttu-id="4f61b-118">Üye türü</span><span class="sxs-lookup"><span data-stu-id="4f61b-118">Member type</span></span>|<span data-ttu-id="4f61b-119">Notlar</span><span class="sxs-lookup"><span data-stu-id="4f61b-119">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider.ScrollIntoView%2A>|<span data-ttu-id="4f61b-120">-Yöntemi</span><span class="sxs-lookup"><span data-stu-id="4f61b-120">-   Method</span></span>|<span data-ttu-id="4f61b-121">Yok.</span><span class="sxs-lookup"><span data-stu-id="4f61b-121">None</span></span>|  
  
 <span data-ttu-id="4f61b-122">Bu denetim düzeni hiçbir ilişkili özellikleri veya olayları vardır.</span><span class="sxs-lookup"><span data-stu-id="4f61b-122">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="4f61b-123">Özel Durumlar</span><span class="sxs-lookup"><span data-stu-id="4f61b-123">Exceptions</span></span>  
 <span data-ttu-id="4f61b-124">Sağlayıcıları, aşağıdaki özel durumlar gerekir.</span><span class="sxs-lookup"><span data-stu-id="4f61b-124">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="4f61b-125">Özel Durum Türü</span><span class="sxs-lookup"><span data-stu-id="4f61b-125">Exception Type</span></span>|<span data-ttu-id="4f61b-126">Koşul</span><span class="sxs-lookup"><span data-stu-id="4f61b-126">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<span data-ttu-id="4f61b-127">Bir öğe görünüme kaydırılan olamaz varsa:</span><span class="sxs-lookup"><span data-stu-id="4f61b-127">If an item cannot be scrolled into view:</span></span><br /><br /> -   <xref:System.Windows.Automation.ScrollItemPattern.ScrollIntoView%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="4f61b-128">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="4f61b-128">See also</span></span>

- [<span data-ttu-id="4f61b-129">UI Otomasyonu Denetim Desenlerine Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="4f61b-129">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="4f61b-130">UI Otomasyonu Sağlayıcıda Denetim Düzenleri Desteği</span><span class="sxs-lookup"><span data-stu-id="4f61b-130">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="4f61b-131">İstemciler İçin UI Otomasyonu Denetim Düzenleri</span><span class="sxs-lookup"><span data-stu-id="4f61b-131">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="4f61b-132">UI Otomasyon Ağacına Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="4f61b-132">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [<span data-ttu-id="4f61b-133">UI Otomasyonunda Önbelleğe Almayı Kullanma</span><span class="sxs-lookup"><span data-stu-id="4f61b-133">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
