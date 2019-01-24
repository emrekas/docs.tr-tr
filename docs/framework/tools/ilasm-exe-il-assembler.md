---
title: Ilasm.exe (IL Derleyici)
ms.date: 03/30/2017
helpviewer_keywords:
- MSIL generators
- metadata, MSIL Assembler
- MSIL Assembler
- portable executable files, MSIL Assembler
- PE files, MSIL Assembler
- MSIL
- Ilasm.exe
- verifying MSIL performance
ms.assetid: 4ca3a4f0-4400-47ce-8936-8e219961c76f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f043fa541073402bee9fc4cf84e8151e6e0192f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549216"
---
# <a name="ilasmexe-il-assembler"></a><span data-ttu-id="c6d3f-102">Ilasm.exe (IL Derleyici)</span><span class="sxs-lookup"><span data-stu-id="c6d3f-102">Ilasm.exe (IL Assembler)</span></span>

<span data-ttu-id="c6d3f-103">IL Derleyicisi ara dil'den (IL) taşınabilir çalıştırılabilir bir (PE) dosya oluşturur.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-103">The IL Assembler generates a portable executable (PE) file from intermediate language (IL).</span></span> <span data-ttu-id="c6d3f-104">(IL hakkında daha fazla bilgi için bkz. [Managed Execution Process](../../../docs/standard/managed-execution-process.md).) IL ve gereken meta veriyi içeren elde edilen çalıştırılabilir dosyayı çalıştırarak IL'in beklendiği gibi çalışıp çalışmadığını belirleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-104">(For more information on IL, see [Managed Execution Process](../../../docs/standard/managed-execution-process.md).) You can run the resulting executable, which contains IL and the required metadata, to determine whether the IL performs as expected.</span></span>

