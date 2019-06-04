---
title: 'Nasıl yapılır: LINQ to XML XPath kullanarak sorgula (C#)'
ms.date: 07/20/2015
ms.assetid: ee5af263-4ab1-45e5-b792-33a3221b426d
ms.openlocfilehash: 639d9ba8af9ae663bc245028cf4bf57f318d397d
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66485186"
---
# <a name="how-to-query-linq-to-xml-using-xpath-c"></a>Nasıl yapılır: LINQ to XML XPath kullanarak sorgula (C#)
Bu konu, bir XML ağacı XPath kullanarak sorgula olanak tanıyan uzantı yöntemleri tanıtır. Bu uzantı yöntemleri kullanma hakkında ayrıntılı bilgi için bkz <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.  
  
 Kullanarak sorgulamak için çok özel bir nedeniniz yoksa, XPath XPath ile LINQ to XML kullanarak eski kod kapsamlı kullanımını gibi önerilmez. XPath sorguları gerçekleştirme yanı [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] sorgular.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, küçük bir XML ağacı oluşturur ve kullanır <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> öğe kümesini seçin.  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", 1),  
    new XElement("Child1", 2),  
    new XElement("Child1", 3),  
    new XElement("Child2", 4),  
    new XElement("Child2", 5),  
    new XElement("Child2", 6)  
);  
IEnumerable<XElement> list = root.XPathSelectElements("./Child2");  
foreach (XElement el in list)  
    Console.WriteLine(el);  
```  
  
 Bu örnek aşağıdaki çıktıyı üretir:  
  
```xml  
<Child2>4</Child2>  
<Child2>5</Child2>  
<Child2>6</Child2>  
```  
  