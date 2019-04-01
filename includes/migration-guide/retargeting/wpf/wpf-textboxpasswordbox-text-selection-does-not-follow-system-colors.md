---
ms.openlocfilehash: 649e4456ef6a11903ab1b390baf56583f31f5562
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760922"
---
### <a name="wpf-textboxpasswordbox-text-selection-does-not-follow-system-colors"></a>Sistem renkleri WPF metin/PasswordBox metin seçimi uymuyor

|   |   |
|---|---|
|Ayrıntılar|.NET Framework 4.7.1 ve önceki sürümlerinde, WPF <code>System.Windows.Controls.TextBox</code> ve <code>System.Windows.Controls.PasswordBox</code> donatıcı katmanında metin seçimi yalnızca getirebilir. Bazı sistem temalar, bu metin, okunmasını kolaylaştırır occlude.  .NET Framework'teki 4.7.2 ve daha sonra geliştiricilerin bu sorunu azaltır bir donatıcı tabanlı olmayan seçim işleme düzeni etkinleştirme seçeneğiniz vardır.|
|Öneri|Bu değişiklik yararlanmak isteyen bir geliştirici aşağıdaki AppContext bayrak uygun şekilde ayarlamanız gerekir.  Bu özelliği kullanmak için yüklü olan .NET Framework sürümü 4.7.2 olmalıdır veya büyük. Donatıcı tabanlı olmayan seçim etkin için aşağıdaki AppContext bayrağını kullanın.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Text.UseAdornerForTextboxSelectionRendering=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Kapsam|Kenar|
|Sürüm|4.7.2|
|Tür|Yeniden Hedefleme|

