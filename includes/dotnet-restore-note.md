---
ms.openlocfilehash: 975edd1bda507b46da353db788d9730560f9b573
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632101"
---
> [!NOTE]
> <span data-ttu-id="358f2-101">.NET Core 2.0 SDK'sı ile başlayarak, çalıştırma gerekmez [ `dotnet restore` ](~/docs/core/tools/dotnet-restore.md) bir geri yükleme, örneğin, gerçekleşmesi için gerekli tüm komutlar tarafından örtük olarak çalıştırıldığından `dotnet new`, `dotnet build` ve `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="358f2-101">Starting with .NET Core 2.0 SDK, you don't have to run [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) because it's run implicitly by all commands that require a restore to occur, such as `dotnet new`, `dotnet build` and `dotnet run`.</span></span>
> <span data-ttu-id="358f2-102">Bunu hala geçerli bir komut burada açık bir geri yükleme yaparsanız anlamlı, bazı senaryolarda olduğu gibi [sürekli tümleştirme derlemeleri Azure DevOps Hizmetleri'nde](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) veya açıkça zaman denetlemek için gereken derleme sistemlerinde geri yükleme gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="358f2-102">It's still a valid command in certain scenarios where doing an explicit restore makes sense, such as [continuous integration builds in Azure DevOps Services](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) or in build systems that need to explicitly control the time at which the restore occurs.</span></span>
