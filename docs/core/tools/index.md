---
title: .NET core komut satırı arabirimi (CLI) araçları
description: .NET Core komut satırı arabirimi (CLI) araçları ve özellikleri genel bakış.
ms.date: 08/14/2017
ms.custom: seodec18
ms.openlocfilehash: ff96023dd0b161271e146f7a7e69924c9db9e769
ms.sourcegitcommit: 4a3c95e91289d16c38979575a245a4f76b0da147
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2019
ms.locfileid: "67569525"
---
# <a name="net-core-command-line-interface-cli-tools"></a><span data-ttu-id="6c03e-103">.NET core komut satırı arabirimi (CLI) araçlarını</span><span class="sxs-lookup"><span data-stu-id="6c03e-103">.NET Core command-line interface (CLI) tools</span></span>

<span data-ttu-id="6c03e-104">.NET Core komut satırı arabirimi (CLI), .NET uygulamaları geliştirmek için yeni bir platformlar arası zincirinin ' dir.</span><span class="sxs-lookup"><span data-stu-id="6c03e-104">The .NET Core command-line interface (CLI) is a new cross-platform toolchain for developing .NET applications.</span></span> <span data-ttu-id="6c03e-105">Tümleşik geliştirme ortamlarından (IDE'ler), düzenleyiciler ve derleme düzenleyicileri tuttuğunuzda gibi CLI hangi üst düzey araçları temel altyapıdır.</span><span class="sxs-lookup"><span data-stu-id="6c03e-105">The CLI is a foundation upon which higher-level tools, such as Integrated Development Environments (IDEs), editors, and build orchestrators, can rest.</span></span>

## <a name="installation"></a><span data-ttu-id="6c03e-106">Yükleme</span><span class="sxs-lookup"><span data-stu-id="6c03e-106">Installation</span></span>

<span data-ttu-id="6c03e-107">Yerel yükleyicilerden kullanabilir veya yükleme Kabuk betikleri kullanın:</span><span class="sxs-lookup"><span data-stu-id="6c03e-107">Either use the native installers or use the installation shell scripts:</span></span>

