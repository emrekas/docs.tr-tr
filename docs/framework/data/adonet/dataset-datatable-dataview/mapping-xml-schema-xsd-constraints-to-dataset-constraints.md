---
title: XML Şeması (XSD) Kısıtlamalarını DataSet Kısıtlamaları ile Eşleme
ms.date: 03/30/2017
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
ms.openlocfilehash: cdbfba96c4cfe52cfbd58246be60842540a84754
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64603994"
---
# <a name="mapping-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="a28eb-102">XML Şeması (XSD) Kısıtlamalarını DataSet Kısıtlamaları ile Eşleme</span><span class="sxs-lookup"><span data-stu-id="a28eb-102">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="a28eb-103">XML Şeması Tanım Dili (XSD) öğeleri ve öznitelikleri tanımlar belirtilmesi kısıtlamaları sağlar.</span><span class="sxs-lookup"><span data-stu-id="a28eb-103">The XML Schema definition language (XSD) allows constraints to be specified on the elements and attributes it defines.</span></span> <span data-ttu-id="a28eb-104">Bir XML Şeması ilişkisel şemasında eşlerken bir <xref:System.Data.DataSet>, XML şema kısıtlamaları uygun ilişkisel tabloları ve sütunları kısıtlamalar eşleştirilmiş **veri kümesi**.</span><span class="sxs-lookup"><span data-stu-id="a28eb-104">When mapping an XML Schema to relational schema in a <xref:System.Data.DataSet>, XML Schema constraints are mapped to appropriate relational constraints on the tables and columns within the **DataSet**.</span></span>  
  
 <span data-ttu-id="a28eb-105">Bu bölümde, aşağıdaki XML şema kısıtlamaları eşleme ele alınmaktadır:</span><span class="sxs-lookup"><span data-stu-id="a28eb-105">This section discusses the mapping of the following XML Schema constraints:</span></span>  
  
- <span data-ttu-id="a28eb-106">Benzersizlik kısıtlamasını kullanarak belirtilen **benzersiz** öğesi.</span><span class="sxs-lookup"><span data-stu-id="a28eb-106">The uniqueness constraint specified using the **unique** element.</span></span>  
  
- <span data-ttu-id="a28eb-107">Anahtar kısıtlamasını kullanarak belirtilen **anahtar** öğesi.</span><span class="sxs-lookup"><span data-stu-id="a28eb-107">The key constraint specified using the **key** element.</span></span>  
  
