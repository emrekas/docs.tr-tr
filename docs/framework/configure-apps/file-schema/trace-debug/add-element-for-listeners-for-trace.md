---
title: <add> Öğe için <listeners> için <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: ba0ffc4f95b9af7fcd319068501ce0bb9714c2ad
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089588"
---
# <a name="add-element-for-listeners-for-trace"></a><span data-ttu-id="59abe-102">\<Ekle > öğesi için \<dinleyicileri > için \<İzleme ></span><span class="sxs-lookup"><span data-stu-id="59abe-102">\<add> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="59abe-103">Bir ekler **dinleyicileri** koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="59abe-103">Adds a listener to the **Listeners** collection.</span></span>  
  
 <span data-ttu-id="59abe-104">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="59abe-104">\<configuration></span></span>  
<span data-ttu-id="59abe-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="59abe-105">\<system.diagnostics></span></span>  
<span data-ttu-id="59abe-106">\<İzleme ></span><span class="sxs-lookup"><span data-stu-id="59abe-106">\<trace></span></span>  
<span data-ttu-id="59abe-107">\<dinleyicileri ></span><span class="sxs-lookup"><span data-stu-id="59abe-107">\<listeners></span></span>  
<span data-ttu-id="59abe-108">\<Ekle ></span><span class="sxs-lookup"><span data-stu-id="59abe-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59abe-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="59abe-109">Syntax</span></span>  
  
