---
title: Module deyimi (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Module
- vb.Module
helpviewer_keywords:
- modules, classes
- modules
- Module statement [Visual Basic]
- modules, declaring
- standard modules
- classes [Visual Basic], vs. modules
- declarations [Visual Basic], modules
ms.assetid: a1243afc-14a5-45df-95d5-51118aeac362
ms.openlocfilehash: f546498e5282bcf58d07a06968bb4303e4e6d7b9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838150"
---
# <a name="module-statement"></a>Module Deyimi
Bir modülün adını bildirir ve değişkenleri, özellikleri, olayları ve modülü oluşturan yordamların tanımını tanıtır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```vb 
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a>Bölümler  
 `attributelist`  
 İsteğe bağlı. Bkz: [öznitelik listesi](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 İsteğe bağlı. Aşağıdakilerden biri olabilir:  
  
-   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 Bkz: [erişim düzeyini Visual Basic'te](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `name`  
 Gerekli. Bu modül adı. Bkz: [bildirilen öğe adları](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 `statements`  
 İsteğe bağlı. Değişkenleri, özellikleri, olayları, yordamları ve bu modülün iç içe geçmiş türleri tanımlamak deyimler.  
  
 `End Module`  
 Sonlandırır `Module` tanımı.  
  
## <a name="remarks"></a>Açıklamalar  
 A `Module` deyimi, ad alanı bir başvuru türü tanımlar. A *Modülü* (bazen adlı bir *standart modül*) benzer bir sınıf, ancak bazı önemli farklılıklar. Her bir modüle tam olarak bir örneği olduğu ve oluşturulamaz veya bir değişkene atanması gerekmez. Modüller devralmayı desteklemez veya arabirimlerini. Bir modül bildirimi bir *türü* bir sınıf veya yapı olan anlamında — bir modülün veri türü için bir programlama öğesi bildiremezsiniz.  
  
 Kullanabileceğiniz `Module` yalnızca ad alanı düzeyinde. Başka bir deyişle *bildirim içeriğinin* bir modül, kaynak dosya veya ad alanı olmalıdır ve bir sınıf, yapı, modül, arabirimi, yordam veya blok olamayacağı için. Bir modülün herhangi bir türü veya başka bir modül içinde iç içe olamaz. Daha fazla bilgi için [bildirim bağlamları ve varsayılan erişim düzeyleri](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Bir modül programınızı olarak aynı kullanım ömrü vardır. Tüm üyeleri olduğundan `Shared`, ayrıca sahip oldukları yaşam süreleri, programın eşit.  
  
 Modüller için varsayılan değer [arkadaş](../../../visual-basic/language-reference/modifiers/friend.md) erişim. Erişim değiştiricileri ile kullanıcıların erişim düzeylerini ayarlayabilirsiniz. Daha fazla bilgi için [erişim düzeyini Visual Basic'te](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Tüm modül örtük olarak üyeleri `Shared`.  
  
## <a name="classes-and-modules"></a>Sınıflar ve modüller  
 Bu öğeleri birçok benzerlikler, ancak bazı önemli farklar da mevcuttur.  
  
-   **Terimler.** Visual Basic'in önceki sürümlerindeki tanımak modülleri iki tür: *sınıf modülleri* (.cls dosyaları) ve *Standart modüller* (.bas dosyaları). Bu sürümdeki çağırır *sınıfları* ve *modülleri*sırasıyla.  
  
-   **Paylaşılan üyeler.** Bir sınıfın üyesi bir paylaşılan olup veya örnek üye denetleyebilirsiniz.  
  
-   **Nesne yönü.** Nesne yönelimli sınıflardır, ancak modüller değildir. Bu nedenle tek sınıf nesneleri olarak oluşturulabilir. Daha fazla bilgi için [nesneler ve sınıflar](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="rules"></a>Kurallar  
  
-   **Değiştiriciler.** Tüm modül örtük olarak üyeleridir [paylaşılan](../../../visual-basic/language-reference/modifiers/shared.md). Kullanamazsınız `Shared` bildirme üyesi ve herhangi bir üyenin paylaşılan durumu değiştirilemiyor, anahtar sözcüğü.  
  
-   **Devralma.** Bir modül dışında herhangi bir türden devralamaz <xref:System.Object>, hangi tüm modüllerden devralır. Özellikle, bir modül bir başkasından devralınamaz.  
  
     Kullanamazsınız [devralan deyimi](../../../visual-basic/language-reference/statements/inherits-statement.md) belirtmek için bir modül tanımında bile <xref:System.Object>.  
  
-   **Varsayılan özellik.** Bir modülün herhangi bir varsayılan özelliği tanımlanamaz. Daha fazla bilgi için [varsayılan](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Davranış  
  
-   **Erişim düzeyi.** Bir modül her bir üyeyi kendi erişim düzeyiyle bildirebilirsiniz. Modül üyeler için varsayılan değer [genel](../../../visual-basic/language-reference/modifiers/public.md) erişim, değişkenler ve sabitler, dışında varsayılan [özel](../../../visual-basic/language-reference/modifiers/private.md) erişim. Bir modül daha üyelerinin birden sınırlı erişimi Belirtilen modül erişim düzeyi önceliklidir.  
  
-   **Kapsam.** Ad alanı kapsamdadır bir modüldür.  
  
     Her modülü üye kapsamı bütün bir modüldür. Tüm üyeleri geçmeleri bildirimi *türü promosyon*, modülü içeren ad alanına yükseltilecek kapsamlarına neden olur. Daha fazla bilgi için [tür promosyonu](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).  
  
-   **Nitelik.** Bir projede birden çok modül sahip olabilir ve iki veya daha fazla modül aynı ada sahip üye bildirebilirsiniz. Ancak, başvurusu bu modül dışında ise herhangi bir referans gibi bir üye uygun modül adıyla nitelemeniz gerekir. Daha fazla bilgi için [bildirilmiş öğelere başvurular](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## <a name="example"></a>Örnek  
 [!code-vb[VbVbalrStatements#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#69)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Class Deyimi](../../../visual-basic/language-reference/statements/class-statement.md)
- [Namespace Deyimi](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [Structure Deyimi](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Interface Deyimi](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Property Deyimi](../../../visual-basic/language-reference/statements/property-statement.md)
- [Tür Yükseltme](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
