---
title: -netcf
ms.date: 03/13/2018
f1_keywords:
- /netcf
- -netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
ms.openlocfilehash: 028fa148d0e5622648a5fdfff1789c3d0bfde057
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/20/2019
ms.locfileid: "67268286"
---
# <a name="-netcf"></a>-netcf

.NET Compact Framework'ü hedefleyen derleyicinin ayarlar.

## <a name="syntax"></a>Sözdizimi

```
-netcf
```

## <a name="remarks"></a>Açıklamalar

`-netcf` Seçeneği tam .NET Framework yerine .NET Compact Framework'ü hedeflemek Visual Basic Derleyicisi neden olur. Yalnızca tam .NET Framework içinde mevcut olan dil işlevselliği devre dışı bırakıldı.

`-netcf` Seçeneği ile kullanılmak üzere tasarlanmıştır [- sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md). Devre dışı dil özellikleri `-netcf` aynı dil özellikleri ile hedeflenen dosyalarda mevcut olan `-sdkpath`.

> [!NOTE]
> `-netcf` Seçeneği, Visual Studio geliştirme ortamında kullanılabilir değil; yalnızca komut satırından derleme yapılırken kullanılabilir. `-netcf` Seçeneği, Visual Basic cihaz projesi yüklendiğinde ayarlanır.

`-netcf` Seçeneği aşağıdaki dil özellikleri değiştirir:

- [Son \<anahtar sözcüğü > deyimi](../../../visual-basic/language-reference/statements/end-keyword-statement.md) anahtar sözcüğü bir programın yürütülmesini sonlandıran, devre dışı bırakıldı. Aşağıdaki programın olmadan çalışır ve `-netcf` ile derleme zamanında başarısız olduğunda `-netcf`.

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- Geç bağlama, tüm formları içinde devre dışı bırakıldı. Tanınan geç bağlama senaryoları karşılaştı, derleme zamanı hatalarına üretilir. Aşağıdaki programın olmadan çalışır ve `-netcf` ile derleme zamanında başarısız olduğunda `-netcf`.

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- [Otomatik](../../../visual-basic/language-reference/modifiers/auto.md), [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md), ve [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) değiştiriciler devre dışı bırakıldı. Söz dizimi [Declare Deyimi'nin](../../../visual-basic/language-reference/statements/declare-statement.md) deyimi için değişiklik de `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`. Aşağıdaki kod etkisini gösterir `-netcf` bir derleme üzerinde.

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- Visual Basic kaldırılan Visual Basic 6.0 anahtar sözcüklerini kullanarak, farklı bir hata oluşturur, `-netcf` kullanılır. Bu, aşağıdaki anahtar sözcükler için hata iletileri etkiler:

  - `Open`

  - `Close`

  - `Put`

  - `Print`

  - `Write`

  - `Input`

  - `Lock`

  - `Unlock`

  - `Seek`

  - `Width`

  - `Name`

  - `FreeFile`

  - `EOF`

  - `Loc`

  - `LOF`

  - `Line`

## <a name="example"></a>Örnek

Aşağıdaki kod derlenir `Myfile.vb` .NET Compact Framework ile mscorlib.dll'nin ve Microsoft.VisualBasic.dll'nin sürümlerini kullanan C sürücüsünde .NET Compact Framework'ün varsayılan yükleme dizini bulunamadı. Genellikle, .NET Compact Framework en son sürümünü kullanmanız gerekir.

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Basic komut satırı derleyicisi](../../../visual-basic/reference/command-line-compiler/index.md)
- [Örnek Derleme Komut Satırları](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
