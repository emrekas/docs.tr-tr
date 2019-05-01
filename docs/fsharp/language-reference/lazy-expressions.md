---
title: Yavaş ifadeler
description: Bilgi nasıl F# yavaş ifadeler, uygulamaları ve kitaplıkları performansını artırabilir.
ms.date: 03/13/2019
ms.openlocfilehash: 6d53d53093f4e93f53e1c956b94e2f1e4a1bbd55
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904117"
---
# <a name="lazy-expressions"></a><span data-ttu-id="b63ba-103">Yavaş ifadeler</span><span class="sxs-lookup"><span data-stu-id="b63ba-103">Lazy Expressions</span></span>

<span data-ttu-id="b63ba-104">*Yavaş ifadeler* hemen değerlendirilmeyen, ancak bunun yerine sonucu gerektiğinde değerlendirilir ifadeler.</span><span class="sxs-lookup"><span data-stu-id="b63ba-104">*Lazy expressions* are expressions that are not evaluated immediately, but are instead evaluated when the result is needed.</span></span> <span data-ttu-id="b63ba-105">Bu, kodunuzun performansını artırmak için yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="b63ba-105">This can help to improve the performance of your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="b63ba-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="b63ba-106">Syntax</span></span>

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a><span data-ttu-id="b63ba-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="b63ba-107">Remarks</span></span>

<span data-ttu-id="b63ba-108">Önceki sözdiziminde, *ifade* kod, yalnızca bir sonuç gerekli olduğunda değerlendirilir ve *tanımlayıcı* sonucu depolayan bir değerdir.</span><span class="sxs-lookup"><span data-stu-id="b63ba-108">In the previous syntax, *expression* is code that is evaluated only when a result is required, and *identifier* is a value that stores the result.</span></span> <span data-ttu-id="b63ba-109">Değer türünde [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), burada gerçek türü için kullanılan `'T` ifadenin sonuç belirlenir.</span><span class="sxs-lookup"><span data-stu-id="b63ba-109">The value is of type [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), where the actual type that is used for `'T` is determined from the result of the expression.</span></span>

<span data-ttu-id="b63ba-110">Yavaş ifadeler bir ifade içinde bir sonuç gereken durumlar için yürütme kısıtlayarak performansını artırmak etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="b63ba-110">Lazy expressions enable you to improve performance by restricting the execution of an expressions to only those situations in which a result is needed.</span></span>

<span data-ttu-id="b63ba-111">Gerçekleştirilecek ifadeleri zorlamak için yöntemi çağırın. `Force`.</span><span class="sxs-lookup"><span data-stu-id="b63ba-111">To force the expressions to be performed, you call the method `Force`.</span></span> <span data-ttu-id="b63ba-112">`Force` yalnızca bir kez gerçekleştirilmek üzere yürütülmesine neden olur.</span><span class="sxs-lookup"><span data-stu-id="b63ba-112">`Force` causes the execution to be performed only one time.</span></span> <span data-ttu-id="b63ba-113">Yapılan sonraki çağrılar `Force` aynı sonucu, ancak herhangi bir kod Yürütülmeyen döndürür.</span><span class="sxs-lookup"><span data-stu-id="b63ba-113">Subsequent calls to `Force` return the same result, but do not execute any code.</span></span>

<span data-ttu-id="b63ba-114">Aşağıdaki kod yavaş ifadeler kullanımını ve kullanımını göstermektedir `Force`.</span><span class="sxs-lookup"><span data-stu-id="b63ba-114">The following code illustrates the use of lazy expressions and the use of `Force`.</span></span> <span data-ttu-id="b63ba-115">Bu kodda, türü `result` olduğu `Lazy<int>`ve `Force` yöntemi döndürür bir `int`.</span><span class="sxs-lookup"><span data-stu-id="b63ba-115">In this code, the type of `result` is `Lazy<int>`, and the `Force` method returns an `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

<span data-ttu-id="b63ba-116">Geç değerlendirme, ama `Lazy` yazın, sıraları için de kullanılır.</span><span class="sxs-lookup"><span data-stu-id="b63ba-116">Lazy evaluation, but not the `Lazy` type, is also used for sequences.</span></span> <span data-ttu-id="b63ba-117">Daha fazla bilgi için [dizileri](sequences.md).</span><span class="sxs-lookup"><span data-stu-id="b63ba-117">For more information, see [Sequences](sequences.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b63ba-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="b63ba-118">See also</span></span>

- [<span data-ttu-id="b63ba-119">F# Dili Başvurusu</span><span class="sxs-lookup"><span data-stu-id="b63ba-119">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="b63ba-120">LazyExtensions Modülü</span><span class="sxs-lookup"><span data-stu-id="b63ba-120">LazyExtensions module</span></span>](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
