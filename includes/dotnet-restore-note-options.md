---
ms.openlocfilehash: 319aca3c5edea7e7bb64fe9081d9f23d3012ff9e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61648635"
---
> [!NOTE]
> .NET Core 2.0 ile başlayarak, çalıştırma gerekmez [ `dotnet restore` ](~/docs/core/tools/dotnet-restore.md) tüm komutlar tarafından gibi örtük olarak çalıştırıldığında çünkü `dotnet build` ve `dotnet run`, gerçekleşmesi için bir geri yükleme gerektirir. Bunu hala geçerli bir komut burada açık bir geri yükleme yaparsanız anlamlı, bazı senaryolarda olduğu gibi [sürekli tümleştirme derlemeleri Azure DevOps Hizmetleri'nde](/azure/devops/build-release/apps/aspnet/build-aspnet-core) veya açıkça zaman denetlemek için gereken derleme sistemlerinde geri yükleme gerçekleşir.
>
> Bu komut ayrıca destekler `dotnet restore` seçenekleri uzun biçiminde geçirildiğinde (örneğin, `--source`). Form Seçenekleri gibi kısa `-s`, desteklenmez.