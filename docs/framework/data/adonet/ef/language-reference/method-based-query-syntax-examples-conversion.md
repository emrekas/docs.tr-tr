---
title: 'Metot tabanlı sorgu söz dizimi örnekleri: Dönüştürme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 19f66872-d5ab-49f8-969f-e53f9632a13d
ms.openlocfilehash: 3e3986bcd956fae45005671cc945ea0c861d7e07
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702320"
---
# <a name="method-based-query-syntax-examples-conversion"></a><span data-ttu-id="dcb3a-102">Metot tabanlı sorgu söz dizimi örnekleri: Dönüştürme</span><span class="sxs-lookup"><span data-stu-id="dcb3a-102">Method-Based Query Syntax Examples: Conversion</span></span>
<span data-ttu-id="dcb3a-103">Bu konudaki örnekler nasıl kullanılacağını gösteren <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> ve <xref:System.Linq.Enumerable.ToList%2A> sorgulamak için yöntemleri [AdventureWorks satışları modeli](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) metot tabanlı sorgu söz dizimini kullanarak.</span><span class="sxs-lookup"><span data-stu-id="dcb3a-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> and <xref:System.Linq.Enumerable.ToList%2A> methods to query the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="dcb3a-104">Bu örneklerde kullanılan AdventureWorks satışları modeli kişi, adres, ürün, SalesOrderHeader ve satış siparişi ayrıntısını tablolarda AdventureWorks örnek veritabanı oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="dcb3a-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="dcb3a-105">Aşağıdaki örneklerde bu konudaki `using` / `Imports` ifadeleri:</span><span class="sxs-lookup"><span data-stu-id="dcb3a-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="toarray"></a><span data-ttu-id="dcb3a-106">ToArray</span><span class="sxs-lookup"><span data-stu-id="dcb3a-106">ToArray</span></span>  
  
### <a name="example"></a><span data-ttu-id="dcb3a-107">Örnek</span><span class="sxs-lookup"><span data-stu-id="dcb3a-107">Example</span></span>  
 <span data-ttu-id="dcb3a-108">Aşağıdaki örnekte <xref:System.Linq.Enumerable.ToArray%2A> hemen bir sıralı bir dizi içine değerlendirmek için bir yöntem.</span><span class="sxs-lookup"><span data-stu-id="dcb3a-108">The following example uses the <xref:System.Linq.Enumerable.ToArray%2A> method to immediately evaluate a sequence into an array.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToArray](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#toarray)]
 [!code-vb[DP L2E Examples#ToArray](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#toarray)]  
  
## <a name="todictionary"></a><span data-ttu-id="dcb3a-109">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="dcb3a-109">ToDictionary</span></span>  
  
### <a name="example"></a><span data-ttu-id="dcb3a-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="dcb3a-110">Example</span></span>  
 <span data-ttu-id="dcb3a-111">Aşağıdaki örnekte <xref:System.Linq.Enumerable.ToDictionary%2A> hemen bir dizisi ve ilişkili bir anahtar ifadesi bir sözlükte değerlendirmek için bir yöntem.</span><span class="sxs-lookup"><span data-stu-id="dcb3a-111">The following example uses the <xref:System.Linq.Enumerable.ToDictionary%2A> method to immediately evaluate a sequence and a related key expression into a dictionary.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#todictionary)]
 [!code-vb[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#todictionary)]  
  
## <a name="tolist"></a><span data-ttu-id="dcb3a-112">ToList</span><span class="sxs-lookup"><span data-stu-id="dcb3a-112">ToList</span></span>  
  
### <a name="example"></a><span data-ttu-id="dcb3a-113">Örnek</span><span class="sxs-lookup"><span data-stu-id="dcb3a-113">Example</span></span>  
 <span data-ttu-id="dcb3a-114">Aşağıdaki örnekte <xref:System.Linq.Enumerable.ToList%2A> hemen bir dizisi olarak değerlendirmek için bir yöntem bir <xref:System.Collections.Generic.List%601>burada `T` türünde <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="dcb3a-114">The following example uses the <xref:System.Linq.Enumerable.ToList%2A> method to immediately evaluate a sequence into a <xref:System.Collections.Generic.List%601>, where `T` is of type <xref:System.Data.DataRow>.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToList](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#tolist)]
 [!code-vb[DP L2E Examples#ToList](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#tolist)]  
  
## <a name="see-also"></a><span data-ttu-id="dcb3a-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="dcb3a-115">See also</span></span>
- [<span data-ttu-id="dcb3a-116">LINQ to Entities Sorguları</span><span class="sxs-lookup"><span data-stu-id="dcb3a-116">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
