---
title: <supportPortability> Öğesi
ms.date: 03/30/2017
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ab9feaa1c46a45471395fd4c6158490a24882a65
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489370"
---
# <a name="supportportability-element"></a><span data-ttu-id="81822-102">\<supportPortability > öğesi</span><span class="sxs-lookup"><span data-stu-id="81822-102">\<supportPortability> Element</span></span>
<span data-ttu-id="81822-103">Bir uygulama derlemeleri uygulama taşınabilirliği amacıyla eşdeğer kabul eder varsayılan davranışı devre dışı bırakarak aynı derlemenin iki farklı uygulamalarında .NET Framework'ün başvurabileceğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="81822-103">Specifies that an application can reference the same assembly in two different implementations of the .NET Framework, by disabling the default behavior that treats the assemblies as equivalent for application portability purposes.</span></span>  
  
 <span data-ttu-id="81822-104">\<Yapılandırma > öğesi</span><span class="sxs-lookup"><span data-stu-id="81822-104">\<configuration> Element</span></span>  
<span data-ttu-id="81822-105">\<çalışma zamanı > öğesi</span><span class="sxs-lookup"><span data-stu-id="81822-105">\<runtime> Element</span></span>  
<span data-ttu-id="81822-106">\<assemblyBinding > öğesi</span><span class="sxs-lookup"><span data-stu-id="81822-106">\<assemblyBinding> Element</span></span>  
<span data-ttu-id="81822-107">\<supportPortability > öğesi</span><span class="sxs-lookup"><span data-stu-id="81822-107">\<supportPortability> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81822-108">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="81822-108">Syntax</span></span>  
  
