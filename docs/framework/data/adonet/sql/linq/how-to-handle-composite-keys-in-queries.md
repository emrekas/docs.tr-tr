---
title: 'Nasıl yapılır: Sorgularda Bileşik Anahtarlar İşleme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ce2f14fd-1038-458a-91e3-a078c61f0d10
ms.openlocfilehash: a6c6e7d1c1d29a049b50f4ea9d70ef5cd9e89a44
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793575"
---
# <a name="how-to-handle-composite-keys-in-queries"></a><span data-ttu-id="89cd2-102">Nasıl yapılır: Sorgularda Bileşik Anahtarlar İşleme</span><span class="sxs-lookup"><span data-stu-id="89cd2-102">How to: Handle Composite Keys in Queries</span></span>
<span data-ttu-id="89cd2-103">Bazı işleçler yalnızca bir bağımsız değişken alabilir.</span><span class="sxs-lookup"><span data-stu-id="89cd2-103">Some operators can take only one argument.</span></span> <span data-ttu-id="89cd2-104">Bağımsız değişkeninizdeki veritabanından birden fazla sütun içermesi gerekiyorsa, birleşimi temsil etmek için anonim bir tür oluşturmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="89cd2-104">If your argument must include more than one column from the database, you must create an anonymous type to represent the combination.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89cd2-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="89cd2-105">Example</span></span>  
 <span data-ttu-id="89cd2-106">Aşağıdaki örnek, yalnızca bir `GroupBy` `key` bağımsız değişken içerebilen işleci çağıran bir sorguyu gösterir.</span><span class="sxs-lookup"><span data-stu-id="89cd2-106">The following example shows a query that invokes the `GroupBy` operator, which can take only one `key` argument.</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#1)]
 [!code-vb[DLinqCompositeKeys#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="89cd2-107">Örnek</span><span class="sxs-lookup"><span data-stu-id="89cd2-107">Example</span></span>  
 <span data-ttu-id="89cd2-108">Aynı durum, aşağıdaki örnekte olduğu gibi birleşimlere aittir:</span><span class="sxs-lookup"><span data-stu-id="89cd2-108">The same situation pertains to joins, as in the following example:</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#2)]
 [!code-vb[DLinqCompositeKeys#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="89cd2-109">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="89cd2-109">See also</span></span>

- [<span data-ttu-id="89cd2-110">Sorgu Kavramları</span><span class="sxs-lookup"><span data-stu-id="89cd2-110">Query Concepts</span></span>](query-concepts.md)
