---
title: Nesne Değişkeni Değerleri (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], values
- values [Visual Basic], of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
ms.openlocfilehash: c17c5f85952596f0a080ca473e8f792740e66b8f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840399"
---
# <a name="object-variable-values-visual-basic"></a>Nesne Değişkeni Değerleri (Visual Basic)
Bir değişken [nesne veri türü](../../../../visual-basic/language-reference/data-types/object-data-type.md) herhangi bir türde veri başvurabilir. Değerin, depolamanın bir `Object` değişkeni tutulur başka bir yerde bellekte değişken bir işaretçi verileri tutan sırada.  
  
## <a name="object-classifier-functions"></a>Nesne sınıflandırıcı işlevleri  
 Visual Basic hakkında bilgi döndüren işlevleri sağlayan bir `Object` değişken için aşağıdaki tabloda gösterildiği gibi ifade eder.  
  
|İşlev|Nesne değişkeni başvuruyorsa, True döndürür|  
|--------------|---------------------------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A>|Tek bir değer yerine değerleri dizisi|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A>|A [Date veri türü](../../../../visual-basic/language-reference/data-types/date-data-type.md) değer veya tarih ve saat değeri olarak yorumlanan dize|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|Bir nesne türü <xref:System.DBNull>, eksik ya da var olmayan verileri temsil eder|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A>|Türetilen bir özel durum nesnesi <xref:System.Exception>|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A>|[Hiçbir şey](../../../../visual-basic/language-reference/nothing.md), diğer bir deyişle, bir nesne değişkenine şu anda atanır|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|Bir sayı veya sayı olarak yorumlanan dize|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A>|Bir başvuru türü (örneğin, bir dize, dizi, temsilci veya sınıf türü)|  
  
 Bu işlevler, bir işlem veya yordam için geçersiz bir değer göndererek önlemek için kullanabilirsiniz.  
  
## <a name="typeof-operator"></a>TypeOf İşleci  
 Ayrıca [TypeOf işleci](../../../../visual-basic/language-reference/operators/typeof-operator.md) bir nesne değişkeninin bir özel veri türü için şu anda başvurmadığını belirlemek için. `TypeOf`... `Is` ifadeyi hesaplar için `True` işlenenin çalışma zamanı tür türetilir veya belirtilen türe uygular.  
  
 Aşağıdaki örnekte `TypeOf` değer ve başvuru türlerine başvuran nesne değişkenleri.  
  
```  
' The following statement puts a value type (Integer) in an Object variable.  
Dim num As Object = 10  
' The following statement puts a reference type (Form) in an Object variable.  
Dim frm As Object = New Form()  
If TypeOf num Is Long Then Debug.WriteLine("num is Long")  
If TypeOf num Is Integer Then Debug.WriteLine("num is Integer")  
If TypeOf num Is Short Then Debug.WriteLine("num is Short")  
If TypeOf num Is Object Then Debug.WriteLine("num is Object")  
If TypeOf frm Is Form Then Debug.WriteLine("frm is Form")  
If TypeOf frm Is Label Then Debug.WriteLine("frm is Label")  
If TypeOf frm Is Object Then Debug.WriteLine("frm is Object")  
```  
  
 Yukarıdaki örnekte aşağıdaki satırları Yazar **hata ayıklama** penceresi:  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 Nesne değişkeni `num` türü verilere başvuran `Integer`, ve `frm` sınıfın bir nesneye başvuruyor <xref:System.Windows.Forms.Form>.  
  
## <a name="object-arrays"></a>Nesne dizileri  
 Bildirme ve bir dizi kullanın `Object` değişkenleri. Çeşitli veri türleri ve nesne sınıflarını işlemek gerektiğinde bu faydalıdır. Bir dizideki tüm öğeler aynı bildirilen veri türüne sahip olmalıdır. Bu veri türü olarak bildirme `Object` , nesneleri depolamak ve diğer veri türleri dizisi birlikte örnekleri sınıfı sağlar.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Nesne Değişkenleri](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Nesne Değişken Bildirimi](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Nesne Değişkeni Ataması](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Nasıl yapılır: Bir nesnenin geçerli örneğine başvurma](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [Nasıl yapılır: Bir nesne değişkeninin için hangi türe başvurduğunu belirleme](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)
- [Nasıl yapılır: İki nesnenin ilgili olup olmadığını belirleme](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Nasıl yapılır: İki nesnenin aynı olup olmadığını belirleme](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
- [Veri Türleri](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
