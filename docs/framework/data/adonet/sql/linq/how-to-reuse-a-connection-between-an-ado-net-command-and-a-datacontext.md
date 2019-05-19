---
title: 'Nasıl yapılır: ADO.NET Komutu ile DataContext Arasında Bağlantıyı Yeniden Kullanma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: 92b0d8cf2c4904fabc17241ef2c31175f0c87baf
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65878533"
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a><span data-ttu-id="89ba4-102">Nasıl yapılır: ADO.NET Komutu ile DataContext Arasında Bağlantıyı Yeniden Kullanma</span><span class="sxs-lookup"><span data-stu-id="89ba4-102">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>
<span data-ttu-id="89ba4-103">Çünkü [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] teknolojileri ADO.NET ailesinin bir parçasıdır ve ADO.NET ile ADO.NET komutu arasında bir bağlantı yeniden sağlanan hizmetleri temel alır ve bir <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="89ba4-103">Because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] is a part of the ADO.NET family of technologies and is based on services provided by ADO.NET, you can reuse a connection between an ADO.NET command and a <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89ba4-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="89ba4-104">Example</span></span>  
 <span data-ttu-id="89ba4-105">Aşağıdaki örnek nasıl ADO.NET komutu arasında aynı bağlantıyı yeniden gösterir ve <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="89ba4-105">The following example shows how to reuse the same connection between an ADO.NET command and the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="89ba4-106">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="89ba4-106">See also</span></span>

- [<span data-ttu-id="89ba4-107">Arka Plan Bilgileri</span><span class="sxs-lookup"><span data-stu-id="89ba4-107">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [<span data-ttu-id="89ba4-108">ADO.NET ve LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="89ba4-108">ADO.NET and LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/ado-net-and-linq-to-sql.md)
- [<span data-ttu-id="89ba4-109">Veritabanı ile İletişim Kurma</span><span class="sxs-lookup"><span data-stu-id="89ba4-109">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
