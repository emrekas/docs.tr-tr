---
title: Satır İçi İşlevler
description: Nasıl kullanacağınızı öğrenin F# satır içi işlevler, doğrudan çağıran kodun içine tümleştirilmiştir.
ms.date: 05/16/2016
ms.openlocfilehash: 12c175e3e46e12d978fe02d3e1fe83142e71a25d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61966601"
---
# <a name="inline-functions"></a><span data-ttu-id="df1ba-103">Satır İçi İşlevler</span><span class="sxs-lookup"><span data-stu-id="df1ba-103">Inline Functions</span></span>

<span data-ttu-id="df1ba-104">*Satır içi işlevleri* doğrudan çağıran kodun içine tümleştirilmiştir işlevlerdir.</span><span class="sxs-lookup"><span data-stu-id="df1ba-104">*Inline functions* are functions that are integrated directly into the calling code.</span></span>

## <a name="using-inline-functions"></a><span data-ttu-id="df1ba-105">Satır içi işlevleri kullanma</span><span class="sxs-lookup"><span data-stu-id="df1ba-105">Using Inline Functions</span></span>

<span data-ttu-id="df1ba-106">Statik tür parametreleri kullandığınızda, tür parametreleri tarafından parametre haline getirilen tüm İşlevler, satır içi olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="df1ba-106">When you use static type parameters, any functions that are parameterized by type parameters must be inline.</span></span> <span data-ttu-id="df1ba-107">Bu, derleyici bu tür parametreleri çözümleyebileceğinden garanti eder.</span><span class="sxs-lookup"><span data-stu-id="df1ba-107">This guarantees that the compiler can resolve these type parameters.</span></span> <span data-ttu-id="df1ba-108">Normal genel tür parametrelerini kullandığınızda, bu tür bir kısıtlama yoktur.</span><span class="sxs-lookup"><span data-stu-id="df1ba-108">When you use ordinary generic type parameters, there is no such restriction.</span></span>

<span data-ttu-id="df1ba-109">Üye kısıtlamaları kullanımını etkinleştirme dışında satır içi işlevler kodu en iyi duruma getirme yararlı olabilir.</span><span class="sxs-lookup"><span data-stu-id="df1ba-109">Other than enabling the use of member constraints, inline functions can be helpful in optimizing code.</span></span> <span data-ttu-id="df1ba-110">Ancak, satır içi işlevlerin aşırı kodunuzu daha az derleyici iyileştirmeleri ve kitaplık işlevleri uygulaması değişikliklere dayanıklı olmasını neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="df1ba-110">However, overuse of inline functions can cause your code to be less resistant to changes in compiler optimizations and the implementation of library functions.</span></span> <span data-ttu-id="df1ba-111">Bu nedenle, tüm iyileştirme teknikleri denediniz mi sürece iyileştirme için satır içi işlevleri kullanarak kaçınmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="df1ba-111">For this reason, you should avoid using inline functions for optimization unless you have tried all other optimization techniques.</span></span> <span data-ttu-id="df1ba-112">Satır içi işlev veya metot yapmak bazen performansı geliştirebilir, ancak bu her zaman böyle değildir.</span><span class="sxs-lookup"><span data-stu-id="df1ba-112">Making a function or method inline can sometimes improve performance, but that is not always the case.</span></span> <span data-ttu-id="df1ba-113">Bu nedenle, herhangi belirli bir işlevi satır içi yapmadan aslında olumlu bir etkiye sahip olduğunu doğrulamak için performans ölçümleri kullanmalısınız.</span><span class="sxs-lookup"><span data-stu-id="df1ba-113">Therefore, you should also use performance measurements to verify that making any given function inline does in fact have a positive effect.</span></span>

<span data-ttu-id="df1ba-114">`inline` Değiştiricisi işlevleri en üst düzeyinde, Modül düzeyinde veya bir sınıftaki yöntemi düzeyinde uygulanabilir.</span><span class="sxs-lookup"><span data-stu-id="df1ba-114">The `inline` modifier can be applied to functions at the top level, at the module level, or at the method level in a class.</span></span>

<span data-ttu-id="df1ba-115">Aşağıdaki kod örneği bir satır içi işlevi en üst düzey, bir satır içi örnek yöntemi ve bir satır içi statik bir yöntemi gösterir.</span><span class="sxs-lookup"><span data-stu-id="df1ba-115">The following code example illustrates an inline function at the top level, an inline instance method, and an inline static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]

## <a name="inline-functions-and-type-inference"></a><span data-ttu-id="df1ba-116">Satır içi işlevleri ve tür çıkarımı</span><span class="sxs-lookup"><span data-stu-id="df1ba-116">Inline Functions and Type Inference</span></span>

<span data-ttu-id="df1ba-117">Varlığını `inline` tür çıkarımı etkiler.</span><span class="sxs-lookup"><span data-stu-id="df1ba-117">The presence of `inline` affects type inference.</span></span> <span data-ttu-id="df1ba-118">Satır içi işlevler statik olarak çözümlenmiş tür parametreleri, ancak satır içi işlevleri kullanılamaz olmasıdır.</span><span class="sxs-lookup"><span data-stu-id="df1ba-118">This is because inline functions can have statically resolved type parameters, whereas non-inline functions cannot.</span></span> <span data-ttu-id="df1ba-119">Aşağıdaki kod örneği bir durumu gösterir. burada `inline` bir statik olarak çözümlenen tür parametresi olan bir işlev kullandığından yararlıdır `float` dönüştürme işleci.</span><span class="sxs-lookup"><span data-stu-id="df1ba-119">The following code example shows a case where `inline` is helpful because you are using a function that has a statically resolved type parameter, the `float` conversion operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

<span data-ttu-id="df1ba-120">Olmadan `inline` değiştiricisi, tür çıkarımı zorlar bu durumda, belirli bir türdeki yararlanmak için işlev `int`.</span><span class="sxs-lookup"><span data-stu-id="df1ba-120">Without the `inline` modifier, type inference forces the function to take a specific type, in this case `int`.</span></span> <span data-ttu-id="df1ba-121">Ancak `inline` statik olarak çözümlenmiş tür parametresi için de değiştiricisi, işlevin çıkarılan.</span><span class="sxs-lookup"><span data-stu-id="df1ba-121">But with the `inline` modifier, the function is also inferred to have a statically resolved type parameter.</span></span> <span data-ttu-id="df1ba-122">İle `inline` aşağıdaki olmasını çıkarılan değiştiricisi, türü:</span><span class="sxs-lookup"><span data-stu-id="df1ba-122">With the `inline` modifier, the type is inferred to be the following:</span></span>

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

<span data-ttu-id="df1ba-123">Bu işlev dönüştürmeyi destekleyen herhangi bir türü kabul eden anlamına gelir **float**.</span><span class="sxs-lookup"><span data-stu-id="df1ba-123">This means that the function accepts any type that supports a conversion to **float**.</span></span>

## <a name="see-also"></a><span data-ttu-id="df1ba-124">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="df1ba-124">See also</span></span>

- [<span data-ttu-id="df1ba-125">İşlevler</span><span class="sxs-lookup"><span data-stu-id="df1ba-125">Functions</span></span>](index.md)
- [<span data-ttu-id="df1ba-126">Kısıtlamalar</span><span class="sxs-lookup"><span data-stu-id="df1ba-126">Constraints</span></span>](../generics/constraints.md)
- [<span data-ttu-id="df1ba-127">Statik Olarak Çözümlenmiş Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="df1ba-127">Statically Resolved Type Parameters</span></span>](../generics/statically-resolved-type-parameters.md)