---
title: dotnet komutu çalıştırın
description: Dotnet komutu çalıştırın, kaynak koddan uygulamanızı çalıştırmak için uygun bir seçenek sağlar.
ms.date: 05/29/2018
ms.openlocfilehash: e96d5c99e7bcb394c6feffa18990f76a83f32276
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612855"
---
# <a name="dotnet-run"></a><span data-ttu-id="20042-103">dotnet çalıştırın</span><span class="sxs-lookup"><span data-stu-id="20042-103">dotnet run</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="20042-104">Ad</span><span class="sxs-lookup"><span data-stu-id="20042-104">Name</span></span>

<span data-ttu-id="20042-105">`dotnet run` -Çalıştırmalar kaynak kodu olmadan herhangi bir özel derleme veya başlatma komutu.</span><span class="sxs-lookup"><span data-stu-id="20042-105">`dotnet run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="20042-106">Synopsis</span><span class="sxs-lookup"><span data-stu-id="20042-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="20042-107">.NET core 2.1</span><span class="sxs-lookup"><span data-stu-id="20042-107">.NET Core 2.1</span></span>](#tab/netcore21)

```
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="20042-108">.NET core 2.0</span><span class="sxs-lookup"><span data-stu-id="20042-108">.NET Core 2.0</span></span>](#tab/netcore20)

```
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="20042-109">.NET core 1.x</span><span class="sxs-lookup"><span data-stu-id="20042-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="20042-110">Açıklama</span><span class="sxs-lookup"><span data-stu-id="20042-110">Description</span></span>

<span data-ttu-id="20042-111">`dotnet run` Komutu bir komut ile kaynak koddan uygulamanızı çalıştırmak için uygun bir seçenek sağlar.</span><span class="sxs-lookup"><span data-stu-id="20042-111">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="20042-112">Komut satırından hızlı yinelemeli geliştirme için kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="20042-112">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="20042-113">Komut bağımlı [ `dotnet build` ](dotnet-build.md) Kodu derlemek için komutu.</span><span class="sxs-lookup"><span data-stu-id="20042-113">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="20042-114">Derleme için tüm gereksinimleri, gibi proje gerekir geri ilk olarak, geçerli `dotnet run` de.</span><span class="sxs-lookup"><span data-stu-id="20042-114">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span>

<span data-ttu-id="20042-115">Çıktı dosyaları olan varsayılan konumuna yazılır `bin/<configuration>/<target>`.</span><span class="sxs-lookup"><span data-stu-id="20042-115">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="20042-116">Örneğin, varsa bir `netcoreapp2.1` ve uygulama çalıştırma `dotnet run`, çıkış yerleştirilir `bin/Debug/netcoreapp2.1`.</span><span class="sxs-lookup"><span data-stu-id="20042-116">For example if you have a `netcoreapp2.1` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp2.1`.</span></span> <span data-ttu-id="20042-117">Dosyaları gerektiği şekilde üzerine yazılır.</span><span class="sxs-lookup"><span data-stu-id="20042-117">Files are overwritten as needed.</span></span> <span data-ttu-id="20042-118">Geçici dosyalar yerleştirildiğinde `obj` dizin.</span><span class="sxs-lookup"><span data-stu-id="20042-118">Temporary files are placed in the `obj` directory.</span></span>

<span data-ttu-id="20042-119">Birden çok çerçeve proje belirtiyorsa, yürütme `dotnet run` sürece hatayla sonuçlanır `-f|--framework <FRAMEWORK>` seçeneği framework belirtmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="20042-119">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="20042-120">`dotnet run` Komut, projeler, derlenen bütünleştirilmiş kodlarda değil bağlamında kullanılır.</span><span class="sxs-lookup"><span data-stu-id="20042-120">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="20042-121">Framework bağımlı uygulama DLL yerine çalıştırılacak çalışıyorsanız, kullanmalısınız [dotnet](dotnet.md) olmadan bir komutu.</span><span class="sxs-lookup"><span data-stu-id="20042-121">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="20042-122">Örneğin, çalıştırılacak `myapp.dll`, kullanın:</span><span class="sxs-lookup"><span data-stu-id="20042-122">For example, to run `myapp.dll`, use:</span></span>

```console
dotnet myapp.dll
```

<span data-ttu-id="20042-123">Daha fazla bilgi için `dotnet` sürücüsü bkz [.NET Core komut satırı araçları (CLI)](index.md) konu.</span><span class="sxs-lookup"><span data-stu-id="20042-123">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="20042-124">Uygulamayı çalıştırmak için `dotnet run` komut paylaşılan çalışma zamanını şuradan NuGet önbelleğini dışında olan uygulama bağımlılıklarını çözümler.</span><span class="sxs-lookup"><span data-stu-id="20042-124">To run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="20042-125">Önbelleğe alınan bağımlılıkları kullandığından, onu kullanmak için önermedi `dotnet run` üretim uygulamaları çalıştırmak için.</span><span class="sxs-lookup"><span data-stu-id="20042-125">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="20042-126">Bunun yerine, [bir dağıtım yaratmanız](../deploying/index.md) kullanarak [ `dotnet publish` ](dotnet-publish.md) komut ve yayımlanan çıkış dağıtın.</span><span class="sxs-lookup"><span data-stu-id="20042-126">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a><span data-ttu-id="20042-127">Seçenekler</span><span class="sxs-lookup"><span data-stu-id="20042-127">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="20042-128">.NET core 2.1</span><span class="sxs-lookup"><span data-stu-id="20042-128">.NET Core 2.1</span></span>](#tab/netcore21)

`--`

<span data-ttu-id="20042-129">Bağımsız değişkenleri sınırlandırır `dotnet run` gelen çalıştırılan uygulama için bağımsız değişkenler.</span><span class="sxs-lookup"><span data-stu-id="20042-129">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="20042-130">Uygulamayı çalıştırmak için bu sınırlandırıcıdan sonra gelen tüm bağımsız değişkenler geçirilir.</span><span class="sxs-lookup"><span data-stu-id="20042-130">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="20042-131">Derleme yapılandırmasını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="20042-131">Defines the build configuration.</span></span> <span data-ttu-id="20042-132">Varsayılan değer `Debug` şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="20042-132">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="20042-133">Oluşturur ve belirtilen kullanarak uygulama çalışır [framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="20042-133">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="20042-134">Çerçeve proje dosyasında belirtilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="20042-134">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="20042-135">Son geri yükleme başarılı olduysa bile çözülmesi için tüm bağımlılıkların zorlar.</span><span class="sxs-lookup"><span data-stu-id="20042-135">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="20042-136">Bu bayrak belirten aynıdır silme *project.assets.json* dosya.</span><span class="sxs-lookup"><span data-stu-id="20042-136">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="20042-137">Komut için kısa bir Yardım yazdırır.</span><span class="sxs-lookup"><span data-stu-id="20042-137">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="20042-138">Başlatma adı profilini (varsa) uygulamayı başlatırken kullanılacak.</span><span class="sxs-lookup"><span data-stu-id="20042-138">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="20042-139">Başlatma profili tanımlanmış *launchSettings.json* dosya ve genellikle çağrıldığında `Development`, `Staging`, ve `Production`.</span><span class="sxs-lookup"><span data-stu-id="20042-139">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="20042-140">Daha fazla bilgi için [birden çok ortamla çalışma](/aspnet/core/fundamentals/environments).</span><span class="sxs-lookup"><span data-stu-id="20042-140">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="20042-141">Çalıştırmadan önce projeyi derle değil.</span><span class="sxs-lookup"><span data-stu-id="20042-141">Doesn't build the project before running.</span></span> <span data-ttu-id="20042-142">Ayrıca örtülü ayarlar `--no-restore` bayrağı.</span><span class="sxs-lookup"><span data-stu-id="20042-142">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="20042-143">Projeden projeye (P2P) başvurular içeren bir proje geri yüklerken, kök proje ve başvuruları geri yükler.</span><span class="sxs-lookup"><span data-stu-id="20042-143">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="20042-144">Kullanılacak çalışmaz *launchSettings.json* uygulamayı yapılandırmak için.</span><span class="sxs-lookup"><span data-stu-id="20042-144">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="20042-145">Örtük bir geri yükleme komutu çalıştırırken yürütülmez.</span><span class="sxs-lookup"><span data-stu-id="20042-145">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="20042-146">(Klasör adı veya tam yolu) çalıştırmak için proje dosyasının yolunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="20042-146">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="20042-147">Belirtilmezse, geçerli dizin için varsayılan olarak.</span><span class="sxs-lookup"><span data-stu-id="20042-147">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="20042-148">Paketleri geri yüklemek için hedef çalışma zamanı belirtir.</span><span class="sxs-lookup"><span data-stu-id="20042-148">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="20042-149">Çalışma zamanı tanımlayıcılarının (RID'ler) bir listesi için bkz. [RID Kataloğu](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="20042-149">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="20042-150">Komutun ayrıntı düzeyini ayarlar.</span><span class="sxs-lookup"><span data-stu-id="20042-150">Sets the verbosity level of the command.</span></span> <span data-ttu-id="20042-151">İzin verilen değerler `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, ve `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="20042-151">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="20042-152">.NET core 2.0</span><span class="sxs-lookup"><span data-stu-id="20042-152">.NET Core 2.0</span></span>](#tab/netcore20)

`--`

<span data-ttu-id="20042-153">Bağımsız değişkenleri sınırlandırır `dotnet run` gelen çalıştırılan uygulama için bağımsız değişkenler.</span><span class="sxs-lookup"><span data-stu-id="20042-153">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="20042-154">Uygulamayı çalıştırmak için bu sınırlandırıcıdan sonra gelen tüm bağımsız değişkenler geçirilir.</span><span class="sxs-lookup"><span data-stu-id="20042-154">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="20042-155">Derleme yapılandırmasını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="20042-155">Defines the build configuration.</span></span> <span data-ttu-id="20042-156">Varsayılan değer `Debug` şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="20042-156">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="20042-157">Oluşturur ve belirtilen kullanarak uygulama çalışır [framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="20042-157">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="20042-158">Çerçeve proje dosyasında belirtilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="20042-158">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="20042-159">Son geri yükleme başarılı olduysa bile çözülmesi için tüm bağımlılıkların zorlar.</span><span class="sxs-lookup"><span data-stu-id="20042-159">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="20042-160">Bu bayrak belirten aynıdır silme *project.assets.json* dosya.</span><span class="sxs-lookup"><span data-stu-id="20042-160">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="20042-161">Komut için kısa bir Yardım yazdırır.</span><span class="sxs-lookup"><span data-stu-id="20042-161">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="20042-162">Başlatma adı profilini (varsa) uygulamayı başlatırken kullanılacak.</span><span class="sxs-lookup"><span data-stu-id="20042-162">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="20042-163">Başlatma profili tanımlanmış *launchSettings.json* dosya ve genellikle çağrıldığında `Development`, `Staging`, ve `Production`.</span><span class="sxs-lookup"><span data-stu-id="20042-163">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="20042-164">Daha fazla bilgi için [birden çok ortamla çalışma](/aspnet/core/fundamentals/environments).</span><span class="sxs-lookup"><span data-stu-id="20042-164">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="20042-165">Çalıştırmadan önce projeyi derle değil.</span><span class="sxs-lookup"><span data-stu-id="20042-165">Doesn't build the project before running.</span></span> <span data-ttu-id="20042-166">Ayrıca örtülü ayarlar `--no-restore` bayrağı.</span><span class="sxs-lookup"><span data-stu-id="20042-166">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="20042-167">Projeden projeye (P2P) başvurular içeren bir proje geri yüklerken, kök proje ve başvuruları geri yükler.</span><span class="sxs-lookup"><span data-stu-id="20042-167">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="20042-168">Kullanılacak çalışmaz *launchSettings.json* uygulamayı yapılandırmak için.</span><span class="sxs-lookup"><span data-stu-id="20042-168">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="20042-169">Örtük bir geri yükleme komutu çalıştırırken yürütülmez.</span><span class="sxs-lookup"><span data-stu-id="20042-169">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="20042-170">(Klasör adı veya tam yolu) çalıştırmak için proje dosyasının yolunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="20042-170">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="20042-171">Belirtilmezse, geçerli dizin için varsayılan olarak.</span><span class="sxs-lookup"><span data-stu-id="20042-171">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="20042-172">Paketleri geri yüklemek için hedef çalışma zamanı belirtir.</span><span class="sxs-lookup"><span data-stu-id="20042-172">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="20042-173">Çalışma zamanı tanımlayıcılarının (RID'ler) bir listesi için bkz. [RID Kataloğu](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="20042-173">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="20042-174">.NET core 1.x</span><span class="sxs-lookup"><span data-stu-id="20042-174">.NET Core 1.x</span></span>](#tab/netcore1x)

`--`

<span data-ttu-id="20042-175">Bağımsız değişkenleri sınırlandırır `dotnet run` gelen çalıştırılan uygulama için bağımsız değişkenler.</span><span class="sxs-lookup"><span data-stu-id="20042-175">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="20042-176">Uygulamayı çalıştırmak için bu sınırlandırıcıdan sonra gelen tüm bağımsız değişkenler geçirilir.</span><span class="sxs-lookup"><span data-stu-id="20042-176">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="20042-177">Derleme yapılandırmasını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="20042-177">Defines the build configuration.</span></span> <span data-ttu-id="20042-178">Varsayılan değer `Debug` şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="20042-178">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="20042-179">Oluşturur ve belirtilen kullanarak uygulama çalışır [framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="20042-179">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="20042-180">Çerçeve proje dosyasında belirtilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="20042-180">The framework must be specified in the project file.</span></span>

`-h|--help`

<span data-ttu-id="20042-181">Komut için kısa bir Yardım yazdırır.</span><span class="sxs-lookup"><span data-stu-id="20042-181">Prints out a short help for the command.</span></span>

`-p|--project <PATH/PROJECT.csproj>`

<span data-ttu-id="20042-182">Proje dosyasının adını ve yolunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="20042-182">Specifies the path and name of the project file.</span></span> <span data-ttu-id="20042-183">(NOTA bakın.) Belirtilmezse, geçerli dizin için varsayılan olarak.</span><span class="sxs-lookup"><span data-stu-id="20042-183">(See the NOTE.) If not specified, it defaults to the current directory.</span></span>

> [!NOTE]
> <span data-ttu-id="20042-184">İle proje dosyasının adını ve yolunu kullanın `-p|--project` seçeneği.</span><span class="sxs-lookup"><span data-stu-id="20042-184">Use the path and name of the project file with the `-p|--project` option.</span></span> <span data-ttu-id="20042-185">CLI'teki bir gerileme, .NET Core SDK'sı ile bir klasör yolu sağlama engeller 1.x.</span><span class="sxs-lookup"><span data-stu-id="20042-185">A regression in the CLI prevents providing a folder path with .NET Core SDK 1.x.</span></span> <span data-ttu-id="20042-186">Bu sorun hakkında daha fazla bilgi için bkz. [dotnet -p çalıştırın (#5992 dotnet/CLI) bir proje başlayamaz](https://github.com/dotnet/cli/issues/5992).</span><span class="sxs-lookup"><span data-stu-id="20042-186">For more information about this issue, see [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span></span>

---

## <a name="examples"></a><span data-ttu-id="20042-187">Örnekler</span><span class="sxs-lookup"><span data-stu-id="20042-187">Examples</span></span>

<span data-ttu-id="20042-188">Projenin geçerli dizinde çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="20042-188">Run the project in the current directory:</span></span>

`dotnet run`

<span data-ttu-id="20042-189">Belirtilen projeyi çalıştır:</span><span class="sxs-lookup"><span data-stu-id="20042-189">Run the specified project:</span></span>

`dotnet run --project ./projects/proj1/proj1.csproj`

<span data-ttu-id="20042-190">Geçerli dizinde projeyi çalıştırın ( `--help` Bu örnekte bağımsız değişken boş beri uygulamaya geçirilir `--` seçeneği kullanıldığında):</span><span class="sxs-lookup"><span data-stu-id="20042-190">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the blank `--` option is used):</span></span>

`dotnet run --configuration Release -- --help`

<span data-ttu-id="20042-191">Bağımlılıklar ve geçerli dizinde proje için araçları çıkışını alır ve ardından projeyi çalıştırın, en az gösteren yalnızca geri yükleme: (.NET Core SDK 2.0 ve sonraki sürümler):</span><span class="sxs-lookup"><span data-stu-id="20042-191">Restore dependencies and tools for the project in the current directory only showing minimal output and then run the project: (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet run --verbosity m`