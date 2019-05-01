---
title: Byte Veri Türü (Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: 217778a21fb9f231f448436ca5a68c42e5837566
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797013"
---
# <a name="byte-data-type-visual-basic"></a>Byte veri türü (Visual Basic)
Değeri 0 ile 255 arasında imzalanmamış 8-bit (1-bayt) tamsayıları tutar.

## <a name="remarks"></a>Açıklamalar

Kullanım `Byte` ikili veri içermesini veri türü.  
  
Varsayılan değer olan `Byte` 0'dır.

## <a name="literal-assignments"></a>Değişmez değer atamaları

Bildirmek ve başlatmak bir `Byte` değişkenini, bir ondalık sabit değeri, onaltılık bir sabit değer, sekizlik bir sabit değer atama ya da (ikili değişmez değer Visual Basic 2017'den itibaren). Tamsayı sabit değeri aralığının dışında ise bir `Byte` (diğer bir deyişle, bu ise kısa <xref:System.Byte.MinValue?displayProperty=nameWithType> veya ondan <xref:System.Byte.MaxValue?displayProperty=nameWithType>), bir derleme hatası oluşur.

Aşağıdaki örnekte, tamsayılar ondalık, onaltılık, gösterilen 201 eşit ve ikili sabit dizeler öğesinden örtük olarak dönüştürülür [tamsayı](integer-data-type.md) için `byte` değerleri.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> Önek kullanın `&h` veya `&H` önek onaltılık bir sabit belirtmek için `&b` veya `&B` ikili sabit ve öneki belirtmek için `&o` veya `&O` sekizlik bir sabit belirtmek için. Ondalık değişmez değerler, önek vardır.

Visual Basic 2017'den itibaren alt çizgi karakteri de kullanabilirsiniz `_`, okunabilirliği artırmak için bir basamak ayırıcı olarak, aşağıdaki örnekte görüldüğü gibi.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

Visual Basic 15.5 ile başlayarak, alt çizgi karakteri de kullanabilirsiniz (`_`) öneki ve onaltılık, ikili veya sekizlik basamak arasında önde gelen bir ayırıcı olarak. Örneğin:

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a>Programlama ipuçları

- **Negatif sayılar.** Çünkü `Byte` işaretsiz bir türü, negatif bir sayıyı temsil edemez. Tek işlenenli eksi işareti kullanırsanız (`-`) yazmak için değerlendirilen bir ifade işlecinin `Byte`, Visual Basic ifade dönüştürür `Short` ilk.
  
- **Biçim dönüştürme.** Visual Basic okur veya yazar dosyaları veya DLL'leri, yöntemleri ve özellikleri çağırdığında, otomatik olarak veri biçimleri arasında dönüştürme yapabilirsiniz. İkili verilerin depolanmasını `Byte` değişkenleri ve dizileri gibi bir biçim dönüştürmelerini sırasında korunur. Kullanmamalısınız bir `String` ikili veriler için değişken içerikleri biçimlerini ANSI ve Unicode arasında dönüştürme sırasında bozuk olduğundan.

- **Genişletme.** `Byte` Widens veri türü için `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, veya `Double`. Yani dönüştürebilirsiniz `Byte` karşılaşmadan bu türlerden birine bir <xref:System.OverflowException?displayProperty=nameWithType> hata.
  
- **Tür karakterleri.** `Byte` değişmez değer türü karakteri ya da tanımlayıcı türü karakteri var.

- **Çerçeve türü.** .NET Framework içinde karşılık gelen türü <xref:System.Byte?displayProperty=nameWithType> yapısı.

## <a name="example"></a>Örnek

 Aşağıdaki örnekte, `b` olduğu bir `Byte` değişkeni. Deyimlerini değişkenin aralık ve bit düzeyinde kaydırma işleçleri, uygulamayı gösterir.

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Byte?displayProperty=nameWithType>
- [Veri Türleri](../../../visual-basic/language-reference/data-types/index.md)
- [Tür Dönüştürme İşlevleri](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Dönüştürme Özeti](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Veri Türlerinin Etkili Kullanımı](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
