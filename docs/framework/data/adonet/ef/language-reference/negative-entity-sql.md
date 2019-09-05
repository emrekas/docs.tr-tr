---
title: '- Negatif (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
ms.openlocfilehash: effd537bcd53052830f2195e18ca959b49d87255
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249932"
---
# <a name="--negative-entity-sql"></a><span data-ttu-id="84c4d-102">-(Negatif) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="84c4d-102">- (Negative) (Entity SQL)</span></span>
<span data-ttu-id="84c4d-103">Sayısal bir ifadenin değerinin negatifini döndürür.</span><span class="sxs-lookup"><span data-stu-id="84c4d-103">Returns the negative of the value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84c4d-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="84c4d-104">Syntax</span></span>  
  
```  
- expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="84c4d-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="84c4d-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="84c4d-106">Sayısal veri türlerinden herhangi birinin geçerli bir ifadesi.</span><span class="sxs-lookup"><span data-stu-id="84c4d-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="84c4d-107">Sonuç türleri</span><span class="sxs-lookup"><span data-stu-id="84c4d-107">Result Types</span></span>  
 <span data-ttu-id="84c4d-108">Veri türü `expression`.</span><span class="sxs-lookup"><span data-stu-id="84c4d-108">The data type of `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84c4d-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="84c4d-109">Remarks</span></span>  
 <span data-ttu-id="84c4d-110">İmzasız bir tür ise, sonuç türü, `expression`türü ile en yakından ilişkili olan imzalı tür olur. `expression`</span><span class="sxs-lookup"><span data-stu-id="84c4d-110">If `expression` is an unsigned type, the result type will be the signed type that most closely relates to the type of `expression`.</span></span> <span data-ttu-id="84c4d-111">Örneğin, `expression` Byte türünde ise, Int16 türünde bir değer döndürülür.</span><span class="sxs-lookup"><span data-stu-id="84c4d-111">For example, if `expression` is of type Byte, a value of type Int16 will be returned.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84c4d-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="84c4d-112">Example</span></span>  
 <span data-ttu-id="84c4d-113">Aşağıdaki Entity SQL sorgusu, bir sayısal ifadenin değerinin negatifini döndürmek için-aritmetik işlecini kullanır.</span><span class="sxs-lookup"><span data-stu-id="84c4d-113">The following Entity SQL query uses the - arithmetic operator to return the negative of the value of a numeric expression.</span></span> <span data-ttu-id="84c4d-114">Sorgu AdventureWorks Sales modelini temel alır.</span><span class="sxs-lookup"><span data-stu-id="84c4d-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="84c4d-115">Bu sorguyu derlemek ve çalıştırmak için aşağıdaki adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="84c4d-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="84c4d-116">[Aşağıdaki adımları uygulayın: StructuralType sonuçları](../how-to-execute-a-query-that-returns-structuraltype-results.md)döndüren bir sorgu yürütün.</span><span class="sxs-lookup"><span data-stu-id="84c4d-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="84c4d-117">Aşağıdaki sorguyu `ExecuteStructuralTypeQuery` yöntemine bir bağımsız değişken olarak geçirin:</span><span class="sxs-lookup"><span data-stu-id="84c4d-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NEGATIVE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#negative)]  
  
## <a name="see-also"></a><span data-ttu-id="84c4d-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="84c4d-118">See also</span></span>

- [<span data-ttu-id="84c4d-119">Entity SQL Başvurusu</span><span class="sxs-lookup"><span data-stu-id="84c4d-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