<span data-ttu-id="c6d3f-105">Bu araç, Visual Studio ile birlikte otomatik olarak yüklenir.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-105">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="c6d3f-106">Aracı çalıştırmak için Visual Studio (veya Windows 7'de Visual Studio komut istemi) için geliştirici Komut İstemi'ni kullanın.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-106">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="c6d3f-107">Daha fazla bilgi için [komut istemleri](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="c6d3f-107">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="c6d3f-108">Komut satırına şunu yazın:</span><span class="sxs-lookup"><span data-stu-id="c6d3f-108">At the command prompt, type the following:</span></span>

## <a name="syntax"></a><span data-ttu-id="c6d3f-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="c6d3f-109">Syntax</span></span>

```console
ilasm [options] filename [[options]filename...]
```

#### <a name="parameters"></a><span data-ttu-id="c6d3f-110">Parametreler</span><span class="sxs-lookup"><span data-stu-id="c6d3f-110">Parameters</span></span>

| <span data-ttu-id="c6d3f-111">Bağımsız Değişken</span><span class="sxs-lookup"><span data-stu-id="c6d3f-111">Argument</span></span> | <span data-ttu-id="c6d3f-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="c6d3f-112">Description</span></span> |
| -------- | ----------- |
|`filename`|<span data-ttu-id="c6d3f-113">.il kaynak dosyasının adı.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-113">The name of the .il source file.</span></span> <span data-ttu-id="c6d3f-114">Bu dosya meta veri bildirim yönergeleri ve simgesel IL yönergelerinden oluşur.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-114">This file consists of metadata declaration directives and symbolic IL instructions.</span></span> <span data-ttu-id="c6d3f-115">Birden çok kaynak dosya bağımsız değişkeni ile tek bir PE dosyası oluşturmak için sağlanan *Ilasm.exe*.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-115">Multiple source file arguments can be supplied to produce a single PE file with *Ilasm.exe*.</span></span> <span data-ttu-id="c6d3f-116">**Not:** .il kaynak dosyasındaki son kod satırının bir boşluk karakteri veya satır sonu karakteri olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-116">**Note:** Ensure that the last line of code in the .il source file has either trailing white space or an end-of-line character.</span></span>|

| <span data-ttu-id="c6d3f-117">Seçenek</span><span class="sxs-lookup"><span data-stu-id="c6d3f-117">Option</span></span> | <span data-ttu-id="c6d3f-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="c6d3f-118">Description</span></span> |
| ------ | ----------- |
|<span data-ttu-id="c6d3f-119">**/32bitpreferred**</span><span class="sxs-lookup"><span data-stu-id="c6d3f-119">**/32bitpreferred**</span></span>|<span data-ttu-id="c6d3f-120">32 bit tercih edilen bir görüntü (PE32) oluşturur.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-120">Creates a 32-bit-preferred image (PE32).</span></span>|
|<span data-ttu-id="c6d3f-121">**/ alignment:** `integer`</span><span class="sxs-lookup"><span data-stu-id="c6d3f-121">**/alignment:** `integer`</span></span>|<span data-ttu-id="c6d3f-122">Filealignment değerini tarafından belirtilen değere ayarlar `integer` NT isteğe bağlı üst bilgisindeki.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-122">Sets FileAlignment to the value specified by `integer` in the NT Optional header.</span></span> <span data-ttu-id="c6d3f-123">Eğer .alignment IL yönergesi dosyada belirtiliyorsa, bu seçenek onu geçersiz kılar.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-123">If the .alignment IL directive is specified in the file, this option overrides it.</span></span>|
|<span data-ttu-id="c6d3f-124">**/ appcontaıner**</span><span class="sxs-lookup"><span data-stu-id="c6d3f-124">**/appcontainer**</span></span>|<span data-ttu-id="c6d3f-125">Üreten bir *.dll* veya *.exe* çıktı olarak Windows uygulama kapsayıcısında çalışan dosya.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-125">Produces a *.dll* or *.exe* file that runs in the Windows app container, as output.</span></span>|
|<span data-ttu-id="c6d3f-126">**/ARM**</span><span class="sxs-lookup"><span data-stu-id="c6d3f-126">**/arm**</span></span>|<span data-ttu-id="c6d3f-127">Hedef işlemci olarak Gelişmiş RISC Makinesi (ARM) belirtir.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-127">Specifies the Advanced RISC Machine (ARM) as the target processor.</span></span><br /><br /> <span data-ttu-id="c6d3f-128">Eğer görüntü bit genişliği belirtilmezse, varsayılan değer **/32bitpreferred**.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-128">If no image bitness is specified, the default is **/32bitpreferred**.</span></span>|
|<span data-ttu-id="c6d3f-129">**/ Base:** `integer`</span><span class="sxs-lookup"><span data-stu-id="c6d3f-129">**/base:** `integer`</span></span>|<span data-ttu-id="c6d3f-130">ImageBase tarafından belirtilen değere ayarlar `integer` NT isteğe bağlı üst bilgisindeki.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-130">Sets ImageBase to the value specified by `integer` in the NT Optional header.</span></span> <span data-ttu-id="c6d3f-131">Eğer .imagebase IL yönergesi dosyada belirtiliyorsa, bu seçenek onu geçersiz kılar.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-131">If the .imagebase IL directive is specified in the file, this option overrides it.</span></span>|
|<span data-ttu-id="c6d3f-132">**/Clock**</span><span class="sxs-lookup"><span data-stu-id="c6d3f-132">**/clock**</span></span>|<span data-ttu-id="c6d3f-133">Belirtilen .il kaynak dosyası için aşağıdaki derleme sürelerini milisaniye cinsinden ölçer ve raporlar:</span><span class="sxs-lookup"><span data-stu-id="c6d3f-133">Measures and reports the following compilation times in milliseconds for the specified .il source file:</span></span><br /><br /> <span data-ttu-id="c6d3f-134">**Toplam çalışma**: İzleyen tüm belirli görevleri gerçekleştirirken geçen toplam süre.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-134">**Total Run**: The total time spent performing all the specific operations that follow.</span></span><br /><br /> <span data-ttu-id="c6d3f-135">**Başlangıç**: Yükleme ve dosya açma.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-135">**Startup**: Loading and opening the file.</span></span><br /><br /> <span data-ttu-id="c6d3f-136">**MD yayma**: Meta veriyi yaymak.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-136">**Emitting MD**: Emitting metadata.</span></span><br /><br /> <span data-ttu-id="c6d3f-137">**Ref Def çözümleme**: Başvuruları dosyadaki tanımlara çözümlemek.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-137">**Ref to Def Resolution**: Resolving references to definitions in the file.</span></span><br /><br /> <span data-ttu-id="c6d3f-138">**CEE dosya oluşturma**: Bellekte dosya görüntüsünü oluşturuluyor.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-138">**CEE File Generation**: Generating the file image in memory.</span></span><br /><br /> <span data-ttu-id="c6d3f-139">**PE dosyası yazma**: Görüntüyü bir PE dosyasına yazmak.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-139">**PE File Writing**: Writing the image to a PE file.</span></span>|
|<span data-ttu-id="c6d3f-140">**/ debug**[:**IMPL**&#124;**OPT**]</span><span class="sxs-lookup"><span data-stu-id="c6d3f-140">**/debug**[:**IMPL**&#124;**OPT**]</span></span>|<span data-ttu-id="c6d3f-141">Hata ayıklama bilgisi içerir (yerel değişken ve bağımsız değişken adları ve satır numaraları).</span><span class="sxs-lookup"><span data-stu-id="c6d3f-141">Includes debug information (local variable and argument names, and line numbers).</span></span> <span data-ttu-id="c6d3f-142">Bir PDB dosyası oluşturur.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-142">Creates a PDB file.</span></span><br /><br /> <span data-ttu-id="c6d3f-143">**/ debug** ek değer olmadan JIT iyileştirmesini devre dışı bırakır ve PDB dosyasındaki dizi noktalarını kullanır.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-143">**/debug** with no additional value disables JIT optimization and uses sequence points from the PDB file.</span></span><br /><br /> <span data-ttu-id="c6d3f-144">**IMPL** JIT iyileştirmesini devre dışı bırakır ve örtülü dizi noktalarını kullanır.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-144">**IMPL** disables JIT optimization and uses implicit sequence points.</span></span><br /><br /> <span data-ttu-id="c6d3f-145">**OPT** JIT iyileştirmesini etkinleştirir ve örtülü dizi noktalarını kullanır.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-145">**OPT** enables JIT optimization and uses implicit sequence points.</span></span>|
|<span data-ttu-id="c6d3f-146">**/ dll**</span><span class="sxs-lookup"><span data-stu-id="c6d3f-146">**/dll**</span></span>|<span data-ttu-id="c6d3f-147">Üreten bir *.dll* çıktı olarak bir dosya.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-147">Produces a *.dll* file as output.</span></span>|
|<span data-ttu-id="c6d3f-148">**ENC:** `file`</span><span class="sxs-lookup"><span data-stu-id="c6d3f-148">**/enc:** `file`</span></span>|<span data-ttu-id="c6d3f-149">Belirtilen kaynak dosyasından Düzenle ve Devam Et deltaları oluşturur.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-149">Creates Edit-and-Continue deltas from the specified source file.</span></span><br /><br /> <span data-ttu-id="c6d3f-150">Bu bağımsız değişken yalnızca akademik amaçlıdır ve ticari kullanım için desteklenmez.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-150">This argument is for academic use only and is not supported for commercial use.</span></span>|
|<span data-ttu-id="c6d3f-151">**/ exe**</span><span class="sxs-lookup"><span data-stu-id="c6d3f-151">**/exe**</span></span>|<span data-ttu-id="c6d3f-152">Çıktı olarak bir yürütülebilir dosya oluşturur.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-152">Produces an executable file as output.</span></span> <span data-ttu-id="c6d3f-153">Bu varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-153">This is the default.</span></span>|
|<span data-ttu-id="c6d3f-154">**/ Flags:** `integer`</span><span class="sxs-lookup"><span data-stu-id="c6d3f-154">**/flags:** `integer`</span></span>|<span data-ttu-id="c6d3f-155">Bilgisindeki ımageflags değerini tarafından belirtilen değere ayarlar `integer` ortak dil çalışma zamanı üst bilgisindeki.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-155">Sets ImageFlags to the value specified by `integer` in the common language runtime header.</span></span> <span data-ttu-id="c6d3f-156">Eğer .corflags IL yönergesi dosyada belirtiliyorsa, bu seçenek onu geçersiz kılar.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-156">If the .corflags IL directive is specified in the file, this option overrides it.</span></span> <span data-ttu-id="c6d3f-157">CorHdr.h, comımage_flags bölümüne için geçerli değerlerin bir listesi için bkz. *tamsayı*.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-157">See CorHdr.h, COMIMAGE_FLAGS for a list of valid values for *integer*.</span></span>|
|<span data-ttu-id="c6d3f-158">**/fold**</span><span class="sxs-lookup"><span data-stu-id="c6d3f-158">**/fold**</span></span>|<span data-ttu-id="c6d3f-159">Eşdeğer metot gövdelerini tek bir gövde olarak katlar.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-159">Folds identical method bodies into one.</span></span>|
|<span data-ttu-id="c6d3f-160">/**highentropyva**</span><span class="sxs-lookup"><span data-stu-id="c6d3f-160">/**highentropyva**</span></span>|<span data-ttu-id="c6d3f-161">Yüksek entropili adres alanı düzenini (ASLR) destekleyen bir çıktı çalıştırılabilir dosyası oluşturur.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-161">Produces an output executable that supports high-entropy address space layout randomization (ASLR).</span></span> <span data-ttu-id="c6d3f-162">(İçin varsayılan **/appcontaıner**.)</span><span class="sxs-lookup"><span data-stu-id="c6d3f-162">(Default for **/appcontainer**.)</span></span>|
|<span data-ttu-id="c6d3f-163">**/ include:** `includePath`</span><span class="sxs-lookup"><span data-stu-id="c6d3f-163">**/include:** `includePath`</span></span>|<span data-ttu-id="c6d3f-164">İle eklenen dosyaların aranacağı bir yol ayarlar `#include`.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-164">Sets a path to search for files included with `#include`.</span></span>|
|<span data-ttu-id="c6d3f-165">**/itanium**</span><span class="sxs-lookup"><span data-stu-id="c6d3f-165">**/itanium**</span></span>|<span data-ttu-id="c6d3f-166">Hedef işlemci olarak Intel Itanium belirtir.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-166">Specifies Intel Itanium as the target processor.</span></span><br /><br /> <span data-ttu-id="c6d3f-167">Eğer görüntü bit genişliği belirtilmezse, varsayılan değer **/pe64**.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-167">If no image bitness is specified, the default is **/pe64**.</span></span>|
|<span data-ttu-id="c6d3f-168">**/Key:** `keyFile`</span><span class="sxs-lookup"><span data-stu-id="c6d3f-168">**/key:** `keyFile`</span></span>|<span data-ttu-id="c6d3f-169">Derleme `filename` bulunan özel anahtarı kullanarak güçlü bir imzayla `keyFile`.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-169">Compiles `filename` with a strong signature using the private key contained in `keyFile`.</span></span>|
|<span data-ttu-id="c6d3f-170">**/Key:** @`keySource`</span><span class="sxs-lookup"><span data-stu-id="c6d3f-170">**/key:** @`keySource`</span></span>|<span data-ttu-id="c6d3f-171">Derleme `filename` , özel anahtarı kullanarak güçlü bir imza ile üretilen `keySource`.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-171">Compiles `filename` with a strong signature using the private key produced at `keySource`.</span></span>|
|<span data-ttu-id="c6d3f-172">**/ listeleme**</span><span class="sxs-lookup"><span data-stu-id="c6d3f-172">**/listing**</span></span>|<span data-ttu-id="c6d3f-173">Standart çıktıda bir listeleme dosyası oluşturur.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-173">Produces a listing file on the standard output.</span></span> <span data-ttu-id="c6d3f-174">Eğer bu seçeneği koymazsanız, listeleme dosyası oluşturulmaz.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-174">If you omit this option, no listing file is produced.</span></span><br /><br /> <span data-ttu-id="c6d3f-175">Bu parametre .NET Framework 2.0 ve sonrasında desteklenmez.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-175">This parameter is not supported in the .NET Framework 2.0 or later.</span></span>|
|<span data-ttu-id="c6d3f-176">**/MDV:** `versionString`</span><span class="sxs-lookup"><span data-stu-id="c6d3f-176">**/mdv:** `versionString`</span></span>|<span data-ttu-id="c6d3f-177">Meta veri sürümü dizesini ayarlar.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-177">Sets the metadata version string.</span></span>|
|<span data-ttu-id="c6d3f-178">**/msv:** `major`.`minor`</span><span class="sxs-lookup"><span data-stu-id="c6d3f-178">**/msv:** `major`.`minor`</span></span>|<span data-ttu-id="c6d3f-179">Meta veri akış sürümünü ayarlar burada `major` ve `minor` tamsayılardır.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-179">Sets the metadata stream version, where `major` and `minor` are integers.</span></span>|
|<span data-ttu-id="c6d3f-180">**/noautoinherit**</span><span class="sxs-lookup"><span data-stu-id="c6d3f-180">**/noautoinherit**</span></span>|<span data-ttu-id="c6d3f-181">Devre dışı bırakır öğesinden varsayılan devralmayı <xref:System.Object> temel sınıfa belirtildiğinde.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-181">Disables default inheritance from <xref:System.Object> when no base class is specified.</span></span>|
|<span data-ttu-id="c6d3f-182">**/nocorstub**</span><span class="sxs-lookup"><span data-stu-id="c6d3f-182">**/nocorstub**</span></span>|<span data-ttu-id="c6d3f-183">CORExeMain taslağının oluşturulmasını bastırır.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-183">Suppresses generation of the CORExeMain stub.</span></span>|
|<span data-ttu-id="c6d3f-184">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="c6d3f-184">**/nologo**</span></span>|<span data-ttu-id="c6d3f-185">Microsoft başlangıç başlığı görüntüsünü bastırır.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-185">Suppresses the Microsoft startup banner display.</span></span>|
|<span data-ttu-id="c6d3f-186">**/ Output:** `file.ext`</span><span class="sxs-lookup"><span data-stu-id="c6d3f-186">**/output:** `file.ext`</span></span>|<span data-ttu-id="c6d3f-187">Çıktı dosyası adını ve uzantısını belirtir.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-187">Specifies the output file name and extension.</span></span> <span data-ttu-id="c6d3f-188">Varsayılan olarak, çıktı dosyası adı ilk kaynak dosyasının adıyla aynıdır.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-188">By default, the output file name is the same as the name of the first source file.</span></span> <span data-ttu-id="c6d3f-189">Varsayılan uzantı *.exe*.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-189">The default extension is *.exe*.</span></span> <span data-ttu-id="c6d3f-190">Belirtirseniz **/dll** seçeneği, varsayılan uzantısıdır *.dll*.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-190">If you specify the **/dll** option, the default extension is *.dll*.</span></span> <span data-ttu-id="c6d3f-191">**Not:** Belirtme **/output**: lt;1}MyFile.dll **/dll** seçeneği.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-191">**Note:** Specifying **/output**:myfile.dll does not set the **/dll** option.</span></span> <span data-ttu-id="c6d3f-192">Siz belirtmezseniz **/dll**, sonuç adlı yürütülebilir bir dosya olacaktır *myfile.dll*.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-192">If you do not specify **/dll**, the result will be an executable file named *myfile.dll*.</span></span>|
|<span data-ttu-id="c6d3f-193">**/optimize**</span><span class="sxs-lookup"><span data-stu-id="c6d3f-193">**/optimize**</span></span>|<span data-ttu-id="c6d3f-194">Uzun yönergeleri kısa olarak iyileştirir.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-194">Optimizes long instructions to short.</span></span> <span data-ttu-id="c6d3f-195">Örneğin, `br` için `br.s`.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-195">For example, `br` to `br.s`.</span></span>|
|<span data-ttu-id="c6d3f-196">**/pe64**</span><span class="sxs-lookup"><span data-stu-id="c6d3f-196">**/pe64**</span></span>|<span data-ttu-id="c6d3f-197">64 bitlik bir görüntü oluşturur (PE32+).</span><span class="sxs-lookup"><span data-stu-id="c6d3f-197">Creates a 64-bit image (PE32+).</span></span><br /><br /> <span data-ttu-id="c6d3f-198">Hiçbir hedef işlemci belirtilmezse, varsayılan değer `/itanium`.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-198">If no target processor is specified, the default is `/itanium`.</span></span>|
|<span data-ttu-id="c6d3f-199">**/ pdb**</span><span class="sxs-lookup"><span data-stu-id="c6d3f-199">**/pdb**</span></span>|<span data-ttu-id="c6d3f-200">Hata ayıklama bilgisi izlemeyi etkinleştirmeden bir PDB dosyası oluşturur.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-200">Creates a PDB file without enabling debug information tracking.</span></span>|
|<span data-ttu-id="c6d3f-201">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="c6d3f-201">**/quiet**</span></span>|<span data-ttu-id="c6d3f-202">Sessiz modu belirtir; hiçbir derleme ilerlemesini bildirmez.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-202">Specifies quiet mode; does not report assembly progress.</span></span>|
|<span data-ttu-id="c6d3f-203">**/ Resource:** `file.res`</span><span class="sxs-lookup"><span data-stu-id="c6d3f-203">**/resource:** `file.res`</span></span>|<span data-ttu-id="c6d3f-204">Belirtilen kaynak dosyayı içeren \*sonuç olarak .res biçimi *.exe* veya *.dll* dosya.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-204">Includes the specified resource file in \*.res format in the resulting *.exe* or *.dll* file.</span></span> <span data-ttu-id="c6d3f-205">Yalnızca tek bir .res dosyası belirtilebilir **/Resource** seçeneği.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-205">Only one .res file can be specified with the **/resource** option.</span></span>|
|<span data-ttu-id="c6d3f-206">**ssver:** `int`.`int`</span><span class="sxs-lookup"><span data-stu-id="c6d3f-206">**/ssver:** `int`.`int`</span></span>|<span data-ttu-id="c6d3f-207">NT isteğe bağlı üst bilgisinde alt sistem sürümünü ayarlar.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-207">Sets the subsystem version number in the NT optional header.</span></span> <span data-ttu-id="c6d3f-208">İçin **/appcontaıner** ve **/arm** 6.02 en düşük sürüm numarasıdır.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-208">For **/appcontainer** and **/arm** the minimum version number is 6.02.</span></span>|
|<span data-ttu-id="c6d3f-209">**/Stack:** `stackSize`</span><span class="sxs-lookup"><span data-stu-id="c6d3f-209">**/stack:** `stackSize`</span></span>|<span data-ttu-id="c6d3f-210">İçin NT isteğe bağlı üst bilgisindeki SizeOfStackReserve değerini ayarlar `stackSize`.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-210">Sets the SizeOfStackReserve value in the NT Optional header to `stackSize`.</span></span>|
|<span data-ttu-id="c6d3f-211">**/stripreloc**</span><span class="sxs-lookup"><span data-stu-id="c6d3f-211">**/stripreloc**</span></span>|<span data-ttu-id="c6d3f-212">Temel yeniden konumlandırmanın gerekmediğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-212">Specifies that no base relocations are needed.</span></span>|
|<span data-ttu-id="c6d3f-213">**/ Subsystem:** `integer`</span><span class="sxs-lookup"><span data-stu-id="c6d3f-213">**/subsystem:** `integer`</span></span>|<span data-ttu-id="c6d3f-214">Alt sistemi tarafından belirtilen değere ayarlar `integer` NT isteğe bağlı üst bilgisindeki.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-214">Sets subsystem to the value specified by `integer` in the NT Optional header.</span></span> <span data-ttu-id="c6d3f-215">Eğer .subsystem IL yönergesi dosyada belirtiliyorsa, bu komut onu geçersiz kılar.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-215">If the .subsystem IL directive is specified in the file, this command overrides it.</span></span> <span data-ttu-id="c6d3f-216">Bkz. Winnt.h, IMAGE_SUBSYSTEM için geçerli değerlerin bir listesi için `integer`.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-216">See winnt.h, IMAGE_SUBSYSTEM for a list of valid values for `integer`.</span></span>|
|<span data-ttu-id="c6d3f-217">**/x64**</span><span class="sxs-lookup"><span data-stu-id="c6d3f-217">**/x64**</span></span>|<span data-ttu-id="c6d3f-218">Hedef işlemci olarak bir 64 bitlik AMD işlemci belirtir.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-218">Specifies a 64-bit AMD processor as the target processor.</span></span><br /><br /> <span data-ttu-id="c6d3f-219">Eğer görüntü bit genişliği belirtilmezse, varsayılan değer **/pe64**.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-219">If no image bitness is specified, the default is **/pe64**.</span></span>|
|<span data-ttu-id="c6d3f-220">**/?**</span><span class="sxs-lookup"><span data-stu-id="c6d3f-220">**/?**</span></span>|<span data-ttu-id="c6d3f-221">Araç için komut sözdizimini ve seçenekleri görüntüler.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-221">Displays command syntax and options for the tool.</span></span>|

