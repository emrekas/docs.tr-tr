---
title: (Varlık SQL) kullanma
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: e14b7857a65898683939647c872c48d0b3fe458a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034113"
---
# <a name="using-entity-sql"></a><span data-ttu-id="70ffa-102">(Varlık SQL) kullanma</span><span class="sxs-lookup"><span data-stu-id="70ffa-102">USING (Entity SQL)</span></span>
<span data-ttu-id="70ffa-103">Bir sorgu ifadesinde kullanılan ad alanlarını belirtir.</span><span class="sxs-lookup"><span data-stu-id="70ffa-103">Specifies namespaces used in a query expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70ffa-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="70ffa-104">Syntax</span></span>  
  
```  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="70ffa-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="70ffa-105">Arguments</span></span>  
 `alias`  
 <span data-ttu-id="70ffa-106">Bir ad alanı ile nitelemek için daha kısa bir diğer ad belirtir.</span><span class="sxs-lookup"><span data-stu-id="70ffa-106">Specifies a shorter alias to qualify a namespace with.</span></span>  
  
 `namespace`  
 <span data-ttu-id="70ffa-107">Geçerli bir ad alanı.</span><span class="sxs-lookup"><span data-stu-id="70ffa-107">Any valid namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70ffa-108">Örnek</span><span class="sxs-lookup"><span data-stu-id="70ffa-108">Example</span></span>  
 <span data-ttu-id="70ffa-109">Aşağıdaki varlık SQL sorgusunu kullanarak işleci bir sorgu ifadesinde kullanılan ad alanları belirtmek için kullanır.</span><span class="sxs-lookup"><span data-stu-id="70ffa-109">The following Entity SQL query uses the USING operator to specify namespaces used in a query expression.</span></span> <span data-ttu-id="70ffa-110">Derleme ve bu sorguyu çalıştırmak için bu adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="70ffa-110">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="70ffa-111">Verilen yordamı izleyin [nasıl yapılır: PrimitiveType sonuçları döndüren bir sorgu yürütme](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="70ffa-111">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="70ffa-112">Aşağıdaki sorguda bağımsız değişken olarak geçirmek `ExecutePrimitiveTypeQuery` yöntemi:</span><span class="sxs-lookup"><span data-stu-id="70ffa-112">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
```  
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a><span data-ttu-id="70ffa-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="70ffa-113">See also</span></span>

- [<span data-ttu-id="70ffa-114">Ad Alanları</span><span class="sxs-lookup"><span data-stu-id="70ffa-114">Namespaces</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)
- [<span data-ttu-id="70ffa-115">Entity SQL Başvurusu</span><span class="sxs-lookup"><span data-stu-id="70ffa-115">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