```xml  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59abe-110">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="59abe-110">Attributes and Elements</span></span>  
 <span data-ttu-id="59abe-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="59abe-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59abe-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="59abe-112">Attributes</span></span>  
  
|<span data-ttu-id="59abe-113">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="59abe-113">Attribute</span></span>|<span data-ttu-id="59abe-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="59abe-114">Description</span></span>|  
|---------------|-----------------|  
|**<span data-ttu-id="59abe-115"> türü</span><span class="sxs-lookup"><span data-stu-id="59abe-115">type</span></span>**|<span data-ttu-id="59abe-116">Gerekli öznitelik.</span><span class="sxs-lookup"><span data-stu-id="59abe-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="59abe-117">Dinleyici türünü belirtir.</span><span class="sxs-lookup"><span data-stu-id="59abe-117">Specifies the type of the listener.</span></span> <span data-ttu-id="59abe-118">Belirtilen gereksinimleri karşılayan bir dize kullanmalısınız [belirtme tam olarak nitelenmiş tür adlarını](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="59abe-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|**<span data-ttu-id="59abe-119">initializeData</span><span class="sxs-lookup"><span data-stu-id="59abe-119">initializeData</span></span>**|<span data-ttu-id="59abe-120">İsteğe bağlı öznitelik.</span><span class="sxs-lookup"><span data-stu-id="59abe-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="59abe-121">Belirtilen sınıf için oluşturucuya geçirilen dizesi.</span><span class="sxs-lookup"><span data-stu-id="59abe-121">The string passed to the constructor for the specified class.</span></span>|  
|**<span data-ttu-id="59abe-122">name</span><span class="sxs-lookup"><span data-stu-id="59abe-122">name</span></span>**|<span data-ttu-id="59abe-123">İsteğe bağlı öznitelik.</span><span class="sxs-lookup"><span data-stu-id="59abe-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="59abe-124">Dinleyicisinin adını belirtir.</span><span class="sxs-lookup"><span data-stu-id="59abe-124">Specifies the name of the listener.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59abe-125">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="59abe-125">Child Elements</span></span>  
  
|<span data-ttu-id="59abe-126">Öğe</span><span class="sxs-lookup"><span data-stu-id="59abe-126">Element</span></span>|<span data-ttu-id="59abe-127">Açıklama</span><span class="sxs-lookup"><span data-stu-id="59abe-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59abe-128">\<Filtre ></span><span class="sxs-lookup"><span data-stu-id="59abe-128">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="59abe-129">Bir dinleyicisi için bir filtre ekler `Listeners` koleksiyonu için bir izleme.</span><span class="sxs-lookup"><span data-stu-id="59abe-129">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="59abe-130">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="59abe-130">Parent Elements</span></span>  
  
|<span data-ttu-id="59abe-131">Öğe</span><span class="sxs-lookup"><span data-stu-id="59abe-131">Element</span></span>|<span data-ttu-id="59abe-132">Açıklama</span><span class="sxs-lookup"><span data-stu-id="59abe-132">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="59abe-133">Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.</span><span class="sxs-lookup"><span data-stu-id="59abe-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="59abe-134">Toplar, depolar, bir dinleyici belirtir ve iletileri yönlendirir.</span><span class="sxs-lookup"><span data-stu-id="59abe-134">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="59abe-135">Dinleyicileri bir uygun hedef izleme çıkışa doğrudan.</span><span class="sxs-lookup"><span data-stu-id="59abe-135">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="59abe-136">ASP.NET yapılandırma bölümü için olan kök öğesini belirtir.</span><span class="sxs-lookup"><span data-stu-id="59abe-136">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="59abe-137">Toplamak, depolamak ve izleme iletilerini yönlendirmek dinleyicileri içerir.</span><span class="sxs-lookup"><span data-stu-id="59abe-137">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59abe-138">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="59abe-138">Remarks</span></span>  
 <span data-ttu-id="59abe-139"><xref:System.Diagnostics.Debug> Ve <xref:System.Diagnostics.Trace> sınıfları paylaşma aynı **dinleyicileri** koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="59abe-139">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="59abe-140">Bu sınıflardan birine koleksiyonuna bir dinleyici nesne eklerseniz, başka bir sınıfın aynı dinleyicisi kullanır.</span><span class="sxs-lookup"><span data-stu-id="59abe-140">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="59abe-141">Dinleyici sınıfların türetilmesi <xref:System.Diagnostics.TraceListener>.</span><span class="sxs-lookup"><span data-stu-id="59abe-141">The listener classes derive from the <xref:System.Diagnostics.TraceListener>.</span></span>  
  
 <span data-ttu-id="59abe-142">Siz belirtmezseniz `name` İzleme dinleyicisi özniteliği <xref:System.Diagnostics.TraceListener.Name%2A> İzleme dinleyicisi Varsayılanları boş bir dize ("").</span><span class="sxs-lookup"><span data-stu-id="59abe-142">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="59abe-143">Uygulamanızın yalnızca bir dinleyicisi varsa, bir adı belirtmeden ekleme ve boş bir dize adı belirterek kaldırın.</span><span class="sxs-lookup"><span data-stu-id="59abe-143">If your application has only one listener, you can add it without specifying a name, and remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="59abe-144">Ancak, uygulamanızın birden fazla dinleyici varsa tanımlamanıza ve içinde tek tek izleme dinleyicilerine yönetmenize olanak tanıyan her İzleme dinleyicisi için benzersiz adlar belirtmeniz gerekir <xref:System.Diagnostics.Debug.Listeners%2A> ve <xref:System.Diagnostics.Trace.Listeners%2A> koleksiyonları.</span><span class="sxs-lookup"><span data-stu-id="59abe-144">However, if your application has more than one listener, you should specify unique names for each trace listener, which allows you to identify and manage individual trace listeners within the <xref:System.Diagnostics.Debug.Listeners%2A> and <xref:System.Diagnostics.Trace.Listeners%2A> collections.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59abe-145">Birden fazla İzleme dinleyicisi aynı türde ve aynı adı yalnızca bir izleme dinleyicisi sonuçlarında türü ekleyip eklenmesini ad `Listeners` koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="59abe-145">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="59abe-146">Ancak, program aracılığıyla birden fazla özdeş dinleyicilere ekleyebilirsiniz `Listeners` koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="59abe-146">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="59abe-147">Değeri **initializeData** özniteliği oluşturduğunuz dinleyici türüne bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="59abe-147">The value for the **initializeData** attribute depends on the type of listener you create.</span></span> <span data-ttu-id="59abe-148">Tüm izleme dinleyicilerine belirtmenizi gerektiren **initializeData**.</span><span class="sxs-lookup"><span data-stu-id="59abe-148">Not all trace listeners require that you specify **initializeData**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59abe-149">Kullanırken `initializeData` özniteliği, "'initializeData' özniteliği. bildirilmedi" uyarı derleyici alabilirsiniz</span><span class="sxs-lookup"><span data-stu-id="59abe-149">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="59abe-150">Bu uyarı oluşur yapılandırma ayarlarını soyut temel sınıf doğrulanır <xref:System.Diagnostics.TraceListener>, hangi tanımıyor `initializeData` özniteliği.</span><span class="sxs-lookup"><span data-stu-id="59abe-150">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="59abe-151">Genellikle, bir parametre alan bir oluşturucu sahip İzleme dinleyicisi uygulamaları için bu uyarıyı yoksayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="59abe-151">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="59abe-152">Aşağıdaki tablo .NET Framework ile birlikte izleme dinleyicilerine gösterir ve değerinin açıklanmıştır kendi **initializeData** öznitelikleri.</span><span class="sxs-lookup"><span data-stu-id="59abe-152">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their **initializeData** attributes.</span></span>  
  
|<span data-ttu-id="59abe-153">İzleme dinleyicisi sınıfı</span><span class="sxs-lookup"><span data-stu-id="59abe-153">Trace listener class</span></span>|<span data-ttu-id="59abe-154">initializeData özniteliği değeri</span><span class="sxs-lookup"><span data-stu-id="59abe-154">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="59abe-155">`useErrorStream` Değerini <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> Oluşturucusu.</span><span class="sxs-lookup"><span data-stu-id="59abe-155">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="59abe-156">Ayarlama `initializeData` özniteliğini "`true`" izleme ve hata ayıklama yazılacak çıkış <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" yazılacak <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="59abe-156">Set the `initializeData` attribute to "`true`" to write trace and debug output to <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" to write to <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="59abe-157">Dosya adı <xref:System.Diagnostics.DelimitedListTraceListener> yazar.</span><span class="sxs-lookup"><span data-stu-id="59abe-157">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="59abe-158">Mevcut bir olay günlüğü kaynağı adı adı.</span><span class="sxs-lookup"><span data-stu-id="59abe-158">The name of the name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="59abe-159">Dosyanın adı, <xref:System.Diagnostics.EventSchemaTraceListener> yazar.</span><span class="sxs-lookup"><span data-stu-id="59abe-159">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="59abe-160">Dosyanın adı, <xref:System.Diagnostics.TextWriterTraceListener> yazar.</span><span class="sxs-lookup"><span data-stu-id="59abe-160">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="59abe-161">Dosyanın adı, <xref:System.Diagnostics.XmlWriterTraceListener> yazar.</span><span class="sxs-lookup"><span data-stu-id="59abe-161">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="59abe-162">Örnek</span><span class="sxs-lookup"><span data-stu-id="59abe-162">Example</span></span>  
 <span data-ttu-id="59abe-163">Aşağıdaki örnek nasıl kullanılacağını gösterir  **\<Ekle >** dinleyiciler eklemek için öğeleri `MyListener` ve `MyEventListener` için **dinleyicileri** koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="59abe-163">The following example shows how to use **\<add>** elements to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> `MyListener` <span data-ttu-id="59abe-164">adlı bir dosya oluşturur `MyListener.log` ve çıkış dosyasına yazar.</span><span class="sxs-lookup"><span data-stu-id="59abe-164">creates a file called `MyListener.log` and writes the output to the file.</span></span> `MyEventListener` <span data-ttu-id="59abe-165">olay günlüğünde bir giriş oluşturur.</span><span class="sxs-lookup"><span data-stu-id="59abe-165">creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
            <add name="MyEventListener"  
                 type="System.Diagnostics.EventLogTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"                 initializeData="MyConfigEventLog"/>  
            <add name="configConsoleListener"  
                 type="System.Diagnostics.ConsoleTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="59abe-166">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="59abe-166">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [<span data-ttu-id="59abe-167">İzleme ve Hata Ayıklama Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="59abe-167">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="59abe-168">İz Dinleyicileri</span><span class="sxs-lookup"><span data-stu-id="59abe-168">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
