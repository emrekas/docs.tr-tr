---
title: -refonly (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: 047b8b148e616c8ad94f55844f8bc4063a9e5cd1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528933"
---
# <a name="-refonly-visual-basic"></a>-refonly (Visual Basic)

**- Refonly** seçeneği gösteren derlemenin birincil çıkışının yerine bir uygulama derlemeye bir başvuru bütünleştirilmiş kodu olmalıdır. `-refonly` Parametre sessiz bir şekilde devre dışı bırakır pdb, çıktısı olarak başvuru bütünleştirilmiş kodları yürütülemez.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Sözdizimi

```console
-refonly
```

## <a name="remarks"></a>Açıklamalar

Visual Basic destekler `-refout` 15.3 sürümünden başlayarak geçin.

Başvuru bütünleştirilmiş kodları meta verileri ancak hiçbir uygulama kodu içeren yalnızca meta veri derlemelerdir. Bunlar, anonim türler dışında her şeyi için tür ve üye bilgilerini içerir. Kullanılmasının nedeni `throw null` gövdeleri (aksine, gövde yok) olan PEVerify çalışmasını ve (Bu nedenle meta veri bütünlüğünü doğrulama) geçirin.

Başvuru derlemelerini içeren bir derleme düzeyi [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) özniteliği. Bu özniteliği, kaynakta belirtilebilir (sonra derleyici bu sentezlemek gerekmez). Bu öznitelik nedeniyle yürütme için başvuru derlemeleri yüklemeye çalışma zamanları reddeder (ancak bunlar yine de salt yansıma bir bağlamda yüklenmiş olabilir). Bunlar salt yansıma olarak başvuru derlemelerini yüklemek emin olmak derlemelerini yansıtan araçları gerekir; Aksi takdirde, çalışma zamanı oluşturur bir <xref:System.BadImageFormatException>.

`-refonly` Ve [ `-refout` ](refout-compiler-option.md) seçenekleri karşılıklı olarak birbirini dışlar.

## <a name="see-also"></a>Ayrıca bkz.
- [-refout](refout-compiler-option.md)
- [Visual Basic komut satırı derleyicisi](index.md)
- [Örnek Derleme Komut Satırları](sample-compilation-command-lines.md)