```xml  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81822-109">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="81822-109">Attributes and Elements</span></span>  
 <span data-ttu-id="81822-110">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="81822-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81822-111">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="81822-111">Attributes</span></span>  
  
|<span data-ttu-id="81822-112">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="81822-112">Attribute</span></span>|<span data-ttu-id="81822-113">Açıklama</span><span class="sxs-lookup"><span data-stu-id="81822-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="81822-114">PKT</span><span class="sxs-lookup"><span data-stu-id="81822-114">PKT</span></span>|<span data-ttu-id="81822-115">Gerekli öznitelik.</span><span class="sxs-lookup"><span data-stu-id="81822-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="81822-116">Etkilenen derlemenin genel anahtar belirtecini bir dize olarak belirtir.</span><span class="sxs-lookup"><span data-stu-id="81822-116">Specifies the public key token of the affected assembly, as a string.</span></span>|  
|<span data-ttu-id="81822-117">Etkin</span><span class="sxs-lookup"><span data-stu-id="81822-117">enabled</span></span>|<span data-ttu-id="81822-118">İsteğe bağlı öznitelik.</span><span class="sxs-lookup"><span data-stu-id="81822-118">Optional attribute.</span></span><br /><br /> <span data-ttu-id="81822-119">Belirtilen .NET Framework derlemesinin uygulamaları arasında taşınabilirlik desteğinin etkinleştirilip etkinleştirilmeyeceğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="81822-119">Specifies whether support for portability between implementations of the specified .NET Framework assembly should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="81822-120">etkin Öznitelik</span><span class="sxs-lookup"><span data-stu-id="81822-120">enabled Attribute</span></span>  
  
|<span data-ttu-id="81822-121">Değer</span><span class="sxs-lookup"><span data-stu-id="81822-121">Value</span></span>|<span data-ttu-id="81822-122">Açıklama</span><span class="sxs-lookup"><span data-stu-id="81822-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="81822-123">true</span><span class="sxs-lookup"><span data-stu-id="81822-123">true</span></span>|<span data-ttu-id="81822-124">Belirtilen .NET Framework derlemesinin uygulamaları arasındaki taşınabilir desteğini etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="81822-124">Enable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="81822-125">Bu varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="81822-125">This is the default.</span></span>|  
|<span data-ttu-id="81822-126">false</span><span class="sxs-lookup"><span data-stu-id="81822-126">false</span></span>|<span data-ttu-id="81822-127">Belirtilen .NET Framework derlemesinin uygulamaları arasındaki taşınabilir desteğini devre dışı bırakın.</span><span class="sxs-lookup"><span data-stu-id="81822-127">Disable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="81822-128">Bu, uygulamanın belirtilen derlemenin çoklu uygulamalarına başvurulara sahip olmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="81822-128">This enables the application to have references to multiple implementations of the specified assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="81822-129">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="81822-129">Child Elements</span></span>  
 <span data-ttu-id="81822-130">Yok.</span><span class="sxs-lookup"><span data-stu-id="81822-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="81822-131">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="81822-131">Parent Elements</span></span>  
  
|<span data-ttu-id="81822-132">Öğe</span><span class="sxs-lookup"><span data-stu-id="81822-132">Element</span></span>|<span data-ttu-id="81822-133">Açıklama</span><span class="sxs-lookup"><span data-stu-id="81822-133">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="81822-134">Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.</span><span class="sxs-lookup"><span data-stu-id="81822-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="81822-135">Derleme bağlama ve atık toplama hakkında bilgi içerir.</span><span class="sxs-lookup"><span data-stu-id="81822-135">Contains information about assembly binding and garbage collection.</span></span>|  
|`assemblyBinding`|<span data-ttu-id="81822-136">Derleme sürümü yeniden yönlendirmesi ve derlemelerin konumları hakkında bilgi içerir.</span><span class="sxs-lookup"><span data-stu-id="81822-136">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81822-137">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="81822-137">Remarks</span></span>  
 <span data-ttu-id="81822-138">.NET Framework 4 ile başlayarak, destek otomatik olarak .NET Framework'ün iki uygulamasından birini kullanan uygulamalar için sağlanan örnek ya da .NET Framework uygulaması veya Silverlight uygulaması için .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="81822-138">Beginning with the .NET Framework 4, support is automatically provided for applications that can use either of two implementations of the .NET Framework, for example either the .NET Framework implementation or the .NET Framework for Silverlight implementation.</span></span> <span data-ttu-id="81822-139">Belirli bir .NET Framework derlemesinin iki uygulaması derleme cildiyle eşdeğer olarak görülür.</span><span class="sxs-lookup"><span data-stu-id="81822-139">The two implementations of a particular .NET Framework assembly are seen as equivalent by the assembly binder.</span></span> <span data-ttu-id="81822-140">Birkaç senaryoda bu uygulama taşınabilirlik özelliği sorunlara neden olur.</span><span class="sxs-lookup"><span data-stu-id="81822-140">In a few scenarios, this application portability feature causes problems.</span></span> <span data-ttu-id="81822-141">Bu senaryolarda `<supportPortability>` öğesi özelliği devre dışı bırakmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="81822-141">In those scenarios, the `<supportPortability>` element can be used to disable the feature.</span></span>  
  
 <span data-ttu-id="81822-142">Bu tür senaryolardan hem .NET Framework uygulamasına hem de belirli bir başvuru derlemesinin Silverlight için .NET Framework başvurması gereken bir derlemedir.</span><span class="sxs-lookup"><span data-stu-id="81822-142">One such scenario is an assembly that has to reference both the .NET Framework implementation and the .NET Framework for Silverlight implementation of a particular reference assembly.</span></span> <span data-ttu-id="81822-143">Örneğin, Windows Presentation Foundation (WPF) yazılı bir XAML tasarımcının hem WPF masaüstü uygulaması için tasarımcının kullanıcı arabirimi ve Silverlight uygulamasında gelen WPF alt kümesi başvuru gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="81822-143">For example, a XAML designer written in Windows Presentation Foundation (WPF) might need to reference both the WPF Desktop implementation, for the designer's user interface, and the subset of WPF that is included in the Silverlight implementation.</span></span> <span data-ttu-id="81822-144">Varsayılan olarak, derleme bağlama iki derlemeyi eşdeğer olarak gördüğünden ayrı başvurular bir derleyici hatasına neden olur.</span><span class="sxs-lookup"><span data-stu-id="81822-144">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span> <span data-ttu-id="81822-145">Bu öğe, varsayılan davranışı devre dışı bırakır ve derlemenin başarılı olması sağlar.</span><span class="sxs-lookup"><span data-stu-id="81822-145">This element disables the default behavior, and allows compilation to succeed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="81822-146">Derleyicinin ortak dil çalışma zamanının derleme bağlama mantığına bilgi geçirmek için sırada kullanmalısınız `/appconfig` derleyici seçeneği, bu öğenin bulunduğu app.config dosyasının konumunu belirtmek için.</span><span class="sxs-lookup"><span data-stu-id="81822-146">In order for the compiler to pass the information to the common language runtime's assembly-binding logic, you must use the `/appconfig` compiler option to specify the location of the app.config file that contains this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81822-147">Örnek</span><span class="sxs-lookup"><span data-stu-id="81822-147">Example</span></span>  
 <span data-ttu-id="81822-148">Aşağıdaki örnek, bir uygulamanın hem .NET Framework uygulamasına hem de her iki uygulamada da bulunan herhangi bir .NET Framework derlemesinin Silverlight için .NET Framework başvuru olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="81822-148">The following example enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="81822-149">`/appconfig` Derleyici seçeneği, bu app.config dosyasının konumunu belirtmek için kullanılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="81822-149">The `/appconfig` compiler option must be used to specify the location of this app.config file.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding>  
         <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
         <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="81822-150">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="81822-150">See also</span></span>

- [<span data-ttu-id="81822-151">/ appConfig (C# Derleyici Seçenekleri)</span><span class="sxs-lookup"><span data-stu-id="81822-151">/appconfig (C# Compiler Options)</span></span>](../../../../../docs/csharp/language-reference/compiler-options/appconfig-compiler-option.md)
- <span data-ttu-id="81822-152">[.NET framework derleme birleştirmeye genel bakış](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="81822-152">[.NET Framework Assembly Unification Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))</span></span>
