---
title: Paket yönetimi ile kullanarak F# Azure
description: Yönetmek için paket veya Nuget kullanma F# Azure bağımlılıkları
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: b180024e2276a2fd7786f35cb922b1aa1d91f0ad
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880014"
---
# <a name="package-management-for-f-azure-dependencies"></a><span data-ttu-id="565c8-103">F# Azure Bağımlılıkları için Paket Yönetimi</span><span class="sxs-lookup"><span data-stu-id="565c8-103">Package Management for F# Azure Dependencies</span></span>

<span data-ttu-id="565c8-104">Bir paket Yöneticisi'ni kullandığınızda, Azure geliştirme için paketler almak kolaydır.</span><span class="sxs-lookup"><span data-stu-id="565c8-104">Obtaining packages for Azure development is easy when you use a package manager.</span></span> <span data-ttu-id="565c8-105">İki seçenek olan [Paket](https://fsprojects.github.io/Paket/) ve [NuGet](https://www.nuget.org/).</span><span class="sxs-lookup"><span data-stu-id="565c8-105">The two options are [Paket](https://fsprojects.github.io/Paket/) and [NuGet](https://www.nuget.org/).</span></span>

## <a name="using-paket"></a><span data-ttu-id="565c8-106">Paket kullanma</span><span class="sxs-lookup"><span data-stu-id="565c8-106">Using Paket</span></span>

<span data-ttu-id="565c8-107">Kullanıyorsanız [Paket](https://fsprojects.github.io/Paket/) bağımlılık Yöneticisi olarak, kullandığınız `paket.exe` aracı Azure bağımlılıkları ekleyin.</span><span class="sxs-lookup"><span data-stu-id="565c8-107">If you're using [Paket](https://fsprojects.github.io/Paket/) as your dependency manager, you can use the `paket.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="565c8-108">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="565c8-108">For example:</span></span>

```
> paket add nuget WindowsAzure.Storage
```

<span data-ttu-id="565c8-109">Veya kullanıyorsanız [Mono](https://www.mono-project.com/) platformlar arası .NET geliştirme için:</span><span class="sxs-lookup"><span data-stu-id="565c8-109">Or, if you're using [Mono](https://www.mono-project.com/) for cross-platform .NET development:</span></span>

```
> mono paket.exe add nuget WindowsAzure.Storage
```

<span data-ttu-id="565c8-110">Bu ekler `WindowsAzure.Storage` kümenize paket bağımlılıklarının geçerli dizinde proje için değişiklik `paket.dependencies` dosya ve paketini indirin.</span><span class="sxs-lookup"><span data-stu-id="565c8-110">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, modify the `paket.dependencies` file, and download the package.</span></span> <span data-ttu-id="565c8-111">Bağımlılıkları daha önce ayarlamış ya da bir proje üzerinde bağımlılıkları başka bir geliştirici tarafından Burada ayarlanan çalışıyorsanız, çözümlemek ve yerel olarak gibi bağımlılıklarını yükleyin:</span><span class="sxs-lookup"><span data-stu-id="565c8-111">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

```
> paket install
```

<span data-ttu-id="565c8-112">Veya, Mono geliştirme için:</span><span class="sxs-lookup"><span data-stu-id="565c8-112">Or, for Mono development:</span></span>

```
> mono paket.exe install
```

<span data-ttu-id="565c8-113">Tüm paket bağımlılıklarını, en son sürüme şöyle güncelleştirebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="565c8-113">You can update all your package dependencies to the latest version like this:</span></span>

```
> paket update
```

<span data-ttu-id="565c8-114">Veya, Mono geliştirme için:</span><span class="sxs-lookup"><span data-stu-id="565c8-114">Or, for Mono development:</span></span>

```
> mono paket.exe update
```

## <a name="using-nuget"></a><span data-ttu-id="565c8-115">Nuget kullanarak</span><span class="sxs-lookup"><span data-stu-id="565c8-115">Using Nuget</span></span>

<span data-ttu-id="565c8-116">Kullanıyorsanız [NuGet](https://www.nuget.org/) bağımlılık Yöneticisi olarak, kullandığınız `nuget.exe` aracı Azure bağımlılıkları ekleyin.</span><span class="sxs-lookup"><span data-stu-id="565c8-116">If you're using [NuGet](https://www.nuget.org/) as your dependency manager, you can use the `nuget.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="565c8-117">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="565c8-117">For example:</span></span>

```
> nuget install WindowsAzure.Storage -ExcludeVersion
```

<span data-ttu-id="565c8-118">Veya, Mono geliştirme için:</span><span class="sxs-lookup"><span data-stu-id="565c8-118">Or, for Mono development:</span></span>

```
> mono nuget.exe install WindowsAzure.Storage -ExcludeVersion
```

<span data-ttu-id="565c8-119">Bu ekler `WindowsAzure.Storage` kümenize proje geçerli dizindeki ve indirme paketi için paket bağımlılıklarının.</span><span class="sxs-lookup"><span data-stu-id="565c8-119">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, and download the package.</span></span> <span data-ttu-id="565c8-120">Bağımlılıkları daha önce ayarlamış ya da bir proje üzerinde bağımlılıkları başka bir geliştirici tarafından Burada ayarlanan çalışıyorsanız, çözümlemek ve yerel olarak gibi bağımlılıklarını yükleyin:</span><span class="sxs-lookup"><span data-stu-id="565c8-120">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

```
> nuget restore
```

<span data-ttu-id="565c8-121">Veya, Mono geliştirme için:</span><span class="sxs-lookup"><span data-stu-id="565c8-121">Or, for Mono development:</span></span>

```
> mono nuget.exe restore
```

<span data-ttu-id="565c8-122">Tüm paket bağımlılıklarını, en son sürüme şöyle güncelleştirebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="565c8-122">You can update all your package dependencies to the latest version like this:</span></span>

```
> nuget update
```

<span data-ttu-id="565c8-123">Veya, Mono geliştirme için:</span><span class="sxs-lookup"><span data-stu-id="565c8-123">Or, for Mono development:</span></span>

```
> mono nuget.exe update
```

## <a name="referencing-assemblies"></a><span data-ttu-id="565c8-124">Başvurulan Derlemeler</span><span class="sxs-lookup"><span data-stu-id="565c8-124">Referencing Assemblies</span></span>

<span data-ttu-id="565c8-125">Paketlerinizi kullanmak için F# komut dosyası için gereksinim duyduğunuz kullanarak paketlerinde derlemelerine bir `#r` yönergesi.</span><span class="sxs-lookup"><span data-stu-id="565c8-125">In order to use your packages in your F# script, you need to reference the assemblies included in the packages using a `#r` directive.</span></span> <span data-ttu-id="565c8-126">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="565c8-126">For example:</span></span>

```
> #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"
```

<span data-ttu-id="565c8-127">Gördüğünüz gibi DLL ve paket adı ile aynı tam olarak olmayabilir tam DLL adı göreli yolunu belirtmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="565c8-127">As you can see, you'll need to specify the relative path to the DLL and the full DLL name, which may not be exactly the same as the package name.</span></span> <span data-ttu-id="565c8-128">Yolun bir framework sürümünü ve büyük olasılıkla bir paket sürüm numarası içerir.</span><span class="sxs-lookup"><span data-stu-id="565c8-128">The path will include a framework version and possibly a package version number.</span></span> <span data-ttu-id="565c8-129">Tüm yüklenmiş derlemeleri bulmak için aşağıdakine benzer bir Windows komut satırında kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="565c8-129">To find all the installed assemblies, you can use something like this on a Windows command line:</span></span>

```
> cd packages/WindowsAzure.Storage
> dir /s/b *.dll
```

<span data-ttu-id="565c8-130">Bir UNIX Kabuğu'nda bir şey gibi veya bu:</span><span class="sxs-lookup"><span data-stu-id="565c8-130">Or in a Unix shell, something like this:</span></span>

```
> find packages/WindowsAzure.Storage -name "*.dll"
```

<span data-ttu-id="565c8-131">Bu yüklenen derlemeler için yollar sağlar.</span><span class="sxs-lookup"><span data-stu-id="565c8-131">This will give you the paths to the installed assemblies.</span></span> <span data-ttu-id="565c8-132">Burada, framework sürümünüz için doğru yol seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="565c8-132">From there, you can select the correct path for your framework version.</span></span>
