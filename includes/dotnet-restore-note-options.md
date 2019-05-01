---
ms.openlocfilehash: 319aca3c5edea7e7bb64fe9081d9f23d3012ff9e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61648635"
---
> [!NOTE]
> <span data-ttu-id="166fa-101">.NET Core 2.0 ile başlayarak, çalıştırma gerekmez [ `dotnet restore` ](~/docs/core/tools/dotnet-restore.md) tüm komutlar tarafından gibi örtük olarak çalıştırıldığında çünkü `dotnet build` ve `dotnet run`, gerçekleşmesi için bir geri yükleme gerektirir.</span><span class="sxs-lookup"><span data-stu-id="166fa-101">Starting with .NET Core 2.0, you don't have to run [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) because it's run implicitly by all commands, such as `dotnet build` and `dotnet run`, that require a restore to occur.</span></span> <span data-ttu-id="166fa-102">Bunu hala geçerli bir komut burada açık bir geri yükleme yaparsanız anlamlı, bazı senaryolarda olduğu gibi [sürekli tümleştirme derlemeleri Azure DevOps Hizmetleri'nde](/azure/devops/build-release/apps/aspnet/build-aspnet-core) veya açıkça zaman denetlemek için gereken derleme sistemlerinde geri yükleme gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="166fa-102">It's still a valid command in certain scenarios where doing an explicit restore makes sense, such as [continuous integration builds in Azure DevOps Services](/azure/devops/build-release/apps/aspnet/build-aspnet-core) or in build systems that need to explicitly control the time at which the restore occurs.</span></span>
>
> <span data-ttu-id="166fa-103">Bu komut ayrıca destekler `dotnet restore` seçenekleri uzun biçiminde geçirildiğinde (örneğin, `--source`).</span><span class="sxs-lookup"><span data-stu-id="166fa-103">This command also supports the `dotnet restore` options when passed in the long form (for example, `--source`).</span></span> <span data-ttu-id="166fa-104">Form Seçenekleri gibi kısa `-s`, desteklenmez.</span><span class="sxs-lookup"><span data-stu-id="166fa-104">Short form options, such as `-s`, are not supported.</span></span>