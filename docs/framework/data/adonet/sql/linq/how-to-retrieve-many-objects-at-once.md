---
title: 'Nasıl yapılır: Tek Seferde Birçok Nesne Alma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 18aff4d8-bde8-461b-9960-ccabb24e9d22
ms.openlocfilehash: dd53c2fd16a82ce0f69a33e0b7d7ffef7815b91b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61877155"
---
# <a name="how-to-retrieve-many-objects-at-once"></a><span data-ttu-id="37670-102">Nasıl yapılır: Tek Seferde Birçok Nesne Alma</span><span class="sxs-lookup"><span data-stu-id="37670-102">How to: Retrieve Many Objects At Once</span></span>
<span data-ttu-id="37670-103">Çok sayıda nesne bir sorgu kullanarak alabileceğiniz <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span><span class="sxs-lookup"><span data-stu-id="37670-103">You can retrieve many objects in one query by using <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37670-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="37670-104">Example</span></span>  
 <span data-ttu-id="37670-105">Aşağıdaki kod <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> yönteminin her ikisi de almak için `Customer` ve `Order` nesneleri.</span><span class="sxs-lookup"><span data-stu-id="37670-105">The following code uses the <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> method to retrieve both `Customer` and `Order` objects.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#9)]
 [!code-vb[DLinqQueryConcepts#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="37670-106">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="37670-106">See also</span></span>

- [<span data-ttu-id="37670-107">Sorgu Kavramları</span><span class="sxs-lookup"><span data-stu-id="37670-107">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
