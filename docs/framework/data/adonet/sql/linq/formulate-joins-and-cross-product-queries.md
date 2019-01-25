---
title: Birleşimler ve çapraz ürün sorguları düzenleme
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
ms.openlocfilehash: a06c7d451d9ad2856092910065f1195a86c737ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54548527"
---
# <a name="formulate-joins-and-cross-product-queries"></a><span data-ttu-id="bc549-102">Birleşimler ve çapraz ürün sorguları düzenleme</span><span class="sxs-lookup"><span data-stu-id="bc549-102">Formulate Joins and Cross-Product Queries</span></span>
<span data-ttu-id="bc549-103">Aşağıdaki örnekler nasıl birden çok tablodan sonuçlar birleştirileceğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="bc549-103">The following examples show how to combine results from multiple tables.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc549-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="bc549-104">Example</span></span>  
 <span data-ttu-id="bc549-105">Yabancı anahtar Gezinti bölmesinde aşağıdaki örnekte `From` Visual Basic'te yan tümcesi (`from` yan tümcesinde C#) müşteriler için tüm siparişleri Londra'da seçin.</span><span class="sxs-lookup"><span data-stu-id="bc549-105">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to select all orders for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a><span data-ttu-id="bc549-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="bc549-106">Example</span></span>  
 <span data-ttu-id="bc549-107">Aşağıdaki örnek, yabancı anahtar Gezinti kullanır `Where` Visual Basic'te yan tümcesi (`where` yan tümcesinde C#) çıkış, stok için filtre uygulamak için `Products` olan `Supplier` Amerika Birleşik Devletleri'nde olduğu.</span><span class="sxs-lookup"><span data-stu-id="bc549-107">The following example uses foreign key navigation in the `Where` clause in Visual Basic (`where` clause in C#) to filter for out-of-stock `Products` whose `Supplier` is in the United States.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a><span data-ttu-id="bc549-108">Örnek</span><span class="sxs-lookup"><span data-stu-id="bc549-108">Example</span></span>  
 <span data-ttu-id="bc549-109">Aşağıdaki örnek, yabancı anahtar Gezinti kullanır `From` Visual Basic'te yan tümcesi (`from` yan tümcesinde C#) Seattle çalışanları için filtre ve bunların bölgeleri listesi.</span><span class="sxs-lookup"><span data-stu-id="bc549-109">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to filter for employees in Seattle and to list their territories.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a><span data-ttu-id="bc549-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="bc549-110">Example</span></span>  
 <span data-ttu-id="bc549-111">Aşağıdaki örnek, yabancı anahtar Gezinti kullanır `Select` Visual Basic'te yan tümcesi (`select` yan tümcesinde C#) çiftleri çalışanlar için her iki çalışanlar aynı olduğu ve burada bir çalışan diğer raporlar filtrelemek için `City`.</span><span class="sxs-lookup"><span data-stu-id="bc549-111">The following example uses foreign key navigation in the `Select` clause in Visual Basic (`select` clause in C#) to filter for pairs of employees where one employee reports to the other and where both employees are from the same `City`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a><span data-ttu-id="bc549-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="bc549-112">Example</span></span>  
 <span data-ttu-id="bc549-113">Aşağıdaki Visual Basic örnek tüm müşteriler ve siparişler için görünür, siparişler müşterilere eşleştirilir emin olur ve bu listedeki her müşteri için bir ilgili kişi adı sağlandığını güvence altına alır.</span><span class="sxs-lookup"><span data-stu-id="bc549-113">The following Visual Basic example looks for all customers and orders, makes sure that the orders are matched to customers, and guarantees that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a><span data-ttu-id="bc549-114">Örnek</span><span class="sxs-lookup"><span data-stu-id="bc549-114">Example</span></span>  
 <span data-ttu-id="bc549-115">Aşağıdaki örnek, her iki tablonun iki tabloları ve projelerin sonuçlarını açıkça birleştirir.</span><span class="sxs-lookup"><span data-stu-id="bc549-115">The following example explicitly joins two tables and projects results from both tables.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a><span data-ttu-id="bc549-116">Örnek</span><span class="sxs-lookup"><span data-stu-id="bc549-116">Example</span></span>  
 <span data-ttu-id="bc549-117">Aşağıdaki örnek, açıkça her biri üç tabloları ve projeleri sonuçları birleştirir.</span><span class="sxs-lookup"><span data-stu-id="bc549-117">The following example explicitly joins three tables and projects results from each of them.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a><span data-ttu-id="bc549-118">Örnek</span><span class="sxs-lookup"><span data-stu-id="bc549-118">Example</span></span>  
 <span data-ttu-id="bc549-119">Aşağıdaki örnek, elde etmek gösterilmiştir bir `LEFT OUTER JOIN` kullanarak `DefaultIfEmpty()`.</span><span class="sxs-lookup"><span data-stu-id="bc549-119">The following example shows how to achieve a `LEFT OUTER JOIN` by using `DefaultIfEmpty()`.</span></span> <span data-ttu-id="bc549-120">`DefaultIfEmpty()` Yöntemi null değerini döndürür olduğunda hiçbir `Order` için `Employee`.</span><span class="sxs-lookup"><span data-stu-id="bc549-120">The `DefaultIfEmpty()` method returns null when there is no `Order` for the `Employee`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a><span data-ttu-id="bc549-121">Örnek</span><span class="sxs-lookup"><span data-stu-id="bc549-121">Example</span></span>  
 <span data-ttu-id="bc549-122">Aşağıdaki örnek proje bir `let` birleştirme sonucu oluşan ifade.</span><span class="sxs-lookup"><span data-stu-id="bc549-122">The following example projects a `let` expression resulting from a join.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a><span data-ttu-id="bc549-123">Örnek</span><span class="sxs-lookup"><span data-stu-id="bc549-123">Example</span></span>  
 <span data-ttu-id="bc549-124">Aşağıdaki örnekte gösterildiği bir `join` bileşik anahtara sahip.</span><span class="sxs-lookup"><span data-stu-id="bc549-124">The following example shows a `join` with a composite key.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a><span data-ttu-id="bc549-125">Örnek</span><span class="sxs-lookup"><span data-stu-id="bc549-125">Example</span></span>  
 <span data-ttu-id="bc549-126">Aşağıdaki örnek nasıl oluşturulacağını gösterir. bir `join` burada bir tarafı null yapılabilir ve diğer değil.</span><span class="sxs-lookup"><span data-stu-id="bc549-126">The following example shows how to construct a `join` where one side is nullable and the other is not.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="bc549-127">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="bc549-127">See also</span></span>
- [<span data-ttu-id="bc549-128">Sorgu Örnekleri</span><span class="sxs-lookup"><span data-stu-id="bc549-128">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
