---
title: << işleci - C# başvurusu
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<_CSharpKeyword
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
ms.openlocfilehash: 0271c97bc624a8946b90508e9ce39d217a128c05
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261756"
---
# <a name="-operator-c-reference"></a>\<\< İşleci (C# Başvurusu)

Sola kaydırma işleci (`<<`) ilk işlenenin sol tarafından ikinci işlenen tarafından belirtilen bit sayısı kadar kaydırır. İkinci işlenenin türünde olmalıdır bir [int](../keywords/int.md) veya önceden tanımlanmış bir örtük sayısal dönüştürme için olan bir türü `int`.

## <a name="remarks"></a>Açıklamalar

Birinci işlenenin ise bir [int](../keywords/int.md) veya [uint](../keywords/uint.md) (32-bit miktarı), kaydırma sayısı tarafından düşük sıra beş bitleri ikinci işlenenin verilir. Diğer bir deyişle, gerçek kaydırma sayısı 0-31 bittir.

Birinci işlenenin ise bir [uzun](../keywords/long.md) veya [ulong](../keywords/ulong.md) (64-bit miktarı), kaydırma sayısı tarafından düşük sıra altı bitleri ikinci işlenenin verilir. Diğer bir deyişle, gerçek kaydırma sayısı 0 ila 63 bittir.

Shift sonra birinci işlenenin türü aralık içinde değil olan herhangi bir yüksek sıra bitleri atılır ve düşük düzey boş bitler sıfır dolguludur. Kaydırma işleçlerini, hiçbir zaman taşıyor neden.

Kullanıcı tanımlı türler aşırı yükleme `<<` işleci (bkz [işleci](../keywords/operator.md)); birinci işlenenin türü kullanıcı tanımlı bir tür olmalı ve ikinci işlenenin türünde olmalıdır `int`. İkili İşleç aşırı karşılık gelen atama işleci, varsa, aynı zamanda örtük olarak aşırı yüklenmiş olur.

## <a name="example"></a>Örnek

[!code-csharp[csRefOperators#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#14)]

## <a name="comments"></a>Açıklamalar

Unutmayın `i<<1` ve `i<<33` aynı düşük sıra beş bitleri 1 ve 33 olduğundan aynı sonucu verir.

## <a name="see-also"></a>Ayrıca bkz.

- [C# başvurusu](../index.md)
- [C# Programlama Kılavuzu](../../programming-guide/index.md)
- [C# İşleçleri](index.md)
