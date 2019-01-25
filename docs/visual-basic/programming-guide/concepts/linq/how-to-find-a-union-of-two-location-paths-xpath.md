---
title: 'Nasıl yapılır: (XPath-LINQ to XML) iki konum yolunun birleşimini bulma (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: c82c09b4-cb0a-47ec-8cc3-a124144c2788
ms.openlocfilehash: 964e42f194cd5e6a4d8f36cfe2164268e650f9da
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728258"
---
# <a name="how-to-find-a-union-of-two-location-paths-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="01a4c-102">Nasıl yapılır: (XPath-LINQ to XML) iki konum yolunun birleşimini bulma (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01a4c-102">How to: Find a Union of Two Location Paths (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="01a4c-103">XPath birleşim iki XPath Konum yolları sonuçlarını bulmanıza olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="01a4c-103">XPath allows you to find the union of the results of two XPath location paths.</span></span>  
  
 <span data-ttu-id="01a4c-104">XPath ifadesidir:</span><span class="sxs-lookup"><span data-stu-id="01a4c-104">The XPath expression is:</span></span>  
  
 `//Category|//Price`  
  
 <span data-ttu-id="01a4c-105">Kullanarak aynı sonucu elde edebileceğiniz <xref:System.Linq.Enumerable.Concat%2A> standart sorgu işleci.</span><span class="sxs-lookup"><span data-stu-id="01a4c-105">You can achieve the same results by using the <xref:System.Linq.Enumerable.Concat%2A> standard query operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01a4c-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="01a4c-106">Example</span></span>  
 <span data-ttu-id="01a4c-107">Bu örnekte tüm bulur `Category` öğeleri ve tüm `Price` öğeleri ve bunları tek bir koleksiyon birleştirir.</span><span class="sxs-lookup"><span data-stu-id="01a4c-107">This example finds all of the `Category` elements and all of the `Price` elements, and concatenates them into a single collection.</span></span> <span data-ttu-id="01a4c-108">Unutmayın [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] sorgu çağrıları <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> sonuçları sıralamak için.</span><span class="sxs-lookup"><span data-stu-id="01a4c-108">Note that the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query calls <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> to order the results.</span></span> <span data-ttu-id="01a4c-109">Belge düzeninde XPath ifade değerlendirme sonuçlarını da var.</span><span class="sxs-lookup"><span data-stu-id="01a4c-109">The results of the XPath expression evaluation are also in document order.</span></span>  
  
 <span data-ttu-id="01a4c-110">Bu örnek aşağıdaki XML belgesi kullanır: [Örnek XML dosyası: Sayısal veriler (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="01a4c-110">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```vb  
Dim data As XDocument = XDocument.Load("Data.xml")  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = _  
    data...<Category>.Concat(data...<Price>).InDocumentOrder()  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = _  
    data.XPathSelectElements("//Category|//Price")  
  
If list1.Count() = list2.Count() And _  
        list1.Intersect(list2).Count() = list1.Count() Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="01a4c-111">Bu örnek aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="01a4c-111">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Category>A</Category>  
<Price>24.50</Price>  
<Category>B</Category>  
<Price>89.99</Price>  
<Category>A</Category>  
<Price>4.95</Price>  
<Category>A</Category>  
<Price>66.00</Price>  
<Category>B</Category>  
<Price>.99</Price>  
<Category>A</Category>  
<Price>29.00</Price>  
<Category>B</Category>  
<Price>6.99</Price>  
```  
  
## <a name="see-also"></a><span data-ttu-id="01a4c-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="01a4c-112">See also</span></span>
- [<span data-ttu-id="01a4c-113">LINQ to XML için XPath kullanıcıları (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01a4c-113">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
