---
title: '&lt;Temizle&gt; öğesi için &lt;dinleyicileri&gt; için &lt;izleme&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 2e0970fe197ecf6e0fbcf94f410364cb59d267e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732615"
---
# <a name="ltcleargt-element-for-ltlistenersgt-for-lttracegt"></a><span data-ttu-id="35be0-102">&lt;Temizle&gt; öğesi için &lt;dinleyicileri&gt; için &lt;izleme&gt;</span><span class="sxs-lookup"><span data-stu-id="35be0-102">&lt;clear&gt; Element for &lt;listeners&gt; for &lt;trace&gt;</span></span>
<span data-ttu-id="35be0-103">Temizler `Listeners` izleme için koleksiyon.</span><span class="sxs-lookup"><span data-stu-id="35be0-103">Clears the `Listeners` collection for trace.</span></span>  
  
 <span data-ttu-id="35be0-104">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="35be0-104">\<configuration></span></span>  
<span data-ttu-id="35be0-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="35be0-105">\<system.diagnostics></span></span>  
<span data-ttu-id="35be0-106">\<İzleme ></span><span class="sxs-lookup"><span data-stu-id="35be0-106">\<trace></span></span>  
<span data-ttu-id="35be0-107">\<dinleyicileri ></span><span class="sxs-lookup"><span data-stu-id="35be0-107">\<listeners></span></span>  
<span data-ttu-id="35be0-108">\<Temizleme ></span><span class="sxs-lookup"><span data-stu-id="35be0-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35be0-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="35be0-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35be0-110">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="35be0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="35be0-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="35be0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35be0-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="35be0-112">Attributes</span></span>  
 <span data-ttu-id="35be0-113">Yok.</span><span class="sxs-lookup"><span data-stu-id="35be0-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="35be0-114">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="35be0-114">Child Elements</span></span>  
 <span data-ttu-id="35be0-115">Yok.</span><span class="sxs-lookup"><span data-stu-id="35be0-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="35be0-116">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="35be0-116">Parent Elements</span></span>  
  
|<span data-ttu-id="35be0-117">Öğe</span><span class="sxs-lookup"><span data-stu-id="35be0-117">Element</span></span>|<span data-ttu-id="35be0-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="35be0-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="35be0-119">Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.</span><span class="sxs-lookup"><span data-stu-id="35be0-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="35be0-120">Toplamak, depolamak ve iletileri ve bir izleme anahtarı ayarlandığı düzeyi izleme dinleyicilerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="35be0-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="35be0-121">Toplamak, depolamak ve izleme iletilerini yönlendirmek dinleyicileri içerir.</span><span class="sxs-lookup"><span data-stu-id="35be0-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="35be0-122">Toplamak, depolamak ve iletileri yönlendirmek dinleyicileri içerir.</span><span class="sxs-lookup"><span data-stu-id="35be0-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="35be0-123">Dinleyicileri bir uygun hedef izleme çıkışa doğrudan.</span><span class="sxs-lookup"><span data-stu-id="35be0-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35be0-124">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="35be0-124">Remarks</span></span>  
 <span data-ttu-id="35be0-125">`<clear>` Öğeyi kaldırır gelen tüm dinleyicileri `Listeners` izleme için koleksiyon.</span><span class="sxs-lookup"><span data-stu-id="35be0-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="35be0-126">Kullanabileceğiniz `<clear>` kullanmadan önce öğesi `<add>` koleksiyondaki herhangi bir etkin dinleyiciler vardır emin olmak için öğesi.</span><span class="sxs-lookup"><span data-stu-id="35be0-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="35be0-127">Temizleyebilir `Listeners` çağırarak programlama yoluyla koleksiyonu <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> metodunda <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> özelliği (`System.Diagnostics.Trace.Listeners.Clear()`).</span><span class="sxs-lookup"><span data-stu-id="35be0-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="35be0-128">Bu öğe, makine yapılandırma dosyası (Machine.config) ve uygulama yapılandırma dosyasında kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="35be0-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35be0-129">`<clear>` Öğeyi kaldırır <xref:System.Diagnostics.DefaultTraceListener> gelen `Listeners` davranışını değiştirme koleksiyonu <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, ve <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="35be0-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="35be0-130">Çağırma bir `Assert` veya `Fail` yöntem normal olarak görüntülenen bir ileti kutusu sonuçlanır.</span><span class="sxs-lookup"><span data-stu-id="35be0-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="35be0-131">Ancak, ileti kutusu varsa görüntülenmez <xref:System.Diagnostics.DefaultTraceListener> kullanımda olmayan `Listeners` koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="35be0-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35be0-132">Örnek</span><span class="sxs-lookup"><span data-stu-id="35be0-132">Example</span></span>  
 <span data-ttu-id="35be0-133">Aşağıdaki örnek nasıl kullanılacağını gösterir `<clear>` kullanmadan önce öğesi `<add>` dinleyici eklemek için öğe `console` için `Listeners` izleme için koleksiyon.</span><span class="sxs-lookup"><span data-stu-id="35be0-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="35be0-134">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="35be0-134">See also</span></span>
- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="35be0-135">İzleme ve Hata Ayıklama Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="35be0-135">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="35be0-136">\<kaldırma ></span><span class="sxs-lookup"><span data-stu-id="35be0-136">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="35be0-137">İzleme Dinleyicileri</span><span class="sxs-lookup"><span data-stu-id="35be0-137">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