> [!NOTE]
> <span data-ttu-id="c6d3f-222">Tüm seçenekler için *Ilasm.exe* büyük/küçük harfe ve ilk üç harfinden tanınır.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-222">All options for *Ilasm.exe* are case-insensitive and recognized by the first three letters.</span></span> <span data-ttu-id="c6d3f-223">Örneğin, **/lis** eşdeğerdir **/listing** ve **/res**: myresfile.res eşdeğerdir **/Resource**: myresfile.res eşdeğerdir. Bağımsız değişkenler belirten seçenekler, seçenek ve bağımsız değişken arasında ayıraç olarak ya iki nokta üst üste (:) ya da eşittir işaretini (=) kabul eder.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-223">For example, **/lis** is equivalent to **/listing** and **/res**:myresfile.res is equivalent to **/resource**:myresfile.res. Options that specify arguments accept either a colon (:) or an equal sign (=) as the separator between the option and the argument.</span></span> <span data-ttu-id="c6d3f-224">Örneğin, **/output**:*file.ext* eşdeğerdir **/output**=*file.ext*.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-224">For example, **/output**:*file.ext* is equivalent to **/output**=*file.ext*.</span></span>

## <a name="remarks"></a><span data-ttu-id="c6d3f-225">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c6d3f-225">Remarks</span></span>

