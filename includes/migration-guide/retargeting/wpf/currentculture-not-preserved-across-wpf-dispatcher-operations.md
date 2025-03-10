---
ms.openlocfilehash: cce19d6c9afa5f5ce9bb17b5b5d92f2060a08414
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804441"
---
### <a name="currentculture-is-not-preserved-across-wpf-dispatcher-operations"></a>CurrentCulture WPF dağıtıcısı işlemleri arasında korunmaz

|   |   |
|---|---|
|Ayrıntılar|.NET Framework 4. 6 ' başlayarak, değişikliklerini <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> veya <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> içinde yapılan bir <xref:System.Windows.Threading.Dispatcher?displayProperty=name> bu dağıtıcı işlemi sonunda kaybolacak. Benzer şekilde, değişikliklerini <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> veya <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> işlemi zaman işlemini yürütür yansımayabilir dışında bir dağıtıcı yapılan. Pratikte, konuşma, diğer bir deyişle <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> ve <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> değişiklikleri WPF UI geri çağırmaları WPF uygulamasında diğer kod arasında akan. Bir değişiklik nedeniyle budur <xref:System.Threading.ExecutionContext?displayProperty=name> neden <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> ve <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> yürütme bağlamı başlangıçta .NET Framework 4.6 targeting uygulamalarla depolanacak. WPF dağıtıcısı operations işlemi başlar ve işlem tamamlandığında, önceki bağlamı geri yüklemek için kullanılan yürütme bağlamı depolayın. Çünkü <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> ve <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> işleminin dışında bir dağıtıcı işlemi içinde bunlara değişiklikler kalıcı değildir, bu içerik artık parçasıdır.|
|Öneri|Bu değişiklikten etkilenen uygulamalar iş etrafında istenen depolayarak <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> veya <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> bir alan ve denetimi (kullanıcı Arabirimi olay geri çağırma işleyicilerinin dahil) tüm dağıtıcı işlemi gövdesi içinde doğru <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> ve <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> ayarlanır. Alternatif olarak, ExecutionContext değiştiği temel WPF bu değişiklik, yalnızca .NET Framework 4.6 veya daha yeni hedefleyen uygulamaları etkiler, bu sonu, hedef .NET Framework 4.6 veya üzeri de çalışabilir .NET Framework 4.5.2.Apps hedefleyerek önlenebilir. Bunu aşağıdaki uyumluluk ayarlayarak anahtarı:<pre><code class="lang-csharp">AppContext.SetSwitch(&quot;Switch.System.Globalization.NoAsyncCurrentCulture&quot;, true);&#13;&#10;</code></pre>.NET Framework 4.6.2 WPF ile bu sorun düzeltilmiştir. .NET Framework 4.6, 4.6.1 üzerinden de de çözülmüştür [KB 3139549](https://support.microsoft.com/kb/3139549). .NET Framework 4.6 veya sonraki sürümlerini hedefleyen uygulamalar otomatik olarak WPF uygulamalarında - doğru davranışları alacak <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> / <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name>) dağıtıcısı işlemleri korunur.|
|Kapsam|İkincil|
|Sürüm|4.6|
|Tür|Yeniden Hedefleme|

