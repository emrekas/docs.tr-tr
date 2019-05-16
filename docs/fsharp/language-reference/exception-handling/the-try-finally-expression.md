---
title: 'Özel durumlar: Try... finally ifadesi'
description: Bilgi nasıl F# ' try... finally' ifadesi, bir kod bloğu bir özel durum oluşturursa bile temizleme kodu yürütme olanak tanır.
ms.date: 05/16/2016
ms.openlocfilehash: d246bce52b5f30d5e8d7e3c36e9f7d7c48627913
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645460"
---
# <a name="exceptions-the-tryfinally-expression"></a><span data-ttu-id="9cce7-103">Özel durumlar: Try... finally ifadesi</span><span class="sxs-lookup"><span data-stu-id="9cce7-103">Exceptions: The try...finally Expression</span></span>

<span data-ttu-id="9cce7-104">`try...finally` İfade bir kod bloğu bir özel durum oluşturursa bile temizleme kodu yürütme olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="9cce7-104">The `try...finally` expression enables you to execute clean-up code even if a block of code throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="9cce7-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="9cce7-105">Syntax</span></span>

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a><span data-ttu-id="9cce7-106">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="9cce7-106">Remarks</span></span>

<span data-ttu-id="9cce7-107">`try...finally` İfade, kodda yürütülecek kullanılabilir *expression2* yürütülmesi sırasında bir özel durum olup oluşturulan bağımsız olarak yukarıdaki söz diziminde *İfade1*.</span><span class="sxs-lookup"><span data-stu-id="9cce7-107">The `try...finally` expression can be used to execute the code in *expression2* in the preceding syntax regardless of whether an exception is generated during the execution of *expression1*.</span></span>

<span data-ttu-id="9cce7-108">Türünü *expression2* tüm ifadenin değerine katılmadığı bir özel durum oluşmaz, döndürülen tür son değer *İfade1*.</span><span class="sxs-lookup"><span data-stu-id="9cce7-108">The type of *expression2* does not contribute to the value of the whole expression; the type returned when an exception does not occur is the last value in *expression1*.</span></span> <span data-ttu-id="9cce7-109">Bir özel durum oluştuğunda hiçbir değer döndürülmez ve çağrı yığınına sonraki eşleşen özel durum işleyicisine denetim akışını aktarır.</span><span class="sxs-lookup"><span data-stu-id="9cce7-109">When an exception does occur, no value is returned and the flow of control transfers to the next matching exception handler up the call stack.</span></span> <span data-ttu-id="9cce7-110">Hiçbir özel durum işleyicisi bulunursa, program sona erer.</span><span class="sxs-lookup"><span data-stu-id="9cce7-110">If no exception handler is found, the program terminates.</span></span> <span data-ttu-id="9cce7-111">Eşleşen bir işleyici içinde kod yürütülür veya program sona erer, kodda önce `finally` dal yürütülür.</span><span class="sxs-lookup"><span data-stu-id="9cce7-111">Before the code in a matching handler is executed or the program terminates, the code in the `finally` branch is executed.</span></span>

<span data-ttu-id="9cce7-112">Aşağıdaki kod kullanımını gösterir `try...finally` ifade.</span><span class="sxs-lookup"><span data-stu-id="9cce7-112">The following code demonstrates the use of the `try...finally` expression.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

<span data-ttu-id="9cce7-113">Konsola çıktı aşağıdaki gibidir.</span><span class="sxs-lookup"><span data-stu-id="9cce7-113">The output to the console is as follows.</span></span>

```
Closing stream
Exception handled.
```

<span data-ttu-id="9cce7-114">Dıştaki özel durum işlenmiş önce çıktısı görebileceğiniz gibi akış kapatıldı ve dosya `test.txt` metni içeren `test1`, arabellek Temizlenen ve özel durum aktarılan olsa bile diske yazılan gösterir dıştaki özel durum işleyicisine denetler.</span><span class="sxs-lookup"><span data-stu-id="9cce7-114">As you can see from the output, the stream was closed before the outer exception was handled, and the file `test.txt` contains the text `test1`, which indicates that the buffers were flushed and written to disk even though the exception transferred control to the outer exception handler.</span></span>

<span data-ttu-id="9cce7-115">Unutmayın `try...with` yapıdır öğesinden ayrı bir yapısı `try...finally` oluşturun.</span><span class="sxs-lookup"><span data-stu-id="9cce7-115">Note that the `try...with` construct is a separate construct from the `try...finally` construct.</span></span> <span data-ttu-id="9cce7-116">Bu nedenle, kodunuzu hem gerektiriyorsa bir `with` blok ve `finally` blok, aşağıdaki kod örneğinde olduğu gibi iki yapılarını iç içe zorunda.</span><span class="sxs-lookup"><span data-stu-id="9cce7-116">Therefore, if your code requires both a `with` block and a `finally` block, you have to nest the two constructs, as in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

<span data-ttu-id="9cce7-117">Hesaplama ifadeleri bağlamında, dizi ifadeleri ve zaman uyumsuz iş akışları dahil olmak üzere **try... finally** ifadeleri, özel bir uygulama olabilir.</span><span class="sxs-lookup"><span data-stu-id="9cce7-117">In the context of computation expressions, including sequence expressions and asynchronous workflows, **try...finally** expressions can have a custom implementation.</span></span> <span data-ttu-id="9cce7-118">Daha fazla bilgi için [hesaplama ifadeleri](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="9cce7-118">For more information, see [Computation Expressions](../computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9cce7-119">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="9cce7-119">See also</span></span>

- [<span data-ttu-id="9cce7-120">Özel Durum İşleme</span><span class="sxs-lookup"><span data-stu-id="9cce7-120">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="9cce7-121">Özel Durumlar: `try...with` İfadesi</span><span class="sxs-lookup"><span data-stu-id="9cce7-121">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
