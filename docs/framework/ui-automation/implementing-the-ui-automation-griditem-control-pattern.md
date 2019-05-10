---
title: UI Otomasyon GridItem Denetim Düzeni Uygulama
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, GridItem
- UI Automation GridItem control pattern
- GridItem control pattern
ms.assetid: bffbae08-fe2a-42fd-ab84-f37187518916
ms.openlocfilehash: 81be2c07f9fd3cc449527c389b0e6bf46182c382
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64659837"
---
# <a name="implementing-the-ui-automation-griditem-control-pattern"></a><span data-ttu-id="edc90-102">UI Otomasyon GridItem Denetim Düzeni Uygulama</span><span class="sxs-lookup"><span data-stu-id="edc90-102">Implementing the UI Automation GridItem Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="edc90-103">Bu belge yönetilen kullanmak isteyen .NET Framework için tasarlanan [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tanımlanan sınıflar <xref:System.Windows.Automation> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="edc90-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="edc90-104">En son bilgileri [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], bkz: [Windows Automation API: UI Otomasyonu](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="edc90-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="edc90-105">Bu konu, yönergeleri ve uygulama kuralları tanıtır <xref:System.Windows.Automation.Provider.IGridItemProvider>, özellikler hakkında bilgiler dahil olmak üzere.</span><span class="sxs-lookup"><span data-stu-id="edc90-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>, including information about properties.</span></span> <span data-ttu-id="edc90-106">Ek başvurular bağlantılar genel bakış sonunda listelenmiştir.</span><span class="sxs-lookup"><span data-stu-id="edc90-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="edc90-107"><xref:System.Windows.Automation.GridItemPattern> Denetim düzeni uygulama kapsayıcılarının tek alt denetimler desteklemek için kullanılan <xref:System.Windows.Automation.Provider.IGridProvider>.</span><span class="sxs-lookup"><span data-stu-id="edc90-107">The <xref:System.Windows.Automation.GridItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IGridProvider>.</span></span> <span data-ttu-id="edc90-108">Bu denetim düzeni uygulama denetimleri örnekleri için bkz: [denetim düzeni eşlemesi için UI Otomasyonu istemcileri](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="edc90-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="edc90-109">Uygulama yönergeleri ve kuralları</span><span class="sxs-lookup"><span data-stu-id="edc90-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="edc90-110">Uygularken <xref:System.Windows.Automation.Provider.IGridProvider>, aşağıdaki yönergeleri ve kuralları dikkat edin:</span><span class="sxs-lookup"><span data-stu-id="edc90-110">When implementing <xref:System.Windows.Automation.Provider.IGridProvider>, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="edc90-111">Kılavuz koordinatları (0, 0) koordinatlarına sahip üst sol hücre sıfır tabanlıdır.</span><span class="sxs-lookup"><span data-stu-id="edc90-111">Grid coordinates are zero-based with the upper left cell having coordinates (0, 0).</span></span>  
  
- <span data-ttu-id="edc90-112">Birleştirilmiş hücreler rapor kendi <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> ve <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> özelliklerine UI Otomasyonu sağlayıcı tarafından tanımlandığı şekilde, temel alınan bağlantı hücreye bağlı.</span><span class="sxs-lookup"><span data-stu-id="edc90-112">Merged cells will report their <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> and <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> properties based on their underlying anchor cell as defined by the UI Automation provider.</span></span> <span data-ttu-id="edc90-113">Genellikle, en üstteki ve soldaki satır veya sütun olacaktır.</span><span class="sxs-lookup"><span data-stu-id="edc90-113">Typically, it will be the topmost and leftmost row or column.</span></span>  
  
- <span data-ttu-id="edc90-114"><xref:System.Windows.Automation.Provider.IGridItemProvider> birleştirme veya hücre bölme gibi kılavuzunun etkin işleme için sağlamaz.</span><span class="sxs-lookup"><span data-stu-id="edc90-114"><xref:System.Windows.Automation.Provider.IGridItemProvider> does not provide for active manipulation of the grid such as merging or splitting cells.</span></span>  
  
