---
ms.openlocfilehash: 8049bf01bc10c5913fa11b25e49afd1b1317eecc
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802957"
---
### <a name="wpf-spell-checking-fails-in-unexpected-ways"></a>WPF yazım denetimi beklenmedik bir şekilde başarısız oluyor

|   |   |
|---|---|
|Ayrıntılar|Bu, bir WPF yazım denetleyicisi sorunların sayısını içerir:<ul><li>WPF yazım denetleyicisi bazen oluşturur <xref:System.Runtime.InteropServices.COMException?displayProperty=name></li><li>WPF yazım denetleyicisi başarısız <xref:System.UnauthorizedAccessException> 'farklı kullanıcı olarak çalıştır' ı kullanarak uygulamaları başlatılan olduğunda</li><li>WPF yazım denetleyicisi, yazım hatalarını Almanca 'Hausnummer' gibi bileşik sözcüklerin yanlış tanımlar.</li></ul>|
|Öneri|Sorun #1 - .NET Framework 4.6.2 düzeltildiğini sorun #2 - WPF yazım denetleyicisi 'farklı kullanıcı olarak çalıştır' ı kullanarak uygulama başlatıldığında, artık desteklenmiyor. .NET Framework 4.6.2 başlayarak, bu şekilde başlatılan uygulamalara artık beklenmedik bir şekilde kilitlenir - bunun yerine yazım denetleyicisi sessiz bir şekilde devre dışı bırakılır. Sorun #3 - .NET Framework 4.6.2 düzeltilmiştir.|
|Kapsam|Kenar|
|Sürüm|4.6.1|
|Tür|Çalışma zamanı|