<span data-ttu-id="c6d3f-226">IL Derleyicisi araç satıcılarına IL oluşturucuları tasarlamaları ve uygulamaları için yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-226">The IL Assembler helps tool vendors design and implement IL generators.</span></span> <span data-ttu-id="c6d3f-227">Kullanarak *Ilasm.exe*, araç ve derleyici geliştiriciler odaklanmasına IL ve meta verileri nesil IL PE dosyası biçiminde yayma ile ilgili olmadan.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-227">Using *Ilasm.exe*, tool and compiler developers can concentrate on IL and metadata generation without being concerned with emitting IL in the PE file format.</span></span>

<span data-ttu-id="c6d3f-228">Benzer şekilde gibi çalışma zamanını hedefleyen diğer derleyiciler C# ve Visual Basic *Ilasm.exe* Ara nesne dosyaları oluşturmaz ve bir PE dosyası oluşturmak için bağlama aşaması gerektirmez.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-228">Similar to other compilers that target the runtime, such as C# and Visual Basic, *Ilasm.exe* does not produce intermediate object files and does not require a linking stage to form a PE file.</span></span>

<span data-ttu-id="c6d3f-229">IL Derleyicisi, çalışma zamanını hedef alan programlama dillerinin tüm varolan meta veri ve IL özelliklerini ifade edebilir.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-229">The IL Assembler can express all the existing metadata and IL features of the programming languages that target the runtime.</span></span> <span data-ttu-id="c6d3f-230">Böylece, IL yeterince ifade edilmesine bu programlama dillerinden birine yazılır ve ile derlenmiş yönetilen kod *Ilasm.exe*.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-230">This allows managed code written in any of these programming languages to be adequately expressed in IL Assembler and compiled with *Ilasm.exe*.</span></span>

