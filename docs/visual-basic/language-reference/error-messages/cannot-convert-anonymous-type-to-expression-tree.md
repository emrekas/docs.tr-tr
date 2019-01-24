---
title: Anonim türün bir alanı başka bir alanı başlatmak için kullanıldığından; anonim tür, ifade ağacına dönüştürülemiyor.
ms.date: 07/20/2015
f1_keywords:
- bc36548
- vbc36548
helpviewer_keywords:
- BC36548
ms.assetid: 27de068f-080e-4160-86bf-1ec23fd1925a
ms.openlocfilehash: a6ddbaa358709fe306f1529112d1f2bd0a715a91
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646951"
---
# <a name="cannot-convert-anonymous-type-to-expression-tree-because-it-contains-a-field-that-is-used-in-the-initialization-of-another-field"></a>Anonim türün bir alanı başka bir alanı başlatmak için kullanıldığından; anonim tür, ifade ağacına dönüştürülemiyor.
Anonim türün başka bir özelliğini başlatmak için anonim türün bir özellik kullanıldığında, derleyici dönüştürülmesi anonim bir ifade ağacı kabul etmiyor. Örneğin, aşağıdaki kodda, `Prop1` başlatma listesinde bildirilen ve ardından ilk değeri olarak kullanılan `Prop2`.  
  
```vb  
Module M2  
  
    Sub ExpressionExample(Of T)(ByVal x As Expressions.Expression(Of Func(Of T)))  
    End Sub  
  
    Sub Main()  
        ' The following line causes the error.  
        ' ExpressionExample(Function() New With {.Prop1 = 2, .Prop2 = .Prop1})  
  
    End Sub  
End Module  
```  
  
 **Hata Kimliği:** BC36548  
  
## <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   İlk değeri atamak `Prop1` yerel bir değişkene. Bu değişken hem de Ata `Prop1` ve `Prop2`aşağıdaki kodda gösterildiği gibi.  
  
    ```  
    Sub Main()  
  
        Dim temp = 2  
        ExpressionExample(Function() New With {.Prop1 = temp, .Prop2 = temp})  
  
    End Sub  
    ```  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Anonim türleri (Visual Basic)](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [İfade ağaçları (Visual Basic)](../../programming-guide/concepts/expression-trees/index.md)
- [Nasıl yapılır: (Visual Basic) dinamik sorgular derlemek için ifade ağaçları kullanma](../../programming-guide/concepts/expression-trees/how-to-use-expression-trees-to-build-dynamic-queries.md)
