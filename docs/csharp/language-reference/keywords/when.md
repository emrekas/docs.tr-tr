---
title: zaman bağlamsal anahtar sözcük - C# başvurusu
ms.custom: seodec18
ms.date: 03/07/2017
f1_keywords:
- when_CSharpKeyword
- when
helpviewer_keywords:
- when keyword [C#]
ms.assetid: dd543335-ae37-48ac-9560-bd5f047b9aea
ms.openlocfilehash: f0dbfb611ab563c16c97b1f6313134df38a174df
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633110"
---
# <a name="when-c-reference"></a>zaman (C# Başvurusu)

Kullanabileceğiniz `when` iki bağlamlarda bir filtre koşulu belirtmek için bağlamsal anahtar sözcük:

- İçinde `catch` deyiminin bir [try/catch](try-catch.md) veya [try/catch/finally](try-catch-finally.md) blok.
- İçinde `case` etiketi bir [geçiş](switch.md) deyimi.

## <a name="when-in-a-catch-statement"></a>`when` içinde bir `catch` deyimi

C# 6 ile başlayarak `when` kullanılabilir bir `catch` deyimini yürütmek belirli bir özel durum işleyicisi için doğru bir koşulu belirtin. Kendi sözdizimi aşağıdaki gibidir:

```csharp
catch (ExceptionType [e]) when (expr)
```

Burada *expr* bir Boole değerini döndüren bir ifadedir. Döndürürse `true`, özel durum işleyicisi; ise yürütülür `false`, yok.

Aşağıdaki örnekte `when` işleyicileri için koşullu olarak yürütülecek anahtar sözcüğü bir <xref:System.Net.Http.HttpRequestException> bağlı özel durum iletisi metni görüntülenir.

[!code-csharp[when-with-catch](~/samples/snippets/csharp/language-reference/keywords/when/catch.cs)]

## <a name="when-in-a-switch-statement"></a>`when` içinde bir `switch` deyimi

C# 7.0 ile başlayan `case` etiketleri artık olması birbirini özel ve sırayı `case` etiketler görünür bir `switch` deyimi, hangi anahtar bloğu belirleyebilir yürütür. `when` Anahtar sözcüğü, yalnızca filtre koşulu da true ise true olması, ilişkili case etiketi neden olan bir filtre koşulu belirtmek için kullanılabilir. Kendi sözdizimi aşağıdaki gibidir:

```csharp
case (expr) when (when-condition):
```

Burada *expr* bir sabit desen veya eşleşme ifadesi için karşılaştırma türü desendir ve *olduğunda koşul* herhangi bir Boolean ifadesi.

Aşağıdaki örnekte `when` sınamak için anahtar sözcüğü `Shape` çeşitli için test etmek için sıfır de bir alan olan nesneleri `Shape` sıfırdan büyük bir alan olan nesne.

[!code-csharp[when-with-case#1](~/samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]

## <a name="see-also"></a>Ayrıca bkz.

- [switch deyimi](switch.md)
- [try/catch deyimi](try-catch.md)
- [try/catch/finally deyimi](try-catch-finally.md)
