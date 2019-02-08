---
title: 'Sorgu ifadesi söz dizimi örnekleri: Öğe işleçleri'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 32268fe2-de18-4065-8060-f250def83837
ms.openlocfilehash: 44bce972ed1c6c09c5db1d7bc9d40cbca64ea285
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826128"
---
# <a name="query-expression-syntax-examples-element-operators"></a><span data-ttu-id="78965-102">Sorgu ifadesi söz dizimi örnekleri: Öğe işleçleri</span><span class="sxs-lookup"><span data-stu-id="78965-102">Query Expression Syntax Examples: Element Operators</span></span>
<span data-ttu-id="78965-103">Bu konudaki örnekler nasıl kullanılacağını gösteren <xref:System.Linq.Enumerable.First%2A> sorgu yöntemine [AdventureWorks satışları modeli](https://archive.codeplex.com/?p=msftdbprodsamples) sorgu ifadesi söz dizimini kullanarak.</span><span class="sxs-lookup"><span data-stu-id="78965-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using the query expression syntax.</span></span> <span data-ttu-id="78965-104">Bu örneklerde kullanılan AdventureWorks satışları modeli kişi, adres, ürün, SalesOrderHeader ve satış siparişi ayrıntısını tablolarda AdventureWorks örnek veritabanı oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="78965-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="78965-105">Aşağıdaki örneklerde bu konudaki `using` / `Imports` ifadeleri:</span><span class="sxs-lookup"><span data-stu-id="78965-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="78965-106">ilk</span><span class="sxs-lookup"><span data-stu-id="78965-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="78965-107">Örnek</span><span class="sxs-lookup"><span data-stu-id="78965-107">Example</span></span>  
 <span data-ttu-id="78965-108">Aşağıdaki örnekte <xref:System.Linq.Enumerable.First%2A> yöntemi ilk kişinin ilk adı döndürülecek olan "Brooke".</span><span class="sxs-lookup"><span data-stu-id="78965-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to return the first contact whose first name is "Brooke".</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstsimple)]
 [!code-vb[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="78965-109">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="78965-109">See also</span></span>
- [<span data-ttu-id="78965-110">LINQ to Entities Sorguları</span><span class="sxs-lookup"><span data-stu-id="78965-110">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
