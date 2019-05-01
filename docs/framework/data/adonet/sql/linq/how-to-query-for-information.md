---
title: 'Nasıl yapılır: Bilgi Sorgulama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: aedf89f1e570b34d31050fabb91842cefe351488
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033741"
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="52d7f-102">Nasıl yapılır: Bilgi Sorgulama</span><span class="sxs-lookup"><span data-stu-id="52d7f-102">How to: Query for Information</span></span>
<span data-ttu-id="52d7f-103">Sorgulara [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sorgularda olarak aynı sözdizimini kullanır [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="52d7f-103">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span> <span data-ttu-id="52d7f-104">Nesneler, başvurulan tek fark, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sorguları bir veritabanında öğelerine eşleştirilir.</span><span class="sxs-lookup"><span data-stu-id="52d7f-104">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="52d7f-105">Daha fazla bilgi için [(C#) LINQ sorgularına giriş](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="52d7f-105">For more information, see [Introduction to LINQ Queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="52d7f-106">eşdeğer SQL sorguları yazma sorguları çevirir ve işlem sunucusuna gönderir.</span><span class="sxs-lookup"><span data-stu-id="52d7f-106">translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="52d7f-107">Bazı özellikleri [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] sorguları özel dikkat ihtiyaç duyabilirsiniz [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] uygulamalar.</span><span class="sxs-lookup"><span data-stu-id="52d7f-107">Some features of [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="52d7f-108">Daha fazla bilgi için [sorgu kavramları](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="52d7f-108">For more information, see [Query Concepts](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="52d7f-109">Örnek</span><span class="sxs-lookup"><span data-stu-id="52d7f-109">Example</span></span>  
 <span data-ttu-id="52d7f-110">Londralı müşteriler listesi için aşağıdaki sorguyu ister.</span><span class="sxs-lookup"><span data-stu-id="52d7f-110">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="52d7f-111">Bu örnekte, `Customers` Northwind örnek veritabanındaki bir tablodur.</span><span class="sxs-lookup"><span data-stu-id="52d7f-111">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="52d7f-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="52d7f-112">See also</span></span>

- [<span data-ttu-id="52d7f-113">Nesne Modeli Oluşturma</span><span class="sxs-lookup"><span data-stu-id="52d7f-113">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
- [<span data-ttu-id="52d7f-114">Örnek Veritabanları İndirme</span><span class="sxs-lookup"><span data-stu-id="52d7f-114">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [<span data-ttu-id="52d7f-115">Veritabanını Sorgulama</span><span class="sxs-lookup"><span data-stu-id="52d7f-115">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
