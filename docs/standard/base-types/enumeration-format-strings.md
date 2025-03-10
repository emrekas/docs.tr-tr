---
title: Numaralandırma biçimi dizeleri - .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- format specifiers, enumeration format strings
- enumeration format strings
- formatting [.NET Framework], enumeration
ms.assetid: dd1ff672-1052-42cf-8666-4924fb6cd1a1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be2e5dbe0d02bcec8974a1e52c0dce107d3bf46b
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66052847"
---
# <a name="enumeration-format-strings"></a>Numaralandırma biçimi dizeleri

Kullanabileceğiniz <xref:System.Enum.ToString%2A?displayProperty=nameWithType> sayısal, onaltılık veya dize değerini bir numaralandırma üyesine temsil eden yeni bir dize nesnesi oluşturmak için yöntemi. Bu yöntem biçimlendirme dizeleri döndürülmesini istediğiniz değeri belirtmek için numaralandırma alır.

Aşağıdaki bölümlerde, sabit listesi biçimlendirme dizeleri ve bunların dönüş değerleri listelenmektedir. Bu biçim tanımlayıcıları büyük küçük harfe duyarlı değildir.

## <a name="g-or-g"></a>G veya g

Dize değeri olarak sabit listesi girişi görüntüler, mümkünse ve aksi takdirde geçerli örneğin tamsayı değeri görüntüler. Sabit listesi ile tanımlanmışsa **bayrakları** virgüllerle ayrılmış şekilde öznitelik kümesi, geçerli her girişin değerleri birleştirilmiş birlikte bir dize. Varsa **bayrakları** özniteliği ayarlanmadı, sayısal bir giriş olarak geçersiz bir değer görüntülenir. Aşağıdaki örnekte, G biçim belirticisi gösterilmektedir.

[!code-csharp[Formatting.Enum#1](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#1)]
[!code-vb[Formatting.Enum#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#1)]

## <a name="f-or-f"></a>F veya f

Sabit listesi girişi mümkünse bir dize değeri görüntüler. Değeri, listedeki girişleri toplamı olarak tamamen görüntülenebilen varsa (bile **bayrakları** özniteliği mevcut değil), virgülle ayrılmış geçerli her girişin dize değerleri birlikte bitiştirilir. Ardından değeri tamamen göre sabit listesi girişi belirlenemiyorsa değeri tamsayı biçimlendirilir. Aşağıdaki örnek, F biçim belirticisi gösterir.

[!code-csharp[Formatting.Enum#2](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#2)]
[!code-vb[Formatting.Enum#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#2)]

## <a name="d-or-d"></a>D veya d

Sabit listesi Giriş bir tamsayı değeri mümkün olan en kısa gösteriminde olarak görüntüler. Aşağıdaki örnek, D biçim belirticisi gösterir.

[!code-csharp[Formatting.Enum#3](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#3)]
[!code-vb[Formatting.Enum#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#3)]

## <a name="x-or-x"></a>X ya da x

Sabit listesi girişi bir onaltılık değer görüntüler. Gerekirse, sonuç dizesi sabit listesi türünün her byte için iki karakter olduğundan emin olmak sayının önüne değerin temsil [sayısal tür temel](xref:System.Enum.GetUnderlyingType%2A). Aşağıdaki örnek X biçim belirticisi gösterir. Örnekte, her ikisi de temel alınan türü <xref:System.ConsoleColor> ve <xref:System.IO.FileAttributes> olduğu <xref:System.Int32>, veya 8 karakter sonuç dizesi oluşturur bir 32-bit (veya 4 baytlık) tamsayı.

[!code-csharp[Formatting.Enum#4](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#4)]      
[!code-vb[Formatting.Enum#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#4)]

## <a name="example"></a>Örnek

Aşağıdaki örnek adlı bir sabit listesi tanımlar `Colors` üç girişlerini oluşur: `Red`, `Blue`, ve `Green`.

[!code-csharp[Formatting.Enum#5](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#5)]
[!code-vb[Formatting.Enum#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#5)]

Numaralandırma tanımlandıktan sonra bir örneğini aşağıdaki şekilde bildirilebilir.

[!code-csharp[Formatting.Enum#6](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#6)]
[!code-vb[Formatting.Enum#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#6)]

`Color.ToString(System.String)` Yöntemi daha sonra geçirilen biçim belirticisi bağlı olarak farklı şekillerde numaralandırma değeri görüntülemek için kullanılabilir.

[!code-csharp[Formatting.Enum#7](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#7)]
[!code-vb[Formatting.Enum#7](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#7)]

## <a name="see-also"></a>Ayrıca bkz.

- [Biçimlendirme Türleri](formatting-types.md)
