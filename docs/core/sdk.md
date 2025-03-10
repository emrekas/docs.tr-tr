---
title: .NET Core SDK genel bakış
description: .NET Core projeleri oluşturmak için kullanılan bir dizi kitaplık ve araç olan .NET Core SDK hakkında bilgi edinin.
ms.date: 07/31/2019
ms.technology: dotnet-cli
ms.openlocfilehash: f4c4982bacaf58c1b8c7db6c5319bd314e89b7ed
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2019
ms.locfileid: "69566248"
---
# <a name="net-core-sdk-overview"></a>.NET Core SDK genel bakış

.NET Core SDK, geliştiricilerin .NET Core Uygulamaları ve kitaplıkları oluşturmalarına izin veren bir kitaplıklar ve araçlar kümesidir. Uygulama derlemek ve çalıştırmak için kullanılan aşağıdaki bileşenleri içerir:

- .NET Core CLI araçları.
- .NET Core kitaplıkları ve çalışma zamanı.
- `dotnet` [Sürücü](tools/index.md#driver).

## <a name="acquiring-the-net-core-sdk"></a>.NET Core SDK alınıyor

Herhangi bir araç ile olduğu gibi, ilk şey makinenize araçları almak için kullanılır. Senaryonuza bağlı olarak, aşağıdaki yöntemlerden birini kullanarak SDK 'Yı yükleyebilirsiniz:

- Yerel yükleyicileri kullanın.
- Yükleme kabuğu betiğini kullanın.

Yerel yükleyiciler öncelikle geliştirici makinelerine yöneliktir. SDK, Windows üzerinde Ubuntu veya MSI paketlerinde DEB paketleri gibi desteklenen her platformun yerel yüklemesi mekanizması kullanılarak dağıtılır. Bu yükleyiciler, kullanıcının yüklemeden hemen sonra SDK 'Yı kullanması için gerektiğinde ortamı yükler ve ayarlar. Ancak, makine üzerinde yönetici ayrıcalıklarına de gereksinim duyar. [.Net İndirmeleri](https://dotnet.microsoft.com/download) sayfasına yüklemek için SDK 'yı bulabilirsiniz.

Diğer yandan, yönetim ayrıcalıkları gerektirmeyen betikleri yükler. Bununla birlikte, makineye hiçbir önkoşul de yüklemez; tüm önkoşulları el ile yüklemeniz gerekir. Betikler genellikle derleme sunucularını ayarlamak için veya araçları yönetici ayrıcalıkları olmadan yüklemek istediğinizde (yukarıdaki önkoşulları desteklenmediği uyarısıyla). Daha fazla bilgi için [komut dosyası başvurusunu yükleyebilirsiniz](tools/dotnet-install-script.md) makalesine ulaşabilirsiniz. CI yapı sunucunuzda SDK 'Yı ayarlama hakkında bilgi edinmek istiyorsanız [sürekli tümleştirme (CI) makalesinde .NET Core SDK ve araçları kullanma](tools/using-ci-with-cli.md) makalesine bakın.

Varsayılan olarak SDK, "yan yana" (SxS) şekilde yüklenir. Bu, CLı araçlarının birden çok sürümünün tek bir makine üzerinde herhangi bir zamanda birlikte yer alabileceği anlamına gelir. CLı komutlarını çalıştırırken sürümün nasıl çekilmesi, [kullanılacak .NET Core sürümünü Seç](versions/selection.md) makalesinde daha ayrıntılı olarak açıklanmıştır.

## <a name="see-also"></a>Ayrıca bkz.

- [.NET Core CLI](tools/index.md)
- [.NET Core sürüm oluşturmaya genel bakış](versions/index.md)
- [.NET Core çalışma zamanı ve SDK 'sını kaldırma](versions/remove-runtime-sdk-versions.md)
- [Kullanılacak .NET Core sürümünü seçin](versions/selection.md)
