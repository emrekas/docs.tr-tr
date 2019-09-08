---
title: 'Nasıl yapılır: Veritabanına Bağlanma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c33d74b3-530d-421b-a121-96786dd263a5
ms.openlocfilehash: 48ff4af2c881104d5699910e20ef86eea0466d2a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793867"
---
# <a name="how-to-connect-to-a-database"></a><span data-ttu-id="7ccc1-102">Nasıl yapılır: Veritabanına Bağlanma</span><span class="sxs-lookup"><span data-stu-id="7ccc1-102">How to: Connect to a Database</span></span>
<span data-ttu-id="7ccc1-103">, <xref:System.Data.Linq.DataContext> Bir veritabanına bağlandığınız, nesneleri buradan alacağınız ve değişiklikleri geri gönderen ana iletken.</span><span class="sxs-lookup"><span data-stu-id="7ccc1-103">The <xref:System.Data.Linq.DataContext> is the main conduit by which you connect to a database, retrieve objects from it, and submit changes back to it.</span></span> <span data-ttu-id="7ccc1-104"><xref:System.Data.Linq.DataContext> Yalnızca bir ADO.net <xref:System.Data.SqlClient.SqlConnection>kullandığınız gibi kullanırsınız.</span><span class="sxs-lookup"><span data-stu-id="7ccc1-104">You use the <xref:System.Data.Linq.DataContext> just as you would use an ADO.NET <xref:System.Data.SqlClient.SqlConnection>.</span></span> <span data-ttu-id="7ccc1-105">Aslında <xref:System.Data.Linq.DataContext> , sağladığınız bir bağlantı veya bağlantı dizesi ile başlatılır.</span><span class="sxs-lookup"><span data-stu-id="7ccc1-105">In fact, the <xref:System.Data.Linq.DataContext> is initialized with a connection or connection string that you supply.</span></span> <span data-ttu-id="7ccc1-106">Daha fazla bilgi için [DataContext yöntemi (O/R Tasarımcısı)](/visualstudio/data-tools/datacontext-methods-o-r-designer).</span><span class="sxs-lookup"><span data-stu-id="7ccc1-106">For more information, see [DataContext Methods (O/R Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer).</span></span>  
  
 <span data-ttu-id="7ccc1-107">' Nin <xref:System.Data.Linq.DataContext> amacı, veritabanına karşı yapılacak isteklerinizi SQL sorgularına dönüştürmek ve ardından nesneleri sonuçlardan elde etmek üzere çevirsağlamaktır.</span><span class="sxs-lookup"><span data-stu-id="7ccc1-107">The purpose of the <xref:System.Data.Linq.DataContext> is to translate your requests for objects into SQL queries to be made against the database, and then to assemble objects out of the results.</span></span> <span data-ttu-id="7ccc1-108"><xref:System.Data.Linq.DataContext> [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] , `Where` Ve gibistandartsorguişleçleriileaynıoperatördeseninin`Select`uygulanması ile etkinleştirilir.</span><span class="sxs-lookup"><span data-stu-id="7ccc1-108">The <xref:System.Data.Linq.DataContext> enables [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] by implementing the same operator pattern as the Standard Query Operators, such as `Where` and `Select`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7ccc1-109">Güvenli bir bağlantının sürdürülmesi en yüksek öneme sahiptir.</span><span class="sxs-lookup"><span data-stu-id="7ccc1-109">Maintaining a secure connection is of the highest importance.</span></span> <span data-ttu-id="7ccc1-110">Daha fazla bilgi için bkz. [LINQ to SQL güvenlik](security-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="7ccc1-110">For more information, see [Security in LINQ to SQL](security-in-linq-to-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ccc1-111">Örnek</span><span class="sxs-lookup"><span data-stu-id="7ccc1-111">Example</span></span>  
 <span data-ttu-id="7ccc1-112">Aşağıdaki örnekte <xref:System.Data.Linq.DataContext> , Northwind örnek veritabanına bağlanmak ve şehri Londra olan müşterilerin satırlarını almak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="7ccc1-112">In the following example, the <xref:System.Data.Linq.DataContext> is used to connect to the Northwind sample database and to retrieve rows of customers whose city is London.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#1)]
 [!code-vb[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#1)]  
  
 <span data-ttu-id="7ccc1-113">Her veritabanı tablosu, `Table` <xref:System.Data.Linq.DataContext.GetTable%2A> yöntemi tarafından kullanılabilen bir koleksiyon olarak temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="7ccc1-113">Each database table is represented as a `Table` collection available by way of the <xref:System.Data.Linq.DataContext.GetTable%2A> method, by using the entity class to identify it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ccc1-114">Örnek</span><span class="sxs-lookup"><span data-stu-id="7ccc1-114">Example</span></span>  
 <span data-ttu-id="7ccc1-115">En iyi yöntem, temel <xref:System.Data.Linq.DataContext> <xref:System.Data.Linq.DataContext> sınıfa ve <xref:System.Data.Linq.DataContext.GetTable%2A> yöntemine güvenmek yerine kesin bir tür bildirimi kullanmaktır.</span><span class="sxs-lookup"><span data-stu-id="7ccc1-115">Best practice is to declare a strongly typed <xref:System.Data.Linq.DataContext> instead of relying on the basic <xref:System.Data.Linq.DataContext> class and the <xref:System.Data.Linq.DataContext.GetTable%2A> method.</span></span> <span data-ttu-id="7ccc1-116">Türü kesin belirlenmiş <xref:System.Data.Linq.DataContext> , aşağıdaki `Table` örnekte olduğu gibi tüm koleksiyonları bağlamın üyesi olarak bildirir.</span><span class="sxs-lookup"><span data-stu-id="7ccc1-116">A strongly typed <xref:System.Data.Linq.DataContext> declares all `Table` collections as members of the context, as in the following example.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#2)]
 [!code-vb[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#2)]  
  
 <span data-ttu-id="7ccc1-117">Daha sonra Londra 'dan daha basit bir şekilde sorgu yapabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="7ccc1-117">You can then express the query for customers from London more simply as:</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#5)]
 [!code-vb[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="7ccc1-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="7ccc1-118">See also</span></span>

- [<span data-ttu-id="7ccc1-119">Veritabanı ile İletişim Kurma</span><span class="sxs-lookup"><span data-stu-id="7ccc1-119">Communicating with the Database</span></span>](communicating-with-the-database.md)
