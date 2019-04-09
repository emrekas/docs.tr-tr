---
title: XML Şema Kısıtlamaları ve İlişkileri
ms.date: 03/30/2017
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
ms.openlocfilehash: 990ae2eef8d9fbd28472494c989ae9ecca34251d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119788"
---
# <a name="xml-schema-constraints-and-relationships"></a><span data-ttu-id="371e7-102">XML Şema Kısıtlamaları ve İlişkileri</span><span class="sxs-lookup"><span data-stu-id="371e7-102">XML Schema Constraints and Relationships</span></span>
<span data-ttu-id="371e7-103">Bir XML Şeması Tanım Dili (XSD) şemasında kısıtlamaları belirtebilirsiniz (benzersiz anahtar ve keyref kısıtlamaları) ve ilişkileri (kullanarak **msdata:Relationship** ek açıklama).</span><span class="sxs-lookup"><span data-stu-id="371e7-103">In an XML Schema definition language (XSD) schema, you can specify constraints (unique, key, and keyref constraints) and relationships (using the **msdata:Relationship** annotation).</span></span> <span data-ttu-id="371e7-104">Bu konu, kısıtlamaları ve bir XML şemasında belirtilen ilişkileri oluşturmak için nasıl yorumlanır açıklar <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="371e7-104">This topic explains how the constraints and relationships specified in an XML Schema are interpreted to generate the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="371e7-105">Genel olarak, bir XML şeması içinde belirttiğiniz **msdata:Relationship** yalnızca ilişkileri oluşturmak istiyorsanız ek açıklama **veri kümesi**.</span><span class="sxs-lookup"><span data-stu-id="371e7-105">In general, in an XML Schema, you specify the **msdata:Relationship** annotation if you want to generate only relationships in the **DataSet**.</span></span> <span data-ttu-id="371e7-106">Daha fazla bilgi için [gelen XML Şeması (XSD) DataSet ilişkileri oluşturma](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="371e7-106">For more information, see [Generating DataSet Relations from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md).</span></span> <span data-ttu-id="371e7-107">Kısıtlamaları belirtin (benzersiz anahtar ve keyref) kısıtlamalarını oluşturmak istiyorsanız **veri kümesi**.</span><span class="sxs-lookup"><span data-stu-id="371e7-107">You specify constraints (unique, key, and keyref) if you want to generate constraints in the **DataSet**.</span></span> <span data-ttu-id="371e7-108">Anahtar ve keyref kısıtlamaları da ilişkiler oluşturmak için bu konunun ilerleyen kısımlarında açıklandığı gibi kullanıldığını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="371e7-108">Note that the key and keyref constraints are also used to generate relationships, as explained later in this topic.</span></span>  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a><span data-ttu-id="371e7-109">Anahtar ve keyref kısıtlamaları bir ilişki oluşturma</span><span class="sxs-lookup"><span data-stu-id="371e7-109">Generating a Relationship from key and keyref Constraints</span></span>  
 <span data-ttu-id="371e7-110">Belirtmek yerine **msdata:Relationship** ek açıklama, XML şema eşleme işlemi sırasında yalnızca kısıtlamaları aynı zamanda ilişki içinde oluşturmakiçinkullanılananahtarvekeyrefkısıtlamalarıbelirtebilirsiniz **Veri kümesi**.</span><span class="sxs-lookup"><span data-stu-id="371e7-110">Instead of specifying the **msdata:Relationship** annotation, you can specify key and keyref constraints, which are used during the XML Schema mapping process to generate not only the constraints but also the relationship in the **DataSet**.</span></span> <span data-ttu-id="371e7-111">Ancak, belirtirseniz `msdata:ConstraintOnly="true"` içinde **keyref** öğesi **veri kümesi** yalnızca kısıtlamaları içerir ve ilişki içermez.</span><span class="sxs-lookup"><span data-stu-id="371e7-111">However, if you specify `msdata:ConstraintOnly="true"` in the **keyref** element, the **DataSet** will include only the constraints and will not include the relationship.</span></span>  
  
 <span data-ttu-id="371e7-112">İçeren bir XML Şeması aşağıdaki örnekte **sipariş** ve **OrderDetail** öğelerinin iç içe yerleştirilmiş.</span><span class="sxs-lookup"><span data-stu-id="371e7-112">The following example shows an XML Schema that includes **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="371e7-113">Şema ayrıca anahtarı ve keyref kısıtlamaları belirtir.</span><span class="sxs-lookup"><span data-stu-id="371e7-113">The schema also specifies key and keyref constraints.</span></span>  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element name="OrderDetail">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNo" type="xs:integer" />  
           <xs:element name="ItemNo" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
      <xs:element name="Order">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:key name="OrderNumberKey"  >  
    <xs:selector xpath=".//Order" />  
    <xs:field xpath="OrderNumber" />  
  </xs:key>  
  
  <xs:keyref name="OrderNoRef" refer="OrderNumberKey">  
    <xs:selector xpath=".//OrderDetail" />  
    <xs:field xpath="OrderNo" />  
  </xs:keyref>  
 </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="371e7-114">**Veri kümesi** eşleme işlemini içeren XML Şeması sırasında oluşturulan **sipariş** ve **OrderDetail** tablolar.</span><span class="sxs-lookup"><span data-stu-id="371e7-114">The **DataSet** that is generated during the XML Schema mapping process includes the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="371e7-115">Ayrıca, **veri kümesi** ilişkiler ve kısıtlamalar içerir.</span><span class="sxs-lookup"><span data-stu-id="371e7-115">In addition, the **DataSet** includes relationships and constraints.</span></span> <span data-ttu-id="371e7-116">Aşağıdaki örnek, bu ilişkileri ve kısıtlamaları gösterir.</span><span class="sxs-lookup"><span data-stu-id="371e7-116">The following example shows these relationships and constraints.</span></span> <span data-ttu-id="371e7-117">Şema belirttiğinde Not **msdata:Relationship** ek açıklama; bunun yerine, anahtar ve keyref kısıtlamaları ilişki oluşturmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="371e7-117">Note that the schema does not specify the **msdata:Relationship** annotation; instead, the key and keyref constraints are used to generate the relation.</span></span>  
  
```  
....ConstraintName: OrderNumberKey  
....Type: UniqueConstraint  
....Table: Order  
....Columns: OrderNumber  
....IsPrimaryKey: False  
  
....ConstraintName: OrderNoRef  
....Type: ForeignKeyConstraint  
....Table: OrderDetail  
....Columns: OrderNo  
....RelatedTable: Order  
....RelatedColumns: OrderNumber  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
```  
  
 <span data-ttu-id="371e7-118">Önceki örnekte şema, **sipariş** ve **OrderDetail** öğeleri içe değil.</span><span class="sxs-lookup"><span data-stu-id="371e7-118">In the previous schema example, the **Order** and **OrderDetail** elements are not nested.</span></span> <span data-ttu-id="371e7-119">Aşağıdaki şema örnekte, bu öğeleri iç içe geçirilmiştir.</span><span class="sxs-lookup"><span data-stu-id="371e7-119">In the following schema example, these elements are nested.</span></span> <span data-ttu-id="371e7-120">Ancak, hiçbir **msdata:Relationship** ek açıklaması belirtildiğinde; bu nedenle, örtük bir ilişkisi olduğu varsayılır.</span><span class="sxs-lookup"><span data-stu-id="371e7-120">However, no **msdata:Relationship** annotation is specified; therefore, an implicit relation is assumed.</span></span> <span data-ttu-id="371e7-121">Daha fazla bilgi için [harita örtük ilişkileri arasında iç içe geçmiş şema öğeleri](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md).</span><span class="sxs-lookup"><span data-stu-id="371e7-121">For more information, see [Map Implicit Relations Between Nested Schema Elements](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md).</span></span> <span data-ttu-id="371e7-122">Şema ayrıca anahtarı ve keyref kısıtlamaları belirtir.</span><span class="sxs-lookup"><span data-stu-id="371e7-122">The schema also specifies key and keyref constraints.</span></span>  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
  
      <xs:element name="Order">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
  
            <xs:element name="OrderDetail">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="OrderNo" type="xs:integer" />  
                  <xs:element name="ItemNo" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:key name="OrderNumberKey"  >  
    <xs:selector xpath=".//Order" />  
    <xs:field xpath="OrderNumber" />  
  </xs:key>  
  
  <xs:keyref name="OrderNoRef" refer="OrderNumberKey">  
    <xs:selector xpath=".//OrderDetail" />  
    <xs:field xpath="OrderNo" />  
  </xs:keyref>  
 </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="371e7-123">**Veri kümesi** XML Şeması eşleme işleminden kaynaklanan iki tablo içerir:</span><span class="sxs-lookup"><span data-stu-id="371e7-123">The **DataSet** resulting from the XML Schema mapping process includes two tables:</span></span>  
  
```  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 <span data-ttu-id="371e7-124">**Veri kümesi** iki ilişki de dahildir (temel alan bir **msdata:relationship** ek açıklama ve diğer temel anahtar ve keyref kısıtlamalar) ve çeşitli kısıtlamalar.</span><span class="sxs-lookup"><span data-stu-id="371e7-124">The **DataSet** also includes the two relationships (one based on the **msdata:relationship** annotation and the other based on the key and keyref constraints) and various constraints.</span></span> <span data-ttu-id="371e7-125">Aşağıdaki örnek, kısıtlamaları ve ilişkileri gösterir.</span><span class="sxs-lookup"><span data-stu-id="371e7-125">The following example shows the relations and constraints.</span></span>  
  
```  
..RelationName: Order_OrderDetail  
..ParentTable: Order  
..ParentColumns: Order_Id  
..ChildTable: OrderDetail  
..ChildColumns: Order_Id  
..ParentKeyConstraint: Constraint1  
..ChildKeyConstraint: Order_OrderDetail  
..Nested: True  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
  
..ConstraintName: OrderNumberKey  
..Type: UniqueConstraint  
..Table: Order  
..Columns: OrderNumber  
..IsPrimaryKey: False  
  
..ConstraintName: Constraint1  
..Type: UniqueConstraint  
..Table: Order  
..Columns: Order_Id  
..IsPrimaryKey: True  
  
..ConstraintName: Order_OrderDetail  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: Order_Id  
..RelatedTable: Order  
..RelatedColumns: Order_Id  
  
..ConstraintName: OrderNoRef  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: OrderNo  
..RelatedTable: Order  
..RelatedColumns: OrderNumber  
```  
  
 <span data-ttu-id="371e7-126">İç içe geçmiş tablosuna başvuran keyref kısıtlama içerip içermediğini **msdata:IsNested = "true"** ek açıklama, **veri kümesi** keyref kısıtlaması dayalı tek bir iç içe geçmiş ilişkisi oluşturmanız gerekir ve ilgili benzersiz/key kısıtlaması.</span><span class="sxs-lookup"><span data-stu-id="371e7-126">If a keyref constraint referring to a nested table contains the **msdata:IsNested="true"** annotation, the **DataSet** will create a single nested relationship that is based on the keyref constraint and the related unique/key constraint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="371e7-127">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="371e7-127">See also</span></span>

- [<span data-ttu-id="371e7-128">XML Şemasından (XSD) DataSet İlişkisel Yapısını Türetme</span><span class="sxs-lookup"><span data-stu-id="371e7-128">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="371e7-129">ADO.NET yönetilen sağlayıcıları ve DataSet Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="371e7-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
