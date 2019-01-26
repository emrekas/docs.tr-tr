---
title: '&lt;Temizle&gt; öğesi için &lt;dinleyicileri&gt; için &lt;izleme&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: c0bb2cabafbaba33f8dde7cbf3399387876e0158
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083593"
---
# <a name="ltcleargt-element-for-ltlistenersgt-for-lttracegt"></a><span data-ttu-id="e10cd-102">&lt;Temizle&gt; öğesi için &lt;dinleyicileri&gt; için &lt;izleme&gt;</span><span class="sxs-lookup"><span data-stu-id="e10cd-102">&lt;clear&gt; Element for &lt;listeners&gt; for &lt;trace&gt;</span></span>
<span data-ttu-id="e10cd-103">Temizler `Listeners` izleme için koleksiyon.</span><span class="sxs-lookup"><span data-stu-id="e10cd-103">Clears the `Listeners` collection for trace.</span></span>  
  
 <span data-ttu-id="e10cd-104">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="e10cd-104">\<configuration></span></span>  
<span data-ttu-id="e10cd-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="e10cd-105">\<system.diagnostics></span></span>  
<span data-ttu-id="e10cd-106">\<İzleme ></span><span class="sxs-lookup"><span data-stu-id="e10cd-106">\<trace></span></span>  
<span data-ttu-id="e10cd-107">\<dinleyicileri ></span><span class="sxs-lookup"><span data-stu-id="e10cd-107">\<listeners></span></span>  
<span data-ttu-id="e10cd-108">\<Temizleme ></span><span class="sxs-lookup"><span data-stu-id="e10cd-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e10cd-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="e10cd-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e10cd-110">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="e10cd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e10cd-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="e10cd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e10cd-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="e10cd-112">Attributes</span></span>  
 <span data-ttu-id="e10cd-113">Yok.</span><span class="sxs-lookup"><span data-stu-id="e10cd-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e10cd-114">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="e10cd-114">Child Elements</span></span>  
 <span data-ttu-id="e10cd-115">Yok.</span><span class="sxs-lookup"><span data-stu-id="e10cd-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e10cd-116">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="e10cd-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e10cd-117">Öğe</span><span class="sxs-lookup"><span data-stu-id="e10cd-117">Element</span></span>|<span data-ttu-id="e10cd-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e10cd-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e10cd-119">Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.</span><span class="sxs-lookup"><span data-stu-id="e10cd-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="e10cd-120">Toplamak, depolamak ve iletileri ve bir izleme anahtarı ayarlandığı düzeyi izleme dinleyicilerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="e10cd-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="e10cd-121">Toplamak, depolamak ve izleme iletilerini yönlendirmek dinleyicileri içerir.</span><span class="sxs-lookup"><span data-stu-id="e10cd-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="e10cd-122">Toplamak, depolamak ve iletileri yönlendirmek dinleyicileri içerir.</span><span class="sxs-lookup"><span data-stu-id="e10cd-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="e10cd-123">Dinleyicileri bir uygun hedef izleme çıkışa doğrudan.</span><span class="sxs-lookup"><span data-stu-id="e10cd-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e10cd-124">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e10cd-124">Remarks</span></span>  
 <span data-ttu-id="e10cd-125">`<clear>` Öğeyi kaldırır gelen tüm dinleyicileri `Listeners` izleme için koleksiyon.</span><span class="sxs-lookup"><span data-stu-id="e10cd-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="e10cd-126">Kullanabileceğiniz `<clear>` kullanmadan önce öğesi `<add>` koleksiyondaki herhangi bir etkin dinleyiciler vardır emin olmak için öğesi.</span><span class="sxs-lookup"><span data-stu-id="e10cd-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="e10cd-127">Temizleyebilir `Listeners` çağırarak programlama yoluyla koleksiyonu <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> metodunda <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> özelliği (`System.Diagnostics.Trace.Listeners.Clear()`).</span><span class="sxs-lookup"><span data-stu-id="e10cd-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="e10cd-128">Bu öğe, makine yapılandırma dosyası (Machine.config) ve uygulama yapılandırma dosyasında kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="e10cd-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e10cd-129">`<clear>` Öğeyi kaldırır <xref:System.Diagnostics.DefaultTraceListener> gelen `Listeners` davranışını değiştirme koleksiyonu <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, ve <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="e10cd-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="e10cd-130">Çağırma bir `Assert` veya `Fail` yöntem normal olarak görüntülenen bir ileti kutusu sonuçlanır.</span><span class="sxs-lookup"><span data-stu-id="e10cd-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="e10cd-131">Ancak, ileti kutusu varsa görüntülenmez <xref:System.Diagnostics.DefaultTraceListener> kullanımda olmayan `Listeners` koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="e10cd-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e10cd-132">Örnek</span><span class="sxs-lookup"><span data-stu-id="e10cd-132">Example</span></span>  
 <span data-ttu-id="e10cd-133">Aşağıdaki örnek nasıl kullanılacağını gösterir `<clear>` kullanmadan önce öğesi `<add>` dinleyici eklemek için öğe `console` için `Listeners` izleme için koleksiyon.</span><span class="sxs-lookup"><span data-stu-id="e10cd-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <clear/>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="e10cd-134">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="e10cd-134">See also</span></span>
- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="e10cd-135">İzleme ve Hata Ayıklama Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="e10cd-135">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="e10cd-136">\<kaldırma ></span><span class="sxs-lookup"><span data-stu-id="e10cd-136">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="e10cd-137">İzleme Dinleyicileri</span><span class="sxs-lookup"><span data-stu-id="e10cd-137">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
