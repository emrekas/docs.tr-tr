---
ms.openlocfilehash: 4f92d773197c914a74dd7e9c18f5aab5309358ae
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760894"
---
### <a name="ensure-systemuri-uses-a-consistent-reserved-character-set"></a>System.Uri tutarlı ayrılmış karakter kümesini kullandığından emin olun

|   |   |
|---|---|
|Ayrıntılar|İçinde <xref:System.Uri?displayProperty=fullName>bazı bazen çözülmüş yüzde olarak kodlanmış karakterlerin artık sol tutarlı olarak kodlanır. Bu URI'ın yol, sorgu, parça ya da UserInfo bileşenleri erişen yöntemler ve özellikleri arasında oluşur. Yalnızca aşağıdakilerin her ikisi de true olduğunda davranışı değiştirir:<ul><li>URI kodlanmış biçiminde şu ayrılmış karakterlerden herhangi birini içeriyor: <code>:</code>, <code>'</code>, <code>(</code>, <code>)</code>, <code>!</code> veya <code>*</code>.</li><li>URI içeren bir Unicode veya kodlanmış karakter ayrılmamış. Yukarıdaki her ikisi de doğruysa kodlanmış ayrılmış karakterleri sol kodlanır. Önceki .NET Framework sürümlerinde, bunlar çözülür.</li></ul>|
|Öneri|4.7.2 ile başlayan .NET Framework sürümlerini hedefleyen uygulamalar için yeni kod çözme davranışı varsayılan olarak etkindir. Bu değişiklik, istenmeyen ise, bunu aşağıdaki ekleyerek devre dışı bırakabilirsiniz [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) geçin <code>&lt;runtime&gt;</code> uygulama yapılandırma dosyası bölümünü:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>.NET Framework'ün önceki sürümlerini hedefleyen ancak 4.7.2 .NET Framework ile başlayarak sürümler altında çalışan uygulamalar için yeni kod çözme davranışı varsayılan olarak devre dışıdır. Aşağıdakileri ekleyerek etkinleştirebilirsiniz [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) geçin <code>&lt;runtime&gt;</code> uygulama yapılandırma dosyası bölümünü::<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Kapsam|İkincil|
|Sürüm|4.7.2|
|Tür|Yeniden Hedefleme|
|Etkilenen API’ler|<ul><li><xref:System.Uri?displayProperty=nameWithType></li></ul>|

