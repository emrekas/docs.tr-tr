---
title: 'Özel durumlar: Try... with ifadesi'
description: Nasıl kullanacağınızı öğrenin F# 'ile özel durum işleme için ifade try...'.
ms.date: 05/16/2016
ms.openlocfilehash: 742e0b595525c69b83a55682c3c8b9b650326ac7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945553"
---
# <a name="exceptions-the-trywith-expression"></a><span data-ttu-id="e1d16-103">Özel durumlar: Try... with ifadesi</span><span class="sxs-lookup"><span data-stu-id="e1d16-103">Exceptions: The try...with Expression</span></span>

<span data-ttu-id="e1d16-104">Bu konu başlığı altında açıklanır `try...with` ifade, özel durum işleme için kullanılan ifade F# dili.</span><span class="sxs-lookup"><span data-stu-id="e1d16-104">This topic describes the `try...with` expression, the expression that is used for exception handling in the F# language.</span></span>

## <a name="syntax"></a><span data-ttu-id="e1d16-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="e1d16-105">Syntax</span></span>

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a><span data-ttu-id="e1d16-106">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e1d16-106">Remarks</span></span>

<span data-ttu-id="e1d16-107">`try...with` Özel durumları işlemek için kullanılan ifade F#.</span><span class="sxs-lookup"><span data-stu-id="e1d16-107">The `try...with` expression is used to handle exceptions in F#.</span></span> <span data-ttu-id="e1d16-108">Benzer `try...catch` C# deyimi.</span><span class="sxs-lookup"><span data-stu-id="e1d16-108">It is similar to the `try...catch` statement in C#.</span></span> <span data-ttu-id="e1d16-109">Önceki sözdiziminde, kodda *İfade1* bir özel durum oluşturabilir.</span><span class="sxs-lookup"><span data-stu-id="e1d16-109">In the preceding syntax, the code in *expression1* might generate an exception.</span></span> <span data-ttu-id="e1d16-110">`try...with` İfade bir değer döndürür.</span><span class="sxs-lookup"><span data-stu-id="e1d16-110">The `try...with` expression returns a value.</span></span> <span data-ttu-id="e1d16-111">Hiçbir özel durum oluşturulursa, ifadenin değerini döndürür. *İfade1*.</span><span class="sxs-lookup"><span data-stu-id="e1d16-111">If no exception is thrown, the whole expression returns the value of *expression1*.</span></span> <span data-ttu-id="e1d16-112">Bir özel durum oluşur, her *deseni* sırayla karşılık gelen ilk eşleşen deseni yanı sıra, özel durum ile karşılaştırıldığında *ifade*olarak bilinen *özel durum işleyicisi*, o dalı çalıştırılır ve genel ifade, özel durum işleyicisinde ifadenin değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="e1d16-112">If an exception is thrown, each *pattern* is compared in turn with the exception, and for the first matching pattern, the corresponding *expression*, known as the *exception handler*, for that branch is executed, and the overall expression returns the value of the expression in that exception handler.</span></span> <span data-ttu-id="e1d16-113">Herhangi bir desen eşleşirse, eşleşen bir işleyici bulunana kadar özel durum çağrı yığınına yayar.</span><span class="sxs-lookup"><span data-stu-id="e1d16-113">If no pattern matches, the exception propagates up the call stack until a matching handler is found.</span></span> <span data-ttu-id="e1d16-114">Özel durum işleyicileri her ifadesinden döndürülen değerlerin türleri ifade öğesinden döndürülen tür eşleşmelidir `try` blok.</span><span class="sxs-lookup"><span data-stu-id="e1d16-114">The types of the values returned from each expression in the exception handlers must match the type returned from the expression in the `try` block.</span></span>

<span data-ttu-id="e1d16-115">Sık sık hatayla ayrıca oluştu her özel durum işleyicisi ifadelerinde döndürüldüğü geçerli bir değer yoktur anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="e1d16-115">Frequently, the fact that an error occurred also means that there is no valid value that can be returned from the expressions in each exception handler.</span></span> <span data-ttu-id="e1d16-116">Bir seçenek türünde ifade türüne sahip sık kullanılan bir desendir.</span><span class="sxs-lookup"><span data-stu-id="e1d16-116">A frequent pattern is to have the type of the expression be an option type.</span></span> <span data-ttu-id="e1d16-117">Aşağıdaki kod örneği, bu deseni gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="e1d16-117">The following code example illustrates this pattern.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

<span data-ttu-id="e1d16-118">Özel durumlar, .NET özel durumları olabilir veya olabilir F# özel durumlar.</span><span class="sxs-lookup"><span data-stu-id="e1d16-118">Exceptions can be .NET exceptions, or they can be F# exceptions.</span></span> <span data-ttu-id="e1d16-119">Tanımlayabileceğiniz F# kullanarak özel durumları `exception` anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="e1d16-119">You can define F# exceptions by using the `exception` keyword.</span></span>

<span data-ttu-id="e1d16-120">Özel durum türü ve diğer koşulları filtrelemek için desenler çeşitli kullanabilirsiniz; Seçenekler aşağıdaki tabloda özetlenmiştir.</span><span class="sxs-lookup"><span data-stu-id="e1d16-120">You can use a variety of patterns to filter on the exception type and other conditions; the options are summarized in the following table.</span></span>

