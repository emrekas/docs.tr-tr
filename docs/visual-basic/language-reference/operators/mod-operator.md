---
title: Mod İşleci (Visual Basic)
ms.date: 04/24/2018
f1_keywords:
- vb.Mod
helpviewer_keywords:
- remainder (Mod operator)
- division operator [Visual Basic], Mod operator
- modulus operator [Visual Basic], Visual Basic
- Mod operator [Visual Basic]
- operators [Visual Basic], division
- arithmetic operators [Visual Basic], Mod
- math operators [Visual Basic]
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
ms.openlocfilehash: b127c50f3319d4fe7c4890fc3bffb295baa37466
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58840178"
---
# <a name="mod-operator-visual-basic"></a><span data-ttu-id="6ee0b-102">Mod işleci (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ee0b-102">Mod operator (Visual Basic)</span></span>
<span data-ttu-id="6ee0b-103">İki sayıyı böler ve yalnızca kalanı döndürür.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-103">Divides two numbers and returns only the remainder.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ee0b-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="6ee0b-104">Syntax</span></span>  
  
```  
number1 Mod number2  
```  
  
## <a name="parts"></a><span data-ttu-id="6ee0b-105">Bölümler</span><span class="sxs-lookup"><span data-stu-id="6ee0b-105">Parts</span></span>  
 `number1`  
 <span data-ttu-id="6ee0b-106">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-106">Required.</span></span> <span data-ttu-id="6ee0b-107">Herhangi bir sayısal ifade.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-107">Any numeric expression.</span></span>  
  
 `number2`  
 <span data-ttu-id="6ee0b-108">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-108">Required.</span></span> <span data-ttu-id="6ee0b-109">Herhangi bir sayısal ifade.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="6ee0b-110">Desteklenen türler</span><span class="sxs-lookup"><span data-stu-id="6ee0b-110">Supported types</span></span>  
 <span data-ttu-id="6ee0b-111">Tüm sayısal türler.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-111">All numeric types.</span></span> <span data-ttu-id="6ee0b-112">Bu imzalanmamış ve kayan nokta türlerini içerir ve `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-112">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="6ee0b-113">Sonuç</span><span class="sxs-lookup"><span data-stu-id="6ee0b-113">Result</span></span>

<span data-ttu-id="6ee0b-114">Sonra kalan sonucudur `number1` bölünür `number2`.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-114">The result is the remainder after `number1` is divided by `number2`.</span></span> <span data-ttu-id="6ee0b-115">Örneğin, ifade `14 Mod 4` 2 olarak değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-115">For example, the expression `14 Mod 4` evaluates to 2.</span></span>  

> [!NOTE]
> <span data-ttu-id="6ee0b-116">Arasında bir fark *kalan* ve *modulus* negatif sayılar için farklı sonuçlarla Matematikte.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-116">There is a difference between *remainder* and *modulus* in mathematics, with different results for negative numbers.</span></span> <span data-ttu-id="6ee0b-117">`Mod` İşleci Visual Basic'te .NET Framework `op_Modulus` işleci ve arka plandaki [rem](<xref:System.Reflection.Emit.OpCodes.Rem>) IL yönergesinin tüm kalan işlemi gerçekleştirin.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-117">The `Mod` operator in Visual Basic, the .NET Framework `op_Modulus` operator, and the underlying [rem](<xref:System.Reflection.Emit.OpCodes.Rem>) IL instruction all perform a remainder operation.</span></span>

<span data-ttu-id="6ee0b-118">Sonucu bir `Mod` işlemi korur bölünen sayının işaretini `number1`, ve pozitif veya negatif olabilir.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-118">The result of a `Mod` operation retains the sign of the dividend, `number1`, and so it may be positive or negative.</span></span> <span data-ttu-id="6ee0b-119">Her zaman aralığında sonucudur (-`number2`, `number2`), özel.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-119">The result is always in the range (-`number2`, `number2`), exclusive.</span></span> <span data-ttu-id="6ee0b-120">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="6ee0b-120">For example:</span></span>

