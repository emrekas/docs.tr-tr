---
title: 'Nasıl yapılır: Bir Namespace (XPath-LINQ to XML) içindeki öğeleri bulma (C#)'
ms.date: 07/20/2015
ms.assetid: cae1c4ac-6cd5-46cf-9b1c-bd85bc9b7ea9
ms.openlocfilehash: 8ba5fc03bbd831cfee0c4fd15e71708c4eafd212
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646782"
---
# <a name="how-to-find-elements-in-a-namespace-xpath-linq-to-xml-c"></a><span data-ttu-id="98b52-102">Nasıl yapılır: Bir Namespace (XPath-LINQ to XML) içindeki öğeleri bulma (C#)</span><span class="sxs-lookup"><span data-stu-id="98b52-102">How to: Find Elements in a Namespace (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="98b52-103">XPath ifadeleri düğüm, belirli bir ad alanında bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="98b52-103">XPath expressions can find nodes in a particular namespace.</span></span> <span data-ttu-id="98b52-104">XPath ifadeleri, ad alanı öneklerini ad alanları belirtmek için kullanın.</span><span class="sxs-lookup"><span data-stu-id="98b52-104">XPath expressions use namespace prefixes for specifying namespaces.</span></span> <span data-ttu-id="98b52-105">Ad alanı öneklerini içeren bir XPath ifadesi ayrıştırılamadı XPath yöntemlere uygulayan bir nesne geçmelidir. <xref:System.Xml.IXmlNamespaceResolver>.</span><span class="sxs-lookup"><span data-stu-id="98b52-105">To parse an XPath expression that contains namespace prefixes, you must pass an object to the XPath methods that implements <xref:System.Xml.IXmlNamespaceResolver>.</span></span> <span data-ttu-id="98b52-106">Bu örnekte <xref:System.Xml.XmlNamespaceManager>.</span><span class="sxs-lookup"><span data-stu-id="98b52-106">This example uses <xref:System.Xml.XmlNamespaceManager>.</span></span>  
  
 <span data-ttu-id="98b52-107">XPath ifadesidir:</span><span class="sxs-lookup"><span data-stu-id="98b52-107">The XPath expression is:</span></span>  
  
 `./aw:*`  
  
## <a name="example"></a><span data-ttu-id="98b52-108">Örnek</span><span class="sxs-lookup"><span data-stu-id="98b52-108">Example</span></span>  
 <span data-ttu-id="98b52-109">Aşağıdaki örnek iki ad alanları içeren bir XML ağacı okur.</span><span class="sxs-lookup"><span data-stu-id="98b52-109">The following example reads an XML tree that contains two namespaces.</span></span> <span data-ttu-id="98b52-110">Bunu kullanan bir <xref:System.Xml.XmlReader> XML belgesi okumak için.</span><span class="sxs-lookup"><span data-stu-id="98b52-110">It uses an <xref:System.Xml.XmlReader> to read the XML document.</span></span> <span data-ttu-id="98b52-111">Ardından alır bir <xref:System.Xml.XmlNameTable> gelen <xref:System.Xml.XmlReader>ve bir <xref:System.Xml.XmlNamespaceManager> gelen <xref:System.Xml.XmlNameTable>.</span><span class="sxs-lookup"><span data-stu-id="98b52-111">It then gets an <xref:System.Xml.XmlNameTable> from the <xref:System.Xml.XmlReader>, and an <xref:System.Xml.XmlNamespaceManager> from the <xref:System.Xml.XmlNameTable>.</span></span> <span data-ttu-id="98b52-112">Kullandığı <xref:System.Xml.XmlNamespaceManager> öğeleri seçerken.</span><span class="sxs-lookup"><span data-stu-id="98b52-112">It uses the <xref:System.Xml.XmlNamespaceManager> when selecting elements.</span></span>  
  
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
  
 <span data-ttu-id="98b52-113">Bu örnek aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="98b52-113">This example produces the following output:</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="98b52-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="98b52-114">See also</span></span>

- [<span data-ttu-id="98b52-115">LINQ to XML için XPath kullanıcıları (C#)</span><span class="sxs-lookup"><span data-stu-id="98b52-115">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
