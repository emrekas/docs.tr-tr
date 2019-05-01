---
title: RelativeSource MarkupExtension
ms.date: 03/30/2017
f1_keywords:
- RelativeSource
helpviewer_keywords:
- RelativeSource markup extensions [WPF]
- XAML [WPF], RelativeSource markup extension
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
ms.openlocfilehash: a6a7d615a3a54fbc75bb86b295fdf80433a31dc5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053502"
---
# <a name="relativesource-markupextension"></a><span data-ttu-id="4d39a-102">RelativeSource MarkupExtension</span><span class="sxs-lookup"><span data-stu-id="4d39a-102">RelativeSource MarkupExtension</span></span>

<span data-ttu-id="4d39a-103">Özelliklerini belirtir bir <xref:System.Windows.Data.RelativeSource> içinde kullanılacak bağlama kaynağı, bir [Binding Markup Extension](binding-markup-extension.md), veya ayarlarken <xref:System.Windows.Data.Binding.RelativeSource%2A> özelliği bir <xref:System.Windows.Data.Binding> XAML içinde oluşturulmuş bir öğe.</span><span class="sxs-lookup"><span data-stu-id="4d39a-103">Specifies properties of a <xref:System.Windows.Data.RelativeSource> binding source, to be used within a [Binding Markup Extension](binding-markup-extension.md), or when setting the <xref:System.Windows.Data.Binding.RelativeSource%2A> property of a <xref:System.Windows.Data.Binding> element established in XAML.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="4d39a-104">XAML Öznitelik Kullanımı</span><span class="sxs-lookup"><span data-stu-id="4d39a-104">XAML Attribute Usage</span></span>

```xml
<Binding RelativeSource="{RelativeSource modeEnumValue}" .../>
```

## <a name="xaml-attribute-usage-nested-within-binding-extension"></a><span data-ttu-id="4d39a-105">XAML Öznitelik Kullanımı (Bağlama uzantıları içinde iç içe geçmiş)</span><span class="sxs-lookup"><span data-stu-id="4d39a-105">XAML Attribute Usage (nested within Binding extension)</span></span>

```xml
<object property="{Binding RelativeSource={RelativeSource modeEnumValue} ...}" .../>
```

## <a name="xaml-object-element-usage"></a><span data-ttu-id="4d39a-106">XAML Nesne Öğesi Kullanımı</span><span class="sxs-lookup"><span data-stu-id="4d39a-106">XAML Object Element Usage</span></span>

```xml
<Binding>
  <Binding.RelativeSource>
    <RelativeSource Mode="modeEnumValue"/>
  </Binding.RelativeSource>
</Binding>
```

<span data-ttu-id="4d39a-107">-veya-</span><span class="sxs-lookup"><span data-stu-id="4d39a-107">-or-</span></span>

```xml
<Binding>
  <Binding.RelativeSource>
    <RelativeSource
      Mode="FindAncestor"
      AncestorType="{x:Type typeName}"
      AncestorLevel="intLevel"
    />
  </Binding.RelativeSource>
</Binding>
```

## <a name="xaml-values"></a><span data-ttu-id="4d39a-108">XAML Değerleri</span><span class="sxs-lookup"><span data-stu-id="4d39a-108">XAML Values</span></span>

