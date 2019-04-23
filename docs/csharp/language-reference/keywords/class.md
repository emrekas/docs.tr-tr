---
title: class anahtar sözcüğü - C# başvurusu
ms.custom: seodec18
ms.date: 07/18/2017
f1_keywords:
- class_CSharpKeyword
- class
helpviewer_keywords:
- class keyword [C#]
ms.assetid: b95d8815-de18-4c3f-a8cc-a0a53bdf8690
ms.openlocfilehash: fbb685abcc5c2e79a64501385edf8f6c2041861d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59974902"
---
# <a name="class-c-reference"></a>class (C# Başvurusu)

Sınıflar, anahtar sözcüğü kullanılarak bildirilir `class`, aşağıdaki örnekte gösterildiği gibi:

```csharp
class TestClass
{
    // Methods, properties, fields, events, delegates
    // and nested classes go here.
}
```

## <a name="remarks"></a>Açıklamalar

C# ' de yalnızca tek devralma izin verilir. Diğer bir deyişle, bir sınıf bir taban sınıftan yalnızca uygulama devralabilir. Ancak, bir sınıf birden fazla arabirim uygulayabilir. Aşağıdaki tablo, sınıf devralma ve arabirim uygulaması örneklerini gösterir:

|Devralma|Örnek|
|-----------------|-------------|
|Yok.|`class ClassA { }`|
|Tek|`class DerivedClass: BaseClass { }`|
|None, iki arabirim uygular|`class ImplClass: IFace1, IFace2 { }`|
|Tek bir arabirim uygular|`class ImplDerivedClass: BaseClass, IFace1 { }`|

Diğer sınıflar içinde iç içe değil doğrudan bir ad alanındaki bildirdiğiniz sınıf ya da olabilir [genel](../../../csharp/language-reference/keywords/public.md) veya [iç](../../../csharp/language-reference/keywords/internal.md). Sınıflar `internal` varsayılan olarak.

İç içe geçmiş sınıflar, sınıf üyelerini olabilir [genel](public.md), [iç korumalı](protected-internal.md), [korumalı](protected.md), [iç](internal.md), [ özel](private.md), veya [korunan özel](private-protected.md). Üyeleri `private` varsayılan olarak.

Daha fazla bilgi için [erişim değiştiricileri](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).

Tür parametrelerine sahip Genel sınıflar bildirebilirsiniz. Daha fazla bilgi için [Genel sınıflar](../../../csharp/programming-guide/generics/generic-classes.md).

Bir sınıf bildirimleri aşağıdaki üyeleri içerir:

- [Oluşturucular](../../../csharp/programming-guide/classes-and-structs/constructors.md)

- [Sabitler](../../../csharp/programming-guide/classes-and-structs/constants.md)

- [Alanlar](../../../csharp/programming-guide/classes-and-structs/fields.md)

- [Sonlandırıcılar](../../../csharp/programming-guide/classes-and-structs/destructors.md)

- [Yöntemler](../../../csharp/programming-guide/classes-and-structs/methods.md)

- [Özellikler](../../../csharp/programming-guide/classes-and-structs/properties.md)

- [Dizin Oluşturucular](../../../csharp/programming-guide/indexers/index.md)

- [İşleçler](../../../csharp/programming-guide/statements-expressions-operators/operators.md)

- [Olaylar](../../../csharp/programming-guide/events/index.md)

- [Temsilciler](../../../csharp/programming-guide/delegates/index.md)

- [Sınıflar](../../../csharp/programming-guide/classes-and-structs/classes.md)

- [Arabirimler](../../../csharp/programming-guide/interfaces/index.md)

- [Yapılar](../../../csharp/programming-guide/classes-and-structs/structs.md)

- [Sabit Listeleri](../../../csharp/programming-guide/enumeration-types.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek, bildirim sınıfı alanlar, Oluşturucular ve yöntemler gösterilmektedir. Ayrıca, nesne örneklemesini ve yazdırma örneği verileri gösterir. Bu örnekte, iki sınıf olarak bildirilir. İlk sınıf `Child`, iki özel alan içeriyor (`name` ve `age`), iki genel oluşturucular ve bir genel yöntem. İkinci sınıfı `StringTest`, kapsamak için kullanılmış `Main`.

[!code-csharp[csrefKeywordsTypes#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#5)]

## <a name="comments"></a>Açıklamalar

Önceki örnekte dikkat özel alanlar (`name` ve `age`) yalnızca genel yöntemi aracılığıyla erişilebilir `Child` sınıfı. Gelen çocuğunuzun adı, örneğin, yazdıramıyorum `Main` yöntemi, şunun gibi bir deyim kullanarak:

```csharp
Console.Write(child1.name);   // Error
```

Özel üyelerine erişme `Child` gelen `Main` yalnızca sağlayabileceğinizden varsa `Main` sınıfının üyesi olan.

Türleri bildirilen bir erişim değiştiricisi varsayılan olmayan bir sınıf içinde `private`, bu örnekte veri üyeleri olmaya `private` anahtar sözcüğü kaldırdıysanız.

Son olarak, parametresiz bir oluşturucu kullanılarak oluşturulan nesne için dikkat edin (`child3`), `age` alan sıfır olarak başlatılmış varsayılan olarak.

## <a name="c-language-specification"></a>C# dili belirtimi

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Ayrıca bkz.

- [C# başvurusu](../../../csharp/language-reference/index.md)
- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)
- [C# Anahtar Sözcükleri](../../../csharp/language-reference/keywords/index.md)
- [Başvuru Türleri](../../../csharp/language-reference/keywords/reference-types.md)
