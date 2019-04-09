---
title: 'Nasıl yapılır: Satır Kümeleri Döndürme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
ms.openlocfilehash: 599ad6f722251003ab56547ce050cbd0e8da831d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168720"
---
# <a name="how-to-return-rowsets"></a><span data-ttu-id="ae52e-102">Nasıl yapılır: Satır Kümeleri Döndürme</span><span class="sxs-lookup"><span data-stu-id="ae52e-102">How to: Return Rowsets</span></span>
<span data-ttu-id="ae52e-103">Bu örnek veritabanından satır döndürür ve sonucu filtrelemek için bir giriş parametresi içerir.</span><span class="sxs-lookup"><span data-stu-id="ae52e-103">This example returns a rowset from the database, and includes an input parameter to filter the result.</span></span>  
  
 <span data-ttu-id="ae52e-104">Bir satır kümesi döndüren bir saklı yordamı çalıştırdığınızda, kullandığınız bir *sonucu* saklı yordamdan döndürür depolayan sınıf.</span><span class="sxs-lookup"><span data-stu-id="ae52e-104">When you execute a stored procedure that returns a rowset, you use a *result* class that stores the returns from the stored procedure.</span></span> <span data-ttu-id="ae52e-105">Daha fazla bilgi için [çözümleme LINQ to SQL kaynak kodunu](../../../../../../docs/framework/data/adonet/sql/linq/analyzing-linq-to-sql-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="ae52e-105">For more information, see [Analyzing LINQ to SQL Source Code](../../../../../../docs/framework/data/adonet/sql/linq/analyzing-linq-to-sql-source-code.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae52e-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="ae52e-106">Example</span></span>  
 <span data-ttu-id="ae52e-107">Aşağıdaki örnek, müşteriler satırlarını döndürür ve bu listeyi "London" müşterinin Şehir olarak yalnızca o satırlar döndürülecek giriş parametresi kullanan bir saklı yordam temsil eder.</span><span class="sxs-lookup"><span data-stu-id="ae52e-107">The following example represents a stored procedure that returns rows of customers and uses an input parameter to return only those rows that list "London" as the customer city.</span></span> <span data-ttu-id="ae52e-108">Örnek bir numaralandırılabilir varsayar `CustomersByCityResult` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="ae52e-108">The example assumes an enumerable `CustomersByCityResult` class.</span></span>  
  
```  
CREATE PROCEDURE [dbo].[Customers By City]  
    (@param1 NVARCHAR(20))  
AS  
BEGIN  
    -- SET NOCOUNT ON added to prevent extra result sets from  
    -- interfering with SELECT statements.  
    SET NOCOUNT ON;  
    SELECT CustomerID, ContactName, CompanyName, City from Customers  
        as c where c.City=@param1  
END  
```  
  
 [!code-csharp[DLinqSprox#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#1)]
 [!code-vb[DLinqSprox#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ae52e-109">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="ae52e-109">See also</span></span>

- [<span data-ttu-id="ae52e-110">Saklı Yordamlar</span><span class="sxs-lookup"><span data-stu-id="ae52e-110">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
- [<span data-ttu-id="ae52e-111">Örnek Veritabanları İndirme</span><span class="sxs-lookup"><span data-stu-id="ae52e-111">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