> [!NOTE]
> <span data-ttu-id="c6d3f-231">Eğer .il kaynak dosyasının son kod satırında bir boşluk veya satır sonu karakteri yoksa derleme başarısız olabilir.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-231">Compilation might fail if the last line of code in the .il source file does not have either trailing white space or an end-of-line character.</span></span>

<span data-ttu-id="c6d3f-232">Kullanabileceğiniz *Ilasm.exe* yardımcı aracı ile birlikte [ *Ildasm.exe*](../../../docs/framework/tools/ildasm-exe-il-disassembler.md).</span><span class="sxs-lookup"><span data-stu-id="c6d3f-232">You can use *Ilasm.exe* in conjunction with its companion tool, [*Ildasm.exe*](../../../docs/framework/tools/ildasm-exe-il-disassembler.md).</span></span> <span data-ttu-id="c6d3f-233">*Ildasm.exe* alır, IL kodunu içeren ve bir metin dosyası olarak uygun oluşturan bir PE dosyası için giriş *Ilasm.exe*.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-233">*Ildasm.exe* takes a PE file that contains IL code and creates a text file suitable as input to *Ilasm.exe*.</span></span> <span data-ttu-id="c6d3f-234">Bu örneğin, tüm çalışma zamanı meta veri özniteliklerini desteklemeyen bir programlama dilinde kod derlerken kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-234">This is useful, for example, when compiling code in a programming language that does not support all the runtime metadata attributes.</span></span> <span data-ttu-id="c6d3f-235">Kodu derledikten ve çıktıyı çalıştıran sonra *Ildasm.exe*, eksik öznitelikler eklemek için elle düzenlenerek elde edilen IL metin dosyası olabilir.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-235">After compiling the code and running the output through *Ildasm.exe*, the resulting IL text file can be hand-edited to add the missing attributes.</span></span> <span data-ttu-id="c6d3f-236">Ardından bu metin dosyasını çalıştırarak *Ilasm.exe* son bir yürütülebilir dosya.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-236">You can then run this text file through the *Ilasm.exe* to produce a final executable file.</span></span>

