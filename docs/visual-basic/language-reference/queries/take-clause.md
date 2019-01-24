---
title: Take Tümcesi (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: bdd12340c5a0bd522c09a22e74c7b4f487cc5821
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626738"
---
# <a name="take-clause-visual-basic"></a><span data-ttu-id="d8b0e-102">Take Tümcesi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d8b0e-102">Take Clause (Visual Basic)</span></span>
<span data-ttu-id="d8b0e-103">Bir koleksiyon başlangıcından belirtilen bir bitişik öğelerin sayısını döndürür.</span><span class="sxs-lookup"><span data-stu-id="d8b0e-103">Returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8b0e-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="d8b0e-104">Syntax</span></span>  
  
```  
Take count  
```  
  
## <a name="parts"></a><span data-ttu-id="d8b0e-105">Bölümler</span><span class="sxs-lookup"><span data-stu-id="d8b0e-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="d8b0e-106">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="d8b0e-106">Required.</span></span> <span data-ttu-id="d8b0e-107">Bir değer veya döndürülecek dizisinin öğe sayısı için değerlendirilen bir ifade.</span><span class="sxs-lookup"><span data-stu-id="d8b0e-107">A value or an expression that evaluates to the number of elements of the sequence to return.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8b0e-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d8b0e-108">Remarks</span></span>  
 <span data-ttu-id="d8b0e-109">`Take` Yan tümcesi bir sorgu sonuç listesini başlangıcından bitişik öğelerin belirtilen bir sayı içerecek şekilde neden olur.</span><span class="sxs-lookup"><span data-stu-id="d8b0e-109">The `Take` clause causes a query to include a specified number of contiguous elements from the start of a results list.</span></span> <span data-ttu-id="d8b0e-110">Eklenecek öğe sayısı tarafından belirtilen `count` parametresi.</span><span class="sxs-lookup"><span data-stu-id="d8b0e-110">The number of elements to include is specified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="d8b0e-111">Kullanabileceğiniz `Take` yan tümcesiyle `Skip` yan tümcesi bir sorgu herhangi bir segmentten veri aralığı döndürülecek.</span><span class="sxs-lookup"><span data-stu-id="d8b0e-111">You can use the `Take` clause with the `Skip` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="d8b0e-112">Bunu yapmak için dizini aralığın ilk öğesine geçirmek `Skip` yan tümcesi ve aralık için boyutunu `Take` yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="d8b0e-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span> <span data-ttu-id="d8b0e-113">Bu durumda, `Take` yan belirtilen, sonra `Skip` yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="d8b0e-113">In this case, the `Take` clause must be specified after the `Skip` clause.</span></span>  
  
 <span data-ttu-id="d8b0e-114">Kullanırken `Take` sorgu yan tümcesi, aynı zamanda gerekebilir sonuçları olanak sağlayacak bir sırada döndürüldüğünden emin olunması `Take` hedeflenen sonuçları içerecek şekilde yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="d8b0e-114">When you use the `Take` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Take` clause to include the intended results.</span></span> <span data-ttu-id="d8b0e-115">Sorgu sonuçlarını sıralama hakkında daha fazla bilgi için bkz. [Order By yan tümcesi](../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="d8b0e-115">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="d8b0e-116">Kullanabileceğiniz `TakeWhile` yan tümcesini yalnızca belirli öğeleri, belirtilen bir koşula bağlı olarak verilmesini belirtin.</span><span class="sxs-lookup"><span data-stu-id="d8b0e-116">You can use the `TakeWhile` clause to specify that only certain elements be returned, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8b0e-117">Örnek</span><span class="sxs-lookup"><span data-stu-id="d8b0e-117">Example</span></span>  
 <span data-ttu-id="d8b0e-118">Aşağıdaki kod örneğinde `Take` yan tümcesi ile birlikte `Skip` veri sayfalarında sorgudan döndürülecek yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="d8b0e-118">The following code example uses the `Take` clause together with the `Skip` clause to return data from a query in pages.</span></span> <span data-ttu-id="d8b0e-119">GetCustomers işlevini kullanan `Skip` sağlanan başlangıç dizini kadar değer ve kullanımlar listesinde müşterileri atlamak için yan tümcesi `Take` yan tümcesi bu dizin değerden başlayan müşteriler bir sayfaya dönün.</span><span class="sxs-lookup"><span data-stu-id="d8b0e-119">The GetCustomers function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d8b0e-120">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d8b0e-120">See also</span></span>
- [<span data-ttu-id="d8b0e-121">Visual Basic'de LINQ'e giriş</span><span class="sxs-lookup"><span data-stu-id="d8b0e-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="d8b0e-122">Sorgular</span><span class="sxs-lookup"><span data-stu-id="d8b0e-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="d8b0e-123">Select Yan Tümcesi</span><span class="sxs-lookup"><span data-stu-id="d8b0e-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="d8b0e-124">From Yan Tümcesi</span><span class="sxs-lookup"><span data-stu-id="d8b0e-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="d8b0e-125">Order By Yan Tümcesi</span><span class="sxs-lookup"><span data-stu-id="d8b0e-125">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="d8b0e-126">Take While Yan Tümcesi</span><span class="sxs-lookup"><span data-stu-id="d8b0e-126">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [<span data-ttu-id="d8b0e-127">Skip Yan Tümcesi</span><span class="sxs-lookup"><span data-stu-id="d8b0e-127">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