|||
|-|-|
|`modeEnumValue`|<span data-ttu-id="4d39a-109">Aşağıdakilerden biri:</span><span class="sxs-lookup"><span data-stu-id="4d39a-109">One of the following:</span></span><br /><br /> <span data-ttu-id="4d39a-110">-Dize belirteci `Self`; karşılık gelen bir <xref:System.Windows.Data.RelativeSource> ile oluşturulmuş kendi <xref:System.Windows.Data.RelativeSource.Mode%2A> özelliğini <xref:System.Windows.Data.RelativeSourceMode.Self>.</span><span class="sxs-lookup"><span data-stu-id="4d39a-110">-   The string token `Self`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.Self>.</span></span><br /><span data-ttu-id="4d39a-111">-Dize belirteci `TemplatedParent`; karşılık gelen bir <xref:System.Windows.Data.RelativeSource> ile oluşturulmuş kendi <xref:System.Windows.Data.RelativeSource.Mode%2A> özelliğini <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>.</span><span class="sxs-lookup"><span data-stu-id="4d39a-111">-   The string token `TemplatedParent`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>.</span></span><br /><span data-ttu-id="4d39a-112">-Dize belirteci `PreviousData`; karşılık gelen bir <xref:System.Windows.Data.RelativeSource> ile oluşturulmuş kendi <xref:System.Windows.Data.RelativeSource.Mode%2A> özelliğini <xref:System.Windows.Data.RelativeSourceMode.PreviousData>.</span><span class="sxs-lookup"><span data-stu-id="4d39a-112">-   The string token `PreviousData`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.PreviousData>.</span></span><br /><span data-ttu-id="4d39a-113">-Aşağıda hakkında bilgi için `FindAncestor` modu.</span><span class="sxs-lookup"><span data-stu-id="4d39a-113">-   See below for information on `FindAncestor` mode.</span></span>|
|`FindAncestor`|<span data-ttu-id="4d39a-114">Dize belirteci `FindAncestor`.</span><span class="sxs-lookup"><span data-stu-id="4d39a-114">The string token `FindAncestor`.</span></span> <span data-ttu-id="4d39a-115">Bu belirteci kullanarak moda girer bir `RelativeSource` 'un üst türü ve isteğe bağlı olarak üst düzeyini belirtir.</span><span class="sxs-lookup"><span data-stu-id="4d39a-115">Using this token enters a mode whereby a `RelativeSource` specifies an ancestor type and optionally an ancestor level.</span></span> <span data-ttu-id="4d39a-116">Bu karşılık gelen bir <xref:System.Windows.Data.RelativeSource> ile oluşturulmuş kendi <xref:System.Windows.Data.RelativeSource.Mode%2A> özelliğini <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>.</span><span class="sxs-lookup"><span data-stu-id="4d39a-116">This corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>.</span></span>|
|`typeName`|<span data-ttu-id="4d39a-117">Gerekli `FindAncestor` modu.</span><span class="sxs-lookup"><span data-stu-id="4d39a-117">Required for `FindAncestor` mode.</span></span> <span data-ttu-id="4d39a-118">Dolduran bir türün adını <xref:System.Windows.Data.RelativeSource.AncestorType%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="4d39a-118">The name of a type, which fills the <xref:System.Windows.Data.RelativeSource.AncestorType%2A> property.</span></span>|
|`intLevel`|<span data-ttu-id="4d39a-119">İçin isteğe bağlı `FindAncestor` modu.</span><span class="sxs-lookup"><span data-stu-id="4d39a-119">Optional for `FindAncestor` mode.</span></span> <span data-ttu-id="4d39a-120">Öncül düzeyi (Mantıksal ağaçta üst yön doğrultusunda değerlendirilen.)</span><span class="sxs-lookup"><span data-stu-id="4d39a-120">An ancestor level (evaluated towards the parent direction in the logical tree).</span></span>|

## <a name="remarks"></a><span data-ttu-id="4d39a-121">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="4d39a-121">Remarks</span></span>

<span data-ttu-id="4d39a-122">`{RelativeSource TemplatedParent}` bağlama kullanımları, denetime ait kullanıcı ve denetim mantığının ayrımı daha büyük bir kavramı ele alan önemli bir tekniktir.</span><span class="sxs-lookup"><span data-stu-id="4d39a-122">`{RelativeSource TemplatedParent}` binding usages are a key technique that addresses a larger concept of the separation of a control's UI and a control's logic.</span></span> <span data-ttu-id="4d39a-123">Bu, şablon tanımı içinden şablonlu üst öğeye (şablonun uygulandığı çalışma zamanı nesnesi örneği) bağlanmaya olanak verir.</span><span class="sxs-lookup"><span data-stu-id="4d39a-123">This enables binding from within the template definition to the templated parent (the run time object instance where the template is applied).</span></span> <span data-ttu-id="4d39a-124">Bu durum için [TemplateBinding Markup Extension](templatebinding-markup-extension.md) aslında şu bağlama ifadesi için bir toplu olduğu: `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span><span class="sxs-lookup"><span data-stu-id="4d39a-124">For this case, the [TemplateBinding Markup Extension](templatebinding-markup-extension.md) is in fact a shorthand for the following binding expression: `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span></span> <span data-ttu-id="4d39a-125">`TemplateBinding` veya `{RelativeSource TemplatedParent}` kullanımları, her ikisi de, bir şablon tanımlayan XAML içinde yalnızca ilgilidir.</span><span class="sxs-lookup"><span data-stu-id="4d39a-125">`TemplateBinding` or `{RelativeSource TemplatedParent}` usages are both only relevant within the XAML that defines a template.</span></span> <span data-ttu-id="4d39a-126">Daha fazla bilgi için [TemplateBinding işaretleme uzantısı](templatebinding-markup-extension.md)</span><span class="sxs-lookup"><span data-stu-id="4d39a-126">For more information, see [TemplateBinding Markup Extension](templatebinding-markup-extension.md)</span></span>

