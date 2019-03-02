---
title: 'Nasıl yapılır: - işaretçiyle bir üyeye erişme C# Programlama Kılavuzu'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], member access
ms.assetid: 1e998498-8c85-4a78-8ce2-4d8c20f08342
ms.openlocfilehash: 9762b9e2487c30b81b7ef6ae22827b64e3cb02e2
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200357"
---
# <a name="how-to-access-a-member-with-a-pointer-c-programming-guide"></a><span data-ttu-id="64d71-102">Nasıl yapılır: işaretçiyle bir üyeye erişme (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="64d71-102">How to: access a member with a pointer (C# Programming Guide)</span></span>
<span data-ttu-id="64d71-103">Güvenli olmayan bir bağlamda bildirilen bir yapının bir üyesine erişmek için üye erişimi işleci aşağıdaki örnekte gösterildiği gibi kullanabileceğiniz `p` işaretçisidir bir [yapı](../../../csharp/language-reference/keywords/struct.md) üye içeren `x`.</span><span class="sxs-lookup"><span data-stu-id="64d71-103">To access a member of a struct that is declared in an unsafe context, you can use the member access operator as shown in the following example in which `p` is a pointer to a [struct](../../../csharp/language-reference/keywords/struct.md) that contains a member `x`.</span></span>  
  
```  
CoOrds* p = &home;  
p -> x = 25; //member access operator ->  
```  
  
## <a name="example"></a><span data-ttu-id="64d71-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="64d71-104">Example</span></span>  
 <span data-ttu-id="64d71-105">Bu örnekte, bir [yapı](../../../csharp/language-reference/keywords/struct.md), `CoOrds`, iki koordinat içeren `x` ve `y` bildirildi ve örneği.</span><span class="sxs-lookup"><span data-stu-id="64d71-105">In this example, a [struct](../../../csharp/language-reference/keywords/struct.md), `CoOrds`, that contains the two coordinates `x` and `y` is declared and instantiated.</span></span> <span data-ttu-id="64d71-106">Üye erişimi işleci kullanarak `->` örneğine bir işaretçi `home`, `x` ve `y` değerler atanır.</span><span class="sxs-lookup"><span data-stu-id="64d71-106">By using the member access operator `->` and a pointer to the instance `home`, `x` and `y` are assigned values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64d71-107">Dikkat ifade `p->x` ifadesine eşdeğerdir `(*p).x`, ve iki ifadeden birini kullanarak aynı sonucu elde edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="64d71-107">Notice that the expression `p->x` is equivalent to the expression `(*p).x`, and you can obtain the same result by using either of the two expressions.</span></span>  
  
 [!code-csharp[csProgGuidePointers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#9)]  
  
 [!code-csharp[csProgGuidePointers#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#10)]  
  
## <a name="see-also"></a><span data-ttu-id="64d71-108">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="64d71-108">See also</span></span>

- [<span data-ttu-id="64d71-109">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="64d71-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="64d71-110">İşaretçi İfadeleri</span><span class="sxs-lookup"><span data-stu-id="64d71-110">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="64d71-111">İşaretçi türleri</span><span class="sxs-lookup"><span data-stu-id="64d71-111">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="64d71-112">Türler</span><span class="sxs-lookup"><span data-stu-id="64d71-112">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="64d71-113">unsafe</span><span class="sxs-lookup"><span data-stu-id="64d71-113">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="64d71-114">fixed Deyimi</span><span class="sxs-lookup"><span data-stu-id="64d71-114">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="64d71-115">stackalloc</span><span class="sxs-lookup"><span data-stu-id="64d71-115">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
