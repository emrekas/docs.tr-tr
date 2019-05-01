---
title: 'Döngüler: for...to İfadesi'
description: Bkz. nasıl F# for... ifade bir döngüde bir dizi bir döngü değişkeninin değerleri üzerinden yinelemek için kullanılır.
ms.date: 05/16/2016
ms.openlocfilehash: 041e98fa4bcc140aa3cd699f6ed35bf52c8b4175
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904039"
---
# <a name="loops-forto-expression"></a><span data-ttu-id="d7566-103">Döngüler: for...to İfadesi</span><span class="sxs-lookup"><span data-stu-id="d7566-103">Loops: for...to Expression</span></span>

<span data-ttu-id="d7566-104">`for...to` İfadesi, bir dizi bir döngü değişkeninin değerleri üzerinden bir döngü içinde yineleme için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="d7566-104">The `for...to` expression is used to iterate in a loop over a range of values of a loop variable.</span></span>

## <a name="syntax"></a><span data-ttu-id="d7566-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="d7566-105">Syntax</span></span>

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="d7566-106">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d7566-106">Remarks</span></span>

<span data-ttu-id="d7566-107">Tanımlayıcı türü türünden çıkarılan *Başlat* ve *son* ifadeler.</span><span class="sxs-lookup"><span data-stu-id="d7566-107">The type of the identifier is inferred from the type of the *start* and *finish* expressions.</span></span> <span data-ttu-id="d7566-108">Bu ifadeler için türler, 32 bit tamsayılar olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="d7566-108">Types for these expressions must be 32-bit integers.</span></span>

<span data-ttu-id="d7566-109">Teknik olarak bir ifade rağmen `for...to` daha geleneksel bir kesinlik temelli bir programlama dili deyiminde gibi.</span><span class="sxs-lookup"><span data-stu-id="d7566-109">Although technically an expression, `for...to` is more like a traditional statement in an imperative programming language.</span></span> <span data-ttu-id="d7566-110">İçin dönüş türü *gövde ifadesi* olmalıdır `unit`.</span><span class="sxs-lookup"><span data-stu-id="d7566-110">The return type for the *body-expression* must be `unit`.</span></span> <span data-ttu-id="d7566-111">Aşağıdaki örnekler çeşitli kullanımları `for...to` ifade.</span><span class="sxs-lookup"><span data-stu-id="d7566-111">The following examples show various uses of the `for...to` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

<span data-ttu-id="d7566-112">Önceki kodun çıktısı aşağıdaki gibidir.</span><span class="sxs-lookup"><span data-stu-id="d7566-112">The output of the previous code is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a><span data-ttu-id="d7566-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d7566-113">See also</span></span>

- [<span data-ttu-id="d7566-114">F# Dili Başvurusu</span><span class="sxs-lookup"><span data-stu-id="d7566-114">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="d7566-115">Döngüler: `for...in` İfade</span><span class="sxs-lookup"><span data-stu-id="d7566-115">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="d7566-116">Döngüler: `while...do` İfade</span><span class="sxs-lookup"><span data-stu-id="d7566-116">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)