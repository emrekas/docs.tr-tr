---
ms.openlocfilehash: 5a45d616001be5a2a2bdf2c654c10526125d7d86
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802642"
---
### <a name="svctraceviewer-combobox-high-contrast-change"></a>svcTraceViewer ComboBox yüksek karşıtlık Değiştir

|   |   |
|---|---|
|Ayrıntılar|İçinde [Microsoft hizmet izleme Görüntüleyicisi aracı](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md), ComboBox denetimleri içinde doğru belirli yüksek karşıtlıklı Tema rengi değil görüntülendi. .NET Framework 4.7.2 sorunu düzeltildi. Ancak, .NET Framework SDK geriye dönük uyumluluk gereksinimleri nedeniyle, düzeltme müşteriler varsayılan olarak görünür değil. .NET 4.8 aşağıdakileri ekleyerek bu değişikliği yüzeyler [AppContext yapılandırma anahtarları](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) svcTraceViewer.exe.config dosyaya:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>|
|Öneri|<ul><li>Yüksek Karşıtlık olmasını istemiyorsanız değişikliği geri çevirmek için davranışı değiştirmek nasıl, bunu aşağıdaki bölümde svcTraceViewer.exe.config dosyadan kaldırarak devre dışı bırakabilirsiniz:</li></ul><pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>|
|Kapsam|Kenar|
|Sürüm|4.8|
|Tür|Çalışma zamanı|

