---
title: İki dizinin küme birleşimini döndürür
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: a2d51e8052c839ea4cd11dec07a3aef95d59d0f1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54546968"
---
# <a name="return-the-set-union-of-two-sequences"></a><span data-ttu-id="beb4a-102">İki dizinin küme birleşimini döndürür</span><span class="sxs-lookup"><span data-stu-id="beb4a-102">Return the Set Union of Two Sequences</span></span>
<span data-ttu-id="beb4a-103">Kullanım <xref:System.Linq.Queryable.Union%2A> işlecini iki dizinin küme birleşimini döndürür.</span><span class="sxs-lookup"><span data-stu-id="beb4a-103">Use the <xref:System.Linq.Queryable.Union%2A> operator to return the set union of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="beb4a-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="beb4a-104">Example</span></span>  
 <span data-ttu-id="beb4a-105">Bu örnekte <xref:System.Linq.Queryable.Union%2A> tüm ülkelerde, vardır ya da bir dizisini döndürmek için `Customers` veya `Employees`.</span><span class="sxs-lookup"><span data-stu-id="beb4a-105">This example uses <xref:System.Linq.Queryable.Union%2A> to return a sequence of all countries in which there are either `Customers` or `Employees`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 <span data-ttu-id="beb4a-106">İçinde [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], <xref:System.Linq.Queryable.Union%2A> işleci için multisets multisets sırasız birleşimi tanımlanır (etkili bir şekilde sonucunu [ `UNION ALL` ](https://docs.microsoft.com/sql/t-sql/language-elements/set-operators-union-transact-sql?view=sql-server-2017) yan tümcesinde SQL).</span><span class="sxs-lookup"><span data-stu-id="beb4a-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Union%2A> operator is defined for multisets as the unordered concatenation of the multisets (effectively the result of the [`UNION ALL`](https://docs.microsoft.com/sql/t-sql/language-elements/set-operators-union-transact-sql?view=sql-server-2017) clause in SQL).</span></span>

<span data-ttu-id="beb4a-107">Daha fazla bilgi ve örnekler için bkz. <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="beb4a-107">For more info and examples, see <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="beb4a-108">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="beb4a-108">See also</span></span>
- [<span data-ttu-id="beb4a-109">Sorgu Örnekleri</span><span class="sxs-lookup"><span data-stu-id="beb4a-109">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="beb4a-110">Standart Sorgu İşleci Çevirisi</span><span class="sxs-lookup"><span data-stu-id="beb4a-110">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
