---
ms.openlocfilehash: ca662b57fae9b1d0d41290f3052f71bca66e9bf3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234845"
---
### <a name="webutilityhtmlencode-and-webutilityhtmldecode-round-trip-bmp-correctly"></a>WebUtility.HtmlEncode ve WebUtility.HtmlDecode, BMP üzerinde doğru şekilde gidiş ve dönüş gerçekleştiriyor

|   |   |
|---|---|
|Ayrıntılar|.NET Framework 4.5’i hedefleyen uygulamalar için, Temel Çok Dilli Düzlem (BMP) dışındaki karakterler <xref:System.Net.WebUtility.HtmlDecode(System.String)> metotlarına geçirildiğinde, doğru bir şekilde gidiş ve dönüş yapar.|
|Öneri|Bu değişiklik geçerli uygulamaları etkilememelidir, ancak özgün davranışı geri yüklemek için, <code>&lt;httpRuntime&gt;</code> öğesinin <code>targetFramework</code> özniteliğini &quot;4.5&quot; dışında bir dize olarak ayarlayabilirsiniz. Ayrıca bu davranışı, hedeflenen .NET Framework sürümünden bağımsız olarak denetlemek için <code>&lt;webUtility&gt;</code> yapılandırma öğesinin <code>unicodeEncodingConformance</code> ve <code>unicodeDecodingConformance</code> özniteliklerini ayarlayabilirsiniz.|
|Kapsam|Kenar|
|Sürüm|4,5|
|Tür|Yeniden Hedefleme|
|Etkilenen API’ler|<ul><li><xref:System.Net.WebUtility.HtmlEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.HtmlEncode(System.String,System.IO.TextWriter)?displayProperty=nameWithType></li></ul>|
