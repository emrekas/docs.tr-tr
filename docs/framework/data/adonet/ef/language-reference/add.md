---
title: + (Ekle)
ms.date: 03/30/2017
ms.assetid: 51769b02-a8f7-4177-9e99-bbd10e77092c
ms.openlocfilehash: 1c525a1cd56d1d8b7ed0dad3a7cec686cb6b1ab3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580661"
---
# <a name="-add"></a><span data-ttu-id="ae0f8-102">+ (Add)</span><span class="sxs-lookup"><span data-stu-id="ae0f8-102">+ (Add)</span></span>
<span data-ttu-id="ae0f8-103">İki sayıyı ekler.</span><span class="sxs-lookup"><span data-stu-id="ae0f8-103">Adds two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae0f8-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="ae0f8-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="ae0f8-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="ae0f8-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ae0f8-106">Herhangi bir geçerli ifade herhangi birinin sayısal veri türleri.</span><span class="sxs-lookup"><span data-stu-id="ae0f8-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ae0f8-107">Sonuç türleri</span><span class="sxs-lookup"><span data-stu-id="ae0f8-107">Result Types</span></span>  
 <span data-ttu-id="ae0f8-108">Bu iki bağımsız değişken örtük tür yükseltme sonuçlarından veri türü.</span><span class="sxs-lookup"><span data-stu-id="ae0f8-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="ae0f8-109">Örtük tür yükseltme hakkında daha fazla bilgi için bkz: [tür sistemi](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="ae0f8-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae0f8-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ae0f8-110">Remarks</span></span>  
 <span data-ttu-id="ae0f8-111">EDM için. Dize türleri, ayrıca birleştirme olur.</span><span class="sxs-lookup"><span data-stu-id="ae0f8-111">For EDM.String types, addition is concatenation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae0f8-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="ae0f8-112">Example</span></span>  
 <span data-ttu-id="ae0f8-113">Aşağıdaki varlık SQL sorgusu kullanır + iki sayıları aritmetik işleç.</span><span class="sxs-lookup"><span data-stu-id="ae0f8-113">The following Entity SQL query uses the + arithmetic operator to add two numbers.</span></span> <span data-ttu-id="ae0f8-114">Sorgu, AdventureWorks satış modelini temel alıyor.</span><span class="sxs-lookup"><span data-stu-id="ae0f8-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ae0f8-115">Derleme ve bu sorguyu çalıştırmak için bu adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="ae0f8-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="ae0f8-116">Verilen yordamı izleyin [nasıl yapılır: StructuralType sonuçları döndüren bir sorgu yürütme](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="ae0f8-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="ae0f8-117">Aşağıdaki sorguda bağımsız değişken olarak geçirmek `ExecuteStructuralTypeQuery` yöntemi:</span><span class="sxs-lookup"><span data-stu-id="ae0f8-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ADD](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#add)]  
  
## <a name="see-also"></a><span data-ttu-id="ae0f8-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="ae0f8-118">See also</span></span>
- [<span data-ttu-id="ae0f8-119">Entity SQL Başvurusu</span><span class="sxs-lookup"><span data-stu-id="ae0f8-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="ae0f8-120">Kavramsal Model türleri (CSDL)</span><span class="sxs-lookup"><span data-stu-id="ae0f8-120">Conceptual Model Types (CSDL)</span></span>](https://msdn.microsoft.com/library/987b995f-e429-4569-9559-b4146744def4)
