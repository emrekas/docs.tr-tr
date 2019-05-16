---
title: 'Döngüler: for...in İfadesi'
description: Bkz. nasıl F# for... ifadesinde döngü yapısı bir sıralanabilir koleksiyonun içindeki bir desenle eşleşmeleri üzerinden yinelemek için kullanılır.
ms.date: 05/16/2016
ms.openlocfilehash: 5346713b1747227f3fe79e308455d976e506f968
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641812"
---
# <a name="loops-forin-expression"></a><span data-ttu-id="31083-103">Döngüler: for...in İfadesi</span><span class="sxs-lookup"><span data-stu-id="31083-103">Loops: for...in Expression</span></span>

<span data-ttu-id="31083-104">Bu uvozuje konstruktor aralık ifadesi, sıra, liste, dizi veya numaralandırma destekleyen diğer yapı gibi bir sıralanabilir koleksiyonun içindeki bir desenle eşleşmeleri üzerinden yinelemek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="31083-104">This looping construct is used to iterate over the matches of a pattern in an enumerable collection such as a range expression, sequence, list, array, or other construct that supports enumeration.</span></span>

## <a name="syntax"></a><span data-ttu-id="31083-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="31083-105">Syntax</span></span>

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="31083-106">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="31083-106">Remarks</span></span>

<span data-ttu-id="31083-107">`for...in` İfade için karşılaştırılabilir `for each` diğer .NET dilleri deyiminde bir sıralanabilir koleksiyonun değerleri üzerinde döngü için kullanıldığından.</span><span class="sxs-lookup"><span data-stu-id="31083-107">The `for...in` expression can be compared to the `for each` statement in other .NET languages because it is used to loop over the values in an enumerable collection.</span></span> <span data-ttu-id="31083-108">Ancak, `for...in` koleksiyon yerine yalnızca yineleme üzerinden tüm koleksiyon üzerinde desen de destekler.</span><span class="sxs-lookup"><span data-stu-id="31083-108">However, `for...in` also supports pattern matching over the collection instead of just iteration over the whole collection.</span></span>

<span data-ttu-id="31083-109">Numaralandırılabilir ifade bir sıralanabilir koleksiyonun olarak veya kullanılarak belirtilebilir `..` olarak bir tamsayı türü üzerinde bir aralık işleci.</span><span class="sxs-lookup"><span data-stu-id="31083-109">The enumerable expression can be specified as an enumerable collection or, by using the `..` operator, as a range on an integral type.</span></span> <span data-ttu-id="31083-110">Numaralandırılabilir koleksiyonları listeler, dizileri, diziler, kümeleri, haritalar ve benzeri içerir.</span><span class="sxs-lookup"><span data-stu-id="31083-110">Enumerable collections include lists, sequences, arrays, sets, maps, and so on.</span></span> <span data-ttu-id="31083-111">Uygulayan herhangi bir tür `System.Collections.IEnumerable` kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="31083-111">Any type that implements `System.Collections.IEnumerable` can be used.</span></span>

<span data-ttu-id="31083-112">Ne zaman, express aralığı kullanarak `..` işleci, aşağıdaki söz dizimini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="31083-112">When you express a range by using the `..` operator, you can use the following syntax.</span></span>

<span data-ttu-id="31083-113">*Başlangıç* ...</span><span class="sxs-lookup"><span data-stu-id="31083-113">*start* ..</span></span> <span data-ttu-id="31083-114">*Son*</span><span class="sxs-lookup"><span data-stu-id="31083-114">*finish*</span></span>

<span data-ttu-id="31083-115">Adlı bir artışı içeren bir sürümünü de kullanabilirsiniz *atla*, aşağıdaki kodda gibi.</span><span class="sxs-lookup"><span data-stu-id="31083-115">You can also use a version that includes an increment called the *skip*, as in the following code.</span></span>

<span data-ttu-id="31083-116">*Başlangıç* ...</span><span class="sxs-lookup"><span data-stu-id="31083-116">*start* ..</span></span> <span data-ttu-id="31083-117">*atla* ...</span><span class="sxs-lookup"><span data-stu-id="31083-117">*skip* ..</span></span> <span data-ttu-id="31083-118">*Son*</span><span class="sxs-lookup"><span data-stu-id="31083-118">*finish*</span></span>

<span data-ttu-id="31083-119">İntegral aralığı ve basit bir sayaç değişkeni bir desen kullandığınızda, her yinelemede 1 sayaç değişkeni artırılacak normal davranış olduğu halde aralık bir atlama değeri içeriyorsa, bu sayaç tarafından atlama değeri bunun yerine artırılır.</span><span class="sxs-lookup"><span data-stu-id="31083-119">When you use integral ranges and a simple counter variable as a pattern, the typical behavior is to increment the counter variable by 1 on each iteration, but if the range includes a skip value, the counter is incremented by the skip value instead.</span></span>

<span data-ttu-id="31083-120">Düzende eşleşen değerleri de gövdesi ifadesinde kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="31083-120">Values matched in the pattern can also be used in the body expression.</span></span>

