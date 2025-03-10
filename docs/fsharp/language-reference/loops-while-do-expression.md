---
title: 'Döngüler: while...do İfadesi'
description: Bkz. while... do ifadesi, belirtilen test koşulu true olduğunda yinelemeli yürütme (döngü) gerçekleştirmek için kullanılır.
ms.date: 05/16/2016
ms.openlocfilehash: f05bdd9f8f4b9446d59f68e1231fb75e18e9b526
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630759"
---
# <a name="loops-whiledo-expression"></a>Döngüler: while...do İfadesi

`while...do` İfade, belirtilen bir test koşulu doğru olduğunda yinelemeli yürütme (döngü) gerçekleştirmek için kullanılır.

## <a name="syntax"></a>Sözdizimi

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a>Açıklamalar

*Test ifadesi* değerlendirilir; Eğer ise `true`, *gövde ifadesi* yürütülür ve test ifadesi yeniden değerlendirilir. *Body ifadesinin* türü `unit`olmalıdır. Test ifadesi ise `false`, yineleme sonlanır.

Aşağıdaki örnek, `while...do` ifadesinin kullanımını gösterir.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

Önceki kodun çıktısı, en fazla 10 olan 1 ile 20 arasında rastgele sayıların bir akışıdır.

```
13 19 8 18 16 2 10
Found a 10!
```

> [!NOTE]
> Dizi ifadelerinde ve `while...do` diğer hesaplama ifadelerinde kullanabilirsiniz, bu durumda `while...do` ifadenin özelleştirilmiş bir sürümü kullanılır. Daha fazla bilgi için bkz. [diziler](sequences.md), [zaman uyumsuz Iş akışları](asynchronous-workflows.md)ve [Hesaplama ifadeleri](computation-expressions.md).

## <a name="see-also"></a>Ayrıca bkz.

- [F# Dili Başvurusu](index.md)
- [Lerin `for...in`İfadesini](loops-for-in-expression.md)
- [Lerin `for...to`İfadesini](loops-for-to-expression.md)
