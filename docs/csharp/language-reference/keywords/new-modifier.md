---
title: New değiştiricisi - C# başvurusu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- new modifier keyword [C#]
ms.assetid: a2e20856-33b9-4620-b535-a60dbce8349b
ms.openlocfilehash: 3a642996da8f0126e59e21d3553a7d8ba73dab23
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422684"
---
# <a name="new-modifier-c-reference"></a>New değiştiricisi (C# Başvurusu)

Bir bildirim değiştirici olarak kullanıldığında `new` anahtar sözcüğü açıkça bir temel sınıftan devralınan üyeyi gizler. Devralınmış bir üyeyi gizlediğinizde, üyenin sürümü temel sınıftaki sürümün yerine geçer. Üyeleri kullanmadan gizleyebilmenize rağmen `new` değiştiricisi, bir derleyici uyarısı alırsınız. Kullanırsanız `new` bir üyeyi açıkça gizlemek için bu uyarı bastırılır.

Devralınan bir üyeyi gizlemek için türetilen sınıfta aynı üye adını kullanarak bildirin ve değiştirin `new` anahtar sözcüğü. Örneğin:

[!code-csharp[csrefKeywordsOperator#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#8)]

Bu örnekte, `BaseC.Invoke` tarafından gizleniyor `DerivedC.Invoke`. Alan `x` çünkü benzer bir adla gizlenmediğinden etkilenmez.

Devralma üzerinden ad gizleme aşağıdaki biçimlerden birini alır:

- Genellikle, bir sabit, alan, özelliği veya bir sınıf veya yapı içinde tanıtılan türü kendi adını paylaşan tüm taban sınıfı üyelerini gizler.  Özel durumlar vardır.  Örneğin, adı ile yeni bir alan bildirmek `N` çağrılmayan bir tür ve temel tür olduğunu `N` bir yöntemi olması için yeni alan taban bildirimini çağırma sözdiziminde gizlemez.  Bkz: [5.0 C# dil belirtimi](https://www.microsoft.com/download/details.aspx?id=7029) için ayrıntıları ("Expressions" bölümünde "Üye arama" bölümüne bakın).

- Bir sınıf ya da struct'a dahil edilen bir yöntem özellikleri, alanları ve temel sınıfta bu adı paylaşan türleri gizler. Ayrıca, aynı imzaya sahip tüm taban sınıfı yöntemlerini gizler.

- Bir sınıf veya yapı içinde tanıtılan bir dizin oluşturucu, aynı imzaya sahip tüm taban sınıfı dizin oluşturucularını gizler.

Her ikisi de kullanmak için bir hata olduğunu `new` ve [geçersiz kılma](override.md) aynı üyede, çünkü iki değiştirici karşılıklı özel anlamlara sahiptir. `new` Değiştiricisi, aynı ada sahip yeni bir üye oluşturur ve ilk üyenin gizli hale gelmesine neden olur. `override` Değiştiricisi devralınan bir üyenin uygulanmasını genişletir.

Kullanarak `new` değiştiricisi devralınan bir üyeyi gizlemek olmayan bir bildirimde kullanmak bir uyarı oluşturur.

## <a name="example"></a>Örnek

Bu örnekte, bir temel sınıf `BaseC`ve bir türetilen sınıf `DerivedC`, aynı alan adını kullanan `x`, devralınan alandaki değeri gizleyen. Bu örnek kullanımını gösterir `new` değiştiricisi. Ayrıca bunların tam nitelikli adlarını kullanarak taban sınıfının gizlenmiş üyelerine nasıl erişileceğini gösteren.

[!code-csharp[csrefKeywordsOperator#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#9)]

## <a name="example"></a>Örnek

Bu örnekte, iç içe geçmiş bir sınıf taban sınıfında aynı ada sahip bir sınıfı gizler. Bu örnek nasıl kullanılacağını gösterir `new` değiştiricisi uyarı iletisini ve gizli sınıf üyelerine bunların tam nitelikli adlarını kullanarak erişmek nasıl ortadan kaldırmak için.

[!code-csharp[csrefKeywordsOperator#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#10)]

Kaldırırsanız `new` değiştiricisi, program hala derler ve çalışır, ancak aşağıdaki uyarıyı alırsınız:

```
The keyword new is required on 'MyDerivedC.x' because it hides inherited member 'MyBaseC.x'.
```

## <a name="c-language-specification"></a>C# dili belirtimi

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Ayrıca bkz.

- [C# başvurusu](../../language-reference/index.md)
- [C# Programlama Kılavuzu](../../programming-guide/index.md)
- [C# Anahtar Sözcükleri](index.md)
- [Değiştiriciler](modifiers.md)
- [Geçersiz Kılma ve Yeni Anahtar Sözcüklerle Sürüm Oluşturma](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)
- [Geçersiz Kılmanın ve Yeni Anahtar Sözcüklerin Ne Zaman Kullanılacağını Bilme](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)