```vb
Public Module Example
   Public Sub Main()
      Console.WriteLine($" 8 Mod  3 = {8 Mod 3}")
      Console.WriteLine($"-8 Mod  3 = {-8 Mod 3}")
      Console.WriteLine($" 8 Mod -3 = {8 Mod -3}")
      Console.WriteLine($"-8 Mod -3 = {-8 Mod -3}")
   End Sub
End Module
' The example displays the following output:
'       8 Mod  3 = 2
'      -8 Mod  3 = -2
'       8 Mod -3 = 2
'      -8 Mod -3 = -2
```

## <a name="remarks"></a><span data-ttu-id="6ee0b-121">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="6ee0b-121">Remarks</span></span>  
 <span data-ttu-id="6ee0b-122">Ya da `number1` veya `number2` bir kayan nokta kayan nokta bölme kalanını döndürülen değerdir.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-122">If either `number1` or `number2` is a floating-point value, the floating-point remainder of the division is returned.</span></span> <span data-ttu-id="6ee0b-123">Sonuç veri türü, veri türlerini bölme kaynaklanan tüm olası değerlerini tutabilecek en küçük veri türüdür `number1` ve `number2`.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-123">The data type of the result is the smallest data type that can hold all possible values that result from division with the data types of `number1` and `number2`.</span></span>  
  
 <span data-ttu-id="6ee0b-124">Varsa `number1` veya `number2` değerlendiren [hiçbir şey](../../../visual-basic/language-reference/nothing.md), sıfır olarak kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-124">If `number1` or `number2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
 <span data-ttu-id="6ee0b-125">İlgili işleçler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="6ee0b-125">Related operators include the following:</span></span>  
  
