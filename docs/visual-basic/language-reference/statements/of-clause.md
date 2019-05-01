---
title: Of Tümcesi (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Of
- vb.Of
- vb.of
helpviewer_keywords:
- Of keyword [Visual Basic]
- arguments [Visual Basic], data types
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- parameters [Visual Basic], type
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
ms.assetid: 0db8f65c-65af-4089-ab7f-6fcfecb60444
ms.openlocfilehash: 880570c714292b0c11eef4e2cd4c4b410bb075f1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61784156"
---
# <a name="of-clause-visual-basic"></a><span data-ttu-id="92428-102">Of Tümcesi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="92428-102">Of Clause (Visual Basic)</span></span>
<span data-ttu-id="92428-103">Tanıtır bir `Of` tanımlayan yan tümcesi bir *tür parametresi* üzerinde bir *genel* sınıfı, yapı, arabirim, temsilci veya yordam.</span><span class="sxs-lookup"><span data-stu-id="92428-103">Introduces an `Of` clause, which identifies a *type parameter* on a *generic* class, structure, interface, delegate, or procedure.</span></span> <span data-ttu-id="92428-104">Genel türler hakkında daha fazla bilgi için bkz: [Visual Basic'de genel türler](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="92428-104">For information on generic types, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span>  
  
## <a name="using-the-of-keyword"></a><span data-ttu-id="92428-105">Kullanarak anahtar sözcüğü</span><span class="sxs-lookup"><span data-stu-id="92428-105">Using the Of Keyword</span></span>  
 <span data-ttu-id="92428-106">Aşağıdaki kod örneğinde `Of` iki tür parametreleri alan sınıfının ana hattı tanımlamak için anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="92428-106">The following code example uses the `Of` keyword to define the outline of a class that takes two type parameters.</span></span> <span data-ttu-id="92428-107">Bunu *kısıtlar* `keyType` parametresiyle <xref:System.IComparable> kullanan kodu uygulayan bir tür bağımsız değişkeni sağlaması gerekir yani arabirimi <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="92428-107">It *constrains* the `keyType` parameter by the <xref:System.IComparable> interface, which means the consuming code must supply a type argument that implements <xref:System.IComparable>.</span></span> <span data-ttu-id="92428-108">Bunun gerekli olmasının böylece `add` yordam çağırabilir <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="92428-108">This is necessary so that the `add` procedure can call the <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="92428-109">Kısıtlamaları hakkında daha fazla bilgi için bkz. [tür listesi](../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="92428-109">For more information on constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
```  
Public Class Dictionary(Of entryType, keyType As IComparable)  
    Public Sub add(ByVal e As entryType, ByVal k As keyType)  
        Dim dk As keyType  
        If k.CompareTo(dk) = 0 Then  
        End If  
    End Sub  
    Public Function find(ByVal k As keyType) As entryType  
    End Function  
End Class  
```  
  
 <span data-ttu-id="92428-110">Önceki bir sınıf tanımı tamamlarsanız, çeşitli oluşturabilirsiniz `dictionary` bu sınıflardan.</span><span class="sxs-lookup"><span data-stu-id="92428-110">If you complete the preceding class definition, you can construct a variety of `dictionary` classes from it.</span></span> <span data-ttu-id="92428-111">Sağladığınız için türleri `entryType` ve `keyType` sınıf giriş türünü içerir ve her bir girdi ilişkilendirir anahtar türünü belirler.</span><span class="sxs-lookup"><span data-stu-id="92428-111">The types you supply to `entryType` and `keyType` determine what type of entry the class holds and what type of key it associates with each entry.</span></span> <span data-ttu-id="92428-112">Kısıtlama nedeniyle, için sağlamalısınız `keyType` uygulayan bir tür <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="92428-112">Because of the constraint, you must supply to `keyType` a type that implements <xref:System.IComparable>.</span></span>  
  
 <span data-ttu-id="92428-113">Aşağıdaki kod örneği içeren bir nesne oluşturur `String` girişleri ve associates bir `Integer` her bir anahtar.</span><span class="sxs-lookup"><span data-stu-id="92428-113">The following code example creates an object that holds `String` entries and associates an `Integer` key with each one.</span></span> <span data-ttu-id="92428-114">`Integer` uygulayan <xref:System.IComparable> ve bu nedenle üzerinde kısıtlamasına `keyType`.</span><span class="sxs-lookup"><span data-stu-id="92428-114">`Integer` implements <xref:System.IComparable> and therefore satisfies the constraint on `keyType`.</span></span>  
  
```  
Dim d As New dictionary(Of String, Integer)  
```  
  
 <span data-ttu-id="92428-115">`Of` Anahtar sözcüğü bu bağlamda kullanılabilir:</span><span class="sxs-lookup"><span data-stu-id="92428-115">The `Of` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="92428-116">Class Deyimi</span><span class="sxs-lookup"><span data-stu-id="92428-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="92428-117">Delegate Deyimi</span><span class="sxs-lookup"><span data-stu-id="92428-117">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="92428-118">Function Deyimi</span><span class="sxs-lookup"><span data-stu-id="92428-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="92428-119">Interface Deyimi</span><span class="sxs-lookup"><span data-stu-id="92428-119">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="92428-120">Structure Deyimi</span><span class="sxs-lookup"><span data-stu-id="92428-120">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="92428-121">Sub Deyimi</span><span class="sxs-lookup"><span data-stu-id="92428-121">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="92428-122">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="92428-122">See also</span></span>

- <xref:System.IComparable>
- [<span data-ttu-id="92428-123">Tür Listesi</span><span class="sxs-lookup"><span data-stu-id="92428-123">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="92428-124">Visual Basic'de genel türler</span><span class="sxs-lookup"><span data-stu-id="92428-124">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="92428-125">İçinde</span><span class="sxs-lookup"><span data-stu-id="92428-125">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [<span data-ttu-id="92428-126">Çıkış</span><span class="sxs-lookup"><span data-stu-id="92428-126">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
