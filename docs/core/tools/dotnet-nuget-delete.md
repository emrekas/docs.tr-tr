---
title: DotNet NuGet Delete komutu
description: DotNet-NuGet-Delete komutu sunucudan bir paketi siler veya listesini kaldırır.
author: karann-msft
ms.date: 06/26/2019
ms.openlocfilehash: 70316a0baa2cf9923738a53af561b5c77014c3ff
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2019
ms.locfileid: "70202576"
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="4b5ae-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="4b5ae-103">dotnet nuget delete</span></span>

<span data-ttu-id="4b5ae-104">**Bu konu şu şekilde geçerlidir: ✓** .NET Core 1. x SDK ve sonraki sürümleri</span><span class="sxs-lookup"><span data-stu-id="4b5ae-104">**This topic applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="4b5ae-105">Ad</span><span class="sxs-lookup"><span data-stu-id="4b5ae-105">Name</span></span>

<span data-ttu-id="4b5ae-106">`dotnet nuget delete`-Sunucudan bir paketi siler veya listesini kaldırır.</span><span class="sxs-lookup"><span data-stu-id="4b5ae-106">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4b5ae-107">Özeti</span><span class="sxs-lookup"><span data-stu-id="4b5ae-107">Synopsis</span></span>

```console
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [--interactive] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```

## <a name="description"></a><span data-ttu-id="4b5ae-108">Açıklama</span><span class="sxs-lookup"><span data-stu-id="4b5ae-108">Description</span></span>

<span data-ttu-id="4b5ae-109">`dotnet nuget delete` Komutu sunucusundan bir paketi siler veya listesini kaldırır.</span><span class="sxs-lookup"><span data-stu-id="4b5ae-109">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="4b5ae-110">[NuGet.org](https://www.nuget.org/)için eylem, paketin listesini kaldırdır.</span><span class="sxs-lookup"><span data-stu-id="4b5ae-110">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="4b5ae-111">Arguments</span><span class="sxs-lookup"><span data-stu-id="4b5ae-111">Arguments</span></span>

* **`PACKAGE_NAME`**

  <span data-ttu-id="4b5ae-112">Silinecek paketin ad/KIMLIĞI.</span><span class="sxs-lookup"><span data-stu-id="4b5ae-112">Name/ID of the package to delete.</span></span>

* **`PACKAGE_VERSION`**

  <span data-ttu-id="4b5ae-113">Silinecek paketin sürümü.</span><span class="sxs-lookup"><span data-stu-id="4b5ae-113">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="4b5ae-114">Seçenekler</span><span class="sxs-lookup"><span data-stu-id="4b5ae-114">Options</span></span>

* **`--force-english-output`**

  <span data-ttu-id="4b5ae-115">Uygulamayı, sabit, Ingilizce tabanlı bir kültür kullanılarak çalışmaya zorlar.</span><span class="sxs-lookup"><span data-stu-id="4b5ae-115">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="4b5ae-116">Komut için kısa bir yardım yazdırır.</span><span class="sxs-lookup"><span data-stu-id="4b5ae-116">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="4b5ae-117">Komutun, kimlik doğrulaması gibi işlemler için el ile eylem yapmasına izin verir.</span><span class="sxs-lookup"><span data-stu-id="4b5ae-117">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="4b5ae-118">.NET Core 2,2 SDK 'dan beri kullanılabilir seçeneği.</span><span class="sxs-lookup"><span data-stu-id="4b5ae-118">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="4b5ae-119">Sunucu için API anahtarı.</span><span class="sxs-lookup"><span data-stu-id="4b5ae-119">The API key for the server.</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="4b5ae-120">Kaynak URL 'ye "API/v2/Package" eklemeyin.</span><span class="sxs-lookup"><span data-stu-id="4b5ae-120">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="4b5ae-121">.NET Core 2,1 SDK 'dan beri kullanılabilir seçeneği.</span><span class="sxs-lookup"><span data-stu-id="4b5ae-121">Option available since .NET Core 2.1 SDK.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="4b5ae-122">Kullanıcı giriş veya teyitlerini istemez.</span><span class="sxs-lookup"><span data-stu-id="4b5ae-122">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="4b5ae-123">Sunucu URL 'sini belirtir.</span><span class="sxs-lookup"><span data-stu-id="4b5ae-123">Specifies the server URL.</span></span> <span data-ttu-id="4b5ae-124">NuGet.org için desteklenen URL 'ler `https://www.nuget.org`, `https://www.nuget.org/api/v3`, ve `https://www.nuget.org/api/v2/package`içerir.</span><span class="sxs-lookup"><span data-stu-id="4b5ae-124">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="4b5ae-125">Özel akışlar için ana bilgisayar adını (örneğin, `%hostname%/api/v3`) değiştirin.</span><span class="sxs-lookup"><span data-stu-id="4b5ae-125">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

## <a name="examples"></a><span data-ttu-id="4b5ae-126">Örnekler</span><span class="sxs-lookup"><span data-stu-id="4b5ae-126">Examples</span></span>

* <span data-ttu-id="4b5ae-127">Paketin `Microsoft.AspNetCore.Mvc`1,0 sürümünü siler:</span><span class="sxs-lookup"><span data-stu-id="4b5ae-127">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0
  ```

* <span data-ttu-id="4b5ae-128">Paketin `Microsoft.AspNetCore.Mvc`1,0 sürümünü siler, kimlik bilgilerini veya diğer girişleri kullanıcıya sormadan:</span><span class="sxs-lookup"><span data-stu-id="4b5ae-128">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive
  ```
