---
title: 'Nasıl yapılır: Bilgi Sorgulama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: 2987e43c83bf84e32cd05a870b24da40dd37d8b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943549"
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="976f7-102">Nasıl yapılır: Bilgi Sorgulama</span><span class="sxs-lookup"><span data-stu-id="976f7-102">How to: Query for Information</span></span>
<span data-ttu-id="976f7-103">İçindeki [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sorgular, içindeki [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]sorgularla aynı sözdizimini kullanır.</span><span class="sxs-lookup"><span data-stu-id="976f7-103">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span> <span data-ttu-id="976f7-104">Tek fark, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sorgularda başvurulan nesnelerin bir veritabanındaki öğelerle eşlendiğine sahiptir.</span><span class="sxs-lookup"><span data-stu-id="976f7-104">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="976f7-105">Daha fazla bilgi için bkz. [LINQ Sorgularına Giriş (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="976f7-105">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="976f7-106">yazdığınız sorguları eşdeğer SQL sorgularına çevirir ve işlenmek üzere sunucuya gönderir.</span><span class="sxs-lookup"><span data-stu-id="976f7-106">translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="976f7-107">[!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] Sorguların bazı özelliklerinin [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] uygulamalarda özel ilgilenilmesi gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="976f7-107">Some features of [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="976f7-108">Daha fazla bilgi için bkz. [sorgu kavramları](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="976f7-108">For more information, see [Query Concepts](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="976f7-109">Örnek</span><span class="sxs-lookup"><span data-stu-id="976f7-109">Example</span></span>  
 <span data-ttu-id="976f7-110">Aşağıdaki sorgu, Londra 'dan müşterilerin bir listesini ister.</span><span class="sxs-lookup"><span data-stu-id="976f7-110">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="976f7-111">Bu örnekte, `Customers` Northwind örnek veritabanındaki bir tablodur.</span><span class="sxs-lookup"><span data-stu-id="976f7-111">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="976f7-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="976f7-112">See also</span></span>

- [<span data-ttu-id="976f7-113">Nesne Modeli Oluşturma</span><span class="sxs-lookup"><span data-stu-id="976f7-113">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
- [<span data-ttu-id="976f7-114">Örnek Veritabanları İndirme</span><span class="sxs-lookup"><span data-stu-id="976f7-114">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [<span data-ttu-id="976f7-115">Veritabanını Sorgulama</span><span class="sxs-lookup"><span data-stu-id="976f7-115">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
