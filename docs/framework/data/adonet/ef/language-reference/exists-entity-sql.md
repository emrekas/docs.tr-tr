---
title: (Varlık SQL) var.
ms.date: 03/30/2017
ms.assetid: d28ead43-4afb-4bdc-af64-efd2e05005d7
ms.openlocfilehash: 72d96c5f24fcedf870370de3792680831145a454
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59311142"
---
# <a name="exists-entity-sql"></a><span data-ttu-id="d2c70-102">(Varlık SQL) var.</span><span class="sxs-lookup"><span data-stu-id="d2c70-102">EXISTS (Entity SQL)</span></span>
<span data-ttu-id="d2c70-103">Bir koleksiyonu boş olup olmadığını belirler.</span><span class="sxs-lookup"><span data-stu-id="d2c70-103">Determines if a collection is empty.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2c70-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="d2c70-104">Syntax</span></span>  
  
```  
[NOT] EXISTS ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="d2c70-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="d2c70-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="d2c70-106">Bir koleksiyonu döndüren herhangi bir geçerli ifade.</span><span class="sxs-lookup"><span data-stu-id="d2c70-106">Any valid expression that returns a collection.</span></span>  
  
 <span data-ttu-id="d2c70-107">DEĞİL</span><span class="sxs-lookup"><span data-stu-id="d2c70-107">NOT</span></span>  
 <span data-ttu-id="d2c70-108">EXISTS sonucunu negatif olduğunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="d2c70-108">Specifies that the result of EXISTS be negated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2c70-109">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="d2c70-109">Return Value</span></span>  
 `true` <span data-ttu-id="d2c70-110">koleksiyon boş değilse; Aksi takdirde, `false`.</span><span class="sxs-lookup"><span data-stu-id="d2c70-110">if the collection is not empty; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2c70-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d2c70-111">Remarks</span></span>  
 <span data-ttu-id="d2c70-112">EXISTS biridir [!INCLUDE[esql](../../../../../../includes/esql-md.md)] işleçleri ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="d2c70-112">EXISTS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="d2c70-113">Tüm [!INCLUDE[esql](../../../../../../includes/esql-md.md)] küme işleci soldan sağa doğru değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="d2c70-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="d2c70-114">Öncelik bilgilerini [!INCLUDE[esql](../../../../../../includes/esql-md.md)] işleçleri, bakın [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="d2c70-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2c70-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="d2c70-115">Example</span></span>  
 <span data-ttu-id="d2c70-116">Aşağıdaki varlık SQL sorgu EXISTS işleci koleksiyonun boş olup olmadığını belirlemek için kullanır.</span><span class="sxs-lookup"><span data-stu-id="d2c70-116">The following Entity SQL query uses the EXISTS operator to determine whether the collection is empty.</span></span> <span data-ttu-id="d2c70-117">Sorgu, AdventureWorks satış modelini temel alıyor.</span><span class="sxs-lookup"><span data-stu-id="d2c70-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d2c70-118">Derleme ve bu sorguyu çalıştırmak için bu adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="d2c70-118">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="d2c70-119">Verilen yordamı izleyin [nasıl yapılır: StructuralType sonuçları döndüren bir sorgu yürütme](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="d2c70-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="d2c70-120">Aşağıdaki sorguda bağımsız değişken olarak geçirmek `ExecuteStructuralTypeQuery` yöntemi:</span><span class="sxs-lookup"><span data-stu-id="d2c70-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EXISTS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#exists)]  
  
## <a name="see-also"></a><span data-ttu-id="d2c70-121">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d2c70-121">See also</span></span>

- [<span data-ttu-id="d2c70-122">Entity SQL Başvurusu</span><span class="sxs-lookup"><span data-stu-id="d2c70-122">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