|<span data-ttu-id="e1d16-121">Desen</span><span class="sxs-lookup"><span data-stu-id="e1d16-121">Pattern</span></span>|<span data-ttu-id="e1d16-122">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e1d16-122">Description</span></span>|
|-------|-----------|
|<span data-ttu-id="e1d16-123">:?</span><span class="sxs-lookup"><span data-stu-id="e1d16-123">:?</span></span> <span data-ttu-id="e1d16-124">*özel durum türü*</span><span class="sxs-lookup"><span data-stu-id="e1d16-124">*exception-type*</span></span>|<span data-ttu-id="e1d16-125">Belirtilen .NET özel durum türüyle eşleşen.</span><span class="sxs-lookup"><span data-stu-id="e1d16-125">Matches the specified .NET exception type.</span></span>|
|<span data-ttu-id="e1d16-126">:?</span><span class="sxs-lookup"><span data-stu-id="e1d16-126">:?</span></span> <span data-ttu-id="e1d16-127">*özel durum türü* olarak *tanımlayıcısı*</span><span class="sxs-lookup"><span data-stu-id="e1d16-127">*exception-type* as *identifier*</span></span>|<span data-ttu-id="e1d16-128">Belirtilen .NET özel durum türüyle eşleşen, ancak özel durum adlandırılmış bir değer sağlar.</span><span class="sxs-lookup"><span data-stu-id="e1d16-128">Matches the specified .NET exception type, but gives the exception a named value.</span></span>|
|<span data-ttu-id="e1d16-129">*özel durum adı*(*bağımsız değişkenleri*)</span><span class="sxs-lookup"><span data-stu-id="e1d16-129">*exception-name*(*arguments*)</span></span>|<span data-ttu-id="e1d16-130">Eşleşen bir F# özel durum türünü ve bağımsız değişkenler bağlar.</span><span class="sxs-lookup"><span data-stu-id="e1d16-130">Matches an F# exception type and binds the arguments.</span></span>|
|<span data-ttu-id="e1d16-131">*tanımlayıcı*</span><span class="sxs-lookup"><span data-stu-id="e1d16-131">*identifier*</span></span>|<span data-ttu-id="e1d16-132">Herhangi bir özel durum ile eşleşen ve adı özel durum nesnesine bağlar.</span><span class="sxs-lookup"><span data-stu-id="e1d16-132">Matches any exception and binds the name to the exception object.</span></span> <span data-ttu-id="e1d16-133">Eşdeğer **:? System.Exception olarak**_tanımlayıcısı_</span><span class="sxs-lookup"><span data-stu-id="e1d16-133">Equivalent to **:? System.Exception as**_identifier_</span></span>|
|<span data-ttu-id="e1d16-134">*tanımlayıcı* olduğunda *koşulu*</span><span class="sxs-lookup"><span data-stu-id="e1d16-134">*identifier* when *condition*</span></span>|<span data-ttu-id="e1d16-135">Koşul true ise bir özel durumla eşleşir.</span><span class="sxs-lookup"><span data-stu-id="e1d16-135">Matches any exception if the condition is true.</span></span>|

## <a name="examples"></a><span data-ttu-id="e1d16-136">Örnekler</span><span class="sxs-lookup"><span data-stu-id="e1d16-136">Examples</span></span>

<span data-ttu-id="e1d16-137">Aşağıdaki kod örnekleri, çeşitli özel durum işleyicisi desenlerinin kullanımını gösterir.</span><span class="sxs-lookup"><span data-stu-id="e1d16-137">The following code examples illustrate the use of the various exception handler patterns.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]

> [!NOTE]
> <span data-ttu-id="e1d16-138">`try...with` Yapıdır ayrı bir ifadeden `try...finally` ifade.</span><span class="sxs-lookup"><span data-stu-id="e1d16-138">The `try...with` construct is a separate expression from the `try...finally` expression.</span></span> <span data-ttu-id="e1d16-139">Bu nedenle, kodunuzu hem gerektiriyorsa bir `with` blok ve `finally` bloğu iki ifadelerini iç içe gerekecektir.</span><span class="sxs-lookup"><span data-stu-id="e1d16-139">Therefore, if your code requires both a `with` block and a `finally` block, you will have to nest the two expressions.</span></span>

> [!NOTE]
> <span data-ttu-id="e1d16-140">Kullanabileceğiniz `try...with` içinde zaman uyumsuz iş akışları ve özelleştirilmiş sürümü durumda diğer hesaplama ifadeleri, hangi `try...with` ifade kullanılır.</span><span class="sxs-lookup"><span data-stu-id="e1d16-140">You can use `try...with` in asynchronous workflows and other computation expressions, in which case a customized version of the `try...with` expression is used.</span></span> <span data-ttu-id="e1d16-141">Daha fazla bilgi için [zaman uyumsuz iş akışları](../asynchronous-workflows.md), ve [hesaplama ifadeleri](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="e1d16-141">For more information, see [Asynchronous Workflows](../asynchronous-workflows.md), and [Computation Expressions](../computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e1d16-142">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="e1d16-142">See also</span></span>

- [<span data-ttu-id="e1d16-143">Özel Durum İşleme</span><span class="sxs-lookup"><span data-stu-id="e1d16-143">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="e1d16-144">Özel Durum Türleri</span><span class="sxs-lookup"><span data-stu-id="e1d16-144">Exception Types</span></span>](exception-types.md)
- [<span data-ttu-id="e1d16-145">Özel Durumlar: `try...finally` İfadesi</span><span class="sxs-lookup"><span data-stu-id="e1d16-145">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)