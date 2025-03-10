---
title: WHERE yan tümcesi C# -başvuru
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- whereclause_CSharpKeyword
helpviewer_keywords:
- where keyword [C#]
- where clause [C#]
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
ms.openlocfilehash: aceda6cfd33a53388a5afb046359c4dcfddfd1f8
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602026"
---
# <a name="where-clause-c-reference"></a>where tümcesi (C# Başvurusu)

`where` Yan tümcesi, sorgu ifadesinde veri kaynağından hangi öğelerin döndürüleceğini belirtmek için bir sorgu ifadesinde kullanılır. Her kaynak öğesine (Aralık değişkeni tarafından başvurulan) bir Boolean koşulu (*koşul*) uygular ve belirtilen koşulun doğru olduğu öğeleri döndürür. Tek bir sorgu ifadesinde birden çok `where` yan tümce bulunabilir ve tek bir yan tümce birden çok koşul alt ifadesi içerebilir.

## <a name="example"></a>Örnek

Aşağıdaki örnekte `where` yan tümce, beş ' dan az olanlar hariç tüm sayıları filtreler. `where` Yan tümcesini kaldırırsanız, veri kaynağındaki tüm sayılar döndürülür. İfade `num < 5` , her bir öğeye uygulanan belirtedir.

[!code-csharp[cscsrefQueryKeywords#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#5)]

## <a name="example"></a>Örnek

Tek `where` bir yan tümce içinde, [&&](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) ve [ &#124; ](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) işleçlerini kullanarak gereken sayıda koşulu belirtebilirsiniz. Aşağıdaki örnekte sorgu, yalnızca beş ' dan küçük olan sayıları seçmek için iki koşul belirtir.

[!code-csharp[cscsrefQueryKeywords#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#6)]  

## <a name="example"></a>Örnek

Bir `where` yan tümce, Boolean değer döndüren bir veya daha fazla yöntem içerebilir. Aşağıdaki örnekte `where` yan tümce, Aralık değişkeninin geçerli değerinin çift mi yoksa tek mi olduğunu anlamak için bir yöntem kullanır.

[!code-csharp[cscsrefQueryKeywords#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#7)]

## <a name="remarks"></a>Açıklamalar

`where` Yan tümce bir filtreleme mekanizmasıdır. Bir sorgu ifadesinde neredeyse her yerde konumlandırılmış olabilir, ancak ilk veya son yan tümce olamaz. Bir `where` yan tümce, kaynak öğeleri gruplandırılmadan önce veya sonra filtrelemeniz gerekip gerekmediğini bağlı olarak, bir [Grup](group-clause.md) yan tümcesinden önce veya sonra görünebilir.

Belirtilen koşul veri kaynağındaki öğeler için geçerli değilse, bir derleme zamanı hatası ortaya kalır. Bu, tarafından [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]sunulan güçlü tür denetiminin bir avantajıdır.

Derleme zamanında `where` anahtar sözcüğü <xref:System.Linq.Enumerable.Where%2A> standart sorgu işleci yöntemine yapılan bir çağrıya dönüştürülür.

## <a name="see-also"></a>Ayrıca bkz.

- [Sorgu anahtar sözcükleri (LINQ)](query-keywords.md)
- [from yan tümcesi](from-clause.md)
- [select yan tümcesi](select-clause.md)
- [Verileri Filtreleme](../../programming-guide/concepts/linq/filtering-data.md)
- [LINQ sorgu Ifadeleri](../../programming-guide/linq-query-expressions/index.md)
- [C#'de LINQ Kullanmaya Başlama](../../programming-guide/concepts/linq/getting-started-with-linq.md)