<span data-ttu-id="4d39a-127">`{RelativeSource FindAncestor}` esas olarak denetim şablonları veya öngörülebilir kendi kullanıcı Arabirimi bileşimlerinde, burada bir denetimi her zaman belirli bir üst öğe türünün görsel ağacında olması beklenen durumlarda kullanılır.</span><span class="sxs-lookup"><span data-stu-id="4d39a-127">`{RelativeSource FindAncestor}` is mainly used in control templates or predictable self-contained UI compositions, for cases where a control is always expected to be in a visual tree of a certain ancestor type.</span></span> <span data-ttu-id="4d39a-128">Örneğin, bir öğeler denetiminin öğeleri kullanabilirsiniz `FindAncestor` öğelerin özelliklerine bağlanacağını kullanımları üst üst denetim.</span><span class="sxs-lookup"><span data-stu-id="4d39a-128">For example, items of an items control might use `FindAncestor` usages to bind to properties of their items control parent ancestor.</span></span> <span data-ttu-id="4d39a-129">Veya bir şablonda denetim bileşiminin parçası olan öğeler kullanabileceğiniz `FindAncestor` , aynı bileşim yapısı içinde üst öğelere bağlar.</span><span class="sxs-lookup"><span data-stu-id="4d39a-129">Or, elements that are part of control composition in a template can use `FindAncestor` bindings to the parent elements in that same composition structure.</span></span>

<span data-ttu-id="4d39a-130">Nesne öğesi sözdizimi içinde `FindAncestor` ikinci nesne öğesi sözdizimi özellikle için kullanılan XAML sözdizimi bölümlerinde gösterilen modu `FindAncestor` modu.</span><span class="sxs-lookup"><span data-stu-id="4d39a-130">In the object element syntax for `FindAncestor` mode shown in the XAML Syntax sections, the second object element syntax is used specifically for `FindAncestor` mode.</span></span> <span data-ttu-id="4d39a-131">`FindAncestor` mod gerektirir bir <xref:System.Windows.Data.RelativeSource.AncestorType%2A> değeri.</span><span class="sxs-lookup"><span data-stu-id="4d39a-131">`FindAncestor` mode requires an <xref:System.Windows.Data.RelativeSource.AncestorType%2A> value.</span></span> <span data-ttu-id="4d39a-132">Ayarlamalısınız <xref:System.Windows.Data.RelativeSource.AncestorType%2A> kullanarak bir özniteliği olarak bir [x: Type işaretleme uzantısı](../../xaml-services/x-type-markup-extension.md) Aranılacak türü referansı.</span><span class="sxs-lookup"><span data-stu-id="4d39a-132">You must set <xref:System.Windows.Data.RelativeSource.AncestorType%2A> as an attribute using an [x:Type Markup Extension](../../xaml-services/x-type-markup-extension.md) reference to the type of ancestor to look for.</span></span> <span data-ttu-id="4d39a-133"><xref:System.Windows.Data.RelativeSource.AncestorType%2A> Değeri, bağlama isteği çalışma zamanında işlendiğinde kullanılır.</span><span class="sxs-lookup"><span data-stu-id="4d39a-133">The <xref:System.Windows.Data.RelativeSource.AncestorType%2A> value is used when the binding request is processed at run-time.</span></span>

<span data-ttu-id="4d39a-134">İçin `FindAncestor` modu, isteğe bağlı özellik <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> durumlarda üst arama belirsizliğinin ortadan kaldırılmasını yardımcı olabilecek birden fazla üst öğe ağacında varolan bu türün büyük olasılıkla olduğu.</span><span class="sxs-lookup"><span data-stu-id="4d39a-134">For `FindAncestor` mode, the optional property <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> can help disambiguate the ancestor lookup in cases where there is possibly more than one ancestor of that type existing in the element tree.</span></span>

<span data-ttu-id="4d39a-135">Nasıl kullanılacağı hakkında daha fazla bilgi için `FindAncestor` modu bkz <xref:System.Windows.Data.RelativeSource>.</span><span class="sxs-lookup"><span data-stu-id="4d39a-135">For more information on how to use the `FindAncestor` mode, see <xref:System.Windows.Data.RelativeSource>.</span></span>

