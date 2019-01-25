---
title: -İşaretçilerde aritmetik işlemler C# Programlama Kılavuzu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], arithmetic operations
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
ms.openlocfilehash: b0b75a6aa47cfc169157b229c4386ed7dc1e627b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710202"
---
# <a name="arithmetic-operations-on-pointers-c-programming-guide"></a><span data-ttu-id="1c7a6-102">İşaretçilerde aritmetik işlemler (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="1c7a6-102">Arithmetic operations on pointers (C# Programming Guide)</span></span>
<span data-ttu-id="1c7a6-103">Aritmetik işleçler kullanarak bu konuda ele alınmıştır `+` ve `-` işaretçileri işlemek için.</span><span class="sxs-lookup"><span data-stu-id="1c7a6-103">This topic discusses using the arithmetic operators `+` and `-` to manipulate pointers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c7a6-104">Tüm void işaretçilerde aritmetik işlemler gerçekleştirilemiyor.</span><span class="sxs-lookup"><span data-stu-id="1c7a6-104">You cannot perform any arithmetic operations on void pointers.</span></span>  
  
## <a name="adding-and-subtracting-numeric-values-to-or-from-pointers"></a><span data-ttu-id="1c7a6-105">Ekleme ve çıkarma işaretçileri gelen veya sayısal değerler</span><span class="sxs-lookup"><span data-stu-id="1c7a6-105">Adding and subtracting numeric values to or from pointers</span></span>  
 <span data-ttu-id="1c7a6-106">Bir değer eklediğiniz `n` türü [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [uzun](../../../csharp/language-reference/keywords/long.md), veya [ulong](../../../csharp/language-reference/keywords/ulong.md) işaretçisi.</span><span class="sxs-lookup"><span data-stu-id="1c7a6-106">You can add a value `n` of type [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), or [ulong](../../../csharp/language-reference/keywords/ulong.md) to a pointer.</span></span> <span data-ttu-id="1c7a6-107">Varsa `p` bir işaretçi türü `pointer-type*`, sonuç `p+n` eklemesini elde edilen işaretçi `n * sizeof(pointer-type)` adresine `p`.</span><span class="sxs-lookup"><span data-stu-id="1c7a6-107">If `p` is a pointer of the type `pointer-type*`, the result `p+n` is the pointer resulting from adding `n * sizeof(pointer-type)` to the address of `p`.</span></span> <span data-ttu-id="1c7a6-108">Benzer şekilde, `p-n` arasındaki çıkarma işleminin sonucu işaretçi `n * sizeof(pointer-type)` adresinden `p`.</span><span class="sxs-lookup"><span data-stu-id="1c7a6-108">Similarly, `p-n` is the pointer resulting from subtracting `n * sizeof(pointer-type)` from the address of `p`.</span></span>  
  
## <a name="subtracting-pointers"></a><span data-ttu-id="1c7a6-109">Çıkarma işaretçileri</span><span class="sxs-lookup"><span data-stu-id="1c7a6-109">Subtracting pointers</span></span>  
 <span data-ttu-id="1c7a6-110">Ayrıca, aynı türde işaretçileri çıkarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1c7a6-110">You can also subtract pointers of the same type.</span></span> <span data-ttu-id="1c7a6-111">Sonucu her zaman türüdür `long`.</span><span class="sxs-lookup"><span data-stu-id="1c7a6-111">The result is always of the type `long`.</span></span> <span data-ttu-id="1c7a6-112">Örneğin, varsa `p1` ve `p2` türünde işaretçiler `pointer-type*`, ifade `p1-p2` sonuçlanır:</span><span class="sxs-lookup"><span data-stu-id="1c7a6-112">For example, if `p1` and `p2` are pointers of the type `pointer-type*`, then the expression `p1-p2` results in:</span></span>  
  
 `((long)p1 - (long)p2)/sizeof(pointer-type)`  
  
 <span data-ttu-id="1c7a6-113">Hiçbir özel durum, etki alanı işaretçinin aritmetik işlemi taşıyor ve sonuç uygulamasının bağlıdır, üretilir.</span><span class="sxs-lookup"><span data-stu-id="1c7a6-113">No exceptions are generated when the arithmetic operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c7a6-114">Örnek</span><span class="sxs-lookup"><span data-stu-id="1c7a6-114">Example</span></span>  
 [!code-csharp[csProgGuidePointers#14](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#15](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="1c7a6-115">C# dili belirtimi</span><span class="sxs-lookup"><span data-stu-id="1c7a6-115">C# language specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1c7a6-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="1c7a6-116">See also</span></span>

- [<span data-ttu-id="1c7a6-117">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="1c7a6-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="1c7a6-118">Güvenli Olmayan Kod ve İşaretçiler</span><span class="sxs-lookup"><span data-stu-id="1c7a6-118">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="1c7a6-119">İşaretçi İfadeleri</span><span class="sxs-lookup"><span data-stu-id="1c7a6-119">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="1c7a6-120">C# İşleçleri</span><span class="sxs-lookup"><span data-stu-id="1c7a6-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
- [<span data-ttu-id="1c7a6-121">İşaretçileri İşleme</span><span class="sxs-lookup"><span data-stu-id="1c7a6-121">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)
- [<span data-ttu-id="1c7a6-122">İşaretçi türleri</span><span class="sxs-lookup"><span data-stu-id="1c7a6-122">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="1c7a6-123">Türler</span><span class="sxs-lookup"><span data-stu-id="1c7a6-123">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="1c7a6-124">unsafe</span><span class="sxs-lookup"><span data-stu-id="1c7a6-124">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="1c7a6-125">fixed Deyimi</span><span class="sxs-lookup"><span data-stu-id="1c7a6-125">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="1c7a6-126">stackalloc</span><span class="sxs-lookup"><span data-stu-id="1c7a6-126">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
