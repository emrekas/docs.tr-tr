---
title: '&lt;kod tabanı&gt; öğesi'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase
helpviewer_keywords:
- <codeBase> element
- container tags, <codeBase> element
- codeBase element
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 295b2c5dd3eb17ca9ba19e52d9f8e51cf108162d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54683157"
---
# <a name="ltcodebasegt-element"></a><span data-ttu-id="36f57-102">&lt;kod tabanı&gt; öğesi</span><span class="sxs-lookup"><span data-stu-id="36f57-102">&lt;codeBase&gt; Element</span></span>
<span data-ttu-id="36f57-103">Ortak dil çalışma zamanının bir derlemeyi nerede belirtir.</span><span class="sxs-lookup"><span data-stu-id="36f57-103">Specifies where the common language runtime can find an assembly.</span></span>  
  
 <span data-ttu-id="36f57-104">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="36f57-104">\<configuration></span></span>  
<span data-ttu-id="36f57-105">\<çalışma zamanı ></span><span class="sxs-lookup"><span data-stu-id="36f57-105">\<runtime></span></span>  
<span data-ttu-id="36f57-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="36f57-106">\<assemblyBinding></span></span>  
<span data-ttu-id="36f57-107">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="36f57-107">\<dependentAssembly></span></span>  
<span data-ttu-id="36f57-108">\<codeBase ></span><span class="sxs-lookup"><span data-stu-id="36f57-108">\<codeBase></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36f57-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="36f57-109">Syntax</span></span>  
  
