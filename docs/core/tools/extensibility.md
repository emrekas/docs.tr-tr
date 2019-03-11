---
title: .NET core CLI genişletilebilirlik modeli
description: Komut satırı arabirimi (CLI) araçlarını nasıl genişletebileceğinizi öğreneceğiz.
ms.date: 04/12/2017
ms.custom: seodec18
ms.openlocfilehash: ca6bf30fb6aaf815a859a00bc391ef790566acaf
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675101"
---
# <a name="net-core-cli-tools-extensibility-model"></a><span data-ttu-id="31de3-103">.NET core CLI araçları genişletilebilirlik modeli</span><span class="sxs-lookup"><span data-stu-id="31de3-103">.NET Core CLI tools extensibility model</span></span>

<span data-ttu-id="31de3-104">Bu belgede, .NET Core komut satırı arabirimi (CLI) araçlarını genişletmek ve her biri sürücü senaryoları açıklayın farklı yöntemleri kapsar.</span><span class="sxs-lookup"><span data-stu-id="31de3-104">This document covers the different ways you can extend the .NET Core Command-line Interface (CLI) tools and explain the scenarios that drive each one of them.</span></span>
<span data-ttu-id="31de3-105">Araçları kullanma ve bunun yanı sıra farklı türlerde araçlar oluşturma görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="31de3-105">You'll see how to consume the tools as well as how to build the different types of tools.</span></span>

## <a name="how-to-extend-cli-tools"></a><span data-ttu-id="31de3-106">CLI araçlarını genişletme</span><span class="sxs-lookup"><span data-stu-id="31de3-106">How to extend CLI tools</span></span>
<span data-ttu-id="31de3-107">CLI araçları üç temel şekilde genişletilebilir:</span><span class="sxs-lookup"><span data-stu-id="31de3-107">The CLI tools can be extended in three main ways:</span></span>

