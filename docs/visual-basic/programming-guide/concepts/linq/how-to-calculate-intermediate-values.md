---
title: 'Nasıl yapılır: Ara değerleri hesapla (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 933a97b2-dfe7-4f4d-94ad-e6e20df84abd
ms.openlocfilehash: d3af616fc3de4baa4bb42d9f9c04d654b7438ab0
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710472"
---
# <a name="how-to-calculate-intermediate-values-visual-basic"></a><span data-ttu-id="66633-102">Nasıl yapılır: Ara değerleri hesapla (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66633-102">How to: Calculate Intermediate Values (Visual Basic)</span></span>
<span data-ttu-id="66633-103">Bu örnek, sıralama, filtreleme ve seçme için kullanılabilen ara değerlerin nasıl hesaplanacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="66633-103">This example shows how to calculate intermediate values that can be used in sorting, filtering, and selecting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66633-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="66633-104">Example</span></span>  
 <span data-ttu-id="66633-105">Aşağıdaki örnek `Let` yan tümcesini kullanır.</span><span class="sxs-lookup"><span data-stu-id="66633-105">The following example uses the `Let` clause.</span></span>  
  
 <span data-ttu-id="66633-106">Bu örnek aşağıdaki XML belgesini kullanır: [Örnek XML dosyası: Sayısal veri (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="66633-106">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("Data.xml")  
Dim extensions As IEnumerable(Of Decimal) = _  
    From el In root.<Data> _  
    Let extension = CDec(el.<Quantity>.Value) * CDec(el.<Price>.Value) _  
    Where extension > 25 _  
    Order By extension _  
    Select extension  
For Each ex As Decimal In extensions  
    Console.WriteLine(ex)  
Next  
```  
  
 <span data-ttu-id="66633-107">Bu kod aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="66633-107">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="example"></a><span data-ttu-id="66633-108">Örnek</span><span class="sxs-lookup"><span data-stu-id="66633-108">Example</span></span>  
 <span data-ttu-id="66633-109">Aşağıdaki örnek, bir ad alanında bulunan XML için aynı sorguyu gösterir.</span><span class="sxs-lookup"><span data-stu-id="66633-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="66633-110">Daha fazla bilgi için bkz. [ad alanlarına genel bakış (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="66633-110">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="66633-111">Bu örnek aşağıdaki XML belgesini kullanır: [Örnek XML dosyası: Bir ad alanındaki](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md)sayısal veri.</span><span class="sxs-lookup"><span data-stu-id="66633-111">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns="http://www.adatum.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("DataInNamespace.xml")  
        Dim extensions As IEnumerable(Of Decimal) = _  
            From el In root.<Data> _  
            Let extension = CDec(el.<Quantity>.Value) * CDec(el.<Price>.Value) _  
            Where extension > 25 _  
            Order By extension _  
            Select extension  
        For Each ex As Decimal In extensions  
            Console.WriteLine(ex)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="66633-112">Bu kod aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="66633-112">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="see-also"></a><span data-ttu-id="66633-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="66633-113">See also</span></span>

- [<span data-ttu-id="66633-114">Temel sorgular (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66633-114">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
