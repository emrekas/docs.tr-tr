---
title: Kısmi türü - C# başvurusu
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
ms.openlocfilehash: 5dba3759d8d0046f2a491e1d3408acb54bd0343d
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633367"
---
# <a name="partial-type-c-reference"></a>Kısmi türü (C# Başvurusu)

Kısmi tür tanımlarını bir sınıf, yapı veya arabirim tanımı için birden fazla dosyaya bölünmesine izin verir.

İçinde *File1.cs*:

[!code-csharp[csrefKeywordsContextual#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#3)]  

İçinde *File2.cs* bildirimi:

[!code-csharp[csrefKeywordsContextual#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#4)]  

## <a name="remarks"></a>Açıklamalar

Büyük projeler veya sağladığı gibi otomatik olarak oluşturulan kod ile çalışırken, bir sınıf bölme, yapı veya arabirim türü çeşitli dosyalar üzerinde yararlı olabilir [Windows Form Tasarımcısı](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md). Kısmi bir tür içerebilir bir [kısmi yöntem](partial-method.md). Daha fazla bilgi için [kısmi sınıflar ve yöntemler](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).

## <a name="c-language-specification"></a>C# dili belirtimi

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Ayrıca bkz.

- [C# başvurusu](../index.md)
- [C# Programlama Kılavuzu](../../programming-guide/index.md)
- [Değiştiriciler](modifiers.md)
- [Genel Türlere Giriş](../../programming-guide/generics/introduction-to-generics.md)
