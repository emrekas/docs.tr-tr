---
title: 'Özel Durumlar: raise İşlevi'
description: Bilgi nasıl F# 'raise' işlevi, bir hata veya olağanüstü bir koşul oluştu belirtmek için kullanılır.
ms.date: 05/16/2016
ms.openlocfilehash: 9e2515ad7b85c1025bc3aa0aa2a6929a8d35436d
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641960"
---
# <a name="exceptions-the-raise-function"></a><span data-ttu-id="79871-103">Özel Durumlar: raise İşlevi</span><span class="sxs-lookup"><span data-stu-id="79871-103">Exceptions: the raise Function</span></span>

<span data-ttu-id="79871-104">`raise` İşlevi, bir hata veya olağanüstü bir koşul oluştu belirtmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="79871-104">The `raise` function is used to indicate that an error or exceptional condition has occurred.</span></span> <span data-ttu-id="79871-105">Hata hakkındaki bilgileri, bir özel durum nesnesine yakalanır.</span><span class="sxs-lookup"><span data-stu-id="79871-105">Information about the error is captured in an exception object.</span></span>

## <a name="syntax"></a><span data-ttu-id="79871-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="79871-106">Syntax</span></span>

```fsharp
raise (expression)
```

## <a name="remarks"></a><span data-ttu-id="79871-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="79871-107">Remarks</span></span>

<span data-ttu-id="79871-108">`raise` İşlev bir özel durum nesnesi oluşturur ve bir yığın geriye doğru işlem başlatır.</span><span class="sxs-lookup"><span data-stu-id="79871-108">The `raise` function generates an exception object and initiates a stack unwinding process.</span></span> <span data-ttu-id="79871-109">Diğer bir .NET dilinde olduğu gibi bu işlemin davranışını aynı olacak şekilde yığın geriye doğru işlem ortak dil çalışma (CLR) tarafından yönetilir.</span><span class="sxs-lookup"><span data-stu-id="79871-109">The stack unwinding process is managed by the common language runtime (CLR), so the behavior of this process is the same as it is in any other .NET language.</span></span> <span data-ttu-id="79871-110">Yığın geriye doğru işlem oluşturulan özel durum ile eşleşen bir özel durum işleyici için bir aramadır.</span><span class="sxs-lookup"><span data-stu-id="79871-110">The stack unwinding process is a search for an exception handler that matches the generated exception.</span></span> <span data-ttu-id="79871-111">Geçerli aramayı başlatır `try...with` varsa ifade.</span><span class="sxs-lookup"><span data-stu-id="79871-111">The search starts in the current `try...with` expression, if there is one.</span></span> <span data-ttu-id="79871-112">Her desende `with` blok seçiliyse, sırasıyla.</span><span class="sxs-lookup"><span data-stu-id="79871-112">Each pattern in the `with` block is checked, in order.</span></span> <span data-ttu-id="79871-113">Eşleşen bir özel durum işleyici bulunduğunda, özel durumu işlenmiş olarak değerlendirilir. Aksi takdirde, yığın geriye doğru çözülür ve `with` çağrı zincirine'kurmak blokları eşleşen bir işleyici bulunana kadar denetlenir.</span><span class="sxs-lookup"><span data-stu-id="79871-113">When a matching exception handler is found, the exception is considered handled; otherwise, the stack is unwound and `with` blocks up the call chain are checked until a matching handler is found.</span></span> <span data-ttu-id="79871-114">Tüm `finally` gibi yığın geriye doğru alır ve çağrı zincirine karşılaşılan blokları sırayla da çalıştırılır.</span><span class="sxs-lookup"><span data-stu-id="79871-114">Any `finally` blocks that are encountered in the call chain are also executed in sequence as the stack unwinds.</span></span>

<span data-ttu-id="79871-115">`raise` İşlev, denk `throw` C# veya C++.</span><span class="sxs-lookup"><span data-stu-id="79871-115">The `raise` function is the equivalent of `throw` in C# or C++.</span></span> <span data-ttu-id="79871-116">Kullanım `reraise` aynı özel durum çağrı zincirine'kurmak yayılması bir catch işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="79871-116">Use `reraise` in a catch handler to propagate the same exception up the call chain.</span></span>

<span data-ttu-id="79871-117">Aşağıdaki kod örnekleri kullanımını gösteren `raise` işlev bir özel durum oluşturur.</span><span class="sxs-lookup"><span data-stu-id="79871-117">The following code examples illustrate the use of the `raise` function to generate an exception.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

<span data-ttu-id="79871-118">`raise` İşlevi de kullanılabilir .NET özel durumları, yükseltmek için aşağıdaki örnekte gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="79871-118">The `raise` function can also be used to raise .NET exceptions, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]

## <a name="see-also"></a><span data-ttu-id="79871-119">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="79871-119">See also</span></span>

- [<span data-ttu-id="79871-120">Özel Durum İşleme</span><span class="sxs-lookup"><span data-stu-id="79871-120">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="79871-121">Özel Durum Türleri</span><span class="sxs-lookup"><span data-stu-id="79871-121">Exception Types</span></span>](exception-types.md)
- [<span data-ttu-id="79871-122">Özel Durumlar: `try...with` İfadesi</span><span class="sxs-lookup"><span data-stu-id="79871-122">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
- [<span data-ttu-id="79871-123">Özel Durumlar: `try...finally` İfadesi</span><span class="sxs-lookup"><span data-stu-id="79871-123">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
- [<span data-ttu-id="79871-124">Özel Durumlar: `failwith` İşlevi</span><span class="sxs-lookup"><span data-stu-id="79871-124">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)
- [<span data-ttu-id="79871-125">Özel Durumlar: `invalidArg` İşlevi</span><span class="sxs-lookup"><span data-stu-id="79871-125">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)
