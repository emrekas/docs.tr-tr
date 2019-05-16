---
title: Global.JSON genel bakış
description: .NET Core SDK'sı sürümü, .NET Core CLI komutlarını çalıştırırken ayarlanacak global.json dosyasını kullanmayı öğrenin.
ms.date: 12/03/2018
ms.custom: updateeachrelease, seodec18
ms.openlocfilehash: a3d90e39401ece8d106d89a7533b7c1e1e4433cd
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632393"
---
# <a name="globaljson-overview"></a><span data-ttu-id="6571d-103">Global.JSON genel bakış</span><span class="sxs-lookup"><span data-stu-id="6571d-103">global.json overview</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

<span data-ttu-id="6571d-104">*Global.json* dosyası hangi .NET Core SDK'sı sürümü, .NET Core CLI komutlarını çalıştırmanız kullanıldığında tanımlamanıza izin verir.</span><span class="sxs-lookup"><span data-stu-id="6571d-104">The *global.json* file allows you to define which .NET Core SDK version is used when you run .NET Core CLI commands.</span></span> <span data-ttu-id="6571d-105">.NET Core SDK'yı seçerek projenizin hedeflediği çalışma zamanı belirtmelerini bağımsızdır.</span><span class="sxs-lookup"><span data-stu-id="6571d-105">Selecting the .NET Core SDK is independent from specifying the runtime your project targets.</span></span> <span data-ttu-id="6571d-106">.NET Core SDK'sı sürümü, .NET Core CLI araçları hangi sürümlerinin kullanıldığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="6571d-106">The .NET Core SDK version indicates which versions of the .NET Core CLI tools are used.</span></span> <span data-ttu-id="6571d-107">Genel olarak, Araçlar, dolayısıyla en son sürümünü kullanmak istediğiniz *global.json* dosyası gereklidir.</span><span class="sxs-lookup"><span data-stu-id="6571d-107">In general, you want to use the latest version of the tools, so no *global.json* file is needed.</span></span>

