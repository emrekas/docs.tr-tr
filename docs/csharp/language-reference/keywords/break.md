---
title: BREAK deyimi - C# başvurusu
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- break
- break_CSharpKeyword
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
ms.openlocfilehash: 15b193d9f294c01826b6b60587678ad76248e976
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422068"
---
# <a name="break-c-reference"></a>break (C# Başvurusu)

`break` Deyimi en yakın kapsayan döngüyü sonlandırır veya [geçiş](../../../csharp/language-reference/keywords/switch.md) göründüğü deyimi. Denetim, varsa, sonlandırılmış deyimi takip eden deyime geçirilir.

## <a name="example"></a>Örnek

Bu örnekte, 100'e 1 ila count için beklenen sayaç koşullu deyim içerir. Ancak, `break` deyimi sonra 4 sayıları döngüyü sonlandırır.

[!code-csharp[csrefKeywordsJump#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#1)]

## <a name="example"></a>Örnek

Bu örnekte, `break` deyimi bir iç iç içe geçmiş döngüden ve denetim için dış döngü döndürmek için kullanılır.

[!code-csharp[csrefKeywordsJump#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#7)]

## <a name="example"></a>Örnek

Bu örnek kullanımını gösterir `break` içinde bir [geçiş](../../../csharp/language-reference/keywords/switch.md) deyimi.

[!code-csharp[csrefKeywordsJump#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#2)]

Girerseniz `4`, çıktı aşağıdaki gibi olur:

```console
Enter your selection (1, 2, or 3): 4
Sorry, invalid selection.
```

## <a name="c-language-specification"></a>C# dili belirtimi

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Ayrıca bkz.

- [C# başvurusu](../../../csharp/language-reference/index.md)
- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)
- [C# Anahtar Sözcükleri](../../../csharp/language-reference/keywords/index.md)
- [switch](../../../csharp/language-reference/keywords/switch.md)
