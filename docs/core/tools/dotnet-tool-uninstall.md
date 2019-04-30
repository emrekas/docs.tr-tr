---
title: DotNet Aracı kaldırma komutu
description: Dotnet araç kaldırma komutu makinenizden belirtilen .NET Core genel aracı kaldırır.
ms.date: 05/29/2018
ms.openlocfilehash: 4d53d305131e3399ab5d9c19f9319f3ba3544c19
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61648561"
---
# <a name="dotnet-tool-uninstall"></a><span data-ttu-id="049da-103">DotNet Aracı kaldırma</span><span class="sxs-lookup"><span data-stu-id="049da-103">dotnet tool uninstall</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="049da-104">Ad</span><span class="sxs-lookup"><span data-stu-id="049da-104">Name</span></span>

<span data-ttu-id="049da-105">`dotnet tool uninstall` -Belirtilen kaldırır [.NET Core genel aracı](global-tools.md) makinenizden.</span><span class="sxs-lookup"><span data-stu-id="049da-105">`dotnet tool uninstall` - Uninstalls the specified [.NET Core Global Tool](global-tools.md) from your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="049da-106">Synopsis</span><span class="sxs-lookup"><span data-stu-id="049da-106">Synopsis</span></span>

```console
dotnet tool uninstall <PACKAGE_NAME> <-g|--global>
dotnet tool uninstall <PACKAGE_NAME> <--tool-path>
dotnet tool uninstall <-h|--help>
```

## <a name="description"></a><span data-ttu-id="049da-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="049da-107">Description</span></span>

<span data-ttu-id="049da-108">`dotnet tool uninstall` Komutu, .NET Core Araçları Genel makinenizden kaldırmak bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="049da-108">The `dotnet tool uninstall` command provides a way for you to uninstall .NET Core Global Tools from your machine.</span></span> <span data-ttu-id="049da-109">Komutunu kullanmak için aşağıdakilerden birini kullanarak bir kullanıcı genelinde aracı kaldırmak istediğiniz belirtmeniz gerekir `--global` nerede yolunu belirtin veya seçeneği kullanılarak yüklenen aracı `--tool-path` seçeneği.</span><span class="sxs-lookup"><span data-stu-id="049da-109">To use the command, you either have to specify that you want to remove a user-wide tool using the `--global` option or specify a path to where the tool is installed using the `--tool-path` option.</span></span>

## <a name="arguments"></a><span data-ttu-id="049da-110">Arguments</span><span class="sxs-lookup"><span data-stu-id="049da-110">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="049da-111">.NET Core genel kaldırmak için Aracı'nı içeren NuGet paket adı/kimliği.</span><span class="sxs-lookup"><span data-stu-id="049da-111">Name/ID of the NuGet package that contains the .NET Core Global Tool to uninstall.</span></span> <span data-ttu-id="049da-112">Paket adını kullanarak bulabilirsiniz [dotnet araç listesi](dotnet-tool-list.md) komutu.</span><span class="sxs-lookup"><span data-stu-id="049da-112">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="049da-113">Seçenekler</span><span class="sxs-lookup"><span data-stu-id="049da-113">Options</span></span>

`-g|--global`

<span data-ttu-id="049da-114">Aracının kaldırılması için kullanıcı genelinde yüklemesinden olduğunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="049da-114">Specifies that the tool to be removed is from a user-wide installation.</span></span> <span data-ttu-id="049da-115">İle birleştirilemez `--tool-path` seçeneği.</span><span class="sxs-lookup"><span data-stu-id="049da-115">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="049da-116">Bu seçeneği belirtmezseniz, belirtmeniz gerekir `--tool-path` seçeneği.</span><span class="sxs-lookup"><span data-stu-id="049da-116">If you don't specify this option, you must specify the `--tool-path` option.</span></span>

`-h|--help`

<span data-ttu-id="049da-117">Komut için kısa bir Yardım yazdırır.</span><span class="sxs-lookup"><span data-stu-id="049da-117">Prints out a short help for the command.</span></span>

`--tool-path <PATH>`

<span data-ttu-id="049da-118">Konum, genel Aracı'nı kaldırmak konumu belirtir.</span><span class="sxs-lookup"><span data-stu-id="049da-118">Specifies the location where to uninstall the Global Tool.</span></span> <span data-ttu-id="049da-119">YOL mutlak veya göreli olabilir.</span><span class="sxs-lookup"><span data-stu-id="049da-119">PATH can be absolute or relative.</span></span> <span data-ttu-id="049da-120">İle birleştirilemez `--global` seçeneği.</span><span class="sxs-lookup"><span data-stu-id="049da-120">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="049da-121">Bu seçeneği belirtmezseniz, belirtmeniz gerekir `--global` seçeneği.</span><span class="sxs-lookup"><span data-stu-id="049da-121">If you don't specify this option, you must specify the `--global` option.</span></span>

## <a name="examples"></a><span data-ttu-id="049da-122">Örnekler</span><span class="sxs-lookup"><span data-stu-id="049da-122">Examples</span></span>

<span data-ttu-id="049da-123">Kaldırır [dotnetsay](https://www.nuget.org/packages/dotnetsay/) genel aracı:</span><span class="sxs-lookup"><span data-stu-id="049da-123">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool:</span></span>

`dotnet tool uninstall -g dotnetsay`

<span data-ttu-id="049da-124">Kaldırır [dotnetsay](https://www.nuget.org/packages/dotnetsay/) belirli bir Windows klasörden genel aracı:</span><span class="sxs-lookup"><span data-stu-id="049da-124">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool from a specific Windows folder:</span></span>

`dotnet tool uninstall dotnetsay --tool-path c:\global-tools`

<span data-ttu-id="049da-125">Kaldırır [dotnetsay](https://www.nuget.org/packages/dotnetsay/) belirli Linux/macOS klasöründe bulunan genel aracı:</span><span class="sxs-lookup"><span data-stu-id="049da-125">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool from a specific Linux/macOS folder:</span></span>

`dotnet tool uninstall dotnetsay --tool-path ~/bin`

## <a name="see-also"></a><span data-ttu-id="049da-126">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="049da-126">See also</span></span>

- [<span data-ttu-id="049da-127">.NET core Araçları Genel</span><span class="sxs-lookup"><span data-stu-id="049da-127">.NET Core Global Tools</span></span>](global-tools.md)