- <span data-ttu-id="edc90-115">Denetimleri uygulayan <xref:System.Windows.Automation.Provider.IGridItemProvider> genellikle çevrilebilen (diğer bir deyişle UI Otomasyonu istemci bitişik denetimlere taşıyabilirsiniz) klavye kullanarak.</span><span class="sxs-lookup"><span data-stu-id="edc90-115">Controls that implement <xref:System.Windows.Automation.Provider.IGridItemProvider> can typically be traversed (that is, a UI Automation client can move to adjacent controls) by using the keyboard.</span></span>  
  
<a name="Required_Members_for_IGridItemProvider"></a>   
## <a name="required-members-for-igriditemprovider"></a><span data-ttu-id="edc90-116">Gerekli üyeleri IGridItemProvider için</span><span class="sxs-lookup"><span data-stu-id="edc90-116">Required Members for IGridItemProvider</span></span>  
 <span data-ttu-id="edc90-117">Aşağıdaki özellikleri ve yöntemleri uygulamak için gerekli olan <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span><span class="sxs-lookup"><span data-stu-id="edc90-117">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span>  
  
|<span data-ttu-id="edc90-118">Gerekli üyeleri</span><span class="sxs-lookup"><span data-stu-id="edc90-118">Required members</span></span>|<span data-ttu-id="edc90-119">Üye türü</span><span class="sxs-lookup"><span data-stu-id="edc90-119">Member type</span></span>|<span data-ttu-id="edc90-120">Notlar</span><span class="sxs-lookup"><span data-stu-id="edc90-120">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>|<span data-ttu-id="edc90-121">Özellik</span><span class="sxs-lookup"><span data-stu-id="edc90-121">Property</span></span>|<span data-ttu-id="edc90-122">Yok.</span><span class="sxs-lookup"><span data-stu-id="edc90-122">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>|<span data-ttu-id="edc90-123">Özellik</span><span class="sxs-lookup"><span data-stu-id="edc90-123">Property</span></span>|<span data-ttu-id="edc90-124">Yok.</span><span class="sxs-lookup"><span data-stu-id="edc90-124">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.RowSpan%2A>|<span data-ttu-id="edc90-125">Özellik</span><span class="sxs-lookup"><span data-stu-id="edc90-125">Property</span></span>|<span data-ttu-id="edc90-126">Yok.</span><span class="sxs-lookup"><span data-stu-id="edc90-126">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ColumnSpan%2A>|<span data-ttu-id="edc90-127">Özellik</span><span class="sxs-lookup"><span data-stu-id="edc90-127">Property</span></span>|<span data-ttu-id="edc90-128">None</span><span class="sxs-lookup"><span data-stu-id="edc90-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A>|<span data-ttu-id="edc90-129">Özellik</span><span class="sxs-lookup"><span data-stu-id="edc90-129">Property</span></span>|<span data-ttu-id="edc90-130">None</span><span class="sxs-lookup"><span data-stu-id="edc90-130">None</span></span>|  
  
 <span data-ttu-id="edc90-131">Bu denetim düzeni ilişkili yöntem ya da olaylar vardır.</span><span class="sxs-lookup"><span data-stu-id="edc90-131">This control pattern has no associated methods or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="edc90-132">Özel Durumlar</span><span class="sxs-lookup"><span data-stu-id="edc90-132">Exceptions</span></span>  
 <span data-ttu-id="edc90-133">Bu denetim düzeni ilişkili hiçbir özel durum vardır.</span><span class="sxs-lookup"><span data-stu-id="edc90-133">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edc90-134">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="edc90-134">See also</span></span>

- [<span data-ttu-id="edc90-135">UI Otomasyonu Denetim Desenlerine Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="edc90-135">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="edc90-136">UI Otomasyonu Sağlayıcıda Denetim Düzenleri Desteği</span><span class="sxs-lookup"><span data-stu-id="edc90-136">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="edc90-137">İstemciler İçin UI Otomasyonu Denetim Düzenleri</span><span class="sxs-lookup"><span data-stu-id="edc90-137">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="edc90-138">UI Otomasyonu Grid Denetim Desenini Uygulama</span><span class="sxs-lookup"><span data-stu-id="edc90-138">Implementing the UI Automation Grid Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)
- [<span data-ttu-id="edc90-139">UI Otomasyon Ağacına Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="edc90-139">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [<span data-ttu-id="edc90-140">UI Otomasyonunda Önbelleğe Almayı Kullanma</span><span class="sxs-lookup"><span data-stu-id="edc90-140">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