<span data-ttu-id="c6d3f-237">Bu tekniği kullanarak ayrı derleyiciler tarafından üretilen çeşitli PE dosyalarından tek bir PE dosyası oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-237">You can also use this technique to produce a single PE file from several PE files originally generated by different compilers.</span></span>

> [!NOTE]
> <span data-ttu-id="c6d3f-238">Şu anda, bu tekniği gömülü yerel kod içeren (örneğin, Visual C++ tarafından üretilen PE dosyaları) PE dosyaları ile kullanamazsınız.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-238">Currently, you cannot use this technique with PE files that contain embedded native code (for example, PE files produced by Visual C++).</span></span>

<span data-ttu-id="c6d3f-239">Bunu yapmak için kullanımını birleştirilmiş *Ildasm.exe* ve *Ilasm.exe* varsayılan olarak, mümkün olduğunca doğru olarak derleyici kısa yazdığınız IL kaynaklarınızda uzun olanlarla kodlamalarınızı değil (veya başka bir derleyici tarafından yayınlanan).</span><span class="sxs-lookup"><span data-stu-id="c6d3f-239">To make this combined use of *Ildasm.exe* and *Ilasm.exe* as accurate as possible, by default the assembler does not substitute short encodings for long ones you might have written in your IL sources (or that might be emitted by another compiler).</span></span> <span data-ttu-id="c6d3f-240">Kullanım **/ optimize** seçeneği kısa kodlamaları mümkün olduğu yerde değiştirin.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-240">Use the **/optimize** option to substitute short encodings wherever possible.</span></span>

