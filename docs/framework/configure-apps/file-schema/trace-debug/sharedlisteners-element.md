---
title: <sharedListeners> Öğesi
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sharedListeners
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners
helpviewer_keywords:
- <sharedListeners> element
- listeners
- shared listeners
- trace listeners, <sharedListeners> element
- sharedListeners element
ms.assetid: de200534-19dd-4156-86cf-c50521802c4c
ms.openlocfilehash: 56a4111f2e0fd290321756c43c7f245e46044b02
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254945"
---
# <a name="sharedlisteners-element"></a><span data-ttu-id="7aeaa-102">\<sharedListeners > öğesi</span><span class="sxs-lookup"><span data-stu-id="7aeaa-102">\<sharedListeners> Element</span></span>
<span data-ttu-id="7aeaa-103">Herhangi bir kaynak veya trace ögesi başvurabilirsiniz dinleyicileri içerir.</span><span class="sxs-lookup"><span data-stu-id="7aeaa-103">Contains listeners that any source or trace element can reference.</span></span>  <span data-ttu-id="7aeaa-104">Dinleyiciler, varsayılan olarak tüm izlemeleri almaz ve çalışma zamanında bu dinleyicileri almak mümkün değildir.</span><span class="sxs-lookup"><span data-stu-id="7aeaa-104">These listeners do not receive any traces by default, and it is not possible to retrieve these listeners at run time.</span></span> <span data-ttu-id="7aeaa-105">Paylaşılan dinleyiciler tanımlanan dinleyicileri adına göre kaynakları veya izlemeleri eklenebilir.</span><span class="sxs-lookup"><span data-stu-id="7aeaa-105">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>  
  
 <span data-ttu-id="7aeaa-106">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="7aeaa-106">\<configuration></span></span>  
<span data-ttu-id="7aeaa-107">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="7aeaa-107">\<system.diagnostics></span></span>  
<span data-ttu-id="7aeaa-108">\<sharedListeners ></span><span class="sxs-lookup"><span data-stu-id="7aeaa-108">\<sharedListeners></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7aeaa-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="7aeaa-109">Syntax</span></span>  
  
```xml  
<sharedListeners>   
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7aeaa-110">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="7aeaa-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7aeaa-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="7aeaa-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7aeaa-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="7aeaa-112">Attributes</span></span>  
 <span data-ttu-id="7aeaa-113">Yok.</span><span class="sxs-lookup"><span data-stu-id="7aeaa-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7aeaa-114">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="7aeaa-114">Child Elements</span></span>  
  
|<span data-ttu-id="7aeaa-115">Öğe</span><span class="sxs-lookup"><span data-stu-id="7aeaa-115">Element</span></span>|<span data-ttu-id="7aeaa-116">Açıklama</span><span class="sxs-lookup"><span data-stu-id="7aeaa-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7aeaa-117">\<Ekle ></span><span class="sxs-lookup"><span data-stu-id="7aeaa-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|<span data-ttu-id="7aeaa-118">Bir ekler `sharedListeners` koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="7aeaa-118">Adds a listener to the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7aeaa-119">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="7aeaa-119">Parent Elements</span></span>  
  
|<span data-ttu-id="7aeaa-120">Öğe</span><span class="sxs-lookup"><span data-stu-id="7aeaa-120">Element</span></span>|<span data-ttu-id="7aeaa-121">Açıklama</span><span class="sxs-lookup"><span data-stu-id="7aeaa-121">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="7aeaa-122">Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.</span><span class="sxs-lookup"><span data-stu-id="7aeaa-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="7aeaa-123">ASP.NET yapılandırma bölümü için olan kök öğesini belirtir.</span><span class="sxs-lookup"><span data-stu-id="7aeaa-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7aeaa-124">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="7aeaa-124">Remarks</span></span>  
 <span data-ttu-id="7aeaa-125">Paylaşılan dinleyici koleksiyonuna bir dinleyici etkin dinleyici yapmaz.</span><span class="sxs-lookup"><span data-stu-id="7aeaa-125">Adding a listener to the shared listeners collection does not make it an active listener.</span></span> <span data-ttu-id="7aeaa-126">Bunu hala bir izleme kaynağı veya bir izleme ekleyerek eklenmelidir `Listeners` izleme öğe için bir koleksiyon.</span><span class="sxs-lookup"><span data-stu-id="7aeaa-126">It must still be added to a trace source or a trace by adding it to the `Listeners` collection for that trace element.</span></span> <span data-ttu-id="7aeaa-127">.NET Framework'teki dinleyici sınıflar türetilen <xref:System.Diagnostics.TraceListener> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="7aeaa-127">The listener classes in the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="7aeaa-128">Bu öğe, makine yapılandırma dosyası (Machine.config) ve uygulama yapılandırma dosyasında kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="7aeaa-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7aeaa-129">Örnek</span><span class="sxs-lookup"><span data-stu-id="7aeaa-129">Example</span></span>  
 <span data-ttu-id="7aeaa-130">Aşağıdaki örnek nasıl kullanılacağını gösterir `<sharedListeners>` dinleyici eklemek için öğe `console` için `Listeners` hem de koleksiyonu <xref:System.Diagnostics.TraceSource> ve <xref:System.Diagnostics.Trace> sınıfları.</span><span class="sxs-lookup"><span data-stu-id="7aeaa-130">The following example shows how to use the `<sharedListeners>` element to add the listener `console` to the `Listeners` collection for both the <xref:System.Diagnostics.TraceSource> and <xref:System.Diagnostics.Trace> classes.</span></span> <span data-ttu-id="7aeaa-131">Konsol iz dinleyicisi izleme bilgilerini ya da yapılan çağrılar aracılığıyla konsola yazar. <xref:System.Diagnostics.TraceSource> veya <xref:System.Diagnostics.Trace>.</span><span class="sxs-lookup"><span data-stu-id="7aeaa-131">The console trace listener writes trace information to the console through calls to either <xref:System.Diagnostics.TraceSource> or <xref:System.Diagnostics.Trace>.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sharedListeners>  
      <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"  
          initializeData="Warning" />  
      </add>  
    </sharedListeners>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"  >  
        <listeners>  
          <add name="console" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Verbose"/>  
    </switches>  
    <trace>  
      <listeners>  
        <add name="console" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration></system.diagnostics>   
```  
  
## <a name="see-also"></a><span data-ttu-id="7aeaa-132">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="7aeaa-132">See also</span></span>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="7aeaa-133">İzleme ve Hata Ayıklama Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="7aeaa-133">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="7aeaa-134">İzleme Dinleyicileri</span><span class="sxs-lookup"><span data-stu-id="7aeaa-134">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
