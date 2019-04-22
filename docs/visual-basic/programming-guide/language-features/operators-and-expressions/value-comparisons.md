---
title: Değer Karşılaştırmaları (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], comparing values
- Visual Basic code, operators
- Visual Basic code, expressions
- comparison operators [Visual Basic], comparing expressions
- numeric expressions
- operators [Visual Basic], comparison
- expressions [Visual Basic], comparing
ms.assetid: 60da0c76-9458-4afc-97e9-44a7939c064c
ms.openlocfilehash: 270b226d0a1aa7d08721e6f9ed36d68492685af3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818611"
---
# <a name="value-comparisons-visual-basic"></a><span data-ttu-id="c5513-102">Değer Karşılaştırmaları (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5513-102">Value Comparisons (Visual Basic)</span></span>
<span data-ttu-id="c5513-103">Karşılaştırma işleçleri, sayısal değişkenlerin değerleri karşılaştırma ifadeleri oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="c5513-103">Comparison operators can be used to construct expressions that compare the values of numeric variables.</span></span> <span data-ttu-id="c5513-104">Bu ifadeler dönüş bir `Boolean` değerine göre karşılaştırma doğru olmasına göre ya da yanlış.</span><span class="sxs-lookup"><span data-stu-id="c5513-104">These expressions return a `Boolean` value based on whether the comparison is true or false.</span></span> <span data-ttu-id="c5513-105">Böyle bir ifade örnekleri aşağıdaki gibidir.</span><span class="sxs-lookup"><span data-stu-id="c5513-105">Examples of such an expression are as follows.</span></span>  
  
 `45 > 26`  
  
 `26 > 45`  
  
 <span data-ttu-id="c5513-106">İlk ifadenin değerlendirdiği `True`45 26 büyük olduğu için.</span><span class="sxs-lookup"><span data-stu-id="c5513-106">The first expression evaluates to `True`, because 45 is greater than 26.</span></span> <span data-ttu-id="c5513-107">İkinci örnek değerlendiren `False`, 26 45 büyük değil.</span><span class="sxs-lookup"><span data-stu-id="c5513-107">The second example evaluates to `False`, because 26 is not greater than 45.</span></span>  
  
 <span data-ttu-id="c5513-108">Sayısal ifadeler bu şekilde de karşılaştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c5513-108">You can also compare numeric expressions in this fashion.</span></span> <span data-ttu-id="c5513-109">Aşağıdaki örnekte olduğu gibi karmaşık ifadeler, karşılaştırma ifadeleri kendilerini olabilir.</span><span class="sxs-lookup"><span data-stu-id="c5513-109">The expressions you compare can themselves be complex expressions, as in the following example.</span></span>  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 <span data-ttu-id="c5513-110">Önceki karmaşık ifadesi, değişmez değerleri ve değişkenleri işlev çağrılarını içerir.</span><span class="sxs-lookup"><span data-stu-id="c5513-110">The preceding complex expression includes literals, variables, and function calls.</span></span> <span data-ttu-id="c5513-111">Karşılaştırma işlecinin her iki tarafında ifadeler değerlendirilir ve elde edilen değerleri, ardından kullanılarak karşılaştırılır `>=` karşılaştırma işleci.</span><span class="sxs-lookup"><span data-stu-id="c5513-111">The expressions on both sides of the comparison operator are evaluated, and the resulting values are then compared using the `>=` comparison operator.</span></span> <span data-ttu-id="c5513-112">Sol tarafta bir ifadenin değerine büyüktür veya sağdaki ifadesinin değerine eşit tüm ifadenin değerlendirdiği `True`; Aksi takdirde olarak değerlendirilen `False`.</span><span class="sxs-lookup"><span data-stu-id="c5513-112">If the value of the expression on the left side is greater than or equal to the value of the expression on the right, the entire expression evaluates to `True`; otherwise, it evaluates to `False`.</span></span>  
  
 <span data-ttu-id="c5513-113">Değerleri karşılaştırma ifadeleri en yaygın olarak kullanılır `If...Then` yapılarını aşağıdaki örnekte olduğu gibi.</span><span class="sxs-lookup"><span data-stu-id="c5513-113">Expressions that compare values are most commonly used in `If...Then` constructions, as in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#84)]  
  
 <span data-ttu-id="c5513-114">`=` İşaretidir bir atama işleci yanı sıra bir karşılaştırma işleci.</span><span class="sxs-lookup"><span data-stu-id="c5513-114">The `=` sign is a comparison operator as well as an assignment operator.</span></span> <span data-ttu-id="c5513-115">Aşağıdaki örnekte gösterildiği gibi soldaki değerin sağdaki değerine eşit olup olmadığını bir karşılaştırma işleci kullanıldığında, değerlendirir.</span><span class="sxs-lookup"><span data-stu-id="c5513-115">When used as a comparison operator, it evaluates whether the value on the left is equal to the value on the right, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#85)]  
  
 <span data-ttu-id="c5513-116">Karşılaştırma ifadesindeki her yerde kullanabilirsiniz bir `Boolean` değerdir gerekli, olduğu gibi bir `If`, `While`, `Loop`, veya `ElseIf` deyimi, atama veya bir değere geçirerek bir `Boolean` değişkeni.</span><span class="sxs-lookup"><span data-stu-id="c5513-116">You can also use a comparison expression anywhere a `Boolean` value is needed, such as in an `If`, `While`, `Loop`, or `ElseIf` statement, or when assigning to or passing a value to a `Boolean` variable.</span></span> <span data-ttu-id="c5513-117">Aşağıdaki örnekte, karşılaştırma ifadesi tarafından döndürülen değer atanmış bir `Boolean` değişkeni.</span><span class="sxs-lookup"><span data-stu-id="c5513-117">In the following example, the value returned by the comparison expression is assigned to a `Boolean` variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#86)]  
  
## <a name="see-also"></a><span data-ttu-id="c5513-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="c5513-118">See also</span></span>

- [<span data-ttu-id="c5513-119">Boole İfadeleri</span><span class="sxs-lookup"><span data-stu-id="c5513-119">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="c5513-120">İşleçler ve İfadeler</span><span class="sxs-lookup"><span data-stu-id="c5513-120">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="c5513-121">Visual Basic'de Karşılaştırma işleçleri</span><span class="sxs-lookup"><span data-stu-id="c5513-121">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="c5513-122">Nasıl yapılır: Sayısal değerleri hesaplama</span><span class="sxs-lookup"><span data-stu-id="c5513-122">How to: Calculate Numeric Values</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)
- [<span data-ttu-id="c5513-123">Visual Basic'de İşleç önceliği</span><span class="sxs-lookup"><span data-stu-id="c5513-123">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
