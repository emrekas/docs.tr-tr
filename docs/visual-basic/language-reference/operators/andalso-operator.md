---
title: AndAlso İşleci (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AndAlso
- AndAlso
helpviewer_keywords:
- short-circuiting
- AndAlso operator [Visual Basic]
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], conjunction
- short-circuit evaluation
ms.assetid: bbc15191-b374-495b-9b8f-7b8c2f4388eb
ms.openlocfilehash: 1cb4d372d3ac228f29c6fa45f124796e5dfb6709
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2019
ms.locfileid: "67859894"
---
# <a name="andalso-operator-visual-basic"></a>AndAlso İşleci (Visual Basic)
Kısa devre mantıksal ve işlecini iki gerçekleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```vb
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a>Bölümler  
  
|Terim|Tanım|  
|---|---|  
|`result`|Gerekli. Tüm `Boolean` ifade. Sonuç `Boolean` karşılaştırma iki ifadenin sonucu.|  
|`expression1`|Gerekli. Tüm `Boolean` ifade.|  
|`expression2`|Gerekli. Tüm `Boolean` ifade.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir mantıksal işlemi olduğu söylenir *kısa devre* , derlenmiş kod başka bir ifadenin sonucu bağlı olarak tek bir ifade değerlendirmesi devre dışı bırakabilir. Hesaplanan ilk ifadenin sonucu işlem son sonucunu belirlerse, ikinci ifade değerlendirilemiyor gerek yoktur nihai sonucu değiştiremezsiniz. Kısa devre Atlanan ifade karmaşıksa veya yordam çağrılarını içeriyorsa performansını iyileştirebilir.  
  
 Her iki ifade sonucunu verirse `True`, `result` olduğu `True`. Aşağıdaki tabloda gösterilmiştir nasıl `result` belirlenir.  
  
|Varsa `expression1` olduğu|Ve `expression2` olduğu|Değerini `result` olduğu|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|(Değerlendirilmedi)|`False`|  
  
## <a name="data-types"></a>Veri Türleri  
 `AndAlso` İşleci yalnızca tanımlanmış [Boole veri türü](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Visual Basic, her işlenen gerektiği şekilde dönüştürür `Boolean` ifade değerlendirmeden önce. Sonucu bir sayısal tür için atarsanız, Visual Basic ondan dönüştürür `Boolean` o türe şekilde `False` olur `0` ve `True` olur `-1`.
Daha fazla bilgi için [Boole tür dönüştürmeleri](../data-types/boolean-data-type.md#type-conversions)
  
## <a name="overloading"></a>Aşırı Yükleme  
 [And işlecini](../../../visual-basic/language-reference/operators/and-operator.md) ve [IsFalse işleci](../../../visual-basic/language-reference/operators/isfalse-operator.md) olabilir *aşırı*, yani bir işlenen türü, söz konusu olduğunda bir sınıf veya yapı davranışlarını tanımlayabilirsiniz, sınıf veya yapı. Aşırı yükleme `And` ve `IsFalse` işleçleri davranışını etkileyen `AndAlso` işleci. Kodunuzu kullanıyorsa `AndAlso` bir sınıf veya aşırı yapısı `And` ve `IsFalse`, yeniden tanımlanan davranışlarını anladığınızdan emin olun. Daha fazla bilgi için [işleç yordamları](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte `AndAlso` mantıksal ve işlecini iki ifadelerini gerçekleştirmek için işleci. Sonuç bir `Boolean` tüm ifade conjoined olup olmadığını gösteren bir değer doğrudur. İlk ifade yanlışsa `False`, ikinci değerlendirilmez.  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 Yukarıdaki örnekte sonuçlarını üretir `True`, `False`, ve `False`sırasıyla. Hesaplamasında `secondCheck`, ilk zaten olduğundan ikinci ifade değerlendirilmez `False`. Ancak, ikinci ifade hesaplamasına değerlendirilir `thirdCheck`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği bir `Function` bir dizinin öğeleri arasında belirli bir değeri arar yordamı. Boş diziyse ya da dizi uzunluğu aşıldı, `While` deyimi, dizi öğesini arama değeri karşı test değil.  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Mantıksal/bit düzeyinde işleçler (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Visual Basic'de İşleç önceliği](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [İşlevselliğe Göre Listelenmiş İşleçler](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [And İşleci](../../../visual-basic/language-reference/operators/and-operator.md)
- [IsFalse İşleci](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [Visual Basic'de mantıksal ve bit düzeyinde işleçler](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
