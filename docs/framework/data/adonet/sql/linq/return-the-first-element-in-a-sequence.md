---
title: Dizideki İlk Öğeyi Döndürme
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccdc3777-b2c2-44e3-a627-abef8d79a555
ms.openlocfilehash: 39cf9270b08fce64590fef418bb428c5a781b0e9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963807"
---
# <a name="return-the-first-element-in-a-sequence"></a><span data-ttu-id="e1456-102">Dizideki İlk Öğeyi Döndürme</span><span class="sxs-lookup"><span data-stu-id="e1456-102">Return the First Element in a Sequence</span></span>
<span data-ttu-id="e1456-103">Bir dizideki ilk öğeyi döndürmek için işlecinikullanın.<xref:System.Linq.Enumerable.First%2A></span><span class="sxs-lookup"><span data-stu-id="e1456-103">Use the <xref:System.Linq.Enumerable.First%2A> operator to return the first element in a sequence.</span></span> <span data-ttu-id="e1456-104"><xref:System.Linq.Enumerable.First%2A> Kullanan sorgular hemen yürütülür.</span><span class="sxs-lookup"><span data-stu-id="e1456-104">Queries that use <xref:System.Linq.Enumerable.First%2A> are executed immediately.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="e1456-105"><xref:System.Linq.Enumerable.Last%2A> işlecini desteklemez.</span><span class="sxs-lookup"><span data-stu-id="e1456-105">does not support the <xref:System.Linq.Enumerable.Last%2A> operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1456-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="e1456-106">Example</span></span>  
 <span data-ttu-id="e1456-107">Aşağıdaki kod, bir tabloda birincni `Shipper` bulur:</span><span class="sxs-lookup"><span data-stu-id="e1456-107">The following code finds the first `Shipper` in a table:</span></span>  
  
 <span data-ttu-id="e1456-108">Bu sorguyu Northwind örnek veritabanında çalıştırırsanız, sonuçlar</span><span class="sxs-lookup"><span data-stu-id="e1456-108">If you run this query against the Northwind sample database, the results are</span></span>  
  
 <span data-ttu-id="e1456-109">`ID = 1, Company = Speedy Express`.</span><span class="sxs-lookup"><span data-stu-id="e1456-109">`ID = 1, Company = Speedy Express`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#14](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#14)]
 [!code-vb[DLinqQueryExamples#14](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="e1456-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="e1456-110">Example</span></span>  
 <span data-ttu-id="e1456-111">Aşağıdaki kod, `CustomerID` priap 'ye `Customer` sahip olan tekli bulur.</span><span class="sxs-lookup"><span data-stu-id="e1456-111">The following code finds the single `Customer` that has the `CustomerID` BONAP.</span></span>  
  
 <span data-ttu-id="e1456-112">Bu sorguyu Northwind örnek veritabanında çalıştırırsanız, sonuçlar olur `ID = BONAP, Contact = Laurence Lebihan`.</span><span class="sxs-lookup"><span data-stu-id="e1456-112">If you run this query against the Northwind sample database, the results are `ID = BONAP, Contact = Laurence Lebihan`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#15](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#15)]
 [!code-vb[DLinqQueryExamples#15](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="e1456-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="e1456-113">See also</span></span>

- [<span data-ttu-id="e1456-114">Sorgu Örnekleri</span><span class="sxs-lookup"><span data-stu-id="e1456-114">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="e1456-115">Örnek Veritabanları İndirme</span><span class="sxs-lookup"><span data-stu-id="e1456-115">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
