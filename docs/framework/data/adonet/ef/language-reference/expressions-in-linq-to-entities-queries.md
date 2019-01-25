---
title: LINQ to Entities sorgularında ifadelerinde
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
ms.openlocfilehash: f449e7d5626d4a8c9709ae2cb4c026869d1e2dc9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661782"
---
# <a name="expressions-in-linq-to-entities-queries"></a><span data-ttu-id="8e74e-102">LINQ to Entities sorgularında ifadelerinde</span><span class="sxs-lookup"><span data-stu-id="8e74e-102">Expressions in LINQ to Entities Queries</span></span>
<span data-ttu-id="8e74e-103">Tek değer, nesne, yöntemi veya ad alanı için değerlendirilen kodun bir parçasını ifadesidir.</span><span class="sxs-lookup"><span data-stu-id="8e74e-103">An expression is a fragment of code that can be evaluated to a single value, object, method, or namespace.</span></span> <span data-ttu-id="8e74e-104">Değişmez değer, bir yöntem çağrısı, bir işleci ve işlenenleri veya basit bir ad ifadeleri içerebilir.</span><span class="sxs-lookup"><span data-stu-id="8e74e-104">Expressions can contain a literal value, a method call, an operator and its operands, or a simple name.</span></span> <span data-ttu-id="8e74e-105">Basit adları bir değişken, tür üyesi, yöntem parametresi, ad alanı veya tür adı olabilir.</span><span class="sxs-lookup"><span data-stu-id="8e74e-105">Simple names can be the name of a variable, type member, method parameter, namespace or type.</span></span> <span data-ttu-id="8e74e-106">İfadeler sırayla parametreleri veya diğer sırayla yöntem çağrılarını parametreleri olan yöntem çağrıları diğer ifadeler kullanan işleçlerini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8e74e-106">Expressions can use operators that in turn use other expressions as parameters, or method calls whose parameters are in turn other method calls.</span></span> <span data-ttu-id="8e74e-107">Bu nedenle, ifadeleri basitten çok karmaşık değişebilir.</span><span class="sxs-lookup"><span data-stu-id="8e74e-107">Therefore, expressions can range from simple to very complex.</span></span>  
  
 <span data-ttu-id="8e74e-108">İçinde [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] sorgu ifadeleri içerebilir türler tarafından izin verilen herhangi bir şey <xref:System.Linq.Expressions> ad alanı, lambda ifadeleri de dahil olmak üzere.</span><span class="sxs-lookup"><span data-stu-id="8e74e-108">In [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries, expressions can contain anything allowed by the types within the <xref:System.Linq.Expressions> namespace, including lambda expressions.</span></span> <span data-ttu-id="8e74e-109">Kullanılabilir ifadeler [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] sorgulardır kullanılabilir ifadeler kümesi için sorgu [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e74e-109">The expressions that can be used in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries are a superset of the expressions that can be used to query the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="8e74e-110">Sorguları parçası olan ifadeleri [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] tarafından desteklenen operations sınırlıdır `ObjectQuery<T>` ve temel alınan veri kaynağı.</span><span class="sxs-lookup"><span data-stu-id="8e74e-110">Expressions that are part of queries against the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are limited to operations supported by `ObjectQuery<T>` and the underlying data source.</span></span>  
  
 <span data-ttu-id="8e74e-111">Aşağıdaki örnekte, Karşılaştırmada `Where` yan tümcesi ise bir ifade:</span><span class="sxs-lookup"><span data-stu-id="8e74e-111">In the following example, the comparison in the `Where` clause is an expression:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
>  <span data-ttu-id="8e74e-112">Belirli dil yapılarını, C# gibi `unchecked`, hiçbir anlamı olmayan [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e74e-112">Specific language constructs, such as C# `unchecked`, have no meaning in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8e74e-113">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="8e74e-113">In This Section</span></span>  
 [<span data-ttu-id="8e74e-114">Sabit İfadeler</span><span class="sxs-lookup"><span data-stu-id="8e74e-114">Constant Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constant-expressions.md)  
  
 [<span data-ttu-id="8e74e-115">Karşılaştırma İfadeleri</span><span class="sxs-lookup"><span data-stu-id="8e74e-115">Comparison Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-expressions.md)  
  
 [<span data-ttu-id="8e74e-116">Null Karşılaştırmalar</span><span class="sxs-lookup"><span data-stu-id="8e74e-116">Null Comparisons</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/null-comparisons.md)  
  
 [<span data-ttu-id="8e74e-117">Başlatma İfadeleri</span><span class="sxs-lookup"><span data-stu-id="8e74e-117">Initialization Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/initialization-expressions.md)  
  
 [<span data-ttu-id="8e74e-118">Gezinti özellikleri</span><span class="sxs-lookup"><span data-stu-id="8e74e-118">Navigation Properties</span></span>](https://msdn.microsoft.com/library/41e1e6b9-8a57-467d-99d9-1857d2ca2ea5)  
  
## <a name="see-also"></a><span data-ttu-id="8e74e-119">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="8e74e-119">See also</span></span>
- [<span data-ttu-id="8e74e-120">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="8e74e-120">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)
