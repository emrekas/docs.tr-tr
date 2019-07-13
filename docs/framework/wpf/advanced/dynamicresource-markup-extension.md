---
title: DynamicResource Biçimlendirme Uzantısı
ms.date: 03/30/2017
f1_keywords:
- DynamicResource
- DynamicResourceExtension
helpviewer_keywords:
- XAML [WPF], DynamicResource markup extension
- DynamicResource markup extensions [WPF]
ms.assetid: 7324f243-03af-4c2b-b0db-26ac6cdfcbe4
ms.openlocfilehash: 90768a0c816e790138ba60bd24afee242e41e652
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2019
ms.locfileid: "67860281"
---
# <a name="dynamicresource-markup-extension"></a><span data-ttu-id="346c2-102">DynamicResource Biçimlendirme Uzantısı</span><span class="sxs-lookup"><span data-stu-id="346c2-102">DynamicResource Markup Extension</span></span>
<span data-ttu-id="346c2-103">İçin herhangi bir değer sağlar [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] özellik özniteliği tarafından tanımlanan kaynağına başvuru olması için bu değeri erteleniyor.</span><span class="sxs-lookup"><span data-stu-id="346c2-103">Provides a value for any [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] property attribute by deferring that value to be a reference to a defined resource.</span></span> <span data-ttu-id="346c2-104">Bu kaynak için arama davranışı için çalışma zamanı arama benzerdir.</span><span class="sxs-lookup"><span data-stu-id="346c2-104">Lookup behavior for that resource is analogous to run-time lookup.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="346c2-105">XAML Öznitelik Kullanımı</span><span class="sxs-lookup"><span data-stu-id="346c2-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{DynamicResource key}" .../>  
```  
  
## <a name="xaml-property-element-usage"></a><span data-ttu-id="346c2-106">XAML Özellik Öğesi Kullanımı</span><span class="sxs-lookup"><span data-stu-id="346c2-106">XAML Property Element Usage</span></span>  
  
```xml  
<object>  
  <object.property>  
    <DynamicResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="346c2-107">XAML Değerleri</span><span class="sxs-lookup"><span data-stu-id="346c2-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`key`|<span data-ttu-id="346c2-108">İstenen kaynak anahtarı.</span><span class="sxs-lookup"><span data-stu-id="346c2-108">The key for the requested resource.</span></span> <span data-ttu-id="346c2-109">Bu anahtar tarafından başlangıçta atandığı [x: Key yönergesi](../../xaml-services/x-key-directive.md) kaynak biçimlendirme içinde oluşturulduysa veya olarak sağlanan `key` çağırırken parametre <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> kaynak kodunda oluşturulduysa.</span><span class="sxs-lookup"><span data-stu-id="346c2-109">This key was initially assigned by the [x:Key Directive](../../xaml-services/x-key-directive.md) if a resource was created in markup, or was provided as the `key` parameter when calling <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> if the resource was created in code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="346c2-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="346c2-110">Remarks</span></span>  
 <span data-ttu-id="346c2-111">A `DynamicResource` ilk derleme sırasında geçici bir ifade oluşturur ve istenen kaynak değeri bir nesne oluşturmak için gerçekten gerekli olana kadar bu nedenle kaynaklara arama erteleyin.</span><span class="sxs-lookup"><span data-stu-id="346c2-111">A `DynamicResource` will create a temporary expression during the initial compilation and thus defer lookup for resources until the requested resource value is actually required in order to construct an object.</span></span> <span data-ttu-id="346c2-112">Bu büyük olasılıkla sonra olabilir [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sayfası yüklenir.</span><span class="sxs-lookup"><span data-stu-id="346c2-112">This may potentially be after the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is loaded.</span></span> <span data-ttu-id="346c2-113">Kaynak değeri geçerli sayfa kapsamdan başlayarak tüm etkin kaynak sözlükleri karşı anahtar arama göre bulundu ve derleme yer tutucu ifade için değiştirilir.</span><span class="sxs-lookup"><span data-stu-id="346c2-113">The resource value will be found based on key search against all active resource dictionaries starting from the current page scope, and is substituted for the placeholder expression from compilation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="346c2-114">Bağımlılık özelliği önceliği açısından bir `DynamicResource` ifade dinamik kaynak başvurusu uygulanan burada konuma eşdeğerdir.</span><span class="sxs-lookup"><span data-stu-id="346c2-114">In terms of dependency property precedence, a `DynamicResource` expression is equivalent to the position where the dynamic resource reference is applied.</span></span> <span data-ttu-id="346c2-115">Daha önce sahip olan özellik için yerel bir değer ayarlarsanız bir `DynamicResource` yerel değer olarak ifade `DynamicResource` tamamen kaldırılır.</span><span class="sxs-lookup"><span data-stu-id="346c2-115">If you set a local value for a property that previously had a `DynamicResource` expression as the local value, the `DynamicResource` is completely removed.</span></span> <span data-ttu-id="346c2-116">Ayrıntılar için bkz [bağımlılık özelliği değer önceliği](dependency-property-value-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="346c2-116">For details, see [Dependency Property Value Precedence](dependency-property-value-precedence.md).</span></span>  
  
 <span data-ttu-id="346c2-117">Belirli kaynak erişim senaryoları için uygun özellikle `DynamicResource` başlangıcı yerine sonundan bir [StaticResource işaretleme uzantısı](staticresource-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="346c2-117">Certain resource access scenarios are particularly appropriate for `DynamicResource` as opposed to a [StaticResource Markup Extension](staticresource-markup-extension.md).</span></span> <span data-ttu-id="346c2-118">Bkz: [XAML kaynakları](xaml-resources.md) göreli değeri ve performans etkilerini hakkında bir tartışma için `DynamicResource` ve `StaticResource`.</span><span class="sxs-lookup"><span data-stu-id="346c2-118">See [XAML Resources](xaml-resources.md) for a discussion about the relative merits and performance implications of `DynamicResource` and `StaticResource`.</span></span>  
  
 <span data-ttu-id="346c2-119">Belirtilen <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> mevcut bir kaynak tarafından belirlenen karşılık gelmelidir [x: Key yönergesi](../../xaml-services/x-key-directive.md) sayfanız, uygulama, kullanılabilir denetim temalar ve dış kaynaklar veya sistem kaynakları düzeyde ve Kaynak arama, o sırada gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="346c2-119">The specified <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> should correspond to an existing resource determined by [x:Key Directive](../../xaml-services/x-key-directive.md) at some level in your page, application, the available control themes and external resources, or system resources, and the resource lookup will happen in that order.</span></span> <span data-ttu-id="346c2-120">Statik ve dinamik kaynaklar için kaynak araması hakkında daha fazla bilgi için bkz: [XAML kaynakları](xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="346c2-120">For more information about resource lookup for static and dynamic resources, see [XAML Resources](xaml-resources.md).</span></span>  
  
 <span data-ttu-id="346c2-121">Kaynak anahtarı içinde tanımlanan herhangi bir dize olabilir [XamlName Dilbilgisi](../../xaml-services/xamlname-grammar.md).</span><span class="sxs-lookup"><span data-stu-id="346c2-121">A resource key may be any string defined in the [XamlName Grammar](../../xaml-services/xamlname-grammar.md).</span></span> <span data-ttu-id="346c2-122">Kaynak anahtarı diğer nesne türleri gibi de içerebilir bir <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="346c2-122">A resource key may also be other object types, such as a <xref:System.Type>.</span></span> <span data-ttu-id="346c2-123">A <xref:System.Type> anahtardır denetimleri tarafından temaları nasıl biçimlendirilebilir için temel.</span><span class="sxs-lookup"><span data-stu-id="346c2-123">A <xref:System.Type> key is fundamental to how controls can be styled by themes.</span></span> <span data-ttu-id="346c2-124">Daha fazla bilgi için [denetim yazmaya genel bakış](../controls/control-authoring-overview.md).</span><span class="sxs-lookup"><span data-stu-id="346c2-124">For more information, see [Control Authoring Overview](../controls/control-authoring-overview.md).</span></span>  
  
 <span data-ttu-id="346c2-125">Kaynak araması için API'leri değerleri, gibi <xref:System.Windows.FrameworkElement.FindResource%2A>, tarafından kullanılan aynı kaynak araması mantığını izleyin `DynamicResource`.</span><span class="sxs-lookup"><span data-stu-id="346c2-125">APIs for lookup of resource values, such as <xref:System.Windows.FrameworkElement.FindResource%2A>, follow the same resource lookup logic as used by `DynamicResource`.</span></span>  
  
 <span data-ttu-id="346c2-126">Alternatif bildirime dayanan bir kaynağa başvuran gibidir bir [StaticResource işaretleme uzantısı](staticresource-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="346c2-126">The alternative declarative means of referencing a resource is as a [StaticResource Markup Extension](staticresource-markup-extension.md).</span></span>  
  
 <span data-ttu-id="346c2-127">Öznitelik sözdizimi, bu işaretleme uzantısı ile kullanılan en yaygın sözdizimidir.</span><span class="sxs-lookup"><span data-stu-id="346c2-127">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="346c2-128">Sonra sağlanan dize belirteci `DynamicResource` tanımlayıcı dizesi olarak atandığı <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> temel değer <xref:System.Windows.DynamicResourceExtension> uzantısı sınıfı.</span><span class="sxs-lookup"><span data-stu-id="346c2-128">The string token provided after the `DynamicResource` identifier string is assigned as the <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> value of the underlying <xref:System.Windows.DynamicResourceExtension> extension class.</span></span>  
  
 <span data-ttu-id="346c2-129">`DynamicResource` nesne öğesi sözdiziminde kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="346c2-129">`DynamicResource` can be used in object element syntax.</span></span> <span data-ttu-id="346c2-130">Bu durumda, değerini belirterek <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> özelliği gereklidir.</span><span class="sxs-lookup"><span data-stu-id="346c2-130">In this case, specifying the value of the <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> property is required.</span></span>  
  
 <span data-ttu-id="346c2-131">`DynamicResource` belirten ayrıntılı öznitelik kullanımında da ayrıca kullanılabilir <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> bir özellik olarak özellik değer eşleştirmesi:</span><span class="sxs-lookup"><span data-stu-id="346c2-131">`DynamicResource` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 <span data-ttu-id="346c2-132">Ayrıntılı kullanım, genellikle birden fazla ayarlanabilir özelliğe sahip uzantılar için veya bazı özellikler isteğe bağlıysa yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="346c2-132">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="346c2-133">Çünkü `DynamicResource` yalnızca gerekli olan bir ayarlanabilir özelliği, bu ayrıntılı kullanım tipik değildir.</span><span class="sxs-lookup"><span data-stu-id="346c2-133">Because `DynamicResource` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="346c2-134">İçinde [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] işlemci uygulamasında, bu işaretleme uzantısının işlenmesi tarafından tanımlanır <xref:System.Windows.DynamicResourceExtension> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="346c2-134">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.DynamicResourceExtension> class.</span></span>  
  
 <span data-ttu-id="346c2-135">`DynamicResource` bir işaretleme uzantısıdır.</span><span class="sxs-lookup"><span data-stu-id="346c2-135">`DynamicResource` is a markup extension.</span></span> <span data-ttu-id="346c2-136">Biçimlendirme uzantıları, genellikle öznitelik değerlerinin değişmez değerler veya işleyici isimleri dışına çıkma gereksinimi olduğunda ve bu gereksinim, belirli türler veya özellikler üzerine tür dönüştürücülerini koymaktan daha genel olduğunda uygulanır.</span><span class="sxs-lookup"><span data-stu-id="346c2-136">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="346c2-137">İçindeki tüm biçimlendirme uzantıları [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] kullanmak {ve} kuralına göre kendi öznitelik sözdizimi içinde karakterler bir [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] işlemcisinin bir işaretleme uzantısı özniteliği işlemesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="346c2-137">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="346c2-138">Daha fazla bilgi için [biçimlendirme uzantıları ve WPF XAML](markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="346c2-138">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="346c2-139">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="346c2-139">See also</span></span>

- [<span data-ttu-id="346c2-140">XAML Kaynakları</span><span class="sxs-lookup"><span data-stu-id="346c2-140">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="346c2-141">Kaynaklar ve Kod</span><span class="sxs-lookup"><span data-stu-id="346c2-141">Resources and Code</span></span>](resources-and-code.md)
- [<span data-ttu-id="346c2-142">x:Key Yönergesi</span><span class="sxs-lookup"><span data-stu-id="346c2-142">x:Key Directive</span></span>](../../xaml-services/x-key-directive.md)
- [<span data-ttu-id="346c2-143">XAML'ye Genel Bakış (WPF)</span><span class="sxs-lookup"><span data-stu-id="346c2-143">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
- [<span data-ttu-id="346c2-144">İşaretleme Uzantıları ve WPF XAML</span><span class="sxs-lookup"><span data-stu-id="346c2-144">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="346c2-145">StaticResource İşaretleme Uzantısı</span><span class="sxs-lookup"><span data-stu-id="346c2-145">StaticResource Markup Extension</span></span>](staticresource-markup-extension.md)
- [<span data-ttu-id="346c2-146">İşaretleme Uzantıları ve WPF XAML</span><span class="sxs-lookup"><span data-stu-id="346c2-146">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
