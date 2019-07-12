---
ms.openlocfilehash: de40d16dbb5e7a7a49ae0988342b3eb75bc078c5
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804505"
---
### <a name="currentculture-and-currentuiculture-flow-across-tasks"></a>CurrentCulture ve CurrentUICulture akışı görevleri arasında

|   |   |
|---|---|
|Ayrıntılar|.NET Framework 4.6, başlangıç <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> ve <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> iş parçacığının içinde depolanan <xref:System.Threading.ExecutionContext?displayProperty=name>, zaman uyumsuz işlemler arasında akar. Yani değişikliklerini <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> veya <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> daha sonra zaman uyumsuz olarak çalışan görevler yansıtılır. Bu önceki .NET Framework sürümü davranışından farklıdır (hangi sıfırlama <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> ve <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> tüm zaman uyumsuz görevler).|
|Öneri|Bu değişiklikten etkilenen uygulamalar iş etrafında açıkça istenen ayarlayarak <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> veya <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> ilk işlemi zaman uyumsuz bir görev olarak. Alternatif olarak, eski davranışı (akışı, <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> / <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name>) aşağıdaki uyumluluk anahtarı ayarlayarak seçimi yaptıysanız:<pre><code class="lang-csharp">AppContext.SetSwitch(&quot;Switch.System.Globalization.NoAsyncCurrentCulture&quot;, true);&#13;&#10;</code></pre>.NET Framework 4.6.2 WPF ile bu sorun düzeltilmiştir. .NET Framework 4.6, 4.6.1 üzerinden de de çözülmüştür [KB 3139549](https://support.microsoft.com/kb/3139549). .NET Framework 4.6 veya sonraki sürümlerini hedefleyen uygulamalar otomatik olarak WPF uygulamalarında - doğru davranışları alacak <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> / <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name>) dağıtıcısı işlemleri korunur.|
|Kapsam|İkincil|
|Sürüm|4.6|
|Tür|Yeniden Hedefleme|
|Etkilenen API’ler|<ul><li><xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType></li><li><xref:System.Threading.Thread.CurrentCulture?displayProperty=nameWithType></li><li><xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=nameWithType></li><li><xref:System.Threading.Thread.CurrentUICulture?displayProperty=nameWithType></li></ul>|

