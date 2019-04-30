---
title: Project.JSON ile csproj karşılaştırma
description: Project.json ile csproj öğeleri arasında bir eşleme bakın.
author: natemcmaster
ms.date: 03/13/2017
ms.custom: seodec18
ms.openlocfilehash: 6ac63f18bd42193e964aaeae3c54c887c9c63163
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61647365"
---
# <a name="a-mapping-between-projectjson-and-csproj-properties"></a><span data-ttu-id="07542-103">Project.json ile csproj özellikleri arasında bir eşleme</span><span class="sxs-lookup"><span data-stu-id="07542-103">A mapping between project.json and csproj properties</span></span>

<span data-ttu-id="07542-104">Tarafından [Nate McMaster](https://github.com/natemcmaster)</span><span class="sxs-lookup"><span data-stu-id="07542-104">By [Nate McMaster](https://github.com/natemcmaster)</span></span>

<span data-ttu-id="07542-105">.NET Core araçları geliştirme sırasında artık desteklemek için bir önemli tasarım değişikliğin yapıldığı *project.json* dosyaları ve bunun yerine .NET Core projeleri için MSBuild/csproj biçimine taşıyın.</span><span class="sxs-lookup"><span data-stu-id="07542-105">During the development of the .NET Core tooling, an important design change was made to no longer support *project.json* files and instead move the .NET Core projects to the MSBuild/csproj format.</span></span>

<span data-ttu-id="07542-106">Bu makale nasıl ayarlarında *project.json* yeni biçimini kullanın ve projenize yükseltirken yükseltme araçları tarafından yapılan değişiklikleri anlama hakkında bilgi edinmek için MSBuild/csproj biçimde temsil edilir araç en son sürümü.</span><span class="sxs-lookup"><span data-stu-id="07542-106">This article shows how the settings in *project.json* are represented in the MSBuild/csproj format so you can learn how to use the new format and understand the changes made by the migration tools when you're upgrading your project to the latest version of the tooling.</span></span>

## <a name="the-csproj-format"></a><span data-ttu-id="07542-107">Csproj biçimine</span><span class="sxs-lookup"><span data-stu-id="07542-107">The csproj format</span></span>

<span data-ttu-id="07542-108">Yeni biçim \*.csproj, XML tabanlı bir biçim olduğu.</span><span class="sxs-lookup"><span data-stu-id="07542-108">The new format, \*.csproj, is an XML-based format.</span></span> <span data-ttu-id="07542-109">Aşağıdaki örnek, gösterir kullanarak bir .NET Core proje kök düğümü `Microsoft.NET.Sdk`.</span><span class="sxs-lookup"><span data-stu-id="07542-109">The following example shows the root node of a .NET Core project using the `Microsoft.NET.Sdk`.</span></span> <span data-ttu-id="07542-110">Web projeleri için kullanılan SDK şeklindedir `Microsoft.NET.Sdk.Web`.</span><span class="sxs-lookup"><span data-stu-id="07542-110">For web projects, the SDK used is `Microsoft.NET.Sdk.Web`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
...
</Project>
```

## <a name="common-top-level-properties"></a><span data-ttu-id="07542-111">Ortak bir üst düzey özellikler</span><span class="sxs-lookup"><span data-stu-id="07542-111">Common top-level properties</span></span>

### <a name="name"></a><span data-ttu-id="07542-112">name</span><span class="sxs-lookup"><span data-stu-id="07542-112">name</span></span>

```json
{
  "name": "MyProjectName"
}
```

<span data-ttu-id="07542-113">Artık desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="07542-113">No longer supported.</span></span> <span data-ttu-id="07542-114">Csproj Bu genellikle dizin adı ile eşleşen proje dosya adı tarafından belirlenir.</span><span class="sxs-lookup"><span data-stu-id="07542-114">In csproj, this is determined by the project filename, which usually matches the directory name.</span></span> <span data-ttu-id="07542-115">Örneğin: `MyProjectName.csproj`</span><span class="sxs-lookup"><span data-stu-id="07542-115">For example, `MyProjectName.csproj`.</span></span>

<span data-ttu-id="07542-116">Varsayılan olarak, proje dosya adına ayrıca değerini belirtir. `<AssemblyName>` ve `<PackageId>` özellikleri.</span><span class="sxs-lookup"><span data-stu-id="07542-116">By default, the project filename also specifies the value of the `<AssemblyName>` and `<PackageId>` properties.</span></span>

```xml
<PropertyGroup>
  <AssemblyName>MyProjectName</AssemblyName>
  <PackageId>MyProjectName</PackageId>
</PropertyGroup>
```

<span data-ttu-id="07542-117">`<AssemblyName>` Değerinden farklı bir değere sahip `<PackageId>` varsa `buildOptions\outputName` özelliği, project.json içinde tanımlandı.</span><span class="sxs-lookup"><span data-stu-id="07542-117">The `<AssemblyName>` will have a different value than `<PackageId>` if `buildOptions\outputName` property was defined in project.json.</span></span>
<span data-ttu-id="07542-118">Daha fazla bilgi için [diğer ortak yapı seçeneklerini](#other-common-build-options).</span><span class="sxs-lookup"><span data-stu-id="07542-118">For more information, see [Other common build options](#other-common-build-options).</span></span>

### <a name="version"></a><span data-ttu-id="07542-119">sürüm</span><span class="sxs-lookup"><span data-stu-id="07542-119">version</span></span>

```json
{
  "version": "1.0.0-alpha-*"
}
```

<span data-ttu-id="07542-120">Kullanım `VersionPrefix` ve `VersionSuffix` özellikleri:</span><span class="sxs-lookup"><span data-stu-id="07542-120">Use the `VersionPrefix` and `VersionSuffix` properties:</span></span>

```xml
<PropertyGroup>
  <VersionPrefix>1.0.0</VersionPrefix>
  <VersionSuffix>alpha</VersionSuffix>
</PropertyGroup>
```

<span data-ttu-id="07542-121">Ayrıca `Version` özelliği, ancak bu geçersiz sürüm ayarlarını paketleme sırasında:</span><span class="sxs-lookup"><span data-stu-id="07542-121">You can also use the `Version` property, but this may override version settings during packaging:</span></span>

```xml
<PropertyGroup>
  <Version>1.0.0-alpha</Version>
</PropertyGroup>
```

### <a name="other-common-root-level-options"></a><span data-ttu-id="07542-122">Diğer ortak kök düzeyinde seçenekleri</span><span class="sxs-lookup"><span data-stu-id="07542-122">Other common root-level options</span></span>

```json
{
  "authors": [ "Anne", "Bob" ],
  "company": "Contoso",
  "language": "en-US",
  "title": "My library",
  "description": "This is my library.\r\nAnd it's really great!",
  "copyright": "Nugetizer 3000",
  "userSecretsId": "xyz123"
}
```

```xml
<PropertyGroup>
  <Authors>Anne;Bob</Authors>
  <Company>Contoso</Company>
  <NeutralLanguage>en-US</NeutralLanguage>
  <AssemblyTitle>My library</AssemblyTitle>
  <Description>This is my library.
And it's really great!</Description>
  <Copyright>Nugetizer 3000</Copyright>
  <UserSecretsId>xyz123</UserSecretsId>
</PropertyGroup>
```

## <a name="frameworks"></a><span data-ttu-id="07542-123">Çerçeveler</span><span class="sxs-lookup"><span data-stu-id="07542-123">frameworks</span></span>

### <a name="one-target-framework"></a><span data-ttu-id="07542-124">Bir hedef çerçeve</span><span class="sxs-lookup"><span data-stu-id="07542-124">One target framework</span></span>

```json
{
  "frameworks": {
    "netcoreapp1.0": {}
  }
}
```

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp1.0</TargetFramework>
</PropertyGroup>
```

### <a name="multiple-target-frameworks"></a><span data-ttu-id="07542-125">Birden çok hedef çerçeve</span><span class="sxs-lookup"><span data-stu-id="07542-125">Multiple target frameworks</span></span>

```json
{
  "frameworks": {
    "netcoreapp1.0": {},
    "net451": {}
  }
}
```

<span data-ttu-id="07542-126">Kullanım `TargetFrameworks` hedef çerçeve listesini tanımlamak için özellik.</span><span class="sxs-lookup"><span data-stu-id="07542-126">Use the `TargetFrameworks` property to define your list of target frameworks.</span></span> <span data-ttu-id="07542-127">Framework değerleri birbirinden ayırmak için noktalı virgül kullanın.</span><span class="sxs-lookup"><span data-stu-id="07542-127">Use semi-colon to separate multiple framework values.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp1.0;net451</TargetFrameworks>
</PropertyGroup>
```

## <a name="dependencies"></a><span data-ttu-id="07542-128">bağımlılıklar</span><span class="sxs-lookup"><span data-stu-id="07542-128">dependencies</span></span>

> [!IMPORTANT]
> <span data-ttu-id="07542-129">Bağımlılık ise bir **proje** ve bir paket biçimi farklıdır.</span><span class="sxs-lookup"><span data-stu-id="07542-129">If the dependency is a **project** and not a package, the format is different.</span></span>
> <span data-ttu-id="07542-130">Daha fazla bilgi için [bağımlılık türü](#dependency-type) bölümü.</span><span class="sxs-lookup"><span data-stu-id="07542-130">For more information, see the [dependency type](#dependency-type) section.</span></span>

### <a name="netstandardlibrary-metapackage"></a><span data-ttu-id="07542-131">NETStandard.Library metapackage</span><span class="sxs-lookup"><span data-stu-id="07542-131">NETStandard.Library metapackage</span></span>

```json
{
  "dependencies": {
    "NETStandard.Library": "1.6.0"
  }
}
```

```xml
<PropertyGroup>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

### <a name="microsoftnetcoreapp-metapackage"></a><span data-ttu-id="07542-132">Microsoft.NETCore.App metapackage</span><span class="sxs-lookup"><span data-stu-id="07542-132">Microsoft.NETCore.App metapackage</span></span>

```json
{
  "dependencies": {
    "Microsoft.NETCore.App": "1.0.0"
  }
}
```

```xml
<PropertyGroup>
  <RuntimeFrameworkVersion>1.0.3</RuntimeFrameworkVersion>
</PropertyGroup>
```

<span data-ttu-id="07542-133">Unutmayın `<RuntimeFrameworkVersion>` geçirilen Proje değeri, SDK'sı yüklü olan sürümü tarafından belirlenir.</span><span class="sxs-lookup"><span data-stu-id="07542-133">Note that the `<RuntimeFrameworkVersion>` value in the migrated project is determined by the version of the SDK you have installed.</span></span>

### <a name="top-level-dependencies"></a><span data-ttu-id="07542-134">Üst düzey bağımlılıkları</span><span class="sxs-lookup"><span data-stu-id="07542-134">Top-level dependencies</span></span>

```json
{
  "dependencies": {
    "Microsoft.AspNetCore": "1.1.0"
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.AspNetCore" Version="1.1.0" />
</ItemGroup>
```

### <a name="per-framework-dependencies"></a><span data-ttu-id="07542-135">Çerçeve başına bağımlılıklarını</span><span class="sxs-lookup"><span data-stu-id="07542-135">Per-framework dependencies</span></span>

```json
{
  "framework": {
    "net451": {
      "dependencies": {
        "System.Collections.Immutable": "1.3.1"
      }
    },
    "netstandard1.5": {
      "dependencies": {
        "Newtonsoft.Json": "9.0.1"
      }
    }
  }
}
```

```xml
<ItemGroup Condition="'$(TargetFramework)'=='net451'">
  <PackageReference Include="System.Collections.Immutable" Version="1.3.1" />
</ItemGroup>

<ItemGroup Condition="'$(TargetFramework)'=='netstandard1.5'">
  <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
</ItemGroup>
```

### <a name="imports"></a><span data-ttu-id="07542-136">içeri aktarmalar</span><span class="sxs-lookup"><span data-stu-id="07542-136">imports</span></span>

```json
{
  "dependencies": {
    "YamlDotNet": "4.0.1-pre309"
  },
  "frameworks": {
    "netcoreapp1.0": {
      "imports": [
        "dnxcore50",
        "dotnet"
      ]
    }
  }
}
```

```xml
<PropertyGroup>
  <PackageTargetFallback>dnxcore50;dotnet</PackageTargetFallback>
</PropertyGroup>
<ItemGroup>
  <PackageReference Include="YamlDotNet" Version="4.0.1-pre309" />
</ItemGroup>
```

### <a name="dependency-type"></a><span data-ttu-id="07542-137">Bağımlılık türü</span><span class="sxs-lookup"><span data-stu-id="07542-137">dependency type</span></span>

#### <a name="type-project"></a><span data-ttu-id="07542-138">Tür: Proje</span><span class="sxs-lookup"><span data-stu-id="07542-138">type: project</span></span>

```json
{
  "dependencies": {
    "MyOtherProject": "1.0.0-*",
    "AnotherProject": {
      "type": "project"
    }
  }
}
```

```xml
<ItemGroup>
  <ProjectReference Include="..\MyOtherProject\MyOtherProject.csproj" />
  <ProjectReference Include="..\AnotherProject\AnotherProject.csproj" />
</ItemGroup>
```

> [!NOTE]
> <span data-ttu-id="07542-139">Bu şekilde çalışmamasına neden olur, `dotnet pack --version-suffix $suffix` bir proje başvurusu bağımlılık sürümünü belirler.</span><span class="sxs-lookup"><span data-stu-id="07542-139">This will break the way that `dotnet pack --version-suffix $suffix` determines the dependency version of a project reference.</span></span>

#### <a name="type-build"></a><span data-ttu-id="07542-140">Tür: derleme</span><span class="sxs-lookup"><span data-stu-id="07542-140">type: build</span></span>

```json
{
  "dependencies": {
    "Microsoft.EntityFrameworkCore.Design": {
      "version": "1.1.0",
      "type": "build"
    }
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.EntityFrameworkCore.Design" Version="1.1.0" PrivateAssets="All" />
</ItemGroup>
```

#### <a name="type-platform"></a><span data-ttu-id="07542-141">Tür: platform</span><span class="sxs-lookup"><span data-stu-id="07542-141">type: platform</span></span>

```json
{
  "dependencies": {
    "Microsoft.NETCore.App": {
      "version": "1.1.0",
      "type": "platform"
    }
  }
}
```

<span data-ttu-id="07542-142">Csproj'a eşdeğeri yoktur.</span><span class="sxs-lookup"><span data-stu-id="07542-142">There is no equivalent in csproj.</span></span>

## <a name="runtimes"></a><span data-ttu-id="07542-143">Çalışma zamanları</span><span class="sxs-lookup"><span data-stu-id="07542-143">runtimes</span></span>

```json
{
  "runtimes": {
    "win7-x64": {},
    "osx.10.11-x64": {},
    "ubuntu.16.04-x64": {}
  }
}
```

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win7-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="standalone-apps-self-contained-deployment"></a><span data-ttu-id="07542-144">Tek başına uygulamaları (müstakil dağıtım)</span><span class="sxs-lookup"><span data-stu-id="07542-144">Standalone apps (self-contained deployment)</span></span>

<span data-ttu-id="07542-145">Project.json'da, tanımlayan bir `runtimes` uygulama olan sırasında tek başına bölüm anlamına gelir oluşturun ve yayınlayın.</span><span class="sxs-lookup"><span data-stu-id="07542-145">In project.json, defining a `runtimes` section means the app was standalone during build and publish.</span></span>
<span data-ttu-id="07542-146">Msbuild'de, tüm projeleri, *taşınabilir* yapı sırasında ancak bağımsız yayımlanabilir.</span><span class="sxs-lookup"><span data-stu-id="07542-146">In MSBuild, all projects are *portable* during build, but can be published as standalone.</span></span>

`dotnet publish --framework netcoreapp1.0 --runtime osx.10.11-x64`

<span data-ttu-id="07542-147">Daha fazla bilgi için [müstakil dağıtımlar (SCD)](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="07542-147">For more information, see [Self-contained deployments (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span>

## <a name="tools"></a><span data-ttu-id="07542-148">araçlar</span><span class="sxs-lookup"><span data-stu-id="07542-148">tools</span></span>

```json
{
  "tools": {
    "Microsoft.EntityFrameworkCore.Tools.DotNet": "1.0.0-*"
  }
}
```

```xml
<ItemGroup>
  <DotNetCliToolReference Include="Microsoft.EntityFrameworkCore.Tools.DotNet" Version="1.0.0" />
</ItemGroup>
```

> [!NOTE]
> <span data-ttu-id="07542-149">`imports` Araçları csproj içinde desteklenmez.</span><span class="sxs-lookup"><span data-stu-id="07542-149">`imports` on tools are not supported in csproj.</span></span> <span data-ttu-id="07542-150">İçeri aktarmalar gereken Araçlar yeni çalışmaz `Microsoft.NET.Sdk`.</span><span class="sxs-lookup"><span data-stu-id="07542-150">Tools that need imports will not work with the new `Microsoft.NET.Sdk`.</span></span>

## <a name="buildoptions"></a><span data-ttu-id="07542-151">buildOptions</span><span class="sxs-lookup"><span data-stu-id="07542-151">buildOptions</span></span>

<span data-ttu-id="07542-152">Ayrıca bkz: [dosyaları](#files).</span><span class="sxs-lookup"><span data-stu-id="07542-152">See also [Files](#files).</span></span>

### <a name="emitentrypoint"></a><span data-ttu-id="07542-153">emitEntryPoint</span><span class="sxs-lookup"><span data-stu-id="07542-153">emitEntryPoint</span></span>

```json
{
  "buildOptions": {
    "emitEntryPoint": true
  }
}
```

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="07542-154">Varsa `emitEntryPoint` olduğu `false`, değerini `OutputType` dönüştürülür `Library`, varsayılan değer olan:</span><span class="sxs-lookup"><span data-stu-id="07542-154">If `emitEntryPoint` was `false`, the value of `OutputType` is converted to `Library`, which is the default value:</span></span>

```json
{
  "buildOptions": {
    "emitEntryPoint": false
  }
}
```

```xml
<PropertyGroup>
  <OutputType>Library</OutputType>
  <!-- or, omit altogether. It defaults to 'Library' -->
</PropertyGroup>
```

### <a name="keyfile"></a><span data-ttu-id="07542-155">KeyFile</span><span class="sxs-lookup"><span data-stu-id="07542-155">keyFile</span></span>

```json
{
  "buildOptions": {
    "keyFile": "MyKey.snk"
  }
}
```

<span data-ttu-id="07542-156">`keyFile` Üç özellik msbuild'de öğe genişletir:</span><span class="sxs-lookup"><span data-stu-id="07542-156">The `keyFile` element expands to three properties in MSBuild:</span></span>

```xml
<PropertyGroup>
  <AssemblyOriginatorKeyFile>MyKey.snk</AssemblyOriginatorKeyFile>
  <SignAssembly>true</SignAssembly>
  <PublicSign Condition="'$(OS)' != 'Windows_NT'">true</PublicSign>
</PropertyGroup>
```

### <a name="other-common-build-options"></a><span data-ttu-id="07542-157">Diğer ortak derleme seçenekleri</span><span class="sxs-lookup"><span data-stu-id="07542-157">Other common build options</span></span>

```json
{
  "buildOptions": {
    "warningsAsErrors": true,
    "nowarn": ["CS0168", "CS0219"],
    "xmlDoc": true,
    "preserveCompilationContext": true,
    "outputName": "Different.AssemblyName",
    "debugType": "portable",
    "allowUnsafe": true,
    "define": ["TEST", "OTHERCONDITION"]
  }
}
```

```xml
<PropertyGroup>
  <TreatWarningsAsErrors>true</TreatWarningsAsErrors>
  <NoWarn>$(NoWarn);CS0168;CS0219</NoWarn>
  <GenerateDocumentationFile>true</GenerateDocumentationFile>
  <PreserveCompilationContext>true</PreserveCompilationContext>
  <AssemblyName>Different.AssemblyName</AssemblyName>
  <DebugType>portable</DebugType>
  <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  <DefineConstants>$(DefineConstants);TEST;OTHERCONDITION</DefineConstants>
</PropertyGroup>
```

## <a name="packoptions"></a><span data-ttu-id="07542-158">packOptions</span><span class="sxs-lookup"><span data-stu-id="07542-158">packOptions</span></span>

<span data-ttu-id="07542-159">Ayrıca bkz: [dosyaları](#files).</span><span class="sxs-lookup"><span data-stu-id="07542-159">See also [Files](#files).</span></span>

### <a name="common-pack-options"></a><span data-ttu-id="07542-160">Ortak paketi seçenekleri</span><span class="sxs-lookup"><span data-stu-id="07542-160">Common pack options</span></span>

```json
{
  "packOptions": {
    "summary": "numl is a machine learning library intended to ease the use of using standard modeling techniques for both prediction and clustering.",
    "tags": ["machine learning", "framework"],
    "releaseNotes": "Version 0.9.12-beta",
    "iconUrl": "http://numl.net/images/ico.png",
    "projectUrl": "http://numl.net",
    "licenseUrl": "https://raw.githubusercontent.com/sethjuarez/numl/master/LICENSE.md",
    "requireLicenseAcceptance": false,
    "repository": {
      "type": "git",
      "url": "https://raw.githubusercontent.com/sethjuarez/numl"
    },
    "owners": ["Seth Juarez"]
  }
}
```

```xml
<PropertyGroup>
  <!-- summary is not migrated from project.json, but you can use the <Description> property for that if needed. -->
  <PackageTags>machine learning;framework</PackageTags>
  <PackageReleaseNotes>Version 0.9.12-beta</PackageReleaseNotes>
  <PackageIconUrl>http://numl.net/images/ico.png</PackageIconUrl>
  <PackageProjectUrl>http://numl.net</PackageProjectUrl>
  <PackageLicenseUrl>https://raw.githubusercontent.com/sethjuarez/numl/master/LICENSE.md</PackageLicenseUrl>
  <PackageRequireLicenseAcceptance>false</PackageRequireLicenseAcceptance>
  <RepositoryType>git</RepositoryType>
  <RepositoryUrl>https://raw.githubusercontent.com/sethjuarez/numl</RepositoryUrl>
  <!-- owners is not supported in MSBuild -->
</PropertyGroup>
```

<span data-ttu-id="07542-161">İçin eşdeğeri yoktur `owners` msbuild'de öğe.</span><span class="sxs-lookup"><span data-stu-id="07542-161">There is no equivalent for the `owners` element in MSBuild.</span></span>
<span data-ttu-id="07542-162">İçin `summary`, MSBuild kullanabilirsiniz `<Description>` özelliği olsa bile değerini `summary` bu özellik eşlendiği olduğundan bu özellik için otomatik olarak taşınmaz [ `description` ](#other-common-root-level-options) öğesi.</span><span class="sxs-lookup"><span data-stu-id="07542-162">For `summary`, you can use the MSBuild `<Description>` property, even though the value of `summary` is not migrated automatically to that property, since that property is mapped to the [`description`](#other-common-root-level-options) element.</span></span>

## <a name="scripts"></a><span data-ttu-id="07542-163">betikler</span><span class="sxs-lookup"><span data-stu-id="07542-163">scripts</span></span>

```json
{
  "scripts": {
    "precompile": "generateCode.cmd",
    "postpublish": [ "obfuscate.cmd", "removeTempFiles.cmd" ]
  }
}
```

<span data-ttu-id="07542-164">MSBuild eşdeğeri olan [hedefleri](/visualstudio/msbuild/msbuild-targets):</span><span class="sxs-lookup"><span data-stu-id="07542-164">Their equivalent in MSBuild are [targets](/visualstudio/msbuild/msbuild-targets):</span></span>

```xml
<Target Name="MyPreCompileTarget" BeforeTargets="Build">
  <Exec Command="generateCode.cmd" />
</Target>

<Target Name="MyPostCompileTarget" AfterTargets="Publish">
  <Exec Command="obfuscate.cmd" />
  <Exec Command="removeTempFiles.cmd" />
</Target>
```

## <a name="runtimeoptions"></a><span data-ttu-id="07542-165">runtimeOptions</span><span class="sxs-lookup"><span data-stu-id="07542-165">runtimeOptions</span></span>

```json
{
  "runtimeOptions": {
    "configProperties": {
      "System.GC.Server": true,
      "System.GC.Concurrent": true,
      "System.GC.RetainVM": true,
      "System.Threading.ThreadPool.MinThreads": 4,
      "System.Threading.ThreadPool.MaxThreads": 25
    }
  }
}
```

<span data-ttu-id="07542-166">Bu gruptaki "System.GC.Server" özelliği dışında tüm ayarlar adlı bir dosyaya yerleştirilir *runtimeconfig.template.json* proje klasöründeki kök nesnesi için geçiş işlemi sırasında yükseltilmiş seçenekleri:</span><span class="sxs-lookup"><span data-stu-id="07542-166">All settings in this group, except for the "System.GC.Server" property, are placed into a file called *runtimeconfig.template.json* in the project folder, with options lifted to the root object during the migration process:</span></span>

```json
{
  "configProperties": {
    "System.GC.Concurrent": true,
    "System.GC.RetainVM": true,
    "System.Threading.ThreadPool.MinThreads": 4,
    "System.Threading.ThreadPool.MaxThreads": 25
  }
}
```

<span data-ttu-id="07542-167">"System.GC.Server" özelliği csproj dosyasına geçirilir:</span><span class="sxs-lookup"><span data-stu-id="07542-167">The "System.GC.Server" property is migrated into the csproj file:</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

<span data-ttu-id="07542-168">Ancak, bu değerleri csproj yanı sıra MSBuild özellikleri ayarlayabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="07542-168">However, you can set all those values in the csproj as well as MSBuild properties:</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
  <ConcurrentGarbageCollection>true</ConcurrentGarbageCollection>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  <ThreadPoolMaxThreads>25</ThreadPoolMaxThreads>
</PropertyGroup>
```

## <a name="shared"></a><span data-ttu-id="07542-169">shared</span><span class="sxs-lookup"><span data-stu-id="07542-169">shared</span></span>

```json
{
  "shared": "shared/**/*.cs"
}
```

<span data-ttu-id="07542-170">Csproj içinde desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="07542-170">Not supported in csproj.</span></span> <span data-ttu-id="07542-171">Bunun yerine oluşturmalısınız içerik dosyalarına dahil, *.nuspec* dosya.</span><span class="sxs-lookup"><span data-stu-id="07542-171">You must instead create include content files in your *.nuspec* file.</span></span>
<span data-ttu-id="07542-172">Daha fazla bilgi için [içerik dosyaları dahil olmak üzere](/nuget/schema/nuspec#including-content-files).</span><span class="sxs-lookup"><span data-stu-id="07542-172">For more information, see [Including content files](/nuget/schema/nuspec#including-content-files).</span></span>

## <a name="files"></a><span data-ttu-id="07542-173">dosyaları</span><span class="sxs-lookup"><span data-stu-id="07542-173">files</span></span>

<span data-ttu-id="07542-174">İçinde *project.json*, derleme ve paketi genişletilmiş derlenip başka klasörlerinden ekleme.</span><span class="sxs-lookup"><span data-stu-id="07542-174">In *project.json*, build and pack could be extended to compile and embed from different folders.</span></span>
<span data-ttu-id="07542-175">Msbuild'de yapıldığını kullanarak [öğeleri](/visualstudio/msbuild/common-msbuild-project-items).</span><span class="sxs-lookup"><span data-stu-id="07542-175">In MSBuild, this is done using [items](/visualstudio/msbuild/common-msbuild-project-items).</span></span> <span data-ttu-id="07542-176">Aşağıdaki örnek bir ortak bir dönüştürmedir:</span><span class="sxs-lookup"><span data-stu-id="07542-176">The following example is a common conversion:</span></span>

```json
{
  "buildOptions": {
    "compile": {
      "copyToOutput": "notes.txt",
      "include": "../Shared/*.cs",
      "exclude": "../Shared/Not/*.cs"
    },
    "embed": {
      "include": "../Shared/*.resx"
    }
  },
  "packOptions": {
    "include": "Views/",
    "mappings": {
      "some/path/in/project.txt": "in/package.txt"
    }
  },
  "publishOptions": {
    "include": [
      "files/",
      "publishnotes.txt"
    ]
  }
}
```

```xml
<ItemGroup>
  <Compile Include="..\Shared\*.cs" Exclude="..\Shared\Not\*.cs" />
  <EmbeddedResource Include="..\Shared\*.resx" />
  <Content Include="Views\**\*" PackagePath="%(Identity)" />
  <None Include="some/path/in/project.txt" Pack="true" PackagePath="in/package.txt" />
  
  <None Include="notes.txt" CopyToOutputDirectory="Always" />
  <!-- CopyToOutputDirectory = { Always, PreserveNewest, Never } -->

  <Content Include="files\**\*" CopyToPublishDirectory="PreserveNewest" />
  <None Include="publishnotes.txt" CopyToPublishDirectory="Always" />
  <!-- CopyToPublishDirectory = { Always, PreserveNewest, Never } -->
</ItemGroup>
```

> [!NOTE]
> <span data-ttu-id="07542-177">Varsayılan birçok [Glob desenlerinin](https://en.wikipedia.org/wiki/Glob_(programming)) .NET Core SDK'sı tarafından otomatik olarak eklenir.</span><span class="sxs-lookup"><span data-stu-id="07542-177">Many of the default [globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are added automatically by the .NET Core SDK.</span></span>
> <span data-ttu-id="07542-178">Daha fazla bilgi için [varsayılan derleme öğe değerleri](https://aka.ms/sdkimplicititems).</span><span class="sxs-lookup"><span data-stu-id="07542-178">For more information, see [Default Compile Item Values](https://aka.ms/sdkimplicititems).</span></span>

<span data-ttu-id="07542-179">Tüm MSBuild `ItemGroup` öğeleri Destek `Include`, `Exclude`, ve `Remove`.</span><span class="sxs-lookup"><span data-stu-id="07542-179">All MSBuild `ItemGroup` elements support `Include`, `Exclude`, and `Remove`.</span></span>

<span data-ttu-id="07542-180">Paket düzeni .nupkg içinde değiştirilebilir `PackagePath="path"`.</span><span class="sxs-lookup"><span data-stu-id="07542-180">Package layout inside the .nupkg can be modified with `PackagePath="path"`.</span></span>

<span data-ttu-id="07542-181">Dışında `Content`, açıkça ekleme çoğu öğesi grupları iste `Pack="true"` pakete dahil edilecek.</span><span class="sxs-lookup"><span data-stu-id="07542-181">Except for `Content`, most item groups require explicitly adding `Pack="true"` to be included in the package.</span></span> <span data-ttu-id="07542-182">`Content` yerleştirilir *içeriği* MSBuild sonrasında bir paket klasörüne `<IncludeContentInPack>` özelliği `true` varsayılan olarak.</span><span class="sxs-lookup"><span data-stu-id="07542-182">`Content` will be put in the *content* folder in a package since the MSBuild `<IncludeContentInPack>` property is set to `true` by default.</span></span>
<span data-ttu-id="07542-183">Daha fazla bilgi için [bir içerik paketine](/nuget/schema/msbuild-targets#including-content-in-a-package).</span><span class="sxs-lookup"><span data-stu-id="07542-183">For more information, see [Including content in a package](/nuget/schema/msbuild-targets#including-content-in-a-package).</span></span>

<span data-ttu-id="07542-184">`PackagePath="%(Identity)"` Proje göreli dosya yolu için paket yolu ayarlama, kısa bir yoludur.</span><span class="sxs-lookup"><span data-stu-id="07542-184">`PackagePath="%(Identity)"` is a short way of setting package path to the project-relative file path.</span></span>

## <a name="testrunner"></a><span data-ttu-id="07542-185">testRunner</span><span class="sxs-lookup"><span data-stu-id="07542-185">testRunner</span></span>

### <a name="xunit"></a><span data-ttu-id="07542-186">xUnit</span><span class="sxs-lookup"><span data-stu-id="07542-186">xUnit</span></span>

```json
{
  "testRunner": "xunit",
  "dependencies": {
    "dotnet-test-xunit": "<any>"
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0-*" />
  <PackageReference Include="xunit" Version="2.2.0-*" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0-*" />
</ItemGroup>
```

### <a name="mstest"></a><span data-ttu-id="07542-187">MSTest</span><span class="sxs-lookup"><span data-stu-id="07542-187">MSTest</span></span>

```json
{
  "testRunner": "mstest",
  "dependencies": {
    "dotnet-test-mstest": "<any>"
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0-*" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.12-*" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.11-*" />
</ItemGroup>
```

## <a name="see-also"></a><span data-ttu-id="07542-188">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="07542-188">See also</span></span>

- [<span data-ttu-id="07542-189">CLI değişiklikleri üst düzey genel bakış</span><span class="sxs-lookup"><span data-stu-id="07542-189">High-level overview of changes in CLI</span></span>](../tools/cli-msbuild-architecture.md)
