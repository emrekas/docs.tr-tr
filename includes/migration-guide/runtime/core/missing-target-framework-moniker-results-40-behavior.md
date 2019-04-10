---
ms.openlocfilehash: 29b8feb7959c718391b963c8402b97351b93fa49
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235975"
---
### <a name="missing-target-framework-moniker-results-in-40-behavior"></a>Eksik hedef çerçeve adı 4.0 davranışla sonuçlanır.

|   |   |
|---|---|
|Ayrıntılar|Olmadan uygulamalar bir <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> otomatik olarak .NET Framework 4.0 (quirks) semantiği kullanarak çalışan derleme düzeyi gerçekleştirilse uygulanır. Yüksek kaliteli emin olmak için birlikte tüm ikili dosyaları açıkça öznitelikli önerilir bir <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> birlikte oluşturuldukları .NET Framework sürümünü gösteren. Otomatik olarak uygulamak MSBuild proje dosyasında hedef çerçeve adı kullanarak neden olacağını unutmayın bir <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name>.|
|Öneri|A <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> doğrudan derleme veya bir hedef çerçeve belirterek öznitelik ekleme yoluyla iletilmelidir [proje dosyası veya Visual Studio Proje Özellikleri GUI](https://devblogs.microsoft.com/visualstudio/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework/).|
|Kapsam|Ana|
|Sürüm|4,5|
|Tür|Çalışma zamanı|