> [!NOTE]
> <span data-ttu-id="c6d3f-241">*Ildasm.exe* yalnızca diskteki dosyalar üzerinde çalışır.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-241">*Ildasm.exe* only operates on files on disk.</span></span> <span data-ttu-id="c6d3f-242">Genel bütünleştirilmiş kod önbelleğine yüklü olan dosyalar üzerinde çalışmaz.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-242">It does not operate on files installed in the global assembly cache.</span></span>

<span data-ttu-id="c6d3f-243">IL grameri daha fazla bilgi için bkz: içindeki asmparse.grammar dosyasına [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6d3f-243">For more information about the grammar of IL, see the asmparse.grammar file in the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span></span>

## <a name="version-information"></a><span data-ttu-id="c6d3f-244">Sürüm Bilgileri</span><span class="sxs-lookup"><span data-stu-id="c6d3f-244">Version Information</span></span>

<span data-ttu-id="c6d3f-245">İle başlayarak [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], aşağıdakine benzer kod kullanarak bir arabirim uygulamasına özel öznitelik ekleyebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="c6d3f-245">Starting with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], you can attach a custom attribute to an interface implementation by using code similar to the following:</span></span>

```
.class interface public abstract auto ansi IMyInterface
{
  .method public hidebysig newslot abstract virtual
    instance int32 method1() cil managed
  {
  } // end of method IMyInterface::method1
} // end of class IMyInterface
.class public auto ansi beforefieldinit MyClass
  extends [mscorlib]System.Object
  implements IMyInterface
  {
    .interfaceimpl type IMyInterface
    .custom instance void
      [mscorlib]System.Diagnostics.DebuggerNonUserCodeAttribute::.ctor() = ( 01 00 00 00 )
      …
```

<span data-ttu-id="c6d3f-246">İle başlayarak [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], bir rastgele sıralama BLOB'u (ikili büyük nesne) ham ikili temsilini kullanarak aşağıdaki kodda gösterildiği gibi belirtebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="c6d3f-246">Starting with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], you can specify an arbitrary marshal BLOB (binary large object) by using its raw binary representation, as shown in the following code:</span></span>

```
.method public hidebysig abstract virtual
        instance void
        marshal({ 38 01 02 FF })
        Test(object A_1) cil managed
```