<span data-ttu-id="4d39a-136">`{RelativeSource Self}` senaryolarda yararlıdır bu iki özellik arasında var. burada örnek bir özellik aynı örneğini ve hiçbir genel bağımlılık özelliği ilişkisi (zorlama gibi) başka bir özelliğin değerini zaten bağlı olmamalıdır.</span><span class="sxs-lookup"><span data-stu-id="4d39a-136">`{RelativeSource Self}` is useful for scenarios where one property of an instance should depend on the value of another property of the same instance, and no general dependency property relationship (such as coercion) already exists between those two properties.</span></span> <span data-ttu-id="4d39a-137">İki özellik mevcut bir nesne üzerinde değerleri değişmez olarak aynı olacak (ve aynı şekilde), ayrıca uygulayabilirsiniz nadir olmasına rağmen bir `Converter` parametresi içeren bir bağlamaya `{RelativeSource Self}`ve kaynak arasında dönüştürmek için dönüştürücüyü kullanabilirsiniz ve Hedef türü.</span><span class="sxs-lookup"><span data-stu-id="4d39a-137">Although it is rare that two properties exist on an object such that the values are literally identical (and are identically typed), you can also apply a `Converter` parameter to a binding that has `{RelativeSource Self}`, and use the converter to convert between source and target types.</span></span> <span data-ttu-id="4d39a-138">Başka bir senaryo için `{RelativeSource Self}` parçası olarak bir <xref:System.Windows.MultiDataTrigger>.</span><span class="sxs-lookup"><span data-stu-id="4d39a-138">Another scenario for `{RelativeSource Self}` is as part of a <xref:System.Windows.MultiDataTrigger>.</span></span>

<span data-ttu-id="4d39a-139">Örneğin, aşağıdaki XAML tanımlayan bir <xref:System.Windows.Shapes.Rectangle> hangi değer için girilen öğesi böyle <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.Shapes.Rectangle> her zaman bir kare olacağı: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`</span><span class="sxs-lookup"><span data-stu-id="4d39a-139">For example, the following XAML defines a <xref:System.Windows.Shapes.Rectangle> element such that no matter what value is entered for <xref:System.Windows.FrameworkElement.Width%2A>, the <xref:System.Windows.Shapes.Rectangle> is always a square: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`</span></span>

<span data-ttu-id="4d39a-140">`{RelativeSource PreviousData}` Veri şablonları veya bağlamaları veri kaynağı olarak bir koleksiyon burada kullanıyorsanız durumlarda yararlı olur.</span><span class="sxs-lookup"><span data-stu-id="4d39a-140">`{RelativeSource PreviousData}` is useful either in data templates, or in cases where bindings are using a collection as the data source.</span></span> <span data-ttu-id="4d39a-141">Kullanabileceğiniz `{RelativeSource PreviousData}` koleksiyondaki bitişik veri öğeleri arasındaki ilişkileri vurgulamak için.</span><span class="sxs-lookup"><span data-stu-id="4d39a-141">You can use `{RelativeSource PreviousData}` to highlight relationships between adjacent data items in the collection.</span></span> <span data-ttu-id="4d39a-142">İlgili bir teknik bir <xref:System.Windows.Data.MultiBinding> veri kaynağı ve iki öğe ve özellikleri arasındaki farkı belirlemek için bu bağlama üzerinde bir dönüştürücü geçerli ve önceki öğeler arasında.</span><span class="sxs-lookup"><span data-stu-id="4d39a-142">A related technique is to establish a <xref:System.Windows.Data.MultiBinding> between the current and previous items in the data source, and use a converter on that binding to determine the difference between the two items and their properties.</span></span>

