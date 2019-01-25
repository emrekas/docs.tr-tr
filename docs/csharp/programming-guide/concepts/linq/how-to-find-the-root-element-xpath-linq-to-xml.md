---
title: 'Nasıl yapılır: Bulma (XPath-LINQ to XML) kök öğe (C#)'
ms.date: 07/20/2015
ms.assetid: 4fd824e0-4d39-429b-b092-f6a5c046ee6c
ms.openlocfilehash: a74556e4b05bc3ae02998eeb6dd3190a3bade36a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54697172"
---
# <a name="how-to-find-the-root-element-xpath-linq-to-xml-c"></a><span data-ttu-id="258c5-102">Nasıl yapılır: Bulma (XPath-LINQ to XML) kök öğe (C#)</span><span class="sxs-lookup"><span data-stu-id="258c5-102">How to: Find the Root Element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="258c5-103">Bu konu XPath kök öğesiyle almak nasıl gösterir ve [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="258c5-103">This topic shows how to get the root element with XPath and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="258c5-104">XPath ifadesidir:</span><span class="sxs-lookup"><span data-stu-id="258c5-104">The XPath expression is:</span></span>  
  
 `/PurchaseOrders`  
  
## <a name="example"></a><span data-ttu-id="258c5-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="258c5-105">Example</span></span>  
 <span data-ttu-id="258c5-106">Bu örnekte, kök öğesi bulur.</span><span class="sxs-lookup"><span data-stu-id="258c5-106">This example finds the root element.</span></span>  
  
 <span data-ttu-id="258c5-107">Bu örnek aşağıdaki XML belgesi kullanır: [Örnek XML dosyası: Birden fazla satın alma siparişi (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="258c5-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
// LINQ to XML query  
XElement el1 = po.Root;  
  
// XPath expression  
XElement el2 = po.XPathSelectElement("/PurchaseOrders");  
  
if (el1 == el2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(el1.Name);  
```  
  
 <span data-ttu-id="258c5-108">Bu örnek aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="258c5-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
PurchaseOrders  
```  
  
## <a name="see-also"></a><span data-ttu-id="258c5-109">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="258c5-109">See also</span></span>

- [<span data-ttu-id="258c5-110">LINQ to XML için XPath kullanıcıları (C#)</span><span class="sxs-lookup"><span data-stu-id="258c5-110">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
