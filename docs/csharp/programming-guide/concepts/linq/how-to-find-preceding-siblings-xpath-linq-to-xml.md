---
title: 'Nasıl yapılır: Önceki eşdüzey öğeleri bul (XPath-LINQ to XML)C#()'
ms.date: 07/20/2015
ms.assetid: b281ff99-d08a-43d0-bea1-eff831b2f8ae
ms.openlocfilehash: 2af2e08fa692142d2932a427f48ba5d323d7a848
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70253654"
---
# <a name="how-to-find-preceding-siblings-xpath-linq-to-xml-c"></a>Nasıl yapılır: Önceki eşdüzey öğeleri bul (XPath-LINQ to XML)C#()
Bu konu, XPath `preceding-sibling` eksenini [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] alt <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> ekseniyle karşılaştırır.  
  
 XPath ifadesi:  
  
 `preceding-sibling::*`  
  
 Hem hem de <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> sonuçlarının belge sırasıyla olduğunu unutmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek `FullAddress` öğesini bulur ve sonra `preceding-sibling` ekseni kullanarak önceki öğeleri alır.  
  
 Bu örnek aşağıdaki XML belgesini kullanır: [Örnek XML dosyası: Müşteriler ve siparişler (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).  
  
```csharp  
XElement co = XElement.Load("CustomersOrders.xml");  
  
XElement add = co.Element("Customers").Element("Customer").Element("FullAddress");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 = add.ElementsBeforeSelf();  
  
// XPath expression  
IEnumerable<XElement> list2 = add.XPathSelectElements("preceding-sibling::*");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list2)  
    Console.WriteLine(el);  
```  
  
 Bu örnek aşağıdaki çıktıyı üretir:  
  
```output  
Results are identical  
<CompanyName>Great Lakes Food Market</CompanyName>  
<ContactName>Howard Snyder</ContactName>  
<ContactTitle>Marketing Manager</ContactTitle>  
<Phone>(503) 555-7555</Phone>  
```  
