---
title: 'Nasıl yapılır: Ad alanındaki öğeleri bulma (XPath-LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: cae1c4ac-6cd5-46cf-9b1c-bd85bc9b7ea9
ms.openlocfilehash: d85426cf7a7073c35b51157e59687e2b3bcdcf8a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70253676"
---
# <a name="how-to-find-elements-in-a-namespace-xpath-linq-to-xml-c"></a>Nasıl yapılır: Ad alanındaki öğeleri bulma (XPath-LINQ to XML) (C#)

XPath ifadeleri, belirli bir ad alanındaki düğümleri bulabilir. XPath ifadeleri ad alanlarını belirtmek için ad alanı öneklerini kullanır. Ad alanı önekleri içeren bir XPath ifadesini ayrıştırmak için, uygulayan <xref:System.Xml.IXmlNamespaceResolver>XPath yöntemlerine bir nesne geçirmeniz gerekir. Bu örnekte, <xref:System.Xml.XmlNamespaceManager>kullanılır.

XPath ifadesi:

`./aw:*`

## <a name="example"></a>Örnek

Aşağıdaki örnek, iki ad alanı içeren bir XML ağacını okur. XML belgesini okumak <xref:System.Xml.XmlReader> için bir kullanır. Daha sonra öğesinden ve <xref:System.Xml.XmlNameTable> <xref:System.Xml.XmlReader> <xref:System.Xml.XmlNamespaceManager> arasında bir alır. <xref:System.Xml.XmlNameTable> Öğeleri seçerken kullanır <xref:System.Xml.XmlNamespaceManager> .

```csharp
XmlReader reader = XmlReader.Create("ConsolidatedPurchaseOrders.xml");
XElement root = XElement.Load(reader);
XmlNameTable nameTable = reader.NameTable;
XmlNamespaceManager namespaceManager = new XmlNamespaceManager(nameTable);
namespaceManager.AddNamespace("aw", "http://www.adventure-works.com");
IEnumerable<XElement> list1 = root.XPathSelectElements("./aw:*", namespaceManager);
IEnumerable<XElement> list2 =
    from el in root.Elements()
    where el.Name.Namespace == "http://www.adventure-works.com"
    select el;
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
<aw:PurchaseOrder PONumber="11223" Date="2000-01-15" xmlns:aw="http://www.adventure-works.com">
    <aw:ShippingAddress>
      <aw:Name>Chris Preston</aw:Name>
      <aw:Street>123 Main St.</aw:Street>
      <aw:City>Seattle</aw:City>
      <aw:State>WA</aw:State>
      <aw:Zip>98113</aw:Zip>
      <aw:Country>USA</aw:Country>
    </aw:ShippingAddress>
    <aw:BillingAddress>
      <aw:Name>Chris Preston</aw:Name>
      <aw:Street>123 Main St.</aw:Street>
      <aw:City>Seattle</aw:City>
      <aw:State>WA</aw:State>
      <aw:Zip>98113</aw:Zip>
      <aw:Country>USA</aw:Country>
    </aw:BillingAddress>
    <aw:DeliveryInstructions>Ship only complete order.</aw:DeliveryInstructions>
    <aw:Item PartNum="LIT-01">
      <aw:ProductID>Litware Networking Card</aw:ProductID>
      <aw:Qty>1</aw:Qty>
      <aw:Price>20.99</aw:Price>
    </aw:Item>
    <aw:Item PartNum="LIT-25">
      <aw:ProductID>Litware 17in LCD Monitor</aw:ProductID>
      <aw:Qty>1</aw:Qty>
      <aw:Price>199.99</aw:Price>
    </aw:Item>
  </aw:PurchaseOrder>
```
