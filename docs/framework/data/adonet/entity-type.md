---
title: varlık türü
ms.date: 03/30/2017
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
ms.openlocfilehash: cb542a1750a6b45dd2fca4d32501719470d9a78a
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410894"
---
# <a name="entity-type"></a><span data-ttu-id="bed73-102">varlık türü</span><span class="sxs-lookup"><span data-stu-id="bed73-102">entity type</span></span>
<span data-ttu-id="bed73-103">*Varlık türü* varlık veri modeli (EDM) ile verilerin yapısını tanımlamak için temel yapı taşı.</span><span class="sxs-lookup"><span data-stu-id="bed73-103">The *entity type* is the fundamental building block for describing the structure of data with the Entity Data Model (EDM).</span></span> <span data-ttu-id="bed73-104">Kavramsal bir modeli içinde bir varlık türü müşteriler veya siparişler gibi üst düzey kavramlar yapısını temsil eder.</span><span class="sxs-lookup"><span data-stu-id="bed73-104">In a conceptual model, an entity type represents the structure of top-level concepts, such as customers or orders.</span></span> <span data-ttu-id="bed73-105">Bir varlık türünün varlık türü örnekleri için bir şablondur.</span><span class="sxs-lookup"><span data-stu-id="bed73-105">An entity type is a template for entity type instances.</span></span> <span data-ttu-id="bed73-106">Her şablon, aşağıdaki bilgileri içerir:</span><span class="sxs-lookup"><span data-stu-id="bed73-106">Each template contains the following information:</span></span>  
  
-   <span data-ttu-id="bed73-107">Benzersiz bir ad.</span><span class="sxs-lookup"><span data-stu-id="bed73-107">A unique name.</span></span> <span data-ttu-id="bed73-108">(Gerekli)</span><span class="sxs-lookup"><span data-stu-id="bed73-108">(Required.)</span></span>  
  
-   <span data-ttu-id="bed73-109">Bir [Varlık anahtarı](../../../../docs/framework/data/adonet/entity-key.md) bir veya daha fazla özellikleri tarafından tanımlanan.</span><span class="sxs-lookup"><span data-stu-id="bed73-109">An [entity key](../../../../docs/framework/data/adonet/entity-key.md) defined by one or more properties.</span></span> <span data-ttu-id="bed73-110">(Gerekli)</span><span class="sxs-lookup"><span data-stu-id="bed73-110">(Required.)</span></span>  
  
-   <span data-ttu-id="bed73-111">Veri biçiminde [özellikleri](../../../../docs/framework/data/adonet/property.md).</span><span class="sxs-lookup"><span data-stu-id="bed73-111">Data in the form of [properties](../../../../docs/framework/data/adonet/property.md).</span></span> <span data-ttu-id="bed73-112">(İsteğe bağlı.)</span><span class="sxs-lookup"><span data-stu-id="bed73-112">(Optional.)</span></span>  
  
-   <span data-ttu-id="bed73-113">[Gezinti özellikleri](../../../../docs/framework/data/adonet/navigation-property.md) tanıyan bir gezinti için [son](../../../../docs/framework/data/adonet/association-end.md) , bir [ilişkilendirme](../../../../docs/framework/data/adonet/association-type.md) diğer ucuna.</span><span class="sxs-lookup"><span data-stu-id="bed73-113">[Navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) that allow for navigation from one [end](../../../../docs/framework/data/adonet/association-end.md) of an [association](../../../../docs/framework/data/adonet/association-type.md) to the other end.</span></span> <span data-ttu-id="bed73-114">(İsteğe bağlı)</span><span class="sxs-lookup"><span data-stu-id="bed73-114">(Optional)</span></span>  
  
 <span data-ttu-id="bed73-115">Bir uygulamada (örneğin, belirli müşteri veya sipariş) belirli bir nesnesi bir varlık türünün bir örneği temsil eder.</span><span class="sxs-lookup"><span data-stu-id="bed73-115">In an application, an instance of an entity type represents a specific object (such as a specific customer or order).</span></span> <span data-ttu-id="bed73-116">Bir varlık türünün her örneğinin benzersiz olmalıdır [Varlık anahtarı](../../../../docs/framework/data/adonet/entity-key.md) içinde bir [varlık kümesi](../../../../docs/framework/data/adonet/entity-set.md).</span><span class="sxs-lookup"><span data-stu-id="bed73-116">Each instance of an entity type must have a unique [entity key](../../../../docs/framework/data/adonet/entity-key.md) within an [entity set](../../../../docs/framework/data/adonet/entity-set.md).</span></span>  
  
 <span data-ttu-id="bed73-117">İki varlık türü örnekleri yalnızca aynı türde oldukları ve bunların varlık anahtarları aynı değerleri eşit olarak kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="bed73-117">Two entity type instances are considered equal only if they are of the same type and the values of their entity keys are the same.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bed73-118">Örnek</span><span class="sxs-lookup"><span data-stu-id="bed73-118">Example</span></span>  
 <span data-ttu-id="bed73-119">Varlık üç kavramsal bir modelle Aşağıdaki diyagramda gösterilmektedir: `Book`, `Publisher`, ve `Author`:</span><span class="sxs-lookup"><span data-stu-id="bed73-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`:</span></span>  
  
 ![Üç varlık türleri ile örnek modeli](./media/entity-type/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="bed73-121">Her varlık türünün varlık anahtarıyla olun özellikleri "(anahtar)" ile belirtilir unutmayın.</span><span class="sxs-lookup"><span data-stu-id="bed73-121">Note that the properties of each entity type that make up its entity key are denoted with "(Key)".</span></span>  
  
 <span data-ttu-id="bed73-122">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) kavramsal şema tanım dili olarak adlandırılan bir etki alanına özgü dil (DSL) kullanır ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) kavramsal modeller tanımlamak için.</span><span class="sxs-lookup"><span data-stu-id="bed73-122">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="bed73-123">Aşağıdaki CSDL tanımlar `Book` Yukarıdaki diyagramda gösterilen varlık türü:</span><span class="sxs-lookup"><span data-stu-id="bed73-123">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a><span data-ttu-id="bed73-124">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="bed73-124">See also</span></span>
- [<span data-ttu-id="bed73-125">Varlık Veri Modeli Temel Kavramları</span><span class="sxs-lookup"><span data-stu-id="bed73-125">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="bed73-126">Varlık Veri Modeli</span><span class="sxs-lookup"><span data-stu-id="bed73-126">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
- [<span data-ttu-id="bed73-127">facet</span><span class="sxs-lookup"><span data-stu-id="bed73-127">facet</span></span>](../../../../docs/framework/data/adonet/facet.md)
