---
ms.openlocfilehash: 242a9952cb47d170aceffa1aa392071eb40cc6ab
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760692"
---
### <a name="rsacng-and-dsacng-are-once-again-usable-in-partial-trust-scenarios"></a>RSACng ve DSACng kısmi güven senaryolarında yine kullanılabilir.

|   |   |
|---|---|
|Ayrıntılar|CngLightup (birden çok üst düzey şifreleme içinde kullanılan API'leri gibi <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType>) ve <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> bazı durumlarda, tam güven kullanır. P/Invoke'lar sunduğundan olmadan bunlar <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType> izinleri ve kod yollarını burada <xref:System.Security.Cryptography.CngKey?displayProperty=nameWithType> için izni taleplerine sahiptir <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType>. .NET Framework 4.6.2 ile başlayarak, CngLightup geçmek için kullanılan <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> mümkün olan her yerde. Sonuç olarak, kısmi güven uygulamaları, başarılı bir şekilde kullanılan <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType> başarısız ve throw başladığı <xref:System.Security.SecurityException> özel durumlar. Bu değişiklik, böylece tüm işlevleri CngLightup kullanarak gerekli izinlere sahip gerekli onaylar ekler.|
|Öneri|.NET Framework 4.6.2 bu değişikliğe, kısmi güven uygulamaları olumsuz etkilediği, .NET Framework 4.7.1 yükseltin.|
|Kapsam|Kenar|
|Sürüm|4.6.2|
|Tür|Çalışma zamanı|
|Etkilenen API’ler|<ul><li><xref:System.Security.Cryptography.DSACng.%23ctor(System.Security.Cryptography.CngKey)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.Key?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.LegalKeySizes?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.CreateSignature(System.Byte[])?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.VerifySignature(System.Byte[],System.Byte[])?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.%23ctor(System.Security.Cryptography.CngKey)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.Key?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.Decrypt(System.Byte[],System.Security.Cryptography.RSAEncryptionPadding)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.SignHash(System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|