```xml  
   <codeBase    
version="Assembly version"  
href="URL of assembly"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36f57-110">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="36f57-110">Attributes and Elements</span></span>  
 <span data-ttu-id="36f57-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="36f57-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36f57-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="36f57-112">Attributes</span></span>  
  
|<span data-ttu-id="36f57-113">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="36f57-113">Attribute</span></span>|<span data-ttu-id="36f57-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="36f57-114">Description</span></span>|  
|---------------|-----------------|  
|`href`|<span data-ttu-id="36f57-115">Gerekli öznitelik.</span><span class="sxs-lookup"><span data-stu-id="36f57-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="36f57-116">Çalışma zamanı derlemenin belirtilen sürümü nereden URL'sini belirtir.</span><span class="sxs-lookup"><span data-stu-id="36f57-116">Specifies the URL where the runtime can find the specified version of the assembly.</span></span>|  
|`version`|<span data-ttu-id="36f57-117">Gerekli öznitelik.</span><span class="sxs-lookup"><span data-stu-id="36f57-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="36f57-118">Kod temeli uygulandığı derleme sürümünü belirtir.</span><span class="sxs-lookup"><span data-stu-id="36f57-118">Specifies the version of the assembly the codebase applies to.</span></span> <span data-ttu-id="36f57-119">Bir derleme sürümü numarasının biçimi *major.minor.build.revision*.</span><span class="sxs-lookup"><span data-stu-id="36f57-119">The format of an assembly version number is *major.minor.build.revision*.</span></span>|  
  
## <a name="version-attribute"></a><span data-ttu-id="36f57-120">Sürüm özniteliği</span><span class="sxs-lookup"><span data-stu-id="36f57-120">version Attribute</span></span>  
  
|<span data-ttu-id="36f57-121">Değer</span><span class="sxs-lookup"><span data-stu-id="36f57-121">Value</span></span>|<span data-ttu-id="36f57-122">Açıklama</span><span class="sxs-lookup"><span data-stu-id="36f57-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="36f57-123">Sürüm numarasının her bölüm için geçerli değerler 0 ile 65535 arasındadır.</span><span class="sxs-lookup"><span data-stu-id="36f57-123">Valid values for each part of the version number are 0 to 65535.</span></span>|<span data-ttu-id="36f57-124">Uygulanamaz.</span><span class="sxs-lookup"><span data-stu-id="36f57-124">Not applicable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="36f57-125">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="36f57-125">Child Elements</span></span>  
 <span data-ttu-id="36f57-126">Yok.</span><span class="sxs-lookup"><span data-stu-id="36f57-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="36f57-127">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="36f57-127">Parent Elements</span></span>  
  
|<span data-ttu-id="36f57-128">Öğe</span><span class="sxs-lookup"><span data-stu-id="36f57-128">Element</span></span>|<span data-ttu-id="36f57-129">Açıklama</span><span class="sxs-lookup"><span data-stu-id="36f57-129">Description</span></span>|  
|-------------|-----------------|  
|`buildproviders`|<span data-ttu-id="36f57-130">Özel kaynak dosyalarını derlemek için kullanılan derleme sağlayıcıları koleksiyonu tanımlar.</span><span class="sxs-lookup"><span data-stu-id="36f57-130">Defines a collection of build providers used to compile custom resource files.</span></span> <span data-ttu-id="36f57-131">Herhangi bir sayıda derleme sağlayıcıları olabilir.</span><span class="sxs-lookup"><span data-stu-id="36f57-131">You can have any number of build providers.</span></span>|  
|`compilation`|<span data-ttu-id="36f57-132">ASP.NET kullanan tüm derleme ayarlarını yapılandırır.</span><span class="sxs-lookup"><span data-stu-id="36f57-132">Configures all the compilation settings that ASP.NET uses.</span></span>|  
|`configuration`|<span data-ttu-id="36f57-133">Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.</span><span class="sxs-lookup"><span data-stu-id="36f57-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.web`|<span data-ttu-id="36f57-134">ASP.NET yapılandırma bölümü için olan kök öğesini belirtir.</span><span class="sxs-lookup"><span data-stu-id="36f57-134">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36f57-135">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="36f57-135">Remarks</span></span>  
 <span data-ttu-id="36f57-136">Çalışma zamanı kullanmak için  **\<codeBase >** bir makine yapılandırma dosyası ya da Yayımcı ilkesi dosyası ayarı dosyası da derleme sürümünü yeniden yönlendirmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="36f57-136">For the runtime to use the **\<codeBase>** setting in a machine configuration file or publisher policy file, the file must also redirect the assembly version.</span></span> <span data-ttu-id="36f57-137">Uygulama yapılandırma dosyaları, derleme sürümü yeniden yönlendirme olmadan bir kod temeli ayarı olabilir.</span><span class="sxs-lookup"><span data-stu-id="36f57-137">Application configuration files can have a codebase setting without redirecting the assembly version.</span></span> <span data-ttu-id="36f57-138">Hangi derleme sürümünün kullanılacağını belirledikten sonra çalışma zamanı sürümünü belirleyen dosyasından codebase ayarı uygulanır.</span><span class="sxs-lookup"><span data-stu-id="36f57-138">After determining which assembly version to use, the runtime applies the codebase setting from the file that determines the version.</span></span> <span data-ttu-id="36f57-139">Herhangi bir kod temelinde belirtilirse, çalışma zamanı derlemesi için her zamanki yolla araştırmaları.</span><span class="sxs-lookup"><span data-stu-id="36f57-139">If no codebase is indicated, the runtime probes for the assembly in the usual way.</span></span>  
  
 <span data-ttu-id="36f57-140">Derlemeyi tanımlayıcı bir ada sahip, codebase ayar herhangi bir yerel intranet veya Internet üzerinde olabilir.</span><span class="sxs-lookup"><span data-stu-id="36f57-140">If the assembly has a strong name, the codebase setting can be anywhere on the local intranet or the Internet.</span></span> <span data-ttu-id="36f57-141">Derleme özel bir derleme ise, kod tabanının ayarı uygulamanın dizinine göreli bir yol olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="36f57-141">If the assembly is a private assembly, the codebase setting must be a path relative to the application's directory.</span></span>  
  
 <span data-ttu-id="36f57-142">Güçlü adı olmayan derlemeler için sürüm göz ardı edilir ve ilk görünümünü yükleyicisi kullanır \<codebase > içinde \<dependentAssembly >.</span><span class="sxs-lookup"><span data-stu-id="36f57-142">For assemblies without a strong name, version is ignored and the loader uses the first appearance of \<codebase> inside \<dependentAssembly>.</span></span> <span data-ttu-id="36f57-143">Başka bir derleme için bağlama yeniden yönlendirmeleri uygulama yapılandırma dosyasında bir girdi varsa, bağlama isteği derleme sürümü eşleşmiyor olsa bile yönlendirme öncelikli olur.</span><span class="sxs-lookup"><span data-stu-id="36f57-143">If there is an entry in the application configuration file that redirects binding to another assembly, the redirection will take precedence even if the assembly version doesnt match the binding request.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36f57-144">Örnek</span><span class="sxs-lookup"><span data-stu-id="36f57-144">Example</span></span>  
 <span data-ttu-id="36f57-145">Aşağıdaki örnek, çalışma zamanının bir derlemeyi nerede belirtmek gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="36f57-145">The following example shows how to specify where the runtime can find an assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="36f57-146">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="36f57-146">See also</span></span>
- [<span data-ttu-id="36f57-147">Çalışma Zamanı Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="36f57-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="36f57-148">Yapılandırma Dosyası Şeması</span><span class="sxs-lookup"><span data-stu-id="36f57-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="36f57-149">Bütünleştirilmiş Kodun Konumunu Belirtme</span><span class="sxs-lookup"><span data-stu-id="36f57-149">Specifying an Assembly's Location</span></span>](../../../../../docs/framework/configure-apps/specify-assembly-location.md)
- [<span data-ttu-id="36f57-150">Çalışma Zamanının Bütünleştirilmiş Kodların Konumunu Bulması</span><span class="sxs-lookup"><span data-stu-id="36f57-150">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
