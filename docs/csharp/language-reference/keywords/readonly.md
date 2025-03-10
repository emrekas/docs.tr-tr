---
title: ReadOnly anahtar sözcüğü - C# başvurusu
ms.custom: seodec18
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 4a51bb0e854de127c632c28f613a7602bf09f432
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2019
ms.locfileid: "67348019"
---
# <a name="readonly-c-reference"></a>readonly (C# Başvurusu)

`readonly` Anahtar sözcüğü, üç bağlamlarda kullanılan bir değiştirici:

- İçinde bir [alan bildirimi](#readonly-field-example), `readonly` alana atama bildirimin veya aynı sınıftaki bir oluşturucunun parçası olarak yalnızca oluşabilir gösterir. Salt okunur bir alan atanabilir ve alan bildirimi ve oluşturucu içinde birden çok kez yeniden atandı. 
  
  A `readonly` alan oluşturucu çıktıktan sonra atanamaz. Değer türleri ve başvuru türleri için farklı biçimlerde olan:
  
  - Değer türleri verilerini doğrudan içerdiği için olan bir alan bir `readonly` değişmez değer türü. 
  - Başvuru türleri verilerine bir başvuru içerdiğinden olan bir alan bir `readonly` başvuru türü her zaman aynı nesneye başvurmalıdır. Bu nesne sabit değil. `readonly` Değiştiricisi başvuru türü farklı bir örneğine yerini alan engeller. Ancak değiştiricisi, örnek veri alanının salt okunur alanı değiştirilmiş engellemez.

  > [!WARNING]
  > Dışarıdan görünen tür, kesilebilir başvuru türü olan bir dışarıdan görünen salt okunur alan içeren bir güvenlik açığı olabilir ve uyarı tetikleyebilir [CA2104](/visualstudio/code-quality/ca2104-do-not-declare-read-only-mutable-reference-types) : "Salt okunur kesilebilir başvuru türleri bildirmeyin."

- İçinde bir [ `readonly struct` tanımı](#readonly-struct-example), `readonly` belirten `struct` sabittir.
- İçinde bir [ `ref readonly` yöntemi dönüş](#ref-readonly-return-example), `readonly` değiştiricisi gösteren bir başvuru ve yazma işlemleri bu başvurusuna izin verilmez yöntemi döndürür.

Son iki bağlamdan, C# 7.2 eklendi.

## <a name="readonly-field-example"></a>Salt okunur alanı örneği

Bu örnekte, alanın değerini `year` yöntemi değiştirilemez `ChangeYear`rağmen sınıf oluşturucusu bir değer atanır:

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

Bir değer atamak için bir `readonly` yalnızca şu bağlamlarda alan:

- Ne zaman Değişken bildiriminde örneğin başlatılır:

  ```csharp
  public readonly int y = 5;
  ```

- Bir sınıfın örnek oluşturucusunda örnek alan bildirimi içerir.
- Statik Oluşturucu sınıfın statik alan bildirimi içerir.

Bu oluşturucu bağlamları de yalnızca bağlamları olduğu geçirmek için geçerli olan bir `readonly` olarak alan bir [kullanıma](out-parameter-modifier.md) veya [ref](ref.md) parametresi.

> [!NOTE]
> `readonly` Anahtar sözcüğü, farklı [const](const.md) anahtar sözcüğü. A `const` alanı alanın bildiriminde yalnızca başlatılabilir. A `readonly` alan alan bildirimi ve herhangi bir oluşturucu birden çok kez atanabilir. Bu nedenle, `readonly` alanları kullanılan oluşturucuya bağlı olarak farklı değerlere sahip olabilir. Ayrıca, while bir `const` alandır bir derleme zamanı sabiti `readonly` alan, aşağıdaki örnekte olduğu gibi çalışma zamanı sabitleri için kullanılabilir:
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

Önceki örnekte, aşağıdaki örnekte olduğu gibi bir deyim kullanıyorsanız:

```csharp
p2.y = 66;        // Error
```

Derleyici hata iletisini alırsınız:

`A readonly field cannot be assigned to (except in a constructor or a variable initializer)`

## <a name="readonly-struct-example"></a>Salt okunur yapı örneği

`readonly` Değiştiricisi bir `struct` tanımı, yapı olduğunu bildirir **değişmez**. Her örnek alan `struct` işaretlenmelidir `readonly`, aşağıdaki örnekte gösterildiği gibi:

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyStruct)]

Önceki örnekte [salt okunur otomatik özellikleri](../../properties.md#read-only) depolamasını bildirmek için. Derleyicinin oluşturmasını söyler `readonly` destek alanları için bu özellikleri. Ayrıca bildirip `readonly` doğrudan alanlar:

```csharp
public readonly struct Point
{
    public readonly double X;
    public readonly double Y;

    public Point(double x, double y) => (X, Y) = (x, y);

    public override string ToString() => $"({X}, {Y})";
}
```

İşaretlenmemiş bir alan ekleme `readonly` derleyici hatası oluşturur `CS8340`: "Salt okunur yapı birimlerinin örnek alanları salt okunur olmalıdır."

## <a name="ref-readonly-return-example"></a>Ref salt okunur dönüş örneği

`readonly` Değiştiricisi bir `ref return` döndürülen başvuru değiştirilemeyeceğini belirtir. Aşağıdaki örnek, kaynağı bir başvuru döndürür. Kullandığı `readonly` değiştiricisi arayanları kaynağı değiştirilemiyor belirtmek için:

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]
Döndürülen tür olması gerekmez bir `readonly struct`. Tarafından döndürülen herhangi bir türü `ref` tarafından döndürülen `ref readonly`.

## <a name="c-language-specification"></a>C# dili belirtimi

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Ayrıca bkz.

- [C# başvurusu](../index.md)
- [C# Programlama Kılavuzu](../../programming-guide/index.md)
- [C# Anahtar Sözcükleri](index.md)
- [Değiştiriciler](modifiers.md)
- [const](const.md)
- [Alanlar](../../programming-guide/classes-and-structs/fields.md)