<span data-ttu-id="31083-121">Aşağıdaki kod örnekleri kullanımını gösteren `for...in` ifade.</span><span class="sxs-lookup"><span data-stu-id="31083-121">The following code examples illustrate the use of the `for...in` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

<span data-ttu-id="31083-122">Çıktı aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="31083-122">The output is as follows.</span></span>

```
1
5
100
450
788
```

<span data-ttu-id="31083-123">Aşağıdaki örnek nasıl bir dizisi üzerinde döngü gerçekleştirmek ve yerine basit bir değişken olarak bir tanımlama grubu düzeni kullanmayı gösterir.</span><span class="sxs-lookup"><span data-stu-id="31083-123">The following example shows how to loop over a sequence, and how to use a tuple pattern instead of a simple variable.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

<span data-ttu-id="31083-124">Çıktı aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="31083-124">The output is as follows.</span></span>

```
1 squared is 1
2 squared is 4
3 squared is 9
4 squared is 16
5 squared is 25
6 squared is 36
7 squared is 49
8 squared is 64
9 squared is 81
10 squared is 100
```

<span data-ttu-id="31083-125">Aşağıdaki örnek, bir basit tamsayı aralığında döngü gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="31083-125">The following example shows how to loop over a simple integer range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

<span data-ttu-id="31083-126">İşlev1 çıktısı aşağıdaki gibidir.</span><span class="sxs-lookup"><span data-stu-id="31083-126">The output of function1 is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
```

<span data-ttu-id="31083-127">Aşağıdaki örnek, her bir öğe aralığı içeren bir atlama 2 ' nin bir aralık boyunca döngüye gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="31083-127">The following example shows how to loop over a range with a skip of 2, which includes every other element of the range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

<span data-ttu-id="31083-128">Çıkışı `function2` gibidir.</span><span class="sxs-lookup"><span data-stu-id="31083-128">The output of `function2` is as follows.</span></span>

```
1 3 5 7 9
```

<span data-ttu-id="31083-129">Aşağıdaki örnek, bir karakter aralığı kullanma işlemini gösterir.</span><span class="sxs-lookup"><span data-stu-id="31083-129">The following example shows how to use a character range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

<span data-ttu-id="31083-130">Çıkışı `function3` gibidir.</span><span class="sxs-lookup"><span data-stu-id="31083-130">The output of `function3` is as follows.</span></span>

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

<span data-ttu-id="31083-131">Aşağıdaki örnek, bir geriye doğru yineleme için negatif atlama değeri kullanmayı gösterir.</span><span class="sxs-lookup"><span data-stu-id="31083-131">The following example shows how to use a negative skip value for a reverse iteration.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

<span data-ttu-id="31083-132">Çıkışı `function4` gibidir.</span><span class="sxs-lookup"><span data-stu-id="31083-132">The output of `function4` is as follows.</span></span>

```
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

<span data-ttu-id="31083-133">Başlangıç ve bitiş aralığı gibi işlevler, aşağıdaki kodda gösterildiği gibi ifadeler de olabilir.</span><span class="sxs-lookup"><span data-stu-id="31083-133">The beginning and ending of the range can also be expressions, such as functions, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

<span data-ttu-id="31083-134">Çıkışı `function5` bu girişle aşağıdaki gibidir.</span><span class="sxs-lookup"><span data-stu-id="31083-134">The output of `function5` with this input is as follows.</span></span>

```
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

<span data-ttu-id="31083-135">Sonraki örnek, bir joker karakter kullanımını gösterir (\_) ne zaman öğesi gerekli değildir döngüde.</span><span class="sxs-lookup"><span data-stu-id="31083-135">The next example shows the use of a wildcard character (\_) when the element is not needed in the loop.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

<span data-ttu-id="31083-136">Çıktı aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="31083-136">The output is as follows.</span></span>

```
Number of elements in list1: 5
```

<span data-ttu-id="31083-137">`Note` Kullanabileceğiniz `for...in` sequence ifadeleri ve diğer hesaplama ifadeleri, özelleştirilmiş bir sürümünü durumda `for...in` ifade kullanılır.</span><span class="sxs-lookup"><span data-stu-id="31083-137">`Note` You can use `for...in` in sequence expressions and other computation expressions, in which case a customized version of the `for...in` expression is used.</span></span> <span data-ttu-id="31083-138">Daha fazla bilgi için [dizileri](sequences.md), [zaman uyumsuz iş akışları](asynchronous-workflows.md), ve [hesaplama ifadeleri](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="31083-138">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="31083-139">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="31083-139">See also</span></span>

- [<span data-ttu-id="31083-140">F# Dili Başvurusu</span><span class="sxs-lookup"><span data-stu-id="31083-140">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="31083-141">Döngüler: `for...to` İfade</span><span class="sxs-lookup"><span data-stu-id="31083-141">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
- [<span data-ttu-id="31083-142">Döngüler: `while...do` İfade</span><span class="sxs-lookup"><span data-stu-id="31083-142">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