<span data-ttu-id="c6d3f-247">IL grameri daha fazla bilgi için bkz: içindeki asmparse.grammar dosyasına [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6d3f-247">For more information about the grammar of IL, see the asmparse.grammar file in the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span></span>

## <a name="examples"></a><span data-ttu-id="c6d3f-248">Örnekler</span><span class="sxs-lookup"><span data-stu-id="c6d3f-248">Examples</span></span>

<span data-ttu-id="c6d3f-249">Aşağıdaki komutu IL dosyasını derler *myTestFile.il* ve yürütülebilir dosya üreten *myTestFile.exe*.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-249">The following command assembles the IL file *myTestFile.il* and produces the executable *myTestFile.exe*.</span></span>

```console
ilasm myTestFile
```

<span data-ttu-id="c6d3f-250">Aşağıdaki komutu IL dosyasını derler *myTestFile.il* ve üretir *.dll* dosya *myTestFile.dll*.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-250">The following command assembles the IL file *myTestFile.il* and produces the *.dll* file *myTestFile.dll*.</span></span>

```console
ilasm myTestFile /dll
```

<span data-ttu-id="c6d3f-251">Aşağıdaki komutu IL dosyasını derler *myTestFile.il* ve üretir *.dll* dosya *myNewTestFile.dll*.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-251">The following command assembles the IL file *myTestFile.il* and produces the *.dll* file *myNewTestFile.dll*.</span></span>

```console
ilasm myTestFile /dll /output:myNewTestFile.dll
```

<span data-ttu-id="c6d3f-252">Aşağıdaki kod örneği, "Hello World!" görüntüleyen son derece basit bir uygulama gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-252">The following code example shows an extremely simple application that displays "Hello World!"</span></span> <span data-ttu-id="c6d3f-253">konsola.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-253">to the console.</span></span> <span data-ttu-id="c6d3f-254">Bu kodu derlemek ve ardından [ *Ildasm.exe* ](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) aracı bir IL dosyası oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-254">You can compile this code and then use the [*Ildasm.exe*](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) tool to generate an IL file.</span></span>

```csharp
using System;

public class Hello
{
    public static void Main(String[] args)
    {
        Console.WriteLine("Hello World!");
    }
}
```

<span data-ttu-id="c6d3f-255">Aşağıdaki IL kod örneği önceki C# kod örneğine karşılık gelir.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-255">The following IL code example corresponds to the previous C# code example.</span></span> <span data-ttu-id="c6d3f-256">Bu kod, IL derleyicisi Aracı'nı kullanarak bir derlemenin içine derleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-256">You can compile this code into an assembly using the IL Assembler tool.</span></span> <span data-ttu-id="c6d3f-257">Hem IL ve C# kod örnekleri, "Hello World!" görüntüle</span><span class="sxs-lookup"><span data-stu-id="c6d3f-257">Both IL and C# code examples display "Hello World!"</span></span> <span data-ttu-id="c6d3f-258">konsola.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-258">to the console.</span></span>

```
// Metadata version: v2.0.50215
.assembly extern mscorlib
{
  .publickeytoken = (B7 7A 5C 56 19 34 E0 89 )                         // .z\V.4..
  .ver 2:0:0:0
}
.assembly sample
{
  .custom instance void [mscorlib]System.Runtime.CompilerServices.CompilationRelaxationsAttribute::.ctor(int32) = ( 01 00 08 00 00 00 00 00 )
  .hash algorithm 0x00008004
  .ver 0:0:0:0
}
.module sample.exe
// MVID: {A224F460-A049-4A03-9E71-80A36DBBBCD3}
.imagebase 0x00400000
.file alignment 0x00000200
.stackreserve 0x00100000
.subsystem 0x0003       // WINDOWS_CUI
.corflags 0x00000001    //  ILONLY
// Image base: 0x02F20000

// =============== CLASS MEMBERS DECLARATION ===================

.class public auto ansi beforefieldinit Hello
       extends [mscorlib]System.Object
{
  .method public hidebysig static void  Main(string[] args) cil managed
  {
    .entrypoint
    // Code size       13 (0xd)
    .maxstack  8
    IL_0000:  nop
    IL_0001:  ldstr      "Hello World!"
    IL_0006:  call       void [mscorlib]System.Console::WriteLine(string)
    IL_000b:  nop
    IL_000c:  ret
  } // end of method Hello::Main

  .method public hidebysig specialname rtspecialname
          instance void  .ctor() cil managed
  {
    // Code size       7 (0x7)
    .maxstack  8
    IL_0000:  ldarg.0
    IL_0001:  call       instance void [mscorlib]System.Object::.ctor()
    IL_0006:  ret
  } // end of method Hello::.ctor

} // end of class Hello
```

## <a name="see-also"></a><span data-ttu-id="c6d3f-259">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="c6d3f-259">See also</span></span>

- [<span data-ttu-id="c6d3f-260">Araçlar</span><span class="sxs-lookup"><span data-stu-id="c6d3f-260">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="c6d3f-261">*Ildasm.exe* (IL ayrıştırıcı)</span><span class="sxs-lookup"><span data-stu-id="c6d3f-261">*Ildasm.exe* (IL Disassembler)</span></span>](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)
- [<span data-ttu-id="c6d3f-262">Yönetilen Yürütme İşlemi</span><span class="sxs-lookup"><span data-stu-id="c6d3f-262">Managed Execution Process</span></span>](../../../docs/standard/managed-execution-process.md)
- [<span data-ttu-id="c6d3f-263">Komut İstemleri</span><span class="sxs-lookup"><span data-stu-id="c6d3f-263">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
