---
title: 'Nasıl yapılır: (XPath-LINQ to XML) bir alt öğe bulma (C#)'
ms.date: 07/20/2015
ms.assetid: 4fa6182d-6196-4ed1-9c9e-82949ff89c71
ms.openlocfilehash: 4a6d18c86416f7c54df554bc2f518994446a2a84
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66485732"
---
# <a name="how-to-find-a-child-element-xpath-linq-to-xml-c"></a>Nasıl yapılır: (XPath-LINQ to XML) bir alt öğe bulma (C#)
Bu konu XPath alt öğe eksene karşılaştırır [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Element%2A> yöntemi.  
  
 XPath ifadesi `DeliveryNotes`.  
  
## <a name="example"></a>Örnek  
 Bu örnekte alt öğesi bulur `DeliveryNotes`.  
  
 Bu örnek aşağıdaki XML belgesi kullanır: [Örnek XML dosyası: Birden fazla satın alma siparişi (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).  
  
```csharp  
XDocument cpo = XDocument.Load("PurchaseOrders.xml");  
XElement po = cpo.Root.Element("PurchaseOrder");  
  
// LINQ to XML query  
XElement el1 = po.Element("DeliveryNotes");  
  
// XPath expression  
XElement el2 = po.XPathSelectElement("DeliveryNotes");  
// same as "child::DeliveryNotes"  
// same as "./DeliveryNotes"  
  
if (el1 == el2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(el1);  
```  
  
 Bu örnek aşağıdaki çıktıyı üretir:  
  
```  
Results are identical  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  