---
title: 'Nasıl yapılır: Onaltılık dizeler ve sayısal türler arasında dönüştürme- C# Programlama Kılavuzu'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- hexadecimal strings [C#], converting to numeric type
- conversions [C#], hexidecimal strings
- strings [C#], converting hexadecimal strings
- hexadecimal strings [C#]
ms.assetid: 7115c49f-7d1d-40c3-8bd9-aae0cc1d46b6
ms.openlocfilehash: a7109945192fe1577cd1b96c8b4d6c05270d54e8
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69588376"
---
# <a name="how-to-convert-between-hexadecimal-strings-and-numeric-types-c-programming-guide"></a>Nasıl yapılır: Onaltılık dizeler ve sayısal türler arasında dönüştürme (C# Programlama Kılavuzu)
Bu örneklerde aşağıdaki görevlerin nasıl gerçekleştirileceği gösterilmektedir:  
  
- [Dizedeki](../../language-reference/keywords/string.md)her karakterin onaltılık değerini elde edin.  
  
- Onaltılık dizedeki her değere karşılık gelen [char](../../language-reference/keywords/char.md) 'ı alın.  
  
- Onaltılı `string` bir [int](../../language-reference/builtin-types/integral-numeric-types.md)'e dönüştürün.  
  
- Bir onaltılık tabandaki `string` bir [float](../../language-reference/builtin-types/floating-point-numeric-types.md)öğesine dönüştürün.  
  
- Bir [bayt](../../language-reference/builtin-types/integral-numeric-types.md) dizisini onaltılı `string`olarak dönüştürür.  
  
## <a name="example"></a>Örnek  
 Bu örnek, içindeki her bir `string`karakterin onaltılık değerini verir. İlk olarak, `string` bir karakter dizisi olarak ayrıştırır. Ardından, sayısal <xref:System.Convert.ToInt32%28System.Char%29> değerini elde etmek için her bir karakter üzerinde çağırır. Son olarak, sayıyı içinde `string`onaltılık gösterimi olarak biçimlendirir.  
  
 [!code-csharp[csProgGuideTypes#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#30)]  
  
## <a name="example"></a>Örnek  
 Bu örnek, onaltılı `string` değerleri ayrıştırır ve her onaltılık değere karşılık gelen karakteri verir. İlk olarak, her onaltılı değeri bir dizide bir kişi `string` olarak almak için [Split (Char\[\])](xref:System.String.Split(System.Char[])) yöntemini çağırır. Ardından, onaltılı <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> değeri [tamsayı](../../language-reference/builtin-types/integral-numeric-types.md)olarak temsil edilen bir ondalık değere dönüştürmek için çağırır. Bu karakter koduna karşılık gelen karakteri almanın iki farklı yolunu gösterir. İlk tekniği kullanır <xref:System.Char.ConvertFromUtf32%28System.Int32%29>ve tamsayı bağımsız değişkenine karşılık gelen karakteri bir `string`olarak döndürür. İkinci teknik, `int` öğesini açıkça bir [char](../../language-reference/keywords/char.md)öğesine yayınlar.  
  
 [!code-csharp[csProgGuideTypes#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#31)]  
  
## <a name="example"></a>Örnek  
 Bu örnek, `string` <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29> yöntemini çağırarak, onaltılı bir tamsayıyı bir tamsayıya dönüştürmenin başka bir yolunu gösterir.  
  
 [!code-csharp[csProgGuideTypes#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#32)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, `string` <xref:System.BitConverter?displayProperty=nameWithType> sınıfı ve <xref:System.UInt32.Parse%2A?displayProperty=nameWithType> yöntemi kullanılarak bir onaltılık tabandaki bir [float](../../language-reference/builtin-types/floating-point-numeric-types.md) öğesine nasıl dönüştürüleceğini gösterir.  
  
 [!code-csharp[csProgGuideTypes#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#39)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, <xref:System.BitConverter?displayProperty=nameWithType> sınıfını kullanarak bir [bayt](../../language-reference/builtin-types/integral-numeric-types.md) dizisinin onaltılık dizeye nasıl dönüştürüleceğini gösterir.  
  
 [!code-csharp[csProgGuideTypes#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#38)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Standart Sayısal Biçim Dizeleri](../../../standard/base-types/standard-numeric-format-strings.md)
- [Türler](./index.md)
- [Nasıl yapılır: Bir dizenin sayısal bir değeri temsil edip etmediğini belirleme](../strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)
