---
ms.openlocfilehash: 5b3f9bcb56d3e34568afd8b97fb9ebe09a677f4c
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802610"
---
### <a name="net-interop-will-now-queryinterface-for-iagileobject-a-winrt-interface"></a>.NET birlikte çalışabilirliği IAgileObject (WinRT arabirimi) için artık QueryInterface olur

|   |   |
|---|---|
|Ayrıntılar|Bir WinRT olay bir .NET temsilci ile kullanırken, Windows ile .NET Framework 4.8 başlangıç IAgileObject için QI olur.  .NET Framework'ün önceki sürümlerinde, çalışma zamanı bu QI başarısız olur ve olaya abone.<ul><li>[x] quirked</li></ul>|
|Öneri|IAgileObject sonları yürütme için QI etkinleştirme, bu kod şu yapılandırma ayarı devre dışı bırakabilirsiniz. <h4>1\. yöntem: Ortam değişkeni</h4> Aşağıdaki ortam değişkeni: COMPLUS_DisableCCWSupportIAgileObject ayarlamak bu ortam değişkeni devralan herhangi bir ortam 1 yöntemi etkiler =. Bu yalnızca bir tek bir konsol oturumu olabilir veya ortam değişkeni genel olarak ayarlarsanız, bu makinenin tamamını etkileyebilir. Ortam değişkeni adı büyük küçük harfe duyarlı değil. <h4>2\. yöntem: Kayıt defteri</h4> Kayıt Defteri Düzenleyicisi'ni (regedit.exe) kullanarak, aşağıdaki: değer adını ekleyin ya da aşağıdaki subkeys:HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework HKEY_CURRENT_USER\SOFTWARE\Microsoft.NETFrameworkThen bulun: DisableCCWSupportIAgileObject türü: DWORD (32-bit) değeri (REG_WORD olarak da bilinir) değeri: Windows kayıt 1yeni kullanabilirsiniz Bu değer, bir komut satırı veya komut dosyası ortamından eklemek için EXE Aracı'nı tıklatın. Örneğin:<pre><code class="lang-console">reg add HKLM\SOFTWARE\Microsoft\.NETFramework /v DisableCCWSupportIAgileObject /t REG_DWORD /d 1&#13;&#10;</code></pre>Bu durumda, <code>HKLM</code> yerine kullanılan <code>HKEY_LOCAL_MACHINE</code>. Kullanım <code>reg add /?</code> görmek için bu sözdizimi hakkında Yardım. Kayıt defteri değeri adı büyük küçük harfe duyarlı değil.|
|Kapsam|Kenar|
|Sürüm|4.8|
|Tür|Çalışma zamanı|

