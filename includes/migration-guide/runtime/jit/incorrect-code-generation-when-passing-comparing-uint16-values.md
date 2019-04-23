---
ms.openlocfilehash: ad624a665dbe8e989ea05acc20213809e515e6ac
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805298"
---
### <a name="incorrect-code-generation-when-passing-and-comparing-uint16-values"></a>Yanlış kod oluşturma geçirme ve UInt16 değerleri karşılaştırma

|   |   |
|---|---|
|Ayrıntılar|Bazı durumlarda .NET Framework 4.7 sunulan değişiklikler nedeniyle, .NET Framework 4.7 üzerinde hatalı çalışan uygulamalar, JIT Derleyici tarafından oluşturulan kodu iki karşılaştırır <code>T:System.UInt16</code> değerleri. Daha fazla bilgi için [sorun #11508: Geçirme ve karşılaştırma ushort args sessiz hatalı codegen](https://github.com/dotnet/coreclr/issues/11508) GitHub.com üzerinde.|
|Öneri|.NET Framework 4.7 16-bit işeritsiz değerler karşılaştırma içindeki sorunlarla karşılaşırsanız, .NET Framework 4.7.1 yükseltin.|
|Kapsam|Kenar|
|Sürüm|4.7|
|Tür|Çalışma zamanı|
