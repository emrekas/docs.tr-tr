---
title: 'Nasıl yapılır: (XPath-LINQ to XML) alt öğeleri bulma (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: e7e2dc9e-bda9-420d-a5b1-4fabf1cca46b
ms.openlocfilehash: 09f12dca7b6278327394126ffb0950682d285f88
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58833405"
---
# <a name="how-to-find-descendant-elements-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="f8af1-102">Nasıl yapılır: (XPath-LINQ to XML) alt öğeleri bulma (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8af1-102">How to: Find Descendant Elements (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="f8af1-103">Bu konuda, belirli bir ada sahip alt öğeleri almak gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="f8af1-103">This topic shows how to get the descendant elements with a particular name.</span></span>  
  
 <span data-ttu-id="f8af1-104">XPath ifadesi `//Name`.</span><span class="sxs-lookup"><span data-stu-id="f8af1-104">The XPath expression is `//Name`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8af1-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="f8af1-105">Example</span></span>  
 <span data-ttu-id="f8af1-106">Bu örnek adlı tüm alt öğeleri bulan `Name`.</span><span class="sxs-lookup"><span data-stu-id="f8af1-106">This example finds all descendants named `Name`.</span></span>  
  
 <span data-ttu-id="f8af1-107">Bu örnek aşağıdaki XML belgesi kullanır: [Örnek XML dosyası: Birden fazla satın alma siparişi (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f8af1-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```vb  
      Dim po As XDocument = XDocument.Load("PurchaseOrders.xml")  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = po...<Name>  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = po.XPathSelectElements("//Name")  
  
If (list1.Count() = list2.Count() And _  
        list1.Intersect(list2).Count() = list1.Count()) Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="f8af1-108">Bu örnek aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="f8af1-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f8af1-109">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="f8af1-109">See also</span></span>

- [<span data-ttu-id="f8af1-110">LINQ to XML için XPath kullanıcıları (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8af1-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
