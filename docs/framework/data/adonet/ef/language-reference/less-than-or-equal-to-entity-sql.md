---
title: < = (küçüktür veya eşittir) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 7c46da5c-fa09-4d90-adcc-c7e1b769d8e6
ms.openlocfilehash: 91dc97b848fd67bad2ecb7abb8f16d72e80c2c4c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250463"
---
# <a name="-less-than-or-equal-to-entity-sql"></a><span data-ttu-id="dedfb-102">\<= (Küçüktür veya eşittir) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="dedfb-102">\<= (Less Than or Equal To) (Entity SQL)</span></span>
<span data-ttu-id="dedfb-103">Sol ifadenin doğru ifadeye eşit veya ondan küçük bir değere sahip olup olmadığını anlamak için iki ifadeyi karşılaştırır.</span><span class="sxs-lookup"><span data-stu-id="dedfb-103">Compares two expressions to determine whether the left expression has a value less than or equal to the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dedfb-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="dedfb-104">Syntax</span></span>  
  
```  
expression <= expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="dedfb-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="dedfb-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="dedfb-106">Herhangi bir geçerli ifade.</span><span class="sxs-lookup"><span data-stu-id="dedfb-106">Any valid expression.</span></span> <span data-ttu-id="dedfb-107">Her iki ifade örtülü olarak dönüştürülebilir veri türlerine sahip olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="dedfb-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="dedfb-108">Sonuç türleri</span><span class="sxs-lookup"><span data-stu-id="dedfb-108">Result Types</span></span>  
 <span data-ttu-id="dedfb-109">`true`sol ifade, doğru ifadeye eşit veya daha küçük bir değere sahipse; Aksi takdirde `false`,.</span><span class="sxs-lookup"><span data-stu-id="dedfb-109">`true` if the left expression has a value less than or equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dedfb-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="dedfb-110">Example</span></span>  
 <span data-ttu-id="dedfb-111">Aşağıdaki Entity SQL sorgusu, sol ifadenin doğru ifadeye eşit veya daha küçük bir değere sahip olup olmadığını belirleyecek iki ifadeyi karşılaştırmak için < = karşılaştırma işlecini kullanır.</span><span class="sxs-lookup"><span data-stu-id="dedfb-111">The following Entity SQL query uses <= comparison operator to compare two expressions to determine whether the left expression has a value less than or equal to the right expression.</span></span> <span data-ttu-id="dedfb-112">Sorgu AdventureWorks Sales modelini temel alır.</span><span class="sxs-lookup"><span data-stu-id="dedfb-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="dedfb-113">Bu sorguyu derlemek ve çalıştırmak için aşağıdaki adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="dedfb-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="dedfb-114">[Aşağıdaki adımları uygulayın: StructuralType sonuçları](../how-to-execute-a-query-that-returns-structuraltype-results.md)döndüren bir sorgu yürütün.</span><span class="sxs-lookup"><span data-stu-id="dedfb-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="dedfb-115">Aşağıdaki sorguyu `ExecuteStructuralTypeQuery` yöntemine bir bağımsız değişken olarak geçirin:</span><span class="sxs-lookup"><span data-stu-id="dedfb-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS_OR_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less_or_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="dedfb-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="dedfb-116">See also</span></span>

- [<span data-ttu-id="dedfb-117">Entity SQL Başvurusu</span><span class="sxs-lookup"><span data-stu-id="dedfb-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
