---
title: <assert> Öğesi
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assert
helpviewer_keywords:
- <assert> element
- assert element
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
ms.openlocfilehash: aa5682c1cb2d662e1352c1d6c78e1a4a7e41f760
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55259525"
---
# <a name="assert-element"></a><span data-ttu-id="af04b-102">\<Assert > öğesi</span><span class="sxs-lookup"><span data-stu-id="af04b-102">\<assert> Element</span></span>
<span data-ttu-id="af04b-103">Bir ileti kutusu çağırdığınızda görüntülenip görüntülenmeyeceğini belirtir <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> yöntemi de ileti yazmak için dosya adını belirtir.</span><span class="sxs-lookup"><span data-stu-id="af04b-103">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>  
  
 <span data-ttu-id="af04b-104">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="af04b-104">\<configuration></span></span>  
<span data-ttu-id="af04b-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="af04b-105">\<system.diagnostics></span></span>  
<span data-ttu-id="af04b-106">\<Assert ></span><span class="sxs-lookup"><span data-stu-id="af04b-106">\<assert></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af04b-107">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="af04b-107">Syntax</span></span>  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af04b-108">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="af04b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="af04b-109">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="af04b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af04b-110">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="af04b-110">Attributes</span></span>  
  
|<span data-ttu-id="af04b-111">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="af04b-111">Attribute</span></span>|<span data-ttu-id="af04b-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="af04b-112">Description</span></span>|  
|---------------|-----------------|  
|`assertuienabled`|<span data-ttu-id="af04b-113">İsteğe bağlı öznitelik.</span><span class="sxs-lookup"><span data-stu-id="af04b-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="af04b-114">Görüntülenecek bir ileti kutusunu olup olmadığını belirtir **Debug.Assert** yöntemi değerlendirilen **false**.</span><span class="sxs-lookup"><span data-stu-id="af04b-114">Specifies whether to display a message box when the **Debug.Assert** method evaluates to **false**.</span></span>|  
|`logfilename`|<span data-ttu-id="af04b-115">İsteğe bağlı öznitelik.</span><span class="sxs-lookup"><span data-stu-id="af04b-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="af04b-116">Eğer ileti yazmak için dosya adını belirtir **Debug.Assert** değerlendiren **false**.</span><span class="sxs-lookup"><span data-stu-id="af04b-116">Specifies the name of the file to write the message to if **Debug.Assert** evaluates to **false**.</span></span>|  
  
## <a name="assertuienabled-attribute"></a><span data-ttu-id="af04b-117">assertuienabled özniteliği</span><span class="sxs-lookup"><span data-stu-id="af04b-117">assertuienabled Attribute</span></span>  
  
|<span data-ttu-id="af04b-118">Değer</span><span class="sxs-lookup"><span data-stu-id="af04b-118">Value</span></span>|<span data-ttu-id="af04b-119">Açıklama</span><span class="sxs-lookup"><span data-stu-id="af04b-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="af04b-120">İleti kutusu görüntüler.</span><span class="sxs-lookup"><span data-stu-id="af04b-120">Displays the message box.</span></span> <span data-ttu-id="af04b-121">Bu varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="af04b-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="af04b-122">İleti kutusu görüntülemez.</span><span class="sxs-lookup"><span data-stu-id="af04b-122">Does not display the message box.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af04b-123">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="af04b-123">Child Elements</span></span>  
 <span data-ttu-id="af04b-124">Yok.</span><span class="sxs-lookup"><span data-stu-id="af04b-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="af04b-125">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="af04b-125">Parent Elements</span></span>  
  
|<span data-ttu-id="af04b-126">Öğe</span><span class="sxs-lookup"><span data-stu-id="af04b-126">Element</span></span>|<span data-ttu-id="af04b-127">Açıklama</span><span class="sxs-lookup"><span data-stu-id="af04b-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="af04b-128">Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.</span><span class="sxs-lookup"><span data-stu-id="af04b-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="af04b-129">Toplamak, depolamak ve iletileri ve bir izleme anahtarı ayarlandığı düzeyi izleme dinleyicilerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="af04b-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af04b-130">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="af04b-130">Remarks</span></span>  
 <span data-ttu-id="af04b-131">Her iki öznitelikleri  **\<assert >** öğe isteğe bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="af04b-131">Both attributes in the **\<assert>** element are optional.</span></span> <span data-ttu-id="af04b-132">İleti yazmak için bir dosya belirtmeden ileti kutularını devre dışı bırakabilir veya ileti kutuları etkin bırakılması while iletiler yazmak için bir dosya belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="af04b-132">You can disable message boxes without specifying a file to write the messages to, or you can specify a file to write messages to while leaving message boxes enabled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af04b-133">Örnek</span><span class="sxs-lookup"><span data-stu-id="af04b-133">Example</span></span>  
 <span data-ttu-id="af04b-134">Aşağıdaki örnek, ileti kutularını görüntüleme çağırdığınızda devre dışı bırakmak gösterilmektedir **Debug.Assert** ve iletileri yazma `c:\log.txt`.</span><span class="sxs-lookup"><span data-stu-id="af04b-134">The following example shows how to disable displaying message boxes when you call **Debug.Assert** and write the messages to `c:\log.txt`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="af04b-135">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="af04b-135">See also</span></span>
- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="af04b-136">İzleme ve Hata Ayıklama Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="af04b-136">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
