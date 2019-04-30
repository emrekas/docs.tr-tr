---
title: .NET Core araçları bağımlılıkları yönetme
description: .NET Core araçları ile bağımlılıklarınızı yönetmesini açıklanmaktadır.
ms.date: 03/06/2017
ms.custom: seodec18
ms.openlocfilehash: ef2de666ee3e6a06ab62f45afe3c624bbbb44ac4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665734"
---
# <a name="managing-dependencies-with-net-core-sdk-10"></a><span data-ttu-id="b88a1-103">.NET Core SDK'sı 1.0 ile bağımlılık Yönetimi</span><span class="sxs-lookup"><span data-stu-id="b88a1-103">Managing dependencies with .NET Core SDK 1.0</span></span>

<span data-ttu-id="b88a1-104">Ciddi bir yatırım, taşıma, .NET Core projeleri ile project.json'ndan csproj ve MSBuild proje dosyası ve bağımlılıkları izlenmesine izin vermek varlıklar birleştirmesi içinde sonuçlanan da oldu.</span><span class="sxs-lookup"><span data-stu-id="b88a1-104">With the move of .NET Core projects from project.json to csproj and MSBuild, a significant investment also happened that resulted in unification of the project file and assets that allow tracking of dependencies.</span></span> <span data-ttu-id="b88a1-105">.NET Core projeleri için hangi project.json benzer budur.</span><span class="sxs-lookup"><span data-stu-id="b88a1-105">For .NET Core projects this is similar to what project.json did.</span></span> <span data-ttu-id="b88a1-106">NuGet bağımlılıklarını izleyen ayrı JSON veya XML dosya yok.</span><span class="sxs-lookup"><span data-stu-id="b88a1-106">There is no separate JSON or XML file that tracks NuGet dependencies.</span></span> <span data-ttu-id="b88a1-107">Bu değişiklik, aynı zamanda başka bir tür tanıttık *başvuru* adlı csproj söz dizimini içine `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="b88a1-107">With this change, we've also introduced another type of *reference* into the csproj syntax called the `<PackageReference>`.</span></span> 

<span data-ttu-id="b88a1-108">Bu belge, yeni başvuru türünü açıklar.</span><span class="sxs-lookup"><span data-stu-id="b88a1-108">This document describes the new reference type.</span></span> <span data-ttu-id="b88a1-109">Ayrıca bu yeni bir başvuru türü projenize kullanarak paket bağımlılık ekleme işlemini de gösterir.</span><span class="sxs-lookup"><span data-stu-id="b88a1-109">It also shows how to add a package dependency using this new reference type to your project.</span></span> 

## <a name="the-new-packagereference-element"></a><span data-ttu-id="b88a1-110">Yeni \<PackageReference > öğesi</span><span class="sxs-lookup"><span data-stu-id="b88a1-110">The new \<PackageReference> element</span></span>
<span data-ttu-id="b88a1-111">`<PackageReference>` Aşağıdaki temel yapıya sahiptir:</span><span class="sxs-lookup"><span data-stu-id="b88a1-111">The `<PackageReference>` has the following basic structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="b88a1-112">Msbuild'i iyi bilmiyorsanız, zaten mevcut olan diğer başvuru türlerine benzer görünecektir.</span><span class="sxs-lookup"><span data-stu-id="b88a1-112">If you are familiar with MSBuild, it will look familiar to the other reference types that already exist.</span></span> <span data-ttu-id="b88a1-113">Anahtar `Include` deyimi projeye eklemek istediğiniz paket kimliğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="b88a1-113">The key is the `Include` statement which specifies the package id that you wish to add to the project.</span></span> <span data-ttu-id="b88a1-114">`<Version>` Sürümü almak için alt öğe belirtir.</span><span class="sxs-lookup"><span data-stu-id="b88a1-114">The `<Version>` child element specifies the version to get.</span></span> <span data-ttu-id="b88a1-115">Sürümler olarak başına belirtilen [NuGet sürümü kurallarını](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="b88a1-115">The versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="b88a1-116">Genel ile aşina değilseniz `csproj` söz dizimini bkz [MSBuild proje başvurusu](/visualstudio/msbuild/msbuild-project-file-schema-reference) daha fazla bilgi için belgelere bakın.</span><span class="sxs-lookup"><span data-stu-id="b88a1-116">If you are not familiar with the overall `csproj` syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>  

<span data-ttu-id="b88a1-117">Yalnızca belirli bir hedef olarak kullanılabilir bir bağımlılık ekleme yapılır gibi koşullar kullanarak aşağıdaki örnekte:</span><span class="sxs-lookup"><span data-stu-id="b88a1-117">Adding a dependency that is available only in a specific target is done using conditions like in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