-   <span data-ttu-id="6ee0b-126">[\ İşleci (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) bölme işleminin tamsayı bölümünü döndürür.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-126">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient of a division.</span></span> <span data-ttu-id="6ee0b-127">Örneğin, ifade `14 \ 4` 3 olarak değerlendirir.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-127">For example, the expression `14 \ 4` evaluates to 3.</span></span>  
  
-   <span data-ttu-id="6ee0b-128">[/ İşleci (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) bir kayan noktalı sayı olarak kalan dahil olmak üzere tam kalanını döndürür.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-128">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, including the remainder, as a floating-point number.</span></span> <span data-ttu-id="6ee0b-129">Örneğin, ifade `14 / 4` 3.5 için değerlendirir.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-129">For example, the expression `14 / 4` evaluates to 3.5.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="6ee0b-130">Denenen sıfıra bölme</span><span class="sxs-lookup"><span data-stu-id="6ee0b-130">Attempted division by zero</span></span>  
 <span data-ttu-id="6ee0b-131">Varsa `number2` sıfır olarak davranışını değerlendirilen `Mod` işleci, işlenen veri türüne bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-131">If `number2` evaluates to zero, the behavior of the `Mod` operator depends on the data type of the operands.</span></span> <span data-ttu-id="6ee0b-132">Bir tamsayı bölme oluşturur bir <xref:System.DivideByZeroException> özel durum.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-132">An integral division throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="6ee0b-133">Kayan nokta bölme döndürür <xref:System.Double.NaN>.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-133">A floating-point division returns <xref:System.Double.NaN>.</span></span>  
  
## <a name="equivalent-formula"></a><span data-ttu-id="6ee0b-134">Eşdeğer formülü</span><span class="sxs-lookup"><span data-stu-id="6ee0b-134">Equivalent formula</span></span>  
 <span data-ttu-id="6ee0b-135">İfade `a Mod b` şu formüllerden birini eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="6ee0b-135">The expression `a Mod b` is equivalent to either of the following formulas:</span></span>  
  
 `a - (b * (a \ b))`  
  
 `a - (b * Fix(a / b))`  
  
## <a name="floating-point-imprecision"></a><span data-ttu-id="6ee0b-136">Kayan nokta kesinlik eksikliği</span><span class="sxs-lookup"><span data-stu-id="6ee0b-136">Floating-point imprecision</span></span>  
 <span data-ttu-id="6ee0b-137">Kayan noktalı sayı ile çalıştığınızda, bunlar her zaman kesin bir ondalık gösterim bellekte olmadığını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-137">When you work with floating-point numbers, remember that they do not always have a precise decimal representation in memory.</span></span> <span data-ttu-id="6ee0b-138">Bu değer karşılaştırması gibi bazı işlemleri öğesinden beklenmeyen sonuçlara açabilir ve `Mod` işleci.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-138">This can lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="6ee0b-139">Daha fazla bilgi için [veri türleri sorunlarını giderme](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="6ee0b-139">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="6ee0b-140">Aşırı Yükleme</span><span class="sxs-lookup"><span data-stu-id="6ee0b-140">Overloading</span></span>  
 <span data-ttu-id="6ee0b-141">`Mod` İşleci olabilir *aşırı*, yani bir sınıf veya yapı davranışını tanımlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-141">The `Mod` operator can be *overloaded*, which means that a class or structure can redefine its behavior.</span></span> <span data-ttu-id="6ee0b-142">Kodunuzu geçerliyse `Mod` bir sınıf veya yapı gibi bir aşırı yüklemeyi içeren bir örneği için yeniden tanımlanan davranışını anladığınızdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-142">If your code applies `Mod` to an instance of a class or structure that includes such an overload, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="6ee0b-143">Daha fazla bilgi için [işleç yordamları](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="6ee0b-143">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ee0b-144">Örnek</span><span class="sxs-lookup"><span data-stu-id="6ee0b-144">Example</span></span>  
 <span data-ttu-id="6ee0b-145">Aşağıdaki örnekte `Mod` işleci iki sayı bölme ve yalnızca kalanı döndürür.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-145">The following example uses the `Mod` operator to divide two numbers and return only the remainder.</span></span> <span data-ttu-id="6ee0b-146">Ya da bir kayan noktalı sayı olan, kalan temsil eden bir kayan noktalı sayı sonucudur.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-146">If either number is a floating-point number, the result is a floating-point number that represents the remainder.</span></span>  
  
 [!code-vb[VbVbalrOperators#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#31)]  
  
## <a name="example"></a><span data-ttu-id="6ee0b-147">Örnek</span><span class="sxs-lookup"><span data-stu-id="6ee0b-147">Example</span></span>  
 <span data-ttu-id="6ee0b-148">Aşağıdaki örnek, kayan nokta işlenenler kesinlik eksikliği olası gösterir.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-148">The following example demonstrates the potential imprecision of floating-point operands.</span></span> <span data-ttu-id="6ee0b-149">İlk ifade, işlenenin olduğu `Double`, ve 0.2 sonsuz yinelenen bir ikili Kesir 0.20000000000000001 depolanan değerine sahip.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-149">In the first statement, the operands are `Double`, and 0.2 is an infinitely repeating binary fraction with a stored value of 0.20000000000000001.</span></span> <span data-ttu-id="6ee0b-150">İkinci ifadede, değişmez değer türü karakteri `D` iki işlenen de zorlar `Decimal`, ve 0.2 kesin bir gösterimi.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-150">In the second statement, the literal type character `D` forces both operands to `Decimal`, and 0.2 has a precise representation.</span></span>  
  
 [!code-vb[VbVbalrOperators#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="6ee0b-151">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="6ee0b-151">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- [<span data-ttu-id="6ee0b-152">Aritmetik İşleçler</span><span class="sxs-lookup"><span data-stu-id="6ee0b-152">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="6ee0b-153">Visual Basic'de İşleç önceliği</span><span class="sxs-lookup"><span data-stu-id="6ee0b-153">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="6ee0b-154">İşlevselliğe Göre Listelenmiş İşleçler</span><span class="sxs-lookup"><span data-stu-id="6ee0b-154">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="6ee0b-155">Veri Türü Sorunlarını Giderme</span><span class="sxs-lookup"><span data-stu-id="6ee0b-155">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="6ee0b-156">Visual Basic'de aritmetik işleçler</span><span class="sxs-lookup"><span data-stu-id="6ee0b-156">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="6ee0b-157">\ İşleci (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ee0b-157">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