- <span data-ttu-id="a28eb-108">Kullanarak belirtilen keyref kısıtlama **keyref** öğesi.</span><span class="sxs-lookup"><span data-stu-id="a28eb-108">The keyref constraint specified using the **keyref** element.</span></span>  
  
 <span data-ttu-id="a28eb-109">Bir öğe veya öznitelik bir kısıtlama kullanarak belirli kısıtlamalara belgenin herhangi bir örneğindeki öğe değerlerini belirtin.</span><span class="sxs-lookup"><span data-stu-id="a28eb-109">By using a constraint on an element or attribute, you specify certain restrictions on the values of the element in any instance of the document.</span></span> <span data-ttu-id="a28eb-110">Örneğin, bir anahtar kısıtlaması bir **CustomerID** alt öğesi bir **müşteri** şema öğesi gösterir değerlerini **CustomerID** alt öğesi olmalıdır. herhangi bir belge örneğindeki benzersiz ve null değerlere izin verilmemektedir.</span><span class="sxs-lookup"><span data-stu-id="a28eb-110">For example, a key constraint on a **CustomerID** child element of a **Customer** element in the schema indicates that the values of the **CustomerID** child element must be unique in any document instance, and that null values are not allowed.</span></span>  
  
 <span data-ttu-id="a28eb-111">Kısıtlamaları da arasında öğeleri ve özniteliklerinin belgede, belge içindeki bir ilişki kurmak için belirtilebilir.</span><span class="sxs-lookup"><span data-stu-id="a28eb-111">Constraints can also be specified between elements and attributes in a document, in order to establish a relationship within the document.</span></span> <span data-ttu-id="a28eb-112">Anahtar ve keyref kısıtlamaları şemada kısıtlamaları belge öğeleri ve öznitelikleri arasında bir ilişki výsledek belgenin içinde belirtmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="a28eb-112">The key and keyref constraints are used in the schema to specify the constraints within the document, resulting in a relationship between document elements and attributes.</span></span>  
  
 <span data-ttu-id="a28eb-113">Bu şema kısıtlamaları eşleme işlemi içinde oluşturulmuş tablolarda uygun kısıtlamaları dönüştürür **veri kümesi**.</span><span class="sxs-lookup"><span data-stu-id="a28eb-113">The mapping process converts these schema constraints into appropriate constraints on the tables created within the **DataSet**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a28eb-114">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="a28eb-114">In This Section</span></span>  
 [<span data-ttu-id="a28eb-115">Benzersiz XML Şeması (XSD) Kısıtlamalarını DataSet Kısıtlamaları ile Eşleme</span><span class="sxs-lookup"><span data-stu-id="a28eb-115">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="a28eb-116">İçinde benzersiz kısıtlamalar oluşturmak için kullanılan XML Şeması öğeleri açıklar bir **veri kümesi**.</span><span class="sxs-lookup"><span data-stu-id="a28eb-116">Describes the XML Schema elements used to create unique constraints in a **DataSet**.</span></span>  
  
 [<span data-ttu-id="a28eb-117">Anahtar XML Şeması (XSD) Kısıtlamalarını DataSet Kısıtlamaları ile Eşleme</span><span class="sxs-lookup"><span data-stu-id="a28eb-117">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="a28eb-118">İçindeki anahtar kısıtlamaları (benzersiz kısıtlamalar burada null değerlere izin verilmez) oluşturmak için kullanılan XML Şeması öğeleri açıklar bir **veri kümesi**.</span><span class="sxs-lookup"><span data-stu-id="a28eb-118">Describes the XML Schema elements used to create key constraints (unique constraints where null values are not allowed) in a **DataSet**.</span></span>  
  
 [<span data-ttu-id="a28eb-119">Keyref XML Şeması (XSD) Kısıtlamalarını DataSet Kısıtlamaları ile Eşleme</span><span class="sxs-lookup"><span data-stu-id="a28eb-119">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="a28eb-120">Keyref (yabancı anahtar) kısıtlamalarını oluşturmak için kullanılan XML Şeması öğeleri açıklar bir **veri kümesi**.</span><span class="sxs-lookup"><span data-stu-id="a28eb-120">Describes the XML Schema elements used to create keyref (foreign key) constraints in a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a28eb-121">İlgili Bölümler</span><span class="sxs-lookup"><span data-stu-id="a28eb-121">Related Sections</span></span>  
 [<span data-ttu-id="a28eb-122">XML Şemasından (XSD) DataSet İlişkisel Yapısını Türetme</span><span class="sxs-lookup"><span data-stu-id="a28eb-122">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="a28eb-123">İlişkisel yapısını veya şema biri açıklar bir **veri kümesi** XSD şema oluşturuldu.</span><span class="sxs-lookup"><span data-stu-id="a28eb-123">Describes the relational structure, or schema, of a **DataSet** that is created from XSD schema.</span></span>  
  
 [<span data-ttu-id="a28eb-124">XML Şemasından (XSD) DataSet İlişkileri Oluşturma</span><span class="sxs-lookup"><span data-stu-id="a28eb-124">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="a28eb-125">Tablo sütunlarını arasındaki ilişkileri oluşturmak için kullanılan XML Şeması öğeleri açıklar bir **veri kümesi**.</span><span class="sxs-lookup"><span data-stu-id="a28eb-125">Describes the XML Schema elements used to create relations between table columns in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a28eb-126">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="a28eb-126">See also</span></span>

- [<span data-ttu-id="a28eb-127">ADO.NET yönetilen sağlayıcıları ve DataSet Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="a28eb-127">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
