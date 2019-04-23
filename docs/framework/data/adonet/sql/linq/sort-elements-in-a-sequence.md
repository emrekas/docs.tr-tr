---
title: Dizideki Öğeleri Sıralama
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d59b93a9-50c8-4770-a114-d902f6a0ea76
ms.openlocfilehash: 33473eadefabc2bcbbb552d225d021eae4bed0bb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59169019"
---
# <a name="sort-elements-in-a-sequence"></a><span data-ttu-id="10963-102">Dizideki Öğeleri Sıralama</span><span class="sxs-lookup"><span data-stu-id="10963-102">Sort Elements in a Sequence</span></span>
<span data-ttu-id="10963-103">Kullanım <xref:System.Linq.Enumerable.OrderBy%2A> bir dizisini bir veya daha fazla anahtarı göre sıralamak için işleci.</span><span class="sxs-lookup"><span data-stu-id="10963-103">Use the <xref:System.Linq.Enumerable.OrderBy%2A> operator to sort a sequence according to one or more keys.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="10963-104">gibi basit ilkel türlere göre sıralama desteklemek için tasarlanan `string`, `int`ve benzeri.</span><span class="sxs-lookup"><span data-stu-id="10963-104">is designed to support ordering by simple primitive types, such as `string`, `int`, and so on.</span></span> <span data-ttu-id="10963-105">Anonim türler gibi karmaşık birden çok değerli sınıflar için sıralama desteklemez.</span><span class="sxs-lookup"><span data-stu-id="10963-105">It does not support ordering for complex multi-valued classes, such as anonymous types.</span></span> <span data-ttu-id="10963-106">Ayrıca desteklemediği `byte` veri türleri.</span><span class="sxs-lookup"><span data-stu-id="10963-106">It also does not support `byte` datatypes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10963-107">Örnek</span><span class="sxs-lookup"><span data-stu-id="10963-107">Example</span></span>  
 <span data-ttu-id="10963-108">Aşağıdaki örnek sıralar `Employees` tarafından işe alma tarihi.</span><span class="sxs-lookup"><span data-stu-id="10963-108">The following example sorts `Employees` by date of hire.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#20](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#20)]
 [!code-vb[DLinqQueryExamples#20](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#20)]  
  
## <a name="example"></a><span data-ttu-id="10963-109">Örnek</span><span class="sxs-lookup"><span data-stu-id="10963-109">Example</span></span>  
 <span data-ttu-id="10963-110">Aşağıdaki örnekte `where` sıralanacak `Orders` sevk `London` freight tarafından.</span><span class="sxs-lookup"><span data-stu-id="10963-110">The following example uses `where` to sort `Orders` shipped to `London` by freight.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#21](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#21)]
 [!code-vb[DLinqQueryExamples#21](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#21)]  
  
## <a name="example"></a><span data-ttu-id="10963-111">Örnek</span><span class="sxs-lookup"><span data-stu-id="10963-111">Example</span></span>  
 <span data-ttu-id="10963-112">Aşağıdaki örnek sıralar `Products` birimine göre fiyat en yüksekten en çok düşük.</span><span class="sxs-lookup"><span data-stu-id="10963-112">The following example sorts `Products` by unit price from highest to lowest.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#22](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#22)]
 [!code-vb[DLinqQueryExamples#22](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="10963-113">Örnek</span><span class="sxs-lookup"><span data-stu-id="10963-113">Example</span></span>  
 <span data-ttu-id="10963-114">Aşağıdaki örnekte bir bileşik `OrderBy` sıralanacak `Customers` Şehir ve ardından ilgili kişi adı.</span><span class="sxs-lookup"><span data-stu-id="10963-114">The following example uses a compound `OrderBy` to sort `Customers` by city and then by contact name.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#24](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#24)]
 [!code-vb[DLinqQueryExamples#24](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#24)]  
  
## <a name="example"></a><span data-ttu-id="10963-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="10963-115">Example</span></span>  
 <span data-ttu-id="10963-116">Aşağıdaki örnekte sipariş sıralar `EmployeeID 1` sevk ülkeye göre ve ardından büyüğe freight göre.</span><span class="sxs-lookup"><span data-stu-id="10963-116">The following example sorts Orders from `EmployeeID 1` by ship-to country, and then by highest to lowest freight.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#25](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#25)]
 [!code-vb[DLinqQueryExamples#25](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#25)]  
  
## <a name="example"></a><span data-ttu-id="10963-117">Örnek</span><span class="sxs-lookup"><span data-stu-id="10963-117">Example</span></span>  
 <span data-ttu-id="10963-118">Aşağıdaki örnek birleştirir <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Max%2A>, ve <xref:System.Linq.Enumerable.GroupBy%2A> bulmak için işleçleri `Products` her kategoride en yüksek birim fiyatı sahip ve ardından grubun kategorisini kimliğine göre sıralar.</span><span class="sxs-lookup"><span data-stu-id="10963-118">The following example combines <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Max%2A>, and <xref:System.Linq.Enumerable.GroupBy%2A> operators to find the `Products` that have the highest unit price in each category, and then sorts the group by category id.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#26](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#26)]
 [!code-vb[DLinqQueryExamples#26](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#26)]  
  
 <span data-ttu-id="10963-119">Northwind örnek veritabanıyla önceki sorguyu çalıştırırsanız, sonuçları şuna benzer:</span><span class="sxs-lookup"><span data-stu-id="10963-119">If you run the previous query against the Northwind sample database, the results will resemble the following:</span></span>  
  
 `1`  
  
 `Côte de Blaye`  
  
 `2`  
  
 `Vegie-spread`  
  
 `3`  
  
 `Sir Rodney's Marmalade`  
  
 `4`  
  
 `Raclette Courdavault`  
  
 `5`  
  
 `Gnocchi di nonna Alice`  
  
 `6`  
  
 `Thüringer Rostbratwurst`  
  
 `7`  
  
 `Manjimup Dried Apples`  
  
 `8`  
  
 `Carnarvon Tigers`  
  
## <a name="see-also"></a><span data-ttu-id="10963-120">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="10963-120">See also</span></span>

- [<span data-ttu-id="10963-121">Sorgu Örnekleri</span><span class="sxs-lookup"><span data-stu-id="10963-121">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="10963-122">Örnek Veritabanları İndirme</span><span class="sxs-lookup"><span data-stu-id="10963-122">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
