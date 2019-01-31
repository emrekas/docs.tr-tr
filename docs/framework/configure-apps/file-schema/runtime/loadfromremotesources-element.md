---
title: <loadFromRemoteSources> Öğesi
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ebb32a74f5413f9c927a84ababf2d60d20e0b024
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269698"
---
# <a name="loadfromremotesources-element"></a><span data-ttu-id="402e9-102">\<loadFromRemoteSources > öğesi</span><span class="sxs-lookup"><span data-stu-id="402e9-102">\<loadFromRemoteSources> element</span></span>
<span data-ttu-id="402e9-103">Uzak kaynaklardan yüklenen derlemeler .NET Framework 4 ve daha sonra tam güven izni olup olmadığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="402e9-103">Specifies whether assemblies loaded from remote sources should be granted full trust in .NET Framework 4 and later.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="402e9-104">Bir hata iletisi Visual Studio projesi hata listesi veya bir yapı hatası nedeniyle bu konuya yönlendirildiniz olup [nasıl yapılır: Visual Studio'da bir bütünleştirilmiş kod Web'den kullanmak](https://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070).</span><span class="sxs-lookup"><span data-stu-id="402e9-104">If you were directed to this topic because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](https://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070).</span></span>  
  
 <span data-ttu-id="402e9-105">\<Yapılandırma ></span><span class="sxs-lookup"><span data-stu-id="402e9-105">\<configuration></span></span>  
<span data-ttu-id="402e9-106">\<çalışma zamanı ></span><span class="sxs-lookup"><span data-stu-id="402e9-106">\<runtime></span></span>  
<span data-ttu-id="402e9-107">\<loadFromRemoteSources ></span><span class="sxs-lookup"><span data-stu-id="402e9-107">\<loadFromRemoteSources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="402e9-108">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="402e9-108">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="402e9-109">Öznitelikler ve öğeler</span><span class="sxs-lookup"><span data-stu-id="402e9-109">Attributes and elements</span></span>
 <span data-ttu-id="402e9-110">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="402e9-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="402e9-111">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="402e9-111">Attributes</span></span>  
  
|<span data-ttu-id="402e9-112">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="402e9-112">Attribute</span></span>|<span data-ttu-id="402e9-113">Açıklama</span><span class="sxs-lookup"><span data-stu-id="402e9-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="402e9-114">Gerekli öznitelik.</span><span class="sxs-lookup"><span data-stu-id="402e9-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="402e9-115">Bir uzak kaynaktan yüklenen bir derlemeyi tam güven izni olup olmadığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="402e9-115">Specifies whether an assembly that is loaded from a remote source should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="402e9-116">Etkin öznitelik</span><span class="sxs-lookup"><span data-stu-id="402e9-116">enabled attribute</span></span>  
  
|<span data-ttu-id="402e9-117">Değer</span><span class="sxs-lookup"><span data-stu-id="402e9-117">Value</span></span>|<span data-ttu-id="402e9-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="402e9-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="402e9-119">Tam güven uzak kaynaklardan gelen uygulamalara vermeyin.</span><span class="sxs-lookup"><span data-stu-id="402e9-119">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="402e9-120">Bu varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="402e9-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="402e9-121">Tam güven uzak kaynaklardan gelen uygulamalara verin.</span><span class="sxs-lookup"><span data-stu-id="402e9-121">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="402e9-122">Alt öğeleri</span><span class="sxs-lookup"><span data-stu-id="402e9-122">Child elements</span></span>  
 <span data-ttu-id="402e9-123">Yok.</span><span class="sxs-lookup"><span data-stu-id="402e9-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="402e9-124">Üst öğeler</span><span class="sxs-lookup"><span data-stu-id="402e9-124">Parent elements</span></span>  
  
|<span data-ttu-id="402e9-125">Öğe</span><span class="sxs-lookup"><span data-stu-id="402e9-125">Element</span></span>|<span data-ttu-id="402e9-126">Açıklama</span><span class="sxs-lookup"><span data-stu-id="402e9-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="402e9-127">Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.</span><span class="sxs-lookup"><span data-stu-id="402e9-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="402e9-128">Çalışma zamanı başlatma seçenekleri hakkında bilgi içerir.</span><span class="sxs-lookup"><span data-stu-id="402e9-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="402e9-129">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="402e9-129">Remarks</span></span>

<span data-ttu-id="402e9-130">Uzak bir konumdan bir derlemeyi yüklemek, .NET Framework 3.5 ve önceki sürümlerinde derleme içindeki kod kısmi güven, yüklendiği bölgesine bağlıdır bir izin kümesi ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="402e9-130">In the .NET Framework 3.5 and earlier versions, if you load an assembly from a remote location, code in the assembly runs in partial trust with a grant set that depends on the zone from which it is loaded.</span></span> <span data-ttu-id="402e9-131">Örneğin, bir Web sitesinden bir derlemeyi yüklemek, bu Internet bölgesine yüklendi ve Internet izni verildi.</span><span class="sxs-lookup"><span data-stu-id="402e9-131">For example, if you load an assembly from a website, it is loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="402e9-132">Diğer bir deyişle, bir Internet korumalı alan içinde yürütülür.</span><span class="sxs-lookup"><span data-stu-id="402e9-132">In other words, it executes in an Internet sandbox.</span></span>

<span data-ttu-id="402e9-133">.NET Framework 4 ile başlayarak, kod erişimi güvenliği (CAS) ilkesi devre dışı bırakıldı ve derlemeleri tam güven yüklenir.</span><span class="sxs-lookup"><span data-stu-id="402e9-133">Starting with the .NET Framework 4, code access security (CAS) policy is disabled and assemblies are loaded in full trust.</span></span> <span data-ttu-id="402e9-134">Normalde, bu tam güven ile yüklenen derlemeler vermek <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> önceden korumalı olan yöntem.</span><span class="sxs-lookup"><span data-stu-id="402e9-134">Ordinarily, this would grant full trust to assemblies loaded with the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method that previously had been sandboxed.</span></span> <span data-ttu-id="402e9-135">Bunu önlemek için bir uzak kaynaktan yüklü bütünleştirilmiş kodu çalıştırma olanağı varsayılan olarak devre dışıdır.</span><span class="sxs-lookup"><span data-stu-id="402e9-135">To prevent this, the ability to run code in assemblies loaded from a remote source is disabled by default.</span></span> <span data-ttu-id="402e9-136">Varsayılan olarak uzak bir derlemeyi yüklemeye çalışırsanız, bir <xref:System.IO.FileLoadException> ile aşağıdaki durum gibi bir özel durum iletisi:</span><span class="sxs-lookup"><span data-stu-id="402e9-136">By default, if you attempt to load a remote assembly, a <xref:System.IO.FileLoadException> with an exception message like the following is thrown:</span></span>

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported. 
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' ---> 
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly 
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default, 
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch. 
```

<span data-ttu-id="402e9-137">Derlemeyi yüklemek ve kendi kod yürütmek için aşağıdakilerden birini yapmanız gerekir:</span><span class="sxs-lookup"><span data-stu-id="402e9-137">To load the assembly and execute its code, you must either:</span></span>

- <span data-ttu-id="402e9-138">Açıkça bir korumalı alan için derleme oluşturma (bkz [nasıl yapılır: Korumalı alanda kısmen güvenilen kodu çalıştırma](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span><span class="sxs-lookup"><span data-stu-id="402e9-138">Explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span></span>

- <span data-ttu-id="402e9-139">Derlemenin kod tam güvende çalıştırma.</span><span class="sxs-lookup"><span data-stu-id="402e9-139">Run the assembly's code in full trust.</span></span> <span data-ttu-id="402e9-140">Yapılandırarak bunu `<loadFromRemoteSources>` öğesi.</span><span class="sxs-lookup"><span data-stu-id="402e9-140">You do this by configuring the `<loadFromRemoteSources>` element.</span></span> <span data-ttu-id="402e9-141">.NET Framework'ün önceki sürümlerindeki kısmi güvende çalışan derlemeler artık .NET Framework 4 ve sonraki sürümlerde tam güven içinde çalıştığını belirtmenize olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="402e9-141">It lets you specify that the assemblies that run in partial trust in earlier versions of the .NET Framework now run in full trust in the .NET Framework 4 and later versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="402e9-142">Bütünleştirilmiş kod tam güvende çalıştırılmayacaksa, bu yapılandırma öğesi ayarlamayın.</span><span class="sxs-lookup"><span data-stu-id="402e9-142">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="402e9-143">Bunun yerine, bir korumalı alan oluşturma <xref:System.AppDomain> hangi derlemesi yüklenemiyor.</span><span class="sxs-lookup"><span data-stu-id="402e9-143">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>

<span data-ttu-id="402e9-144">`enabled` Özniteliğini `<loadFromRemoteSources>` öğedir etkili yalnızca zaman kod erişimi güvenliği (CAS) devre dışı bırakılır.</span><span class="sxs-lookup"><span data-stu-id="402e9-144">The `enabled` attribute for the `<loadFromRemoteSources>` element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="402e9-145">Varsayılan olarak, .NET Framework 4 ve sonraki sürümlerinde, CAS ilkesini devre dışıdır.</span><span class="sxs-lookup"><span data-stu-id="402e9-145">By default, CAS policy is disabled in the .NET Framework 4 and later versions.</span></span> <span data-ttu-id="402e9-146">Ayarlarsanız `enabled` için `true`, uzak derlemeleri tam güven izni.</span><span class="sxs-lookup"><span data-stu-id="402e9-146">If you set `enabled` to `true`, remote assemblies are granted full trust.</span></span>

<span data-ttu-id="402e9-147">Varsa `enabled` ayarlı değil `true`, <xref:System.IO.FileLoadException> aşağıdaki durumlardan herhangi biri altında oluşturulur:</span><span class="sxs-lookup"><span data-stu-id="402e9-147">If `enabled` is not set to `true`, a <xref:System.IO.FileLoadException> is thrown under the either of the following conditions:</span></span>

- <span data-ttu-id="402e9-148">Geçerli etki alanı korumalı alana alma davranışını, .NET Framework 3.5, davranışı farklıdır.</span><span class="sxs-lookup"><span data-stu-id="402e9-148">The sandboxing behavior of the current domain is different from its behavior in the .NET Framework 3.5.</span></span> <span data-ttu-id="402e9-149">Bu, CAS ilkesini devre dışı bırakılması ve korumalı olmaması için geçerli etki alanı gerektirir.</span><span class="sxs-lookup"><span data-stu-id="402e9-149">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>

- <span data-ttu-id="402e9-150">Yüklenen derleme gelen değil `MyComputer` bölge.</span><span class="sxs-lookup"><span data-stu-id="402e9-150">The assembly being loaded is not from the `MyComputer` zone.</span></span>

<span data-ttu-id="402e9-151">Ayarı `<loadFromRemoteSources>` öğesine `true` öğesinden oluşturulan bu özel durumu önler.</span><span class="sxs-lookup"><span data-stu-id="402e9-151">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="402e9-152">Ortak dil çalışma zamanı için korumalı alan yüklenen derlemeler için güvenlik bağlı değil, belirtmenizi sağlar ve bunlar içinde yürütülen olmasına izin, tam güven.</span><span class="sxs-lookup"><span data-stu-id="402e9-152">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute in full trust.</span></span>

## <a name="notes"></a><span data-ttu-id="402e9-153">Notlar</span><span class="sxs-lookup"><span data-stu-id="402e9-153">Notes</span></span>

- <span data-ttu-id="402e9-154">.NET Framework 4.5 ve sonraki sürümlerinde, yerel ağ paylaşımlarında derlemeleri tam güven varsayılan olarak çalıştırın; etkinleştirme gerekmez `<loadFromRemoteSources>` öğesi.</span><span class="sxs-lookup"><span data-stu-id="402e9-154">In the .NET Framework 4.5 and later versions, assemblies on local network shares run in full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>

- <span data-ttu-id="402e9-155">Bir uygulamanın Web'den kopyalandı, yerel bilgisayarda bulunsa bile, Windows tarafından bir web uygulaması olacak şekilde işaretlenir.</span><span class="sxs-lookup"><span data-stu-id="402e9-155">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="402e9-156">Dosya özelliklerini değiştirerek bu ataması değiştirebilir veya kullanabileceğiniz `<loadFromRemoteSources>` öğesi derlemeyi vermek için tam güven.</span><span class="sxs-lookup"><span data-stu-id="402e9-156">You can change that designation by changing its file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="402e9-157">Alternatif olarak, kullandığınız <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> yöntemi işletim sistemi Web'den yüklenmiş olan olarak işaretlenmiş bir yerel derlemesi yüklenemiyor.</span><span class="sxs-lookup"><span data-stu-id="402e9-157">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>

- <span data-ttu-id="402e9-158">Alabilirsiniz bir <xref:System.IO.FileLoadException> bir Windows Virtual PC uygulama içinde çalışan bir uygulamada.</span><span class="sxs-lookup"><span data-stu-id="402e9-158">You may get a <xref:System.IO.FileLoadException> in an application that is running in a Windows Virtual PC application.</span></span> <span data-ttu-id="402e9-159">Bağlantılı klasörlerden barındıran bilgisayarda bir dosya yüklemeye çalıştığınızda bu durum oluşabilir.</span><span class="sxs-lookup"><span data-stu-id="402e9-159">This can happen when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="402e9-160">Ayrıca üzerinden bağlı bir klasörden bir dosya yüklemeye çalıştığınızda oluşabilir [Uzak Masaüstü Hizmetleri](https://go.microsoft.com/fwlink/?LinkId=182775) (Terminal Hizmetleri).</span><span class="sxs-lookup"><span data-stu-id="402e9-160">It can also occur when you try to load a file from a folder linked over [Remote Desktop Services](https://go.microsoft.com/fwlink/?LinkId=182775) (Terminal Services).</span></span> <span data-ttu-id="402e9-161">Özel durumdan kaçınmak için ayarlanmış `enabled` için `true`.</span><span class="sxs-lookup"><span data-stu-id="402e9-161">To avoid the exception, set `enabled` to `true`.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="402e9-162">Yapılandırma dosyası</span><span class="sxs-lookup"><span data-stu-id="402e9-162">Configuration file</span></span>

<span data-ttu-id="402e9-163">Bu öğe uygulama yapılandırma dosyasında genellikle kullanılır, ancak diğer yapılandırma dosyalarını bağlam bağlı olarak kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="402e9-163">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="402e9-164">Daha fazla bilgi için bkz [daha fazla örtük kullanır, CAS ilkesini: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839) .NET güvenliği blogundaki.</span><span class="sxs-lookup"><span data-stu-id="402e9-164">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839) in the .NET Security blog.</span></span>  

## <a name="example"></a><span data-ttu-id="402e9-165">Örnek</span><span class="sxs-lookup"><span data-stu-id="402e9-165">Example</span></span>

<span data-ttu-id="402e9-166">Aşağıdaki örnek, uzak kaynaklardan yüklenen derlemeleri tam güven vermek gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="402e9-166">The following example shows how to grant full trust to assemblies loaded from remote sources.</span></span>

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a><span data-ttu-id="402e9-167">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="402e9-167">See also</span></span>

- [<span data-ttu-id="402e9-168">CAS ilkesini daha örtük kullanır: loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="402e9-168">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=266839)
- [<span data-ttu-id="402e9-169">Nasıl yapılır: Korumalı alanda kısmen güvenilen kodu çalıştırma</span><span class="sxs-lookup"><span data-stu-id="402e9-169">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="402e9-170">Çalışma Zamanı Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="402e9-170">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="402e9-171">Yapılandırma Dosyası Şeması</span><span class="sxs-lookup"><span data-stu-id="402e9-171">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