<span data-ttu-id="4d39a-143">Aşağıdaki örnekte, ilk <xref:System.Windows.Controls.TextBlock> öğeleri şablon geçerli sayıyı gösterir.</span><span class="sxs-lookup"><span data-stu-id="4d39a-143">In the following example, the first <xref:System.Windows.Controls.TextBlock> in the items template displays the current number.</span></span> <span data-ttu-id="4d39a-144">İkinci <xref:System.Windows.Controls.TextBlock> bağlamanın bir <xref:System.Windows.Data.MultiBinding> iki olup sahip <xref:System.Windows.Data.Binding> seçmenlere: geçerli kayıt ve kullanarak, önceki veri kaydını kasıtlı olarak kullanan bir bağlama `{RelativeSource PreviousData}`.</span><span class="sxs-lookup"><span data-stu-id="4d39a-144">The second <xref:System.Windows.Controls.TextBlock> binding is a <xref:System.Windows.Data.MultiBinding> that nominally has two <xref:System.Windows.Data.Binding> constituents: the current record, and a binding that deliberately uses the previous data record by using `{RelativeSource PreviousData}`.</span></span> <span data-ttu-id="4d39a-145">Ardından, üzerinde bir dönüştürücü <xref:System.Windows.Data.MultiBinding> farkı hesaplar ve bağlamaya geri döndürür.</span><span class="sxs-lookup"><span data-stu-id="4d39a-145">Then, a converter on the <xref:System.Windows.Data.MultiBinding> calculates the difference and returns it to the binding.</span></span>

```xml
<ListBox Name="fibolist">
    <ListBox.ItemTemplate>
        <DataTemplate>
            <StackPanel Orientation="Horizontal">
            <TextBlock Text="{Binding}"/>
            <TextBlock>, difference = </TextBlock>
                <TextBlock>
                    <TextBlock.Text>
                        <MultiBinding Converter="{StaticResource DiffConverter}">
                            <Binding/>
                            <Binding RelativeSource="{RelativeSource PreviousData}"/>
                        </MultiBinding>
                    </TextBlock.Text>
                </TextBlock>
            </StackPanel>
        </DataTemplate>
    </ListBox.ItemTemplate>
```

<span data-ttu-id="4d39a-146">Bir kavram, burada kapsanmayan olarak veri bağlamasını açıklama bkz [Data Binding Overview](../data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4d39a-146">Describing data binding as a concept is not covered here, see [Data Binding Overview](../data/data-binding-overview.md).</span></span>

<span data-ttu-id="4d39a-147">İçinde [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML işlemci uygulamasında, bu işaretleme uzantısının işlenmesi tarafından tanımlanır <xref:System.Windows.Data.RelativeSource> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="4d39a-147">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.Data.RelativeSource> class.</span></span>

<span data-ttu-id="4d39a-148">`RelativeSource` bir işaretleme uzantısıdır.</span><span class="sxs-lookup"><span data-stu-id="4d39a-148">`RelativeSource` is a markup extension.</span></span> <span data-ttu-id="4d39a-149">Biçimlendirme uzantıları, genellikle öznitelik değerlerinin değişmez değerler veya işleyici isimleri dışına çıkma gereksinimi olduğunda ve bu gereksinim, belirli türler veya özellikler üzerine tür dönüştürücülerini koymaktan daha genel olduğunda uygulanır.</span><span class="sxs-lookup"><span data-stu-id="4d39a-149">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="4d39a-150">XAML kullanım içindeki tüm biçimlendirme uzantıları `{` ve `}` karakter olarak bir XAML işlemcisinin bir işaretleme uzantısı özniteliği işlenmesi gerektiğini, kuralına göre kendi öznitelik sözdizimi.</span><span class="sxs-lookup"><span data-stu-id="4d39a-150">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="4d39a-151">Daha fazla bilgi için [biçimlendirme uzantıları ve WPF XAML](markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="4d39a-151">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4d39a-152">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="4d39a-152">See also</span></span>

- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="4d39a-153">Stil ve Şablon Oluşturma</span><span class="sxs-lookup"><span data-stu-id="4d39a-153">Styling and Templating</span></span>](../controls/styling-and-templating.md)
- [<span data-ttu-id="4d39a-154">XAML'ye Genel Bakış (WPF)</span><span class="sxs-lookup"><span data-stu-id="4d39a-154">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
- [<span data-ttu-id="4d39a-155">İşaretleme Uzantıları ve WPF XAML</span><span class="sxs-lookup"><span data-stu-id="4d39a-155">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="4d39a-156">Veri Bağlamaya Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="4d39a-156">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="4d39a-157">Bağlama Bildirimlerine Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="4d39a-157">Binding Declarations Overview</span></span>](../data/binding-declarations-overview.md)
- [<span data-ttu-id="4d39a-158">x:Type İşaretleme Uzantısı</span><span class="sxs-lookup"><span data-stu-id="4d39a-158">x:Type Markup Extension</span></span>](../../xaml-services/x-type-markup-extension.md)
