---
title: 'Nasıl yapılır: LINQ to SQL Komutlarını Görüntüleme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1decb05e-37ad-4ed6-ab2f-071eb4c4f628
ms.openlocfilehash: d71eaf834ebf36d462f8581f0074b2f6a90bae17
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211614"
---
# <a name="how-to-display-linq-to-sql-commands"></a><span data-ttu-id="83f0f-102">Nasıl yapılır: LINQ to SQL Komutlarını Görüntüleme</span><span class="sxs-lookup"><span data-stu-id="83f0f-102">How to: Display LINQ to SQL Commands</span></span>
<span data-ttu-id="83f0f-103">Kullanım <xref:System.Data.Linq.DataContext.GetCommand%2A> SQL komutları ve diğer bilgileri görüntülemek için.</span><span class="sxs-lookup"><span data-stu-id="83f0f-103">Use <xref:System.Data.Linq.DataContext.GetCommand%2A> to display SQL commands and other information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83f0f-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="83f0f-104">Example</span></span>  
 <span data-ttu-id="83f0f-105">Aşağıdaki örnekte, sorgudan oluşturulan SQL komutları, komut türü koyun ve bağlantı türü tarafından çıkış konsol penceresinde görüntüler.</span><span class="sxs-lookup"><span data-stu-id="83f0f-105">In the following example, the console window displays the output from the query, followed by the SQL commands that are generated, the type of commands, and the type of connection.</span></span>  
  
 [!code-csharp[DLinqDebuggingSupport#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#3)]
 [!code-vb[DLinqDebuggingSupport#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#3)]  
  
 <span data-ttu-id="83f0f-106">Çıktı aşağıdaki gibi görünür:</span><span class="sxs-lookup"><span data-stu-id="83f0f-106">Output appears as follows:</span></span>  
  
```  
Customers from London:  
    Thomas Hardy  
    Victoria Ashworth  
    Elizabeth Brown  
    Ann Devon  
    Simon Crowther  
    Marie Bertrand  
    Hari Kumar  
    Dominique Perrier  
```  
  
```  
Command Text:  
SELECT [t0].[CustomerID], [t0].[CompanyName], [t0].[ContactName], [t0].[ContactT  
itle], [t0].[Address], [t0].[City], [t0].[Region], [t0].[PostalCode], [t0].[Coun  
try], [t0].[Phone], [t0].[Fax]  
FROM [dbo].[Customers] AS [t0]  
WHERE [t0].[City] = @p0  
  
Command Type: Text  
  
Connection: System.Data.SqlClient.SqlConnection  
```  
  
## <a name="see-also"></a><span data-ttu-id="83f0f-107">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="83f0f-107">See also</span></span>

- [<span data-ttu-id="83f0f-108">Hata Ayıklama Desteği</span><span class="sxs-lookup"><span data-stu-id="83f0f-108">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)