1. [<span data-ttu-id="31de3-108">Proje başına temelinde NuGet paketleri</span><span class="sxs-lookup"><span data-stu-id="31de3-108">Via NuGet packages on a per-project basis</span></span>](#per-project-based-extensibility)

   <span data-ttu-id="31de3-109">Proje başına araçları projenin bağlamı içinde yer alır, ancak geri yükleme yoluyla kolay yükleme sağlarlar.</span><span class="sxs-lookup"><span data-stu-id="31de3-109">Per-project tools are contained within the project's context, but they allow easy installation through restoration.</span></span>

2. [<span data-ttu-id="31de3-110">Özel hedefleri NuGet paketleri</span><span class="sxs-lookup"><span data-stu-id="31de3-110">Via NuGet packages with custom targets</span></span>](#custom-targets)

   <span data-ttu-id="31de3-111">Özel hedefleri özel görevleri birlikte derleme işlemini kolayca genişletmenizi sağlar.</span><span class="sxs-lookup"><span data-stu-id="31de3-111">Custom targets allow you to easily extend the build process with custom tasks.</span></span>

3. [<span data-ttu-id="31de3-112">Sistem yolu</span><span class="sxs-lookup"><span data-stu-id="31de3-112">Via the system's PATH</span></span>](#path-based-extensibility)

   <span data-ttu-id="31de3-113">YOL tabanlı araçlar, tek bir makinede kullanılabilir olan genel, projeler arası araçlar için uygundur.</span><span class="sxs-lookup"><span data-stu-id="31de3-113">PATH-based tools are good for general, cross-project tools that are usable on a single machine.</span></span>

<span data-ttu-id="31de3-114">Yukarıda özetlenen, üç genişletilebilirlik mekanizması dışlamaz.</span><span class="sxs-lookup"><span data-stu-id="31de3-114">The three extensibility mechanisms outlined above are not exclusive.</span></span> <span data-ttu-id="31de3-115">Bir ya da tamamını kullanabilirsiniz veya onları birleşimi.</span><span class="sxs-lookup"><span data-stu-id="31de3-115">You can use one, or all, or a combination of them.</span></span> <span data-ttu-id="31de3-116">Hangisinin seçmek için büyük ölçüde uzantınız ile elde etmek çalıştığınız hedef bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="31de3-116">Which one to pick depends largely on the goal you are trying to achieve with your extension.</span></span>

## <a name="per-project-based-extensibility"></a><span data-ttu-id="31de3-117">Proje başına tabanlı genişletilebilirliği</span><span class="sxs-lookup"><span data-stu-id="31de3-117">Per-project based extensibility</span></span>
<span data-ttu-id="31de3-118">Proje başına Araçlar [framework bağımlı dağıtımları](../deploying/index.md#framework-dependent-deployments-fdd) NuGet paketleri olarak dağıtılır.</span><span class="sxs-lookup"><span data-stu-id="31de3-118">Per-project tools are [framework-dependent deployments](../deploying/index.md#framework-dependent-deployments-fdd) that are distributed as NuGet packages.</span></span> <span data-ttu-id="31de3-119">Araçlar, yalnızca onlara başvuran ve bunlar geri yüklenir, proje bağlamında kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="31de3-119">Tools are only available in the context of the project that references them and for which they are restored.</span></span> <span data-ttu-id="31de3-120">Komut bulunamadığı için (örneğin, projesini içeren dizin dışında) bir projenin bağlamı dışında çağırma başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="31de3-120">Invocation outside of the context of the project (for example, outside of the directory that contains the project) will fail because the command cannot be found.</span></span>

<span data-ttu-id="31de3-121">Proje dosyası dışında bir şey gerekli olmadığından bu araçlar, derleme sunucuları için mükemmeldir.</span><span class="sxs-lookup"><span data-stu-id="31de3-121">These tools are perfect for build servers, since nothing outside of the project file is needed.</span></span> <span data-ttu-id="31de3-122">Derleme işlem çalıştırmalarını derlemeler geri için proje ve araçlar kullanılabilir olacak.</span><span class="sxs-lookup"><span data-stu-id="31de3-122">The build process runs restore for the project it builds and tools will be available.</span></span> <span data-ttu-id="31de3-123">Gibi dil projeleri F#, ayrıca bu kategorideki, çünkü her proje yalnızca belirli bir dilde yazılabilir.</span><span class="sxs-lookup"><span data-stu-id="31de3-123">Language projects, such as F#, are also in this category since each project can only be written in one specific language.</span></span>

<span data-ttu-id="31de3-124">Son olarak, bu genişletilebilirlik modeli proje çıkışı erişmesi gereken araçları oluşturulması için destek sağlar.</span><span class="sxs-lookup"><span data-stu-id="31de3-124">Finally, this extensibility model provides support for creation of tools that need access to the built output of the project.</span></span> <span data-ttu-id="31de3-125">Örneğin, çeşitli Razor Görünüm Araçları [ASP.NET](https://www.asp.net/) MVC uygulamaları bu kategoriye girer.</span><span class="sxs-lookup"><span data-stu-id="31de3-125">For instance, various Razor view tools in [ASP.NET](https://www.asp.net/) MVC applications fall into this category.</span></span>

### <a name="consuming-per-project-tools"></a><span data-ttu-id="31de3-126">Proje başına araçları kullanma</span><span class="sxs-lookup"><span data-stu-id="31de3-126">Consuming per-project tools</span></span>
<span data-ttu-id="31de3-127">Bu araçlar kullanan gerektirir eklemek bir `<DotNetCliToolReference>` proje dosyanıza kullanmak istediğiniz her aracı için öğesi.</span><span class="sxs-lookup"><span data-stu-id="31de3-127">Consuming these tools requires you to add a `<DotNetCliToolReference>` element to your project file for each tool you want to use.</span></span> <span data-ttu-id="31de3-128">İçinde `<DotNetCliToolReference>` öğesi, araç bulunduğu paket başvurusu ve ihtiyacınız olan sürümü belirtin.</span><span class="sxs-lookup"><span data-stu-id="31de3-128">Inside the `<DotNetCliToolReference>` element, you reference the package in which the tool resides and specify the version you need.</span></span> <span data-ttu-id="31de3-129">Çalıştırdıktan sonra [ `dotnet restore` ](dotnet-restore.md), Aracı'nı ve bağımlılıklarını geri yüklenir.</span><span class="sxs-lookup"><span data-stu-id="31de3-129">After running [`dotnet restore`](dotnet-restore.md), the tool and its dependencies are restored.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="31de3-130">Proje yürütme için yapı çıkışını yüklemek için gereken araçları için normal bağımlılıkları proje dosyasında altında listelenen genellikle başka bir bağımlılık yoktur.</span><span class="sxs-lookup"><span data-stu-id="31de3-130">For tools that need to load the build output of the project for execution, there is usually another dependency which is listed under the regular dependencies in the project file.</span></span> <span data-ttu-id="31de3-131">CLI, yapı altyapısı olarak MSBuild kullandığından, bu aracın bölümlerini özel MSBuild yazılması öneririz [hedefleri](/visualstudio/msbuild/msbuild-targets) ve [görevleri](/visualstudio/msbuild/msbuild-tasks), sonra bunlar daha sonra genel derleme işleminde yer alabilir.</span><span class="sxs-lookup"><span data-stu-id="31de3-131">Since CLI uses MSBuild as its build engine, we recommend that these parts of the tool be written as custom MSBuild [targets](/visualstudio/msbuild/msbuild-targets) and [tasks](/visualstudio/msbuild/msbuild-tasks), since they can then take part in the overall build process.</span></span> <span data-ttu-id="31de3-132">Ayrıca, bunlar alabilirsiniz kolayca çıktı dosyalarının konumu gibi yapılandırma yoluyla oluşturulmakta olan geçerli yapılandırmasını üretilen tüm veriler, vb. Bu bilgiler, herhangi bir hedef okunabilir MSBuild özellikleri kümesi olur.</span><span class="sxs-lookup"><span data-stu-id="31de3-132">Also, they can get any and all data easily that is produced via the build, such as the location of the output files, the current configuration being built, etc. All this information becomes a set of MSBuild properties that can be read from any target.</span></span> <span data-ttu-id="31de3-133">NuGet kullanarak bu belgede daha sonra özel bir hedef ekleme görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="31de3-133">You can see how to add a custom target using NuGet later in this document.</span></span>

<span data-ttu-id="31de3-134">Basit bir proje için basit bir salt araçları aracı ekleme örneği gözden geçirelim.</span><span class="sxs-lookup"><span data-stu-id="31de3-134">Let's review an example of adding a simple tools-only tool to a simple project.</span></span> <span data-ttu-id="31de3-135">Adlı bir örnek komut verilen `dotnet-api-search` belirtilen API'si aracılığıyla NuGet paketlerinin aramanıza olanak sağlayan, bu aracı kullanan bir konsol uygulamasının proje dosyası şu şekildedir:</span><span class="sxs-lookup"><span data-stu-id="31de3-135">Given an example command called `dotnet-api-search` that allows you to search through the NuGet packages for the specified API, here is a console application's project file that uses that tool:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>

  <!-- The tools reference -->
  <ItemGroup>
    <DotNetCliToolReference Include="dotnet-api-search" Version="1.0.0" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="31de3-136">`<DotNetCliToolReference>` Öğesi benzer bir şekilde yapılandırıldığı `<PackageReference>` öğesi.</span><span class="sxs-lookup"><span data-stu-id="31de3-136">The `<DotNetCliToolReference>` element is structured in a similar way as the `<PackageReference>` element.</span></span> <span data-ttu-id="31de3-137">Bu, geri yüklemek için araç ve sürümü içeren paketin paket kimliği gerekiyor.</span><span class="sxs-lookup"><span data-stu-id="31de3-137">It needs the package ID of the package containing the tool and its version to be able to restore.</span></span>

### <a name="building-tools"></a><span data-ttu-id="31de3-138">Yapı araçları</span><span class="sxs-lookup"><span data-stu-id="31de3-138">Building tools</span></span>
<span data-ttu-id="31de3-139">Belirtildiği gibi yalnızca taşınabilir konsol uygulamaları araçlardır.</span><span class="sxs-lookup"><span data-stu-id="31de3-139">As mentioned, tools are just portable console applications.</span></span> <span data-ttu-id="31de3-140">Diğer bir konsol uygulaması oluşturmayı tercih gibi araçları oluşturun.</span><span class="sxs-lookup"><span data-stu-id="31de3-140">You build tools as you would build any other console application.</span></span>
<span data-ttu-id="31de3-141">Bunu derledikten sonra kullandığınız [ `dotnet pack` ](dotnet-pack.md) vb. kodunuzu, bağımlılıkları hakkında bilgi içeren bir NuGet paketi (.nupkg dosyası) oluşturmak için komutu.</span><span class="sxs-lookup"><span data-stu-id="31de3-141">After you build it, you use the [`dotnet pack`](dotnet-pack.md) command to create a NuGet package (.nupkg file) that contains your code, information about its dependencies, and so on.</span></span> <span data-ttu-id="31de3-142">Paket, ancak içindeki ikili gerçek aracı uygulama için istediğiniz adı verebilirsiniz, kuralı için uygun olan `dotnet-<command>` sırayla `dotnet` onu çağırmak için.</span><span class="sxs-lookup"><span data-stu-id="31de3-142">You can give any name to the package, but the application inside, the actual tool binary, has to conform to the convention of `dotnet-<command>` in order for `dotnet` to be able to invoke it.</span></span>

> [!NOTE]
> <span data-ttu-id="31de3-143">.NET Core komut satırı araçları RC3 öncesi sürümlerinde `dotnet pack` komut neden bir hata vardı `runtime.config.json` aracıyla değil ve heyecanla.</span><span class="sxs-lookup"><span data-stu-id="31de3-143">In pre-RC3 versions of the .NET Core command-line tools, the `dotnet pack` command had a bug that caused the `runtime.config.json` to not be packed with the tool.</span></span> <span data-ttu-id="31de3-144">Çalışma zamanı hatalarını, dosya sonuçlarında eksik.</span><span class="sxs-lookup"><span data-stu-id="31de3-144">Lacking that file results in errors at runtime.</span></span> <span data-ttu-id="31de3-145">Bu davranış karşılaşırsanız, en son araçları ve deneyin güncelleştirdiğinizden emin olması `dotnet pack` yeniden.</span><span class="sxs-lookup"><span data-stu-id="31de3-145">If you encounter this behavior, be sure to update to the latest tooling and try the `dotnet pack` again.</span></span>

<span data-ttu-id="31de3-146">Aracı'nı kullanan kullanıcı, Araçlar taşınabilir uygulamaları olduğundan, aracı çalıştırmak için aracın derlendiği .NET Core kitaplıkları sürümüne sahip olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="31de3-146">Since tools are portable applications, the user consuming the tool must have the version of the .NET Core libraries that the tool was built against in order to run the tool.</span></span> <span data-ttu-id="31de3-147">Aracı tarafından kullanılan ve yer almıyor, .NET Core kitaplıkları içinde herhangi bir bağımlılık geri ve NuGet önbelleğine yerleştirilmesi.</span><span class="sxs-lookup"><span data-stu-id="31de3-147">Any other dependency that the tool uses and that is not contained within the .NET Core libraries is restored and placed in the NuGet cache.</span></span> <span data-ttu-id="31de3-148">Tüm aracı bu nedenle, .NET Core kitaplıkları derlemelerden yanı sıra derlemeleri NuGet önbellekten kullanarak Çalıştır.</span><span class="sxs-lookup"><span data-stu-id="31de3-148">The entire tool is, therefore, run using the assemblies from the .NET Core libraries as well as assemblies from the NuGet cache.</span></span>

<span data-ttu-id="31de3-149">Bu tür araçların bunları kullanan projenin bağımlılık grafı denetiminin dışında tamamen ayrı olan bir bağımlılık grafiği vardır.</span><span class="sxs-lookup"><span data-stu-id="31de3-149">These kinds of tools have a dependency graph that is completely separate from the dependency graph of the project that uses them.</span></span> <span data-ttu-id="31de3-150">Geri yükleme işlemi önce projenin bağımlılıkları yükler ve her biri araçları ve bunların bağımlılıklarını yükler.</span><span class="sxs-lookup"><span data-stu-id="31de3-150">The restore process first restores the project's dependencies and then restores each of the tools and their dependencies.</span></span>

<span data-ttu-id="31de3-151">Daha zengin örnekler ve bu farklı birleşimlerini bulabilirsiniz [.NET Core CLI depo](https://github.com/dotnet/cli/tree/release/2.1/TestAssets/TestProjects).</span><span class="sxs-lookup"><span data-stu-id="31de3-151">You can find richer examples and different combinations of this in the [.NET Core CLI repo](https://github.com/dotnet/cli/tree/release/2.1/TestAssets/TestProjects).</span></span>
<span data-ttu-id="31de3-152">Ayrıca bkz [kullanılan araçları uygulaması](https://github.com/dotnet/cli/tree/release/2.1/TestAssets/TestPackages) aynı depodaki.</span><span class="sxs-lookup"><span data-stu-id="31de3-152">You can also see the [implementation of tools used](https://github.com/dotnet/cli/tree/release/2.1/TestAssets/TestPackages) in the same repo.</span></span>

## <a name="custom-targets"></a><span data-ttu-id="31de3-153">Özel hedefleri</span><span class="sxs-lookup"><span data-stu-id="31de3-153">Custom targets</span></span>
<span data-ttu-id="31de3-154">NuGet yeteneğine sahip [paket özel MSBuild hedeflerini ve özellik dosyalarını](/nuget/create-packages/creating-a-package#including-msbuild-props-and-targets-in-a-package).</span><span class="sxs-lookup"><span data-stu-id="31de3-154">NuGet has the capability to [package custom MSBuild targets and props files](/nuget/create-packages/creating-a-package#including-msbuild-props-and-targets-in-a-package).</span></span> <span data-ttu-id="31de3-155">.NET Core CLI araçları, MSBuild kullanmak için taşıma ile aynı mekanizması genişletilebilirlik artık .NET Core projeleri için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="31de3-155">With the move of the .NET Core CLI tools to use MSBuild, the same mechanism of extensibility now applies to .NET Core projects.</span></span> <span data-ttu-id="31de3-156">Derleme işlemini genişletme istediğinizde ya da yapı çağırıldığı yapılandırmayı incelemek istediğiniz veya oluşturulan dosyalar gibi yapı işleminde yapıtlar erişmek istediğinizde, bu tür bir genişletilebilirlik kullanırsınız , vs.</span><span class="sxs-lookup"><span data-stu-id="31de3-156">You would use this type of extensibility when you want to extend the build process, or when you want to access any of the artifacts in the build process, such as generated files, or you want to inspect the configuration under which the build is invoked, etc.</span></span>

<span data-ttu-id="31de3-157">Aşağıdaki örnekte, hedefin proje gördüğünüz kullanarak dosya `csproj` söz dizimi.</span><span class="sxs-lookup"><span data-stu-id="31de3-157">In the following example, you can see the target's project file using the `csproj` syntax.</span></span> <span data-ttu-id="31de3-158">Bu bildirir [ `dotnet pack` ](dotnet-pack.md) ne derlemelerine yanı sıra hedef dosyaları yerleştirmek paket komutunu *derleme* paket klasöründen.</span><span class="sxs-lookup"><span data-stu-id="31de3-158">This instructs the [`dotnet pack`](dotnet-pack.md) command what to package, placing the targets files as well as the assemblies into the *build* folder inside the package.</span></span> <span data-ttu-id="31de3-159">Bildirim `<ItemGroup>` sahip öğe `Label` özelliğini `dotnet pack instructions`, hedef altında tanımlanmış.</span><span class="sxs-lookup"><span data-stu-id="31de3-159">Notice the `<ItemGroup>` element that has the `Label` property set to `dotnet pack instructions`, and the Target defined beneath it.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <Description>Sample Packer</Description>
    <VersionPrefix>0.1.0-preview</VersionPrefix>
    <TargetFramework>netstandard1.3</TargetFramework>
    <DebugType>portable</DebugType>
    <AssemblyName>SampleTargets.PackerTarget</AssemblyName>
  </PropertyGroup>
  <ItemGroup>
    <EmbeddedResource Include="Resources\Pkg\dist-template.xml;compiler\resources\**\*" Exclude="bin\**;obj\**;**\*.xproj;packages\**" />
    <None Include="build\SampleTargets.PackerTarget.targets" />
  </ItemGroup>
  <ItemGroup Label="dotnet pack instructions">
    <Content Include="build\*.targets">
      <Pack>true</Pack>
      <PackagePath>build\</PackagePath>
    </Content>
  </ItemGroup>
  <Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">
    <!-- Collect these items inside a target that runs after build but before packaging. -->
    <ItemGroup>
      <Content Include="$(OutputPath)\*.dll;$(OutputPath)\*.json">
        <Pack>true</Pack>
        <PackagePath>build\</PackagePath>
      </Content>
    </ItemGroup>
  </Target>
  <ItemGroup>
    <PackageReference Include="Microsoft.Extensions.DependencyModel" Version="1.0.1-beta-000933"/>
    <PackageReference Include="Microsoft.Build.Framework" Version="0.1.0-preview-00028-160627" />
    <PackageReference Include="Microsoft.Build.Utilities.Core" Version="0.1.0-preview-00028-160627" />
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
  <ItemGroup />
  <PropertyGroup Label="Globals">
    <ProjectGuid>463c66f0-921d-4d34-8bde-7c9d0bffaf7b</ProjectGuid>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(TargetFramework)' == 'netstandard1.3' ">
    <DefineConstants>$(DefineConstants);NETSTANDARD1_3</DefineConstants>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)' == 'Release' ">
    <DefineConstants>$(DefineConstants);RELEASE</DefineConstants>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="31de3-160">Özel hedefleri tüketen yapılır sağlayarak bir `<PackageReference>` işaret eden paket ve Genişletilmekte olan proje içinde sürümü.</span><span class="sxs-lookup"><span data-stu-id="31de3-160">Consuming custom targets is done by providing a `<PackageReference>` that points to the package and its version inside the project that is being extended.</span></span> <span data-ttu-id="31de3-161">Araçları özel hedefleri paket kaybı projenin bağımlılık kapanış dahil.</span><span class="sxs-lookup"><span data-stu-id="31de3-161">Unlike the tools, the custom targets package does get included into the consuming project's dependency closure.</span></span>

<span data-ttu-id="31de3-162">Özel hedef kullanarak yalnızca nasıl yapılandırmanız üzerinde bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="31de3-162">Using the custom target depends solely on how you configure it.</span></span> <span data-ttu-id="31de3-163">MSBuild hedefi olduğundan, güvenebileceğiniz bir belirtilen hedef sonra başka bir hedef çalıştırın ve ayrıca el ile çağrılabilir `dotnet msbuild -t:<target-name>` komutu.</span><span class="sxs-lookup"><span data-stu-id="31de3-163">Since it's an MSBuild target, it can depend on a given target, run after another target and can also be manually invoked using the `dotnet msbuild -t:<target-name>` command.</span></span>

<span data-ttu-id="31de3-164">Ancak, kullanıcılarınıza daha iyi bir kullanıcı deneyimi sağlamak istiyorsanız, proje başına Araçlar ve özel hedefleri birleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="31de3-164">However, if you want to provide a better user experience to your users, you can combine per-project tools and custom targets.</span></span> <span data-ttu-id="31de3-165">Bu senaryoda, her proje araç aslında yalnızca ne olursa olsun gerekli parametreleri ve gerekli çevirir kabul [ `dotnet msbuild` ](dotnet-msbuild.md) hedef yürüterek çağırma.</span><span class="sxs-lookup"><span data-stu-id="31de3-165">In this scenario, the per-project tool would essentially just accept whatever needed parameters and would translate that into the required [`dotnet msbuild`](dotnet-msbuild.md) invocation that would execute the target.</span></span> <span data-ttu-id="31de3-166">Bu tür bir synergy örneği gördüğünüz [MVP Zirvesi 2016 HACK Maratonunda örnekleri](https://github.com/dotnet/MVPSummitHackathon2016) depoda [ `dotnet-packer` ](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer) proje.</span><span class="sxs-lookup"><span data-stu-id="31de3-166">You can see a sample of this kind of synergy on the [MVP Summit 2016 Hackathon samples](https://github.com/dotnet/MVPSummitHackathon2016) repo in the [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer) project.</span></span>

## <a name="path-based-extensibility"></a><span data-ttu-id="31de3-167">YOL tabanlı genişletilebilirliği</span><span class="sxs-lookup"><span data-stu-id="31de3-167">PATH-based extensibility</span></span>
<span data-ttu-id="31de3-168">YOL tabanlı genişletilebilirliği, genellikle kavramsal olarak tek bir projede birden fazla kapsayan bir aracı gerek duyduğunuz geliştirme makineler için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="31de3-168">PATH-based extensibility is usually used for development machines where you need a tool that conceptually covers more than a single project.</span></span> <span data-ttu-id="31de3-169">Bu uzantı mekanizması en büyük dezavantajı, bu aracın bulunduğu makineye bağlıdır ' dir.</span><span class="sxs-lookup"><span data-stu-id="31de3-169">The main drawback of this extension mechanism is that it's tied to the machine where the tool exists.</span></span> <span data-ttu-id="31de3-170">Başka bir makineye ihtiyacınız varsa, bunu dağıtmak gerekir.</span><span class="sxs-lookup"><span data-stu-id="31de3-170">If you need it on another machine, you would have to deploy it.</span></span>

<span data-ttu-id="31de3-171">Bu düzen CLI araç takımı genişletilebilirlik çok kolaydır.</span><span class="sxs-lookup"><span data-stu-id="31de3-171">This pattern of CLI toolset extensibility is very simple.</span></span> <span data-ttu-id="31de3-172">İçinde anlatıldığı gibi [.NET Core CLI genel bakış](index.md), `dotnet` sürücü sonra adlı herhangi bir komutu çalıştırabilir `dotnet-<command>` kuralı.</span><span class="sxs-lookup"><span data-stu-id="31de3-172">As covered in the [.NET Core CLI overview](index.md), `dotnet` driver can run any command that is named after the `dotnet-<command>` convention.</span></span> <span data-ttu-id="31de3-173">Varsayılan çözümleme mantığı ilk çeşitli konumlardan araştırmaları ve son olarak sisteme yolu geri döner.</span><span class="sxs-lookup"><span data-stu-id="31de3-173">The default resolution logic first probes several locations and finally falls back to the system PATH.</span></span> <span data-ttu-id="31de3-174">İstenen komut yolu sistemde mevcut ve çağrılabilir, bir ikili dosyadır `dotnet` sürücü, çağırılır.</span><span class="sxs-lookup"><span data-stu-id="31de3-174">If the requested command exists in the system PATH and is a binary that can be invoked, `dotnet` driver will invoke it.</span></span>

<span data-ttu-id="31de3-175">Dosyanın yürütülebilir olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="31de3-175">The file must be executable.</span></span> <span data-ttu-id="31de3-176">UNIX sistemlerde aracılığıyla yürütme biti ayarlanmış herhangi bir şeyi yani `chmod +x`.</span><span class="sxs-lookup"><span data-stu-id="31de3-176">On Unix systems, this means anything that has the execute bit set via `chmod +x`.</span></span> <span data-ttu-id="31de3-177">Windows üzerinde kullanabileceğiniz *cmd* dosyaları.</span><span class="sxs-lookup"><span data-stu-id="31de3-177">On Windows, you can use *cmd* files.</span></span>

<span data-ttu-id="31de3-178">Çok basit bir "Merhaba Dünya" aracı uygulaması bir göz atalım.</span><span class="sxs-lookup"><span data-stu-id="31de3-178">Let's take a look at the very simple implementation of a "Hello World" tool.</span></span> <span data-ttu-id="31de3-179">Her ikisi de kullanacağız `bash` ve `cmd` Windows üzerinde.</span><span class="sxs-lookup"><span data-stu-id="31de3-179">We will use both `bash` and `cmd` on Windows.</span></span>
<span data-ttu-id="31de3-180">Aşağıdaki komutu yalnızca konsolda "Hello World" echo.</span><span class="sxs-lookup"><span data-stu-id="31de3-180">The following command will simply echo "Hello World" to the console.</span></span>

```bash
#!/bin/bash

echo "Hello World!"
```

```cmd
echo "Hello World"
```

<span data-ttu-id="31de3-181">MacOS, biz bu komut dosyası olarak kaydedebilirsiniz `dotnet-hello` ve ile yürütülebilir, biti `chmod +x dotnet-hello`.</span><span class="sxs-lookup"><span data-stu-id="31de3-181">On macOS, we can save this script as `dotnet-hello` and set its executable bit with `chmod +x dotnet-hello`.</span></span> <span data-ttu-id="31de3-182">İçinde bir sembolik bağlantısını ardından oluşturabiliriz `/usr/local/bin` komutunu kullanarak `ln -s <full_path>/dotnet-hello /usr/local/bin/`.</span><span class="sxs-lookup"><span data-stu-id="31de3-182">We can then create a symbolic link to it in `/usr/local/bin` using the command `ln -s <full_path>/dotnet-hello /usr/local/bin/`.</span></span> <span data-ttu-id="31de3-183">Bu, komutu kullanarak çağırmak mümkün hale getirir `dotnet hello` söz dizimi.</span><span class="sxs-lookup"><span data-stu-id="31de3-183">This will make it possible to invoke the command using the `dotnet hello` syntax.</span></span>

<span data-ttu-id="31de3-184">Windows üzerinde Biz bu komut dosyası olarak kaydedebilirsiniz `dotnet-hello.cmd` ve sistem yolunda bir konuma yerleştirin (veya zaten yolunda bir klasöre ekleyebilirsiniz).</span><span class="sxs-lookup"><span data-stu-id="31de3-184">On Windows, we can save this script as `dotnet-hello.cmd` and put it in a location that is in a system path (or you can add it to a folder that is already in the path).</span></span> <span data-ttu-id="31de3-185">Bundan sonra yalnızca kullanabilirsiniz `dotnet hello` Bu örneği çalıştırmak için.</span><span class="sxs-lookup"><span data-stu-id="31de3-185">After this, you can just use `dotnet hello` to run this example.</span></span>
