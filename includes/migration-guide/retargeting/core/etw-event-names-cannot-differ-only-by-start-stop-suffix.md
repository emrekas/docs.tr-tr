---
ms.openlocfilehash: 71c81cf188fa4c2300661f10eb87e7ae00e031f6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234580"
---
### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a>ETW olay adları yalnızca "Başlangıç" veya "Durdur" soneki ile farklı olamaz

|   |   |
|---|---|
|Ayrıntılar|.NET Framework 4.6 ve 4.6.1, çalışma zamanı oluşturur bir <xref:System.ArgumentException> iki olay izleme için Windows (ETW) olayı adları farklı yalnızca ne zaman bir &quot;Başlat&quot; veya &quot;Durdur&quot; soneki (bir olay zamanadlıolarak<code>LogUser</code>ve başka adlı <code>LogUserStart</code>). Bu durumda, çalışma zamanı, tüm günlük yayılamıyor olay kaynağı oluşturulamıyor.|
|Öneri|Özel durum önlemek için hiçbir iki olay adları yalnızca farklı olun bir &quot;Başlat&quot; veya &quot;Durdur&quot; soneki. Bu gereksinim, .NET Framework 4.6.2 ile başlayarak kaldırıldı; çalışma zamanı tarafından yalnızca farklı olay adlarını ayırt etmek &quot;Başlat&quot; ve &quot;Durdur&quot; soneki.|
|Kapsam|Kenar|
|Sürüm|4.6|
|Tür|Yeniden Hedefleme|