<span data-ttu-id="b88a1-118">Bağımlılık yalnızca derleme için hedef verilen karşılaşıyorsanız geçerli olacağını yukarıdaki anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="b88a1-118">The above means that the dependency will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="b88a1-119">`$(TargetFramework)` Koşulda projede ayarlanan bir MSBuild özelliğidir.</span><span class="sxs-lookup"><span data-stu-id="b88a1-119">The `$(TargetFramework)` in the condition is a MSBuild property that is being set in the project.</span></span> <span data-ttu-id="b88a1-120">En yaygın .NET Core uygulamaları için bunu yapmak gerekmez.</span><span class="sxs-lookup"><span data-stu-id="b88a1-120">For most common .NET Core applications, you will not need to do this.</span></span> 

## <a name="adding-a-dependency-to-your-project"></a><span data-ttu-id="b88a1-121">Projenize bir bağımlılık ekleme</span><span class="sxs-lookup"><span data-stu-id="b88a1-121">Adding a dependency to your project</span></span>
<span data-ttu-id="b88a1-122">Bir bağımlılık projenize eklemek oldukça basittir.</span><span class="sxs-lookup"><span data-stu-id="b88a1-122">Adding a dependency to your project is straightforward.</span></span> <span data-ttu-id="b88a1-123">İşte bir örnek Json.NET sürüm ekleme `9.0.1` projenize.</span><span class="sxs-lookup"><span data-stu-id="b88a1-123">Here is an example of how to add Json.NET version `9.0.1` to your project.</span></span> <span data-ttu-id="b88a1-124">Elbette, diğer NuGet bağımlılık için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="b88a1-124">Of course, it is applicable to any other NuGet dependency.</span></span> 

<span data-ttu-id="b88a1-125">Proje dosyanız açtığınızda, iki veya daha fazla görürsünüz `<ItemGroup>` düğümleri.</span><span class="sxs-lookup"><span data-stu-id="b88a1-125">When you open your project file, you will see two or more `<ItemGroup>` nodes.</span></span> <span data-ttu-id="b88a1-126">Düğümlerden biri zaten olduğunu fark edebilirsiniz `<PackageReference>` öğelere.</span><span class="sxs-lookup"><span data-stu-id="b88a1-126">You will notice that one of the nodes already has `<PackageReference>` elements in it.</span></span> <span data-ttu-id="b88a1-127">Bu düğüme yeni, bağımlılık ekleme ya da yeni bir tane oluşturun; Sonuç aynı olacaktır. Bu tamamen size bağlıdır aynıdır.</span><span class="sxs-lookup"><span data-stu-id="b88a1-127">You can add your new dependency to this node, or create a new one; it is completely up to you as the result will be the same.</span></span> 

<span data-ttu-id="b88a1-128">Bu örnekte bırakılan tarafından varsayılan şablonu kullanacağız `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="b88a1-128">In this example we will use the default template that is dropped by `dotnet new console`.</span></span> <span data-ttu-id="b88a1-129">Bu basit bir konsol uygulamasıdır.</span><span class="sxs-lookup"><span data-stu-id="b88a1-129">This is a simple console application.</span></span> <span data-ttu-id="b88a1-130">Biz projeyi açtığınızda, ilk buluyoruz `<ItemGroup>` zaten varolan `<PackageReference>` da.</span><span class="sxs-lookup"><span data-stu-id="b88a1-130">When we open up the project, we first find the `<ItemGroup>` with already existing `<PackageReference>` in it.</span></span> <span data-ttu-id="b88a1-131">Biz ardından aşağıdakileri ekleyin:</span><span class="sxs-lookup"><span data-stu-id="b88a1-131">We then add the following to it:</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```

<span data-ttu-id="b88a1-132">Bundan sonra biz projeyi kaydedin ve çalıştırın `dotnet restore` bağımlılık yüklemek için komutu.</span><span class="sxs-lookup"><span data-stu-id="b88a1-132">After this, we save the project and run the `dotnet restore` command to install the dependency.</span></span> 

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="b88a1-133">Tam proje şöyle görünür:</span><span class="sxs-lookup"><span data-stu-id="b88a1-133">The full project looks like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
</Project>
```

## <a name="removing-a-dependency-from-the-project"></a><span data-ttu-id="b88a1-134">Projeden bir bağımlılık kaldırma</span><span class="sxs-lookup"><span data-stu-id="b88a1-134">Removing a dependency from the project</span></span>
<span data-ttu-id="b88a1-135">Proje dosyasından bir bağımlılık kaldırmayı içerir yalnızca kaldırma `<PackageReference>` proje dosyasında.</span><span class="sxs-lookup"><span data-stu-id="b88a1-135">Removing a dependency from the project file involves simply removing the `<PackageReference>` from the project file.</span></span>