* <span data-ttu-id="6c03e-108">Yerel yükleyicilerden öncelikle geliştiricinin makinelerde kullanılır ve desteklenen kullanımı her platformun yerel mekanizması, örneğin, Ubuntu veya MSI paketleri Windows üzerinde DEB paketleri yükleyin.</span><span class="sxs-lookup"><span data-stu-id="6c03e-108">The native installers are primarily used on developer's machines and use each supported platform's native install mechanism, for instance, DEB packages on Ubuntu or MSI bundles on Windows.</span></span> <span data-ttu-id="6c03e-109">Bu yükleyicilerden yükleyin ve geliştirici tarafından anında kullanmak için ortamı yapılandırmak ancak makinedeki yönetici ayrıcalıkları gerektirir.</span><span class="sxs-lookup"><span data-stu-id="6c03e-109">These installers install and configure the environment for immediate use by the developer but require administrative privileges on the machine.</span></span> <span data-ttu-id="6c03e-110">Yükleme yönergeleri görüntüleyebileceğiniz [.NET Core Yükleme Kılavuzu](https://aka.ms/dotnetcoregs).</span><span class="sxs-lookup"><span data-stu-id="6c03e-110">You can view the installation instructions in the [.NET Core installation guide](https://aka.ms/dotnetcoregs).</span></span>
* <span data-ttu-id="6c03e-111">Kabuk betikleri, öncelikle yapı sunucuları veya yönetici ayrıcalıklarına gerek kalmadan araçları yüklemek istediğiniz zaman ayarlamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="6c03e-111">Shell scripts are primarily used for setting up build servers or when you wish to install the tools without administrative privileges.</span></span> <span data-ttu-id="6c03e-112">Yükleme betikleri el ile yüklenmesi gereken makine Önkoşulları Yükleme yok.</span><span class="sxs-lookup"><span data-stu-id="6c03e-112">Install scripts don't install prerequisites on the machine, which must be installed manually.</span></span> <span data-ttu-id="6c03e-113">Daha fazla bilgi için [yükleme komut dosyası başvuru konusu](dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="6c03e-113">For more information, see the [install script reference topic](dotnet-install-script.md).</span></span> <span data-ttu-id="6c03e-114">Sürekli Tümleştirme (CI) yapılandırma sunucunuzda CLI'yı ayarlama hakkında daha fazla bilgi için bkz: [kullanarak .NET Core SDK'sı ve araçları, sürekli tümleştirme (CI)](using-ci-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="6c03e-114">For information on how to set up CLI on your continuous integration (CI) build server, see [Using .NET Core SDK and tools in Continuous Integration (CI)](using-ci-with-cli.md).</span></span>

<span data-ttu-id="6c03e-115">Varsayılan olarak, CLI yan yana (SxS) şekilde yüklediği CLI araçları birden çok sürümünü tek bir makinede bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="6c03e-115">By default, the CLI installs in a side-by-side (SxS) manner, so multiple versions of the CLI tools can coexist on a single machine.</span></span> <span data-ttu-id="6c03e-116">Birden çok sürümünün yüklü olduğu bir makinede kullanılan hangi sürümünü belirleme bölümünde daha ayrıntılı olarak açıklanmıştır [sürücü](#driver) bölümü.</span><span class="sxs-lookup"><span data-stu-id="6c03e-116">Determining which version is used on a machine where multiple versions are installed is explained in more detail in the [Driver](#driver) section.</span></span>

## <a name="cli-commands"></a><span data-ttu-id="6c03e-117">CLI komutları</span><span class="sxs-lookup"><span data-stu-id="6c03e-117">CLI commands</span></span>

<span data-ttu-id="6c03e-118">Aşağıdaki komutlar, varsayılan olarak yüklenir:</span><span class="sxs-lookup"><span data-stu-id="6c03e-118">The following commands are installed by default:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="6c03e-119">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="6c03e-119">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="6c03e-120">**Temel komutlar**</span><span class="sxs-lookup"><span data-stu-id="6c03e-120">**Basic commands**</span></span>

* [<span data-ttu-id="6c03e-121">new</span><span class="sxs-lookup"><span data-stu-id="6c03e-121">new</span></span>](dotnet-new.md)
* [<span data-ttu-id="6c03e-122">restore</span><span class="sxs-lookup"><span data-stu-id="6c03e-122">restore</span></span>](dotnet-restore.md)
* [<span data-ttu-id="6c03e-123">Derleme</span><span class="sxs-lookup"><span data-stu-id="6c03e-123">build</span></span>](dotnet-build.md)
* [<span data-ttu-id="6c03e-124">Yayımlama</span><span class="sxs-lookup"><span data-stu-id="6c03e-124">publish</span></span>](dotnet-publish.md)
* [<span data-ttu-id="6c03e-125">run</span><span class="sxs-lookup"><span data-stu-id="6c03e-125">run</span></span>](dotnet-run.md)
* [<span data-ttu-id="6c03e-126">Test</span><span class="sxs-lookup"><span data-stu-id="6c03e-126">test</span></span>](dotnet-test.md)
* [<span data-ttu-id="6c03e-127">vstest</span><span class="sxs-lookup"><span data-stu-id="6c03e-127">vstest</span></span>](dotnet-vstest.md)
* [<span data-ttu-id="6c03e-128">pack</span><span class="sxs-lookup"><span data-stu-id="6c03e-128">pack</span></span>](dotnet-pack.md)
* [<span data-ttu-id="6c03e-129">Geçirme</span><span class="sxs-lookup"><span data-stu-id="6c03e-129">migrate</span></span>](dotnet-migrate.md)
* [<span data-ttu-id="6c03e-130">Temizleme</span><span class="sxs-lookup"><span data-stu-id="6c03e-130">clean</span></span>](dotnet-clean.md)
* [<span data-ttu-id="6c03e-131">sln</span><span class="sxs-lookup"><span data-stu-id="6c03e-131">sln</span></span>](dotnet-sln.md)
* [<span data-ttu-id="6c03e-132">Yardım</span><span class="sxs-lookup"><span data-stu-id="6c03e-132">help</span></span>](dotnet-help.md)
* [<span data-ttu-id="6c03e-133">Store</span><span class="sxs-lookup"><span data-stu-id="6c03e-133">store</span></span>](dotnet-store.md)

<span data-ttu-id="6c03e-134">**Proje değişikliği komutları**</span><span class="sxs-lookup"><span data-stu-id="6c03e-134">**Project modification commands**</span></span>

* [<span data-ttu-id="6c03e-135">Paket Ekle</span><span class="sxs-lookup"><span data-stu-id="6c03e-135">add package</span></span>](dotnet-add-package.md)
* [<span data-ttu-id="6c03e-136">Başvuru ekleme</span><span class="sxs-lookup"><span data-stu-id="6c03e-136">add reference</span></span>](dotnet-add-reference.md)
* [<span data-ttu-id="6c03e-137">Paketi Kaldır</span><span class="sxs-lookup"><span data-stu-id="6c03e-137">remove package</span></span>](dotnet-remove-package.md)
* [<span data-ttu-id="6c03e-138">başvuru Kaldır</span><span class="sxs-lookup"><span data-stu-id="6c03e-138">remove reference</span></span>](dotnet-remove-reference.md)
* [<span data-ttu-id="6c03e-139">Liste başvurusu</span><span class="sxs-lookup"><span data-stu-id="6c03e-139">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="6c03e-140">**Gelişmiş komutları**</span><span class="sxs-lookup"><span data-stu-id="6c03e-140">**Advanced commands**</span></span>

* [<span data-ttu-id="6c03e-141">nuget Sil</span><span class="sxs-lookup"><span data-stu-id="6c03e-141">nuget delete</span></span>](dotnet-nuget-delete.md)
* [<span data-ttu-id="6c03e-142">nuget yerel öğeler</span><span class="sxs-lookup"><span data-stu-id="6c03e-142">nuget locals</span></span>](dotnet-nuget-locals.md)
* [<span data-ttu-id="6c03e-143">nuget anında iletme</span><span class="sxs-lookup"><span data-stu-id="6c03e-143">nuget push</span></span>](dotnet-nuget-push.md)
* [<span data-ttu-id="6c03e-144">MSBuild</span><span class="sxs-lookup"><span data-stu-id="6c03e-144">msbuild</span></span>](dotnet-msbuild.md)
* [<span data-ttu-id="6c03e-145">DotNet yükleme betiği</span><span class="sxs-lookup"><span data-stu-id="6c03e-145">dotnet install script</span></span>](dotnet-install-script.md)

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6c03e-146">.NET core 1.x</span><span class="sxs-lookup"><span data-stu-id="6c03e-146">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="6c03e-147">**Temel komutlar**</span><span class="sxs-lookup"><span data-stu-id="6c03e-147">**Basic commands**</span></span>

* [<span data-ttu-id="6c03e-148">new</span><span class="sxs-lookup"><span data-stu-id="6c03e-148">new</span></span>](dotnet-new.md)
* [<span data-ttu-id="6c03e-149">restore</span><span class="sxs-lookup"><span data-stu-id="6c03e-149">restore</span></span>](dotnet-restore.md)
* [<span data-ttu-id="6c03e-150">Derleme</span><span class="sxs-lookup"><span data-stu-id="6c03e-150">build</span></span>](dotnet-build.md)
* [<span data-ttu-id="6c03e-151">Yayımlama</span><span class="sxs-lookup"><span data-stu-id="6c03e-151">publish</span></span>](dotnet-publish.md)
* [<span data-ttu-id="6c03e-152">run</span><span class="sxs-lookup"><span data-stu-id="6c03e-152">run</span></span>](dotnet-run.md)
* [<span data-ttu-id="6c03e-153">Test</span><span class="sxs-lookup"><span data-stu-id="6c03e-153">test</span></span>](dotnet-test.md)
* [<span data-ttu-id="6c03e-154">vstest</span><span class="sxs-lookup"><span data-stu-id="6c03e-154">vstest</span></span>](dotnet-vstest.md)
* [<span data-ttu-id="6c03e-155">pack</span><span class="sxs-lookup"><span data-stu-id="6c03e-155">pack</span></span>](dotnet-pack.md)
* [<span data-ttu-id="6c03e-156">Geçirme</span><span class="sxs-lookup"><span data-stu-id="6c03e-156">migrate</span></span>](dotnet-migrate.md)
* [<span data-ttu-id="6c03e-157">Temizleme</span><span class="sxs-lookup"><span data-stu-id="6c03e-157">clean</span></span>](dotnet-clean.md)
* [<span data-ttu-id="6c03e-158">sln</span><span class="sxs-lookup"><span data-stu-id="6c03e-158">sln</span></span>](dotnet-sln.md)

<span data-ttu-id="6c03e-159">**Proje değişikliği komutları**</span><span class="sxs-lookup"><span data-stu-id="6c03e-159">**Project modification commands**</span></span>

* [<span data-ttu-id="6c03e-160">Paket Ekle</span><span class="sxs-lookup"><span data-stu-id="6c03e-160">add package</span></span>](dotnet-add-package.md)
* [<span data-ttu-id="6c03e-161">Başvuru ekleme</span><span class="sxs-lookup"><span data-stu-id="6c03e-161">add reference</span></span>](dotnet-add-reference.md)
* [<span data-ttu-id="6c03e-162">Paketi Kaldır</span><span class="sxs-lookup"><span data-stu-id="6c03e-162">remove package</span></span>](dotnet-remove-package.md)
* [<span data-ttu-id="6c03e-163">başvuru Kaldır</span><span class="sxs-lookup"><span data-stu-id="6c03e-163">remove reference</span></span>](dotnet-remove-reference.md)
* [<span data-ttu-id="6c03e-164">Liste başvurusu</span><span class="sxs-lookup"><span data-stu-id="6c03e-164">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="6c03e-165">**Gelişmiş komutları**</span><span class="sxs-lookup"><span data-stu-id="6c03e-165">**Advanced commands**</span></span>

* [<span data-ttu-id="6c03e-166">nuget Sil</span><span class="sxs-lookup"><span data-stu-id="6c03e-166">nuget delete</span></span>](dotnet-nuget-delete.md)
* [<span data-ttu-id="6c03e-167">nuget yerel öğeler</span><span class="sxs-lookup"><span data-stu-id="6c03e-167">nuget locals</span></span>](dotnet-nuget-locals.md)
* [<span data-ttu-id="6c03e-168">nuget anında iletme</span><span class="sxs-lookup"><span data-stu-id="6c03e-168">nuget push</span></span>](dotnet-nuget-push.md)
* [<span data-ttu-id="6c03e-169">MSBuild</span><span class="sxs-lookup"><span data-stu-id="6c03e-169">msbuild</span></span>](dotnet-msbuild.md)
* [<span data-ttu-id="6c03e-170">DotNet yükleme betiği</span><span class="sxs-lookup"><span data-stu-id="6c03e-170">dotnet install script</span></span>](dotnet-install-script.md)

---

<span data-ttu-id="6c03e-171">CLI'yı projeleriniz için ek araçlar belirtmenizi sağlar bir genişletilebilirlik modeli devralır.</span><span class="sxs-lookup"><span data-stu-id="6c03e-171">The CLI adopts an extensibility model that allows you to specify additional tools for your projects.</span></span> <span data-ttu-id="6c03e-172">Daha fazla bilgi için [.NET Core CLI genişletilebilirlik modeli](extensibility.md) konu.</span><span class="sxs-lookup"><span data-stu-id="6c03e-172">For more information, see the [.NET Core CLI extensibility model](extensibility.md) topic.</span></span>

## <a name="command-structure"></a><span data-ttu-id="6c03e-173">Komut yapısı</span><span class="sxs-lookup"><span data-stu-id="6c03e-173">Command structure</span></span>

<span data-ttu-id="6c03e-174">CLI komut yapısını oluşur [("dotnet") sürücü](#driver), [komutu](#command)ve büyük olasılıkla komut [bağımsız değişkenleri](#arguments) ve [seçenekleri](#options).</span><span class="sxs-lookup"><span data-stu-id="6c03e-174">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="6c03e-175">Adlı bir dizinden çalıştırıldığında Göster yeni bir konsol uygulaması oluşturma ve aşağıdaki komutları komut satırından çalıştırma gibi çoğu CLI işlemi bu düzende gördüğünüz *my_app_3.sft*:</span><span class="sxs-lookup"><span data-stu-id="6c03e-175">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="6c03e-176">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="6c03e-176">.NET Core 2.x</span></span>](#tab/netcore2x)

```console
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6c03e-177">.NET core 1.x</span><span class="sxs-lookup"><span data-stu-id="6c03e-177">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new console
dotnet restore
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

---

### <a name="driver"></a><span data-ttu-id="6c03e-178">Sürücü</span><span class="sxs-lookup"><span data-stu-id="6c03e-178">Driver</span></span>

<span data-ttu-id="6c03e-179">Sürücü adlı [dotnet](dotnet.md) ve iki sorumlulukları, ya da çalışan bir [framework bağımlı uygulama](../deploying/index.md) veya bir komut yürütülüyor.</span><span class="sxs-lookup"><span data-stu-id="6c03e-179">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span> 

<span data-ttu-id="6c03e-180">Framework bağımlı uygulamayı çalıştırın, sonra sürücüsü, örneğin, uygulamayı belirtmek için `dotnet /path/to/my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="6c03e-180">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="6c03e-181">Uygulamanın DLL bulunduğu klasörün komutu yürütülürken, yalnızca yürütme `dotnet my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="6c03e-181">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="6c03e-182">Belirli bir .NET Core çalışma zamanı sürümünü kullanmak istiyorsanız, kullanın `--fx-version <VERSION>` seçeneği (bkz [dotnet komut](dotnet.md) başvuru).</span><span class="sxs-lookup"><span data-stu-id="6c03e-182">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="6c03e-183">Sürücü komut sağladığında `dotnet.exe` CLI komut yürütme işlemi başlatır.</span><span class="sxs-lookup"><span data-stu-id="6c03e-183">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="6c03e-184">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="6c03e-184">For example:</span></span>

```bash
> dotnet build
```

<span data-ttu-id="6c03e-185">İlk olarak, sürücü kullanmak için SDK'sı sürümünü belirler.</span><span class="sxs-lookup"><span data-stu-id="6c03e-185">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="6c03e-186">Yoksa hiçbir ['global.json'](global-json.md), kullanılabilir SDK'sının en son sürümü kullanılır.</span><span class="sxs-lookup"><span data-stu-id="6c03e-186">If there is no ['global.json'](global-json.md), the latest version of the SDK available is used.</span></span> <span data-ttu-id="6c03e-187">Bu bir önizleme veya kararlı bir sürüm makinede en son nedir bağlı olarak, olabilir.</span><span class="sxs-lookup"><span data-stu-id="6c03e-187">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="6c03e-188">SDK sürümü belirlendikten sonra komutu yürütür.</span><span class="sxs-lookup"><span data-stu-id="6c03e-188">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="6c03e-189">Komut</span><span class="sxs-lookup"><span data-stu-id="6c03e-189">Command</span></span>

<span data-ttu-id="6c03e-190">Komutu, bir eylem gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="6c03e-190">The command performs an action.</span></span> <span data-ttu-id="6c03e-191">Örneğin, `dotnet build` kod oluşturur.</span><span class="sxs-lookup"><span data-stu-id="6c03e-191">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="6c03e-192">`dotnet publish` kod yayımlar.</span><span class="sxs-lookup"><span data-stu-id="6c03e-192">`dotnet publish` publishes code.</span></span> <span data-ttu-id="6c03e-193">Konsolunu kullanarak bir uygulama olarak komutlar uygulanan bir `dotnet {command}` kuralı.</span><span class="sxs-lookup"><span data-stu-id="6c03e-193">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="6c03e-194">Arguments</span><span class="sxs-lookup"><span data-stu-id="6c03e-194">Arguments</span></span>

<span data-ttu-id="6c03e-195">Çağrılan komut bağımsız değişkenleri komut satırında geçirdiğiniz bağımsız değişkenler.</span><span class="sxs-lookup"><span data-stu-id="6c03e-195">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="6c03e-196">Yürüttüğünüzde örneğin `dotnet publish my_app.csproj`, `my_app.csproj` bağımsız değişken geçirilir ve yayımlanacak projeyi belirtir `publish` komutu.</span><span class="sxs-lookup"><span data-stu-id="6c03e-196">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="6c03e-197">Seçenekler</span><span class="sxs-lookup"><span data-stu-id="6c03e-197">Options</span></span>

<span data-ttu-id="6c03e-198">Komut satırında geçirdiğiniz çağrılan komut seçenekleri seçeneklerdir.</span><span class="sxs-lookup"><span data-stu-id="6c03e-198">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="6c03e-199">Yürüttüğünüzde örneğin `dotnet publish --output /build_output`, `--output` seçeneği ve değerini geçirilir `publish` komutu.</span><span class="sxs-lookup"><span data-stu-id="6c03e-199">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="migration-from-projectjson"></a><span data-ttu-id="6c03e-200">Project.json geçiş</span><span class="sxs-lookup"><span data-stu-id="6c03e-200">Migration from project.json</span></span>

<span data-ttu-id="6c03e-201">Preview 2'de üretmek için kullanılan *project.json*-tabanlı projeler başvurun [dotnet geçirme](dotnet-migrate.md) projenizi MSBuild'e geçirme hakkında bilgi için konu / *.csproj*yayın araçları ile kullanmak için.</span><span class="sxs-lookup"><span data-stu-id="6c03e-201">If you used Preview 2 tooling to produce *project.json*-based projects, consult the [dotnet migrate](dotnet-migrate.md) topic for information on migrating your project to MSBuild/*.csproj* for use with release tooling.</span></span> <span data-ttu-id="6c03e-202">.NET Core için Önizleme 2 araçlarının sürümden önce ya da el ile oluşturulan projeleri kılavuzunda aşağıdaki proje güncelleştirmesi [: .NET Core CLI (project.json) DNX'ten geçiş](../migration/from-dnx.md) ve ardından `dotnet migrate` veya doğrudan yükseltme projelerinizi.</span><span class="sxs-lookup"><span data-stu-id="6c03e-202">For .NET Core projects created prior to the release of Preview 2 tooling, either manually update the project following the guidance in [Migrating from DNX to .NET Core CLI (project.json)](../migration/from-dnx.md) and then use `dotnet migrate` or directly upgrade your projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c03e-203">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="6c03e-203">See also</span></span>

- [<span data-ttu-id="6c03e-204">DotNet/CLI GitHub deposu</span><span class="sxs-lookup"><span data-stu-id="6c03e-204">dotnet/CLI GitHub Repository</span></span>](https://github.com/dotnet/cli/)
- [<span data-ttu-id="6c03e-205">.NET core Yükleme Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="6c03e-205">.NET Core installation guide</span></span>](https://aka.ms/dotnetcoregs)
