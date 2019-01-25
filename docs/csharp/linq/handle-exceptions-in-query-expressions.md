---
title: (C# üzerinde LINQ) sorgu ifadelerinde özel durumları işleme
description: C# LINQ Sorgu ifadelerinde özel durumları işleme hakkında bilgi edinin.
ms.date: 12/1/2016
ms.assetid: 2bf0c397-13fb-4f68-bc2b-531c6c88a167
ms.openlocfilehash: e0fa9a20251d3d185448ee386de81d127ae7a42c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564074"
---
# <a name="handle-exceptions-in-query-expressions"></a><span data-ttu-id="65656-103">Sorgu ifadelerinde özel durumları işleme</span><span class="sxs-lookup"><span data-stu-id="65656-103">Handle exceptions in query expressions</span></span>

<span data-ttu-id="65656-104">Sorgu ifadesi bağlamında herhangi bir yöntemi çağırmak mümkündür.</span><span class="sxs-lookup"><span data-stu-id="65656-104">It's possible to call any method in the context of a query expression.</span></span> <span data-ttu-id="65656-105">Ancak, veri kaynağı içeriğini değiştirme ya da bir özel durum gibi bir yan etkisi oluşturabilmeniz için bir sorgu ifadesinde herhangi bir yöntemini çağırmadan kaçınmanızı öneririz.</span><span class="sxs-lookup"><span data-stu-id="65656-105">However, we recommend that you avoid calling any method in a query expression that can create a side effect such as modifying the contents of the data source or throwing an exception.</span></span> <span data-ttu-id="65656-106">Bu örnek, genel özel durum işleme .NET yönergeleri ihlal etmeden sorgu ifadesinde yöntem çağırdığınızda, özel durumlarını oluşturma önlemek gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="65656-106">This example shows how to avoid raising exceptions when you call methods in a query expression without violating the general .NET guidelines on exception handling.</span></span> <span data-ttu-id="65656-107">Kabul edilebilir neden belirli bir bağlamda durum anladığınızda, belirli bir özel durum yakalamak için bu yönergeleri durumu.</span><span class="sxs-lookup"><span data-stu-id="65656-107">Those guidelines state that it's acceptable to catch a specific exception when you understand why it's thrown in a given context.</span></span> <span data-ttu-id="65656-108">Daha fazla bilgi için [özel durumlar için en iyi yöntemler](../../standard/exceptions/best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="65656-108">For more information, see [Best Practices for Exceptions](../../standard/exceptions/best-practices-for-exceptions.md).</span></span>

<span data-ttu-id="65656-109">Son örnek bir sorgu yürütülürken bir özel durum gerekir, bu durumların nasıl işleneceğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="65656-109">The final example shows how to handle those cases when you must throw an exception during execution of a query.</span></span>

## <a name="example"></a><span data-ttu-id="65656-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="65656-110">Example</span></span>

<span data-ttu-id="65656-111">Aşağıdaki örnek, özel durum işleme bir sorgu ifadesinin dışındaki kod taşımak gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="65656-111">The following example shows how to move exception handling code outside a query expression.</span></span> <span data-ttu-id="65656-112">Yalnızca yöntemi sorguya yerel değişkenlerin bağlı olmayan mümkün olur.</span><span class="sxs-lookup"><span data-stu-id="65656-112">This is only possible when the method does not depend on any variables local to the query.</span></span>

[!code-csharp[csProgGuideLINQ#10](~/samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_1.cs)]

## <a name="example"></a><span data-ttu-id="65656-113">Örnek</span><span class="sxs-lookup"><span data-stu-id="65656-113">Example</span></span>

<span data-ttu-id="65656-114">Bazı durumlarda, sorgu yürütme hemen durdurmak için bir sorgu içinde oluşturulan bir özel durum için en iyi yanıtı olabilir.</span><span class="sxs-lookup"><span data-stu-id="65656-114">In some cases, the best response to an exception that is thrown from within a query might be to stop the query execution immediately.</span></span> <span data-ttu-id="65656-115">Aşağıdaki örnek, gelen sorgu gövdesi içinde oluşturulabilecek özel durumların nasıl işleneceğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="65656-115">The following example shows how to handle exceptions that might be thrown from inside a query body.</span></span> <span data-ttu-id="65656-116">Varsayımında `SomeMethodThatMightThrow` durdurmak için sorgu yürütme gerektiren bir özel durum neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="65656-116">Assume that `SomeMethodThatMightThrow` can potentially cause an exception that requires the query execution to stop.</span></span>

<span data-ttu-id="65656-117">Unutmayın `try` blok kapsayan `foreach` döngüsü ve sorgunun kendisi.</span><span class="sxs-lookup"><span data-stu-id="65656-117">Note that the `try` block encloses the `foreach` loop, and not the query itself.</span></span> <span data-ttu-id="65656-118">Bunun nedeni, `foreach` döngü, hangi sorgu gerçekte yürütülür noktasıdır.</span><span class="sxs-lookup"><span data-stu-id="65656-118">This is because the `foreach` loop is the point at which the query is actually executed.</span></span> <span data-ttu-id="65656-119">Daha fazla bilgi için [LINQ sorgularına giriş](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="65656-119">For more information, see [Introduction to LINQ queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>

[!code-csharp[csProgGuideLINQ#12](~/samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_2.cs)]

## <a name="see-also"></a><span data-ttu-id="65656-120">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="65656-120">See also</span></span>

- [<span data-ttu-id="65656-121">Dil ile Tümleşik Sorgu (LINQ)</span><span class="sxs-lookup"><span data-stu-id="65656-121">Language Integrated Query (LINQ)</span></span>](index.md)
