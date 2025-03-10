---
ms.openlocfilehash: 2c54912e5c29b2ed8f4c8163550050e12e367263
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67857472"
---
### <a name="signedxml-and-encryptedxml-breaking-changes"></a>SignedXml ve EncryptedXml bozucu değişiklikler

|   |   |
|---|---|
|Ayrıntılar|.NET Framework 4.6.2, güvenlik giderir <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=name> ve <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=name> farklı çalışma zamanı davranışları neden olabilir. Örneğin,<ul><li>Bir belgede aynı sahip birden çok öğe varsa <code>id</code> özniteliğini ve bir imza hedeflediği bu öğelerden birini imza kökü olarak belge artık geçersiz kabul edilir.</li><li>Kurallı olmayan XPath dönüştürme algoritmaları başvurular belgeleri artık geçersiz olarak kabul edilir.</li><li>Kurallı olmayan XSLT dönüşümü algoritmaları başvurular belgeleri artık dikkat edilmelidir geçersiz.</li><li>Dış kaynak ayrılmış imzaları program yapmayı kullanımı yapmanız mümkün olacaktır.</li></ul>|
|Öneri|Geliştiriciler, kullanımını gözden geçirmek isteyebileceğiniz <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> ve <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform>, yanı sıra türetilmiş türler <xref:System.Security.Cryptography.Xml.Transform> bu yana belge alıcı işlem sırasında mümkün olmayabilir.|
|`Scope`|Küçük|
|Version|4.6.2|
|Type|Çalışma zamanı|
|Etkilenen API’ler|<ul><li><xref:System.Security.Cryptography.Xml.Transform?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.XmlDsigXPathTransform?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform?displayProperty=nameWithType></li></ul>|