<span data-ttu-id="6571d-108">Bunun yerine çalışma zamanı belirtme hakkında daha fazla bilgi için bkz. [hedef çerçeveyi](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="6571d-108">For more information about specifying the runtime instead, see [Target frameworks](../../standard/frameworks.md).</span></span>

<span data-ttu-id="6571d-109">.NET core SDK'sı arayan bir *global.json* dosyasında (Bu proje dizinine aynı olmak zorunda olmayan) geçerli çalışma dizinine veya onun üst dizinlerin biri.</span><span class="sxs-lookup"><span data-stu-id="6571d-109">.NET Core SDK looks for a *global.json* file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="globaljson-schema"></a><span data-ttu-id="6571d-110">Global.JSON şeması</span><span class="sxs-lookup"><span data-stu-id="6571d-110">global.json schema</span></span>

### <a name="sdk"></a><span data-ttu-id="6571d-111">SDK'sı</span><span class="sxs-lookup"><span data-stu-id="6571d-111">sdk</span></span>

<span data-ttu-id="6571d-112">Tür: Nesne</span><span class="sxs-lookup"><span data-stu-id="6571d-112">Type: Object</span></span>

<span data-ttu-id="6571d-113">Seçmek için .NET Core SDK'sı hakkında bilgileri belirtir.</span><span class="sxs-lookup"><span data-stu-id="6571d-113">Specifies information about the .NET Core SDK to select.</span></span>

#### <a name="version"></a><span data-ttu-id="6571d-114">sürüm</span><span class="sxs-lookup"><span data-stu-id="6571d-114">version</span></span>

<span data-ttu-id="6571d-115">Tür: Dize</span><span class="sxs-lookup"><span data-stu-id="6571d-115">Type: String</span></span>

<span data-ttu-id="6571d-116">.NET Core SDK'sını kullanmaya sürümü.</span><span class="sxs-lookup"><span data-stu-id="6571d-116">The version of the .NET Core SDK to use.</span></span>

<span data-ttu-id="6571d-117">Unutmayın, bu alan:</span><span class="sxs-lookup"><span data-stu-id="6571d-117">Note that this field:</span></span>

- <span data-ttu-id="6571d-118">Değil Glob desteğine sahip, diğer bir deyişle, tam sürüm numarası belirtilmiş olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="6571d-118">Doesn't have globbing support, that is, the full version number has to be specified.</span></span>
- <span data-ttu-id="6571d-119">Sürüm aralıklarını desteklemiyor.</span><span class="sxs-lookup"><span data-stu-id="6571d-119">Doesn't support version ranges.</span></span>

<span data-ttu-id="6571d-120">Aşağıdaki örnek, içeriğini gösterir. bir *global.json* dosyası:</span><span class="sxs-lookup"><span data-stu-id="6571d-120">The following example shows the contents of a *global.json* file:</span></span>

```json
{
  "sdk": {
    "version": "2.2.100"
  }
}
```

## <a name="globaljson-and-the-net-core-cli"></a><span data-ttu-id="6571d-121">Global.JSON ve .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="6571d-121">global.json and the .NET Core CLI</span></span>

<span data-ttu-id="6571d-122">Hangi sürümlerinin bir ayarlamak için kullanılabilir olduğunu öğrenmek yararlıdır *global.json* dosya.</span><span class="sxs-lookup"><span data-stu-id="6571d-122">It's helpful to know which versions are available in order to set one in the *global.json* file.</span></span> <span data-ttu-id="6571d-123">Desteklenen kullanılabilir SDK'lar tam listesini bulabilirsiniz [.NET indirir](https://www.microsoft.com/net/download/all) site.</span><span class="sxs-lookup"><span data-stu-id="6571d-123">You can find the full list of supported available SDKs at the [.NET Downloads](https://www.microsoft.com/net/download/all) site.</span></span> <span data-ttu-id="6571d-124">.NET Core 2.1 SDK ile başlayarak, hangi SDK sürümlerinin makinenizde zaten yüklü olduğunu doğrulamak için aşağıdaki komutu çalıştırabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="6571d-124">Starting with .NET Core 2.1 SDK, you can run the following command to verify which SDK versions are already installed on your machine:</span></span>

```console
dotnet --list-sdks
```

<span data-ttu-id="6571d-125">Makinenizde ek .NET Core SDK'sı sürümünü birden yüklemek için şurayı ziyaret edin [.NET indirir](https://www.microsoft.com/net/download/all) site.</span><span class="sxs-lookup"><span data-stu-id="6571d-125">To install additional .NET Core SDK versions on your machine, visit the [.NET Downloads](https://www.microsoft.com/net/download/all) site.</span></span>

<span data-ttu-id="6571d-126">Yeni bir oluşturabilirsiniz *global.json* yürüterek geçerli dizin dosyası [yeni dotnet](dotnet-new.md) komutu, aşağıdaki örneğe benzer:</span><span class="sxs-lookup"><span data-stu-id="6571d-126">You can create a new the *global.json* file in the current directory by executing the [dotnet new](dotnet-new.md) command, similar to the following example:</span></span>

```console
dotnet new globaljson --sdk-version 2.2.100
```

## <a name="matching-rules"></a><span data-ttu-id="6571d-127">Eşleştirme kuralları</span><span class="sxs-lookup"><span data-stu-id="6571d-127">Matching rules</span></span>

> [!NOTE]
> <span data-ttu-id="6571d-128">Eşleştirme kuralları, .NET Core çalışma zamanı bir parçası olduğu apphost tarafından yönetilir.</span><span class="sxs-lookup"><span data-stu-id="6571d-128">The matching rules are governed by the apphost, which is part of the .NET Core runtime.</span></span>
> <span data-ttu-id="6571d-129">Konak en son sürümünü, birden çok çalışma zamanları yüklü yan yana olduğunda kullanılır.</span><span class="sxs-lookup"><span data-stu-id="6571d-129">The latest version of the host is used when you have multiple runtimes installed side-by-side.</span></span>

<span data-ttu-id="6571d-130">.NET Core 2.0 ile başlayarak, SDK'yı kullanmak için hangi sürümünün belirlerken aşağıdaki kurallar geçerlidir:</span><span class="sxs-lookup"><span data-stu-id="6571d-130">Starting with .NET Core 2.0, the following rules apply when determining which version of the SDK to use:</span></span>

- <span data-ttu-id="6571d-131">Hayır ise *global.json* dosya bulunduğunda veya *global.json* bir SDK sürümü belirtmeyen en son yüklenen SDK sürüm kullanılır.</span><span class="sxs-lookup"><span data-stu-id="6571d-131">If no *global.json* file is found or *global.json* doesn't specify an SDK version, the latest installed SDK version is used.</span></span> <span data-ttu-id="6571d-132">En son SDK sürümü, yayın veya yayın öncesi-en yüksek sürüm numarası WINS olabilir.</span><span class="sxs-lookup"><span data-stu-id="6571d-132">Latest SDK version can be either release or pre-release - the highest version number wins.</span></span>
- <span data-ttu-id="6571d-133">Varsa *global.json* SDK sürümü belirtin:</span><span class="sxs-lookup"><span data-stu-id="6571d-133">If *global.json* does specify an SDK version:</span></span>
  - <span data-ttu-id="6571d-134">Belirtilen SDK sürümü makinede bulunursa o tam sürümü kullanılır.</span><span class="sxs-lookup"><span data-stu-id="6571d-134">If the specified SDK version is found on the machine, that exact version is used.</span></span>
  - <span data-ttu-id="6571d-135">Belirtilen SDK sürümü makinede bulunamazsa, en son SDK'sı yüklü **düzeltme eki sürümü** olan sürümü kullanılır.</span><span class="sxs-lookup"><span data-stu-id="6571d-135">If the specified SDK version can't be found on the machine, the latest installed SDK **patch version** of that version is used.</span></span> <span data-ttu-id="6571d-136">SDK'sı yüklü en son sürüm **düzeltme eki sürümü** yayın veya yayın öncesi-en yüksek sürüm numarası WINS olabilir.</span><span class="sxs-lookup"><span data-stu-id="6571d-136">Latest installed SDK **patch version** can be either release or pre-release - the highest version number wins.</span></span> <span data-ttu-id="6571d-137">.NET Core 2.1 ve üzeri **düzeltme eki sürümleri** tutardan **düzeltme eki sürümü** belirtilen SDK seçiminde göz ardı edilir.</span><span class="sxs-lookup"><span data-stu-id="6571d-137">In .NET Core 2.1 and higher, the **patch versions** lower than the **patch version** specified are ignored in the SDK selection.</span></span>
  - <span data-ttu-id="6571d-138">Varsa belirtilen SDK sürümü ve uygun bir SDK **düzeltme eki sürümü** bulunamıyor, hata oluşur.</span><span class="sxs-lookup"><span data-stu-id="6571d-138">If the specified SDK version and an appropriate SDK **patch version** can't be found, an error is thrown.</span></span>

<span data-ttu-id="6571d-139">SDK sürümü, şu anda aşağıdaki bölümlerden oluşur:</span><span class="sxs-lookup"><span data-stu-id="6571d-139">The SDK version is currently composed of the following parts:</span></span>

`[.NET Core major version].[.NET Core minor version].[xyz][-optional preview name]`

<span data-ttu-id="6571d-140">**Özellik yayın** .NET Core SDK'ın ilk basamak tarafından temsil edilen (`x`) numarasının son bölümünde (`xyz`) 2.1.100 SDK sürümleri ve üzeri.</span><span class="sxs-lookup"><span data-stu-id="6571d-140">The **feature release** of the .NET Core SDK is represented by the first digit (`x`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="6571d-141">Genel olarak, .NET Core SDK'sı, .NET Core daha hızlı sürüm döngüsü vardır.</span><span class="sxs-lookup"><span data-stu-id="6571d-141">In general, the .NET Core SDK has a faster release cycle than .NET Core.</span></span>

<span data-ttu-id="6571d-142">**Düzeltme eki sürümü** son iki basamak tarafından tanımlanan (`yz`) numarasının son bölümünde (`xyz`) 2.1.100 SDK sürümleri ve üzeri.</span><span class="sxs-lookup"><span data-stu-id="6571d-142">The **patch version** is defined by the last two digits (`yz`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="6571d-143">Örneğin, belirttiğiniz `2.1.300` SDK sürümü kadar SDK seçimi bulur `2.1.399` ancak `2.1.400` için bir düzeltme eki sürümü kabul değil `2.1.300`.</span><span class="sxs-lookup"><span data-stu-id="6571d-143">For example, if you specify `2.1.300` as the SDK version, SDK selection finds up to `2.1.399` but `2.1.400` isn't considered a patch version for `2.1.300`.</span></span>

<span data-ttu-id="6571d-144">.NET core SDK sürümleri `2.1.100` aracılığıyla `2.1.201` sürüm numarası düzeni arasında geçiş sırasında yayımlanan ve doğru bir şekilde işlemez `xyz` gösterimi.</span><span class="sxs-lookup"><span data-stu-id="6571d-144">.NET Core SDK versions `2.1.100` through `2.1.201` were released during the transition between version number schemes and don't correctly handle the `xyz` notation.</span></span> <span data-ttu-id="6571d-145">Bu sürümlerde belirtirseniz önerilir *global.json* dosyası belirtilen sürümlerde hedef makinelerde olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="6571d-145">We highly recommend if you specify these versions in the *global.json* file, that you ensure the specified versions are on the target machines.</span></span>

<span data-ttu-id="6571d-146">.NET Core SDK'sı ile bir sürüm ve tam eşleşme belirtilmişse 1.x bulunamadı, en son yüklenen SDK sürüm kullanıldı.</span><span class="sxs-lookup"><span data-stu-id="6571d-146">With .NET Core SDK 1.x, if you specified a version and no exact match was found, the latest installed SDK version was used.</span></span> <span data-ttu-id="6571d-147">En son SDK sürümü, yayın veya yayın öncesi-en yüksek sürüm numarası WINS olabilir.</span><span class="sxs-lookup"><span data-stu-id="6571d-147">Latest SDK version can be either release or pre-release - the highest version number wins.</span></span>

## <a name="troubleshooting-build-warnings"></a><span data-ttu-id="6571d-148">Sorun giderme derleme uyarıları</span><span class="sxs-lookup"><span data-stu-id="6571d-148">Troubleshooting build warnings</span></span>

> [!WARNING]
> <span data-ttu-id="6571d-149">.NET Core SDK'sını bir önizleme sürümü ile çalışıyor.</span><span class="sxs-lookup"><span data-stu-id="6571d-149">You are working with a preview version of the .NET Core SDK.</span></span> <span data-ttu-id="6571d-150">Geçerli projede SDK sürümü bir global.json dosyasını aracılığıyla tanımlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6571d-150">You can define the SDK version via a global.json file in the current project.</span></span> <span data-ttu-id="6571d-151">Daha fazla bilgi için <https://go.microsoft.com/fwlink/?linkid=869452></span><span class="sxs-lookup"><span data-stu-id="6571d-151">More at <https://go.microsoft.com/fwlink/?linkid=869452></span></span>

<span data-ttu-id="6571d-152">Bu uyarı, projeniz .NET Core SDK'sı, bir önizleme sürümünü kullanarak açıklandığı şekilde derleniyor olduğunu gösterir. [kurallarına](#matching-rules) bölümü.</span><span class="sxs-lookup"><span data-stu-id="6571d-152">This warning indicates that your project is being compiled using a preview version of the .NET Core SDK, as explained in the [Matching rules](#matching-rules) section.</span></span> <span data-ttu-id="6571d-153">.NET core SDK'sı sürümü geçmişi ve yüksek kaliteli olma taahhüdü bulunuyor.</span><span class="sxs-lookup"><span data-stu-id="6571d-153">.NET Core SDK versions have a history and commitment of being high quality.</span></span> <span data-ttu-id="6571d-154">Ancak, bir önizleme sürümünü kullanmak istemiyorsanız, ekleme bir *global.json* proje hiyerarşisi yapısı kullanın ve hangi SDK sürümünü belirtmek üzere dosyaya `dotnet --list-sdks` sürümü, makinenizde yüklü olduğundan emin olmak için.</span><span class="sxs-lookup"><span data-stu-id="6571d-154">However, if you don't want to use a preview version, add a *global.json* file to your project hierarchy structure to specify which SDK version to use, and use `dotnet --list-sdks` to confirm that the version is installed on your machine.</span></span> <span data-ttu-id="6571d-155">Yeni bir sürümü yayımlandığında yeni sürümü kullanmak için ya da kaldırma *global.json* dosya ya da daha yeni sürümünü kullanacak şekilde güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="6571d-155">When a new version is released, to use the new version, either remove the *global.json* file or update it to use the newer version.</span></span>

> [!WARNING]
> <span data-ttu-id="6571d-156">Başlangıç projesi '{startupProject}' hedef framework '. NETCoreApp' sürümü '{targetFrameworkVersion}'.</span><span class="sxs-lookup"><span data-stu-id="6571d-156">Startup project '{startupProject}' targets framework '.NETCoreApp' version '{targetFrameworkVersion}'.</span></span> <span data-ttu-id="6571d-157">Entity Framework Core ve .NET komut satırı araçları bu sürümü yalnızca sürüm 2.0 veya üstü destekler.</span><span class="sxs-lookup"><span data-stu-id="6571d-157">This version of the Entity Framework Core .NET Command-line Tools only supports version 2.0 or higher.</span></span> <span data-ttu-id="6571d-158">Araçlar'ın eski sürümlerini kullanma hakkında daha fazla bilgi için bkz. <https://go.microsoft.com/fwlink/?linkid=871254></span><span class="sxs-lookup"><span data-stu-id="6571d-158">For information on using older versions of the tools, see <https://go.microsoft.com/fwlink/?linkid=871254></span></span>

<span data-ttu-id="6571d-159">.NET Core 2.1 SDK (sürüm 2.1.300) ile başlayan `dotnet ef` komutu birlikte gelen SDK.</span><span class="sxs-lookup"><span data-stu-id="6571d-159">Starting with .NET Core 2.1 SDK (version 2.1.300), the `dotnet ef` command comes included in the SDK.</span></span> <span data-ttu-id="6571d-160">Bu uyarı, projenizi EF Core 1.0 veya 1.1, .NET Core 2.1 SDK ve sonraki sürümler ile uyumlu değil hedefleyen olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="6571d-160">This warning indicates that your project targets EF Core 1.0 or 1.1, which isn't compatible with .NET Core 2.1 SDK and later versions.</span></span> <span data-ttu-id="6571d-161">Projenizi derlemek için .NET Core 2.0 SDK'sını (sürüm 2.1.201) yükleyin ve makinenizde önceki ve istenen SDK sürümüyle tanımlamak *global.json* dosya.</span><span class="sxs-lookup"><span data-stu-id="6571d-161">To compile your project, install .NET Core 2.0 SDK (version 2.1.201) and earlier on your machine and define the desired SDK version using the *global.json* file.</span></span> <span data-ttu-id="6571d-162">Hakkında daha fazla bilgi için `dotnet ef` komutu, bkz: [EF Core .NET komut satırı araçları](/ef/core/miscellaneous/cli/dotnet).</span><span class="sxs-lookup"><span data-stu-id="6571d-162">For more information about the `dotnet ef` command, see [EF Core .NET Command-line Tools](/ef/core/miscellaneous/cli/dotnet).</span></span>

## <a name="see-also"></a><span data-ttu-id="6571d-163">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="6571d-163">See also</span></span>

- [<span data-ttu-id="6571d-164">Proje SDK'ları nasıl çözümlenir</span><span class="sxs-lookup"><span data-stu-id="6571d-164">How project SDKs are resolved</span></span>](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved)
