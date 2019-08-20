---
title: 'Nasıl yapılır: Iki koleksiyonu birleştirin (LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 7b817ede-911a-4cff-9dd3-639c3fc228c9
ms.openlocfilehash: aa774e23cfd232709f9824826f5084fe6049ef37
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69593201"
---
# <a name="how-to-join-two-collections-linq-to-xml-c"></a><span data-ttu-id="67ba9-102">Nasıl yapılır: Iki koleksiyonu birleştirin (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="67ba9-102">How to: Join Two Collections (LINQ to XML) (C#)</span></span>
<span data-ttu-id="67ba9-103">XML belgesindeki bir öğe veya öznitelik, bazen başka bir öğe veya özniteliğe başvurabilir.</span><span class="sxs-lookup"><span data-stu-id="67ba9-103">An element or attribute in an XML document can sometimes refer to another element or attribute.</span></span> <span data-ttu-id="67ba9-104">Örneğin, [örnek xml dosyası: Müşteriler ve siparişler (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md) XML belgesi, müşterilerin ve siparişlerin listesinin bir listesini içerir.</span><span class="sxs-lookup"><span data-stu-id="67ba9-104">For example, the [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md) XML document contains a list of customers and a list of orders.</span></span> <span data-ttu-id="67ba9-105">Her `Customer` öğe bir `CustomerID` özniteliği içerir.</span><span class="sxs-lookup"><span data-stu-id="67ba9-105">Each `Customer` element contains a `CustomerID` attribute.</span></span> <span data-ttu-id="67ba9-106">Her `Order` öğe bir `CustomerID` öğesi içerir.</span><span class="sxs-lookup"><span data-stu-id="67ba9-106">Each `Order` element contains a `CustomerID` element.</span></span> <span data-ttu-id="67ba9-107">Her siparişte bulunan `CustomerID` `CustomerID` öğe, bir müşterinin özniteliği anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="67ba9-107">The `CustomerID` element in each order refers to the `CustomerID` attribute in a customer.</span></span>  
  
 <span data-ttu-id="67ba9-108">[Örnek örnek xsd dosyası: Müşteriler ve siparişler](./sample-xsd-file-customers-and-orders1.md) , bu belgeyi doğrulamak için kullanılabilecek bir xsd içerir.</span><span class="sxs-lookup"><span data-stu-id="67ba9-108">The topic [Sample XSD File: Customers and Orders](./sample-xsd-file-customers-and-orders1.md) contains an XSD that can be used to validate this document.</span></span> <span data-ttu-id="67ba9-109">`xs:key` `CustomerID` `xs:keyref`Öğeözniteliğinin biranahtar`CustomerID` olduğunu ve her`Order` öğe ve içindeki öğe arasında bir ilişki oluşturmasını sağlamak için xsd 'nin ve özelliklerini kullanır. `Customer` `CustomerID` her`Customer` öğe için özniteliği.</span><span class="sxs-lookup"><span data-stu-id="67ba9-109">It uses the `xs:key` and `xs:keyref` features of XSD to establish that the `CustomerID` attribute of the `Customer` element is a key, and to establish a relationship between the `CustomerID` element in each `Order` element and the `CustomerID` attribute in each `Customer` element.</span></span>  
  
 <span data-ttu-id="67ba9-110">İle [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], `join` yan tümcesini kullanarak bu ilişkiyi kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="67ba9-110">With [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can take advantage of this relationship by using the `join` clause.</span></span>  
  
 <span data-ttu-id="67ba9-111">Kullanılabilir dizin olmadığından, bu tür bir birleştirme çalışma zamanı performansına sahip olacaktır.</span><span class="sxs-lookup"><span data-stu-id="67ba9-111">Note that because there is no index available, such joining will have poor runtime performance.</span></span>  
  
 <span data-ttu-id="67ba9-112">Hakkında `join`daha ayrıntılı bilgi için bkz. [JOIN Operations (C#)](./join-operations.md).</span><span class="sxs-lookup"><span data-stu-id="67ba9-112">For more detailed information about `join`, see [Join Operations (C#)](./join-operations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="67ba9-113">Örnek</span><span class="sxs-lookup"><span data-stu-id="67ba9-113">Example</span></span>  
 <span data-ttu-id="67ba9-114">Aşağıdaki örnek öğeleri `Order` öğelerine birleştirir `Customer` ve siparişlerdeki `CompanyName` öğesini içeren yeni bir XML belgesi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="67ba9-114">The following example joins the `Customer` elements to the `Order` elements, and generates a new XML document that includes the `CompanyName` element in the orders.</span></span>  
  
 <span data-ttu-id="67ba9-115">Sorguyu yürütmeden önce örnek, belgenin [örnek xsd dosyasındaki şemayla uyumlu olduğunu doğrular: Müşteriler ve siparişler](./sample-xsd-file-customers-and-orders1.md).</span><span class="sxs-lookup"><span data-stu-id="67ba9-115">Before executing the query, the example validates that the document complies with the schema in [Sample XSD File: Customers and Orders](./sample-xsd-file-customers-and-orders1.md).</span></span> <span data-ttu-id="67ba9-116">Bu, JOIN yan tümcesinin her zaman çalışmasına de sağlar.</span><span class="sxs-lookup"><span data-stu-id="67ba9-116">This ensures that the join clause will always work.</span></span>  
  
 <span data-ttu-id="67ba9-117">Bu sorgu önce tüm `Customer` öğeleri alır ve ardından bunları `Order` öğelerine birleştirir.</span><span class="sxs-lookup"><span data-stu-id="67ba9-117">This query first retrieves all `Customer` elements, and then joins them to the `Order` elements.</span></span> <span data-ttu-id="67ba9-118">Yalnızca "K" dan `CustomerID` büyük müşterilere ait siparişleri seçer.</span><span class="sxs-lookup"><span data-stu-id="67ba9-118">It selects only the orders for customers with a `CustomerID` greater than "K".</span></span> <span data-ttu-id="67ba9-119">Ardından, her bir sırada `Order` müşteri bilgilerini içeren yeni bir öğesi projeler.</span><span class="sxs-lookup"><span data-stu-id="67ba9-119">It then projects a new `Order` element that contains the customer information within each order.</span></span>  
  
 <span data-ttu-id="67ba9-120">Bu örnek aşağıdaki XML belgesini kullanır: [Örnek XML dosyası: Müşteriler ve siparişler (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="67ba9-120">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
 <span data-ttu-id="67ba9-121">Bu örnek, aşağıdaki XSD şemasını kullanır: [Örnek XSD Dosyası: Müşteriler ve siparişler](./sample-xsd-file-customers-and-orders1.md).</span><span class="sxs-lookup"><span data-stu-id="67ba9-121">This example uses the following XSD schema: [Sample XSD File: Customers and Orders](./sample-xsd-file-customers-and-orders1.md).</span></span>  
  
 <span data-ttu-id="67ba9-122">Bu biçimde birleştirme işlemi çok iyi gerçekleştirmez.</span><span class="sxs-lookup"><span data-stu-id="67ba9-122">Note that joining in this fashion will not perform very well.</span></span> <span data-ttu-id="67ba9-123">Birleşimler, doğrusal bir arama yoluyla yapılır.</span><span class="sxs-lookup"><span data-stu-id="67ba9-123">Joins are performed via a linear search.</span></span> <span data-ttu-id="67ba9-124">Performansla ilgili yardım için hiçbir karma tablo veya dizin yok.</span><span class="sxs-lookup"><span data-stu-id="67ba9-124">There are no hash tables or indexes to help with performance.</span></span>  
  
```csharp  
XmlSchemaSet schemas = new XmlSchemaSet();  
schemas.Add("", "CustomersOrders.xsd");  
  
Console.Write("Attempting to validate, ");  
XDocument custOrdDoc = XDocument.Load("CustomersOrders.xml");  
  
bool errors = false;  
custOrdDoc.Validate(schemas, (o, e) =>  
                     {  
                         Console.WriteLine("{0}", e.Message);  
                         errors = true;  
                     });  
Console.WriteLine("custOrdDoc {0}", errors ? "did not validate" : "validated");  
  
if (!errors)  
{  
    // Join customers and orders, and create a new XML document with  
    // a different shape.  
  
    // The new document contains orders only for customers with a  
    // CustomerID > 'K'  
    XElement custOrd = custOrdDoc.Element("Root");  
    XElement newCustOrd = new XElement("Root",  
        from c in custOrd.Element("Customers").Elements("Customer")  
        join o in custOrd.Element("Orders").Elements("Order")  
                   on (string)c.Attribute("CustomerID") equals  
                      (string)o.Element("CustomerID")  
        where ((string)c.Attribute("CustomerID")).CompareTo("K") > 0  
        select new XElement("Order",  
            new XElement("CustomerID", (string)c.Attribute("CustomerID")),  
            new XElement("CompanyName", (string)c.Element("CompanyName")),  
            new XElement("ContactName", (string)c.Element("ContactName")),  
            new XElement("EmployeeID", (string)o.Element("EmployeeID")),  
            new XElement("OrderDate", (DateTime)o.Element("OrderDate"))  
        )  
    );  
    Console.WriteLine(newCustOrd);  
}  
```  
  
 <span data-ttu-id="67ba9-125">Bu kod aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="67ba9-125">This code produces the following output:</span></span>  
  
```  
Attempting to validate, custOrdDoc validated  
<Root>  
  <Order>  
    <CustomerID>LAZYK</CustomerID>  
    <CompanyName>Lazy K Kountry Store</CompanyName>  
    <ContactName>John Steel</ContactName>  
    <EmployeeID>1</EmployeeID>  
    <OrderDate>1997-03-21T00:00:00</OrderDate>  
  </Order>  
  <Order>  
    <CustomerID>LAZYK</CustomerID>  
    <CompanyName>Lazy K Kountry Store</CompanyName>  
    <ContactName>John Steel</ContactName>  
    <EmployeeID>8</EmployeeID>  
    <OrderDate>1997-05-22T00:00:00</OrderDate>  
  </Order>  
  <Order>  
    <CustomerID>LETSS</CustomerID>  
    <CompanyName>Let's Stop N Shop</CompanyName>  
    <ContactName>Jaime Yorres</ContactName>  
    <EmployeeID>1</EmployeeID>  
    <OrderDate>1997-06-25T00:00:00</OrderDate>  
  </Order>  
  <Order>  
    <CustomerID>LETSS</CustomerID>  
    <CompanyName>Let's Stop N Shop</CompanyName>  
    <ContactName>Jaime Yorres</ContactName>  
    <EmployeeID>8</EmployeeID>  
    <OrderDate>1997-10-27T00:00:00</OrderDate>  
  </Order>  
  <Order>  
    <CustomerID>LETSS</CustomerID>  
    <CompanyName>Let's Stop N Shop</CompanyName>  
    <ContactName>Jaime Yorres</ContactName>  
    <EmployeeID>6</EmployeeID>  
    <OrderDate>1997-11-10T00:00:00</OrderDate>  
  </Order>  
  <Order>  
    <CustomerID>LETSS</CustomerID>  
    <CompanyName>Let's Stop N Shop</CompanyName>  
    <ContactName>Jaime Yorres</ContactName>  
    <EmployeeID>4</EmployeeID>  
    <OrderDate>1998-02-12T00:00:00</OrderDate>  
  </Order>  
</Root>  
```  
