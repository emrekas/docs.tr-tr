---
title: 'Metot tabanlı sorgu söz dizimi örnekleri: Gruplandırma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb23c25c-1075-4cc3-a8ff-4db72e536c0d
ms.openlocfilehash: d414218604887fca2d69a02b40dfa87f13961aae
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825387"
---
# <a name="method-based-query-syntax-examples-grouping"></a><span data-ttu-id="baf7e-102">Metot tabanlı sorgu söz dizimi örnekleri: Gruplandırma</span><span class="sxs-lookup"><span data-stu-id="baf7e-102">Method-Based Query Syntax Examples: Grouping</span></span>
<span data-ttu-id="baf7e-103">Bu konudaki örnekler nasıl kullanılacağını size gösterir `GroupBy` sorgu yöntemine [AdventureWorks satışları modeli](https://archive.codeplex.com/?p=msftdbprodsamples) metot tabanlı sorgu söz dizimini kullanarak.</span><span class="sxs-lookup"><span data-stu-id="baf7e-103">The examples in this topic show you how to use the `GroupBy` method to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="baf7e-104">Bu örneklerde kullanılan AdventureWorks satışları modeli kişi, adres, ürün, SalesOrderHeader ve satış siparişi ayrıntısını tablolarda AdventureWorks örnek veritabanı oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="baf7e-104">The AdventureWorks Sales Model that is used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="baf7e-105">Aşağıdaki örneklerde bu konudaki `using` / `Imports` ifadeleri:</span><span class="sxs-lookup"><span data-stu-id="baf7e-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="baf7e-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="baf7e-106">Example</span></span>  
 <span data-ttu-id="baf7e-107">Aşağıdaki örnekte `GroupBy` döndürülecek yöntemi `Address` posta koduna göre gruplandırılan nesneleri.</span><span class="sxs-lookup"><span data-stu-id="baf7e-107">The following example uses the `GroupBy` method to return `Address` objects that are grouped by postal code.</span></span> <span data-ttu-id="baf7e-108">Anonim bir tür yansıtılan sonuçları.</span><span class="sxs-lookup"><span data-stu-id="baf7e-108">The results are projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3_mq)]  
  
## <a name="example"></a><span data-ttu-id="baf7e-109">Örnek</span><span class="sxs-lookup"><span data-stu-id="baf7e-109">Example</span></span>  
 <span data-ttu-id="baf7e-110">Aşağıdaki örnekte `GroupBy` döndürülecek yöntemi `Contact` kişinin soyadı ilk harfini tarafından gruplandırılmış olan nesneler.</span><span class="sxs-lookup"><span data-stu-id="baf7e-110">The following example uses the `GroupBy` method to return `Contact` objects that are grouped by the first letter of the contact's last name.</span></span> <span data-ttu-id="baf7e-111">Sonuçları da son adının ilk harfi sıralanır ve anonim bir tür yansıtılır.</span><span class="sxs-lookup"><span data-stu-id="baf7e-111">The results are also sorted by the first letter of the last name and projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2_mq)]  
  
## <a name="example"></a><span data-ttu-id="baf7e-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="baf7e-112">Example</span></span>  
 <span data-ttu-id="baf7e-113">Aşağıdaki örnekte `GroupBy` döndürülecek yöntemi `SalesOrderHeader` müşteri kimliğine göre gruplandırılmış nesneleri</span><span class="sxs-lookup"><span data-stu-id="baf7e-113">The following example uses the `GroupBy` method to return `SalesOrderHeader` objects that are grouped by customer ID.</span></span> <span data-ttu-id="baf7e-114">Ayrıca, her müşteri için satış sayısı döndürülür.</span><span class="sxs-lookup"><span data-stu-id="baf7e-114">The number of sales for each customer is also returned.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount_mq)]
 [!code-vb[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="baf7e-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="baf7e-115">See also</span></span>
- [<span data-ttu-id="baf7e-116">LINQ to Entities Sorguları</span><span class="sxs-lookup"><span data-stu-id="baf7e-116">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
