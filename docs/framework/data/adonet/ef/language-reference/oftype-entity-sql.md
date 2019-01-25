---
title: OFTYPE (varlık SQL)
ms.date: 03/30/2017
ms.assetid: 6d259ca7-bbf0-40f8-a154-181d25c0d67e
ms.openlocfilehash: 2b2ee1af536f1bd92faebbca45ec3c7acf79c43b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722575"
---
# <a name="oftype-entity-sql"></a><span data-ttu-id="0b818-102">OFTYPE (varlık SQL)</span><span class="sxs-lookup"><span data-stu-id="0b818-102">OFTYPE (Entity SQL)</span></span>
<span data-ttu-id="0b818-103">Belirli bir tür bir sorgu ifadesinden nesnelerinin bir koleksiyonunu döndürür.</span><span class="sxs-lookup"><span data-stu-id="0b818-103">Returns a collection of objects from a query expression that is of a specific type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b818-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="0b818-104">Syntax</span></span>  
  
```  
OFTYPE ( expression, [ONLY] test_type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="0b818-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="0b818-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="0b818-106">Nesnelerin bir koleksiyonunu döndürür herhangi bir geçerli ifade.</span><span class="sxs-lookup"><span data-stu-id="0b818-106">Any valid query expression that returns a collection of objects.</span></span>  
  
 `test_type`  
 <span data-ttu-id="0b818-107">Tarafından döndürülen her nesne sınanacak tür `expression` karşı.</span><span class="sxs-lookup"><span data-stu-id="0b818-107">The type to test each object returned by `expression` against.</span></span> <span data-ttu-id="0b818-108">Türü bir ad alanı tarafından nitelendirilmelidir.</span><span class="sxs-lookup"><span data-stu-id="0b818-108">The type must be qualified by a namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b818-109">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="0b818-109">Return Value</span></span>  
 <span data-ttu-id="0b818-110">Türündeki nesneler koleksiyonunu `test_type`, veya bir temel tür veya türetilmiş bir tür `test_type`.</span><span class="sxs-lookup"><span data-stu-id="0b818-110">A collection of objects that are of type `test_type`, or a base type or derived type of `test_type`.</span></span> <span data-ttu-id="0b818-111">YALNIZCA belirtilen yalnızca örnekler, `test_type` ya da boş bir koleksiyon döndürülür.</span><span class="sxs-lookup"><span data-stu-id="0b818-111">If ONLY is specified, only instances of the `test_type` or an empty collection will be returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b818-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="0b818-112">Remarks</span></span>  
 <span data-ttu-id="0b818-113">Bir `OFTYPE` koleksiyonun her öğesine karşı bir tür testi gerçekleştirmek için verilen bir tür ifadesi ifade belirtir.</span><span class="sxs-lookup"><span data-stu-id="0b818-113">An `OFTYPE` expression specifies a type expression that is issued to perform a type test against each element of a collection.</span></span>  <span data-ttu-id="0b818-114">`OFTYPE` İfade ya da olan öğeleri içeren belirtilen türe ait yeni bir koleksiyon oluşturur, tür veya alt türünü eşdeğerdir.</span><span class="sxs-lookup"><span data-stu-id="0b818-114">The `OFTYPE` expression produces a new collection of the specified type containing only those elements that were either equivalent to that type or a sub-type of it.</span></span>  
  
 <span data-ttu-id="0b818-115">Bir `OFTYPE` aşağıdaki sorgu ifadesinin bir kısaltma ifadesidir:</span><span class="sxs-lookup"><span data-stu-id="0b818-115">An `OFTYPE` expression is an abbreviation of the following query expression:</span></span>  
  
```  
select value treat(t as T) from ts as t where t is of (T)  
```  
  
 <span data-ttu-id="0b818-116">Çalışan bir alt yöneticisidir düşünüldüğünde, aşağıdaki ifade yalnızca çalışanlar koleksiyonu yöneticileri koleksiyonu oluşturur:</span><span class="sxs-lookup"><span data-stu-id="0b818-116">Given that a Manager is a subtype of Employee, the following expression produces a collection of only managers from a collection of employees:</span></span>  
  
```  
OfType(employees, NamespaceName.Manager)  
```  
  
 <span data-ttu-id="0b818-117">En fazla türü filtresi kullanarak koleksiyon türüne mümkündür:</span><span class="sxs-lookup"><span data-stu-id="0b818-117">It is also possible to up cast a collection using the type filter:</span></span>  
  
```  
OfType(executives, NamespaceName.Manager)  
```  
  
 <span data-ttu-id="0b818-118">Tüm Yöneticiler yöneticileri olduğundan, koleksiyon artık yöneticileri koleksiyonu olarak yazılmış olsa, elde edilen koleksiyon hala tüm özgün Yöneticiler içeriyor.</span><span class="sxs-lookup"><span data-stu-id="0b818-118">Since all executives are managers, the resulting collection still contains all the original executives, though the collection is now typed as a collection of managers.</span></span>  
  
 <span data-ttu-id="0b818-119">Aşağıdaki tabloda davranışını gösteren `OFTYPE` bazı desenleri üzerinden işleci.</span><span class="sxs-lookup"><span data-stu-id="0b818-119">The following table shows the behavior of the `OFTYPE` operator over some patterns.</span></span> <span data-ttu-id="0b818-120">Sağlayıcı çağrılmadan önce tüm istemci tarafında özel durumlar:</span><span class="sxs-lookup"><span data-stu-id="0b818-120">All exceptions are thrown from the client side before the provider is invoked:</span></span>  
  
|<span data-ttu-id="0b818-121">Desen</span><span class="sxs-lookup"><span data-stu-id="0b818-121">Pattern</span></span>|<span data-ttu-id="0b818-122">Davranış</span><span class="sxs-lookup"><span data-stu-id="0b818-122">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="0b818-123">OFTYPE(Collection(EntityType), EntityType)</span><span class="sxs-lookup"><span data-stu-id="0b818-123">OFTYPE(Collection(EntityType), EntityType)</span></span>|<span data-ttu-id="0b818-124">Collection(EntityType)</span><span class="sxs-lookup"><span data-stu-id="0b818-124">Collection(EntityType)</span></span>|  
|<span data-ttu-id="0b818-125">OFTYPE(Collection(complexType), ComplexType)</span><span class="sxs-lookup"><span data-stu-id="0b818-125">OFTYPE(Collection(ComplexType), ComplexType)</span></span>|<span data-ttu-id="0b818-126">Oluşturur</span><span class="sxs-lookup"><span data-stu-id="0b818-126">Throws</span></span>|  
|<span data-ttu-id="0b818-127">OFTYPE(Collection(RowType), RowType)</span><span class="sxs-lookup"><span data-stu-id="0b818-127">OFTYPE(Collection(RowType), RowType)</span></span>|<span data-ttu-id="0b818-128">Oluşturur</span><span class="sxs-lookup"><span data-stu-id="0b818-128">Throws</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0b818-129">Örnek</span><span class="sxs-lookup"><span data-stu-id="0b818-129">Example</span></span>  
 <span data-ttu-id="0b818-130">Aşağıdaki [!INCLUDE[esql](../../../../../../includes/esql-md.md)] sorgu OnsiteCourse nesnelerden oluşan bir koleksiyon bir koleksiyondan Elbette nesneler döndürmeye OFTYPE işleci kullanır.</span><span class="sxs-lookup"><span data-stu-id="0b818-130">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the OFTYPE operator to return a collection of OnsiteCourse objects from a collection of Course objects.</span></span> <span data-ttu-id="0b818-131">Sorgu dayanır [Okul modeli](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac).</span><span class="sxs-lookup"><span data-stu-id="0b818-131">The query is based on the [School Model](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac).</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#OFTYPE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#oftype)]  
  
## <a name="see-also"></a><span data-ttu-id="0b818-132">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="0b818-132">See also</span></span>
- [<span data-ttu-id="0b818-133">Entity SQL Başvurusu</span><span class="sxs-lookup"><span data-stu-id="0b818-133">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
