---
title: '|| Operator - C# başvurusu'
ms.custom: seodec18
ms.date: 11/06/2018
f1_keywords:
- '||_CSharpKeyword'
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
ms.openlocfilehash: 079c021eb68ece097c7f644416f1e9469a82dcea
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415435"
---
# <a name="-operator-c-reference"></a>|| İşleci (C# Başvurusu)

Koşullu mantıksal OR işlecinin `||`, "kısa devre" mantıksal OR işleci, hesaplar, mantıksal OR olarak da bilinir, [bool](../keywords/bool.md) işlenen. Sonucu `x || y` olduğu `true` ya da `x` veya `y` değerlendiren `true`. Aksi halde sonuç, `false`. Birinci işlenenin değerlendirilirse `true`, ikinci işlenenin değerlendirilmez ve işlemin sonucu olan `true`. Aşağıdaki örnek, bu davranış gösterir:

[!code-csharp-interactive[conditional logical OR](~/samples/snippets/csharp/language-reference/operators/ConditionalLogicalOperatorsExamples.cs#Or)]

[Mantıksal OR işlecinin](or-operator.md) `|` Ayrıca, mantıksal OR hesaplar, `bool` işlenenler, ancak her iki işlenen de her zaman değerlendirilir.

## <a name="operator-overloadability"></a>İşleç overloadability

Kullanıcı tanımlı bir tür koşullu mantıksal OR işlecinin aşırı yüklenemez. Ancak, kullanıcı tanımlı bir tür aşırı [mantıksal OR](or-operator.md) ve [true ve false işleçleri](../keywords/true-false-operators.md) belirli bir şekilde `||` işlemi, bu türündeki işlenenler için değerlendirmesi yapılamıyor. Daha fazla bilgi için [kullanıcı tanımlı koşullu mantıksal işleçler](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) bölümünü [ C# dil belirtimi](../language-specification/index.md).

## <a name="c-language-specification"></a>C# dili belirtimi

Daha fazla bilgi için [koşullu mantıksal işleçler](~/_csharplang/spec/expressions.md#conditional-logical-operators) bölümünü [ C# dil belirtimi](../language-specification/index.md).

## <a name="see-also"></a>Ayrıca bkz.

- [C# başvurusu](../index.md)
- [C# Programlama Kılavuzu](../../programming-guide/index.md)
- [C# İşleçleri](index.md)
- [& & işleci](conditional-and-operator.md)
- [\! İşleci](logical-negation-operator.md)
- [| işleci](or-operator.md)
