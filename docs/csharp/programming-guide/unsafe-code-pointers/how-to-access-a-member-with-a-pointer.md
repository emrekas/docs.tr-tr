---
title: 'Nasıl yapılır: - işaretçiyle bir üyeye erişme C# Programlama Kılavuzu'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], member access
ms.assetid: 1e998498-8c85-4a78-8ce2-4d8c20f08342
ms.openlocfilehash: 153e5f1cfc1f4f8309a31ab58d699a273b417563
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54546497"
---
# <a name="how-to-access-a-member-with-a-pointer-c-programming-guide"></a>Nasıl yapılır: işaretçiyle bir üyeye erişme (C# Programlama Kılavuzu)
Güvenli olmayan bir bağlamda bildirilen bir yapının bir üyesine erişmek için üye erişimi işleci aşağıdaki örnekte gösterildiği gibi kullanabileceğiniz `p` işaretçisidir bir [yapı](../../../csharp/language-reference/keywords/struct.md) üye içeren `x`.  
  
```  
CoOrds* p = &home;  
p -> x = 25; //member access operator ->  
```  
  
## <a name="example"></a>Örnek  
 Bu örnekte, bir [yapı](../../../csharp/language-reference/keywords/struct.md), `CoOrds`, iki koordinat içeren `x` ve `y` bildirildi ve örneği. Üye erişimi işleci kullanarak `->` örneğine bir işaretçi `home`, `x` ve `y` değerler atanır.  
  
> [!NOTE]
>  Dikkat ifade `p->x` ifadesine eşdeğerdir `(*p).x`, ve iki ifadeden birini kullanarak aynı sonucu elde edebilirsiniz.  
  
 [!code-csharp[csProgGuidePointers#9](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#10](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_2.cs)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)
- [İşaretçi İfadeleri](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [İşaretçi türleri](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [Türler](../../../csharp/language-reference/keywords/types.md)
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)
- [fixed Deyimi](../../../csharp/language-reference/keywords/fixed-statement.md)
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
