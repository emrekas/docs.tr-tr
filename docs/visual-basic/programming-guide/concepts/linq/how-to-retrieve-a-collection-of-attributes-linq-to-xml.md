---
title: 'Nasıl yapılır: Öznitelikler (LINQ to XML) koleksiyonu alma (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: a07e9645-b45b-403b-b698-f652f904c7d2
ms.openlocfilehash: 2e99e561c1d479412c7c5cd2a19563446b872049
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58833548"
---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-visual-basic"></a><span data-ttu-id="ca7a0-102">Nasıl yapılır: Öznitelikler (LINQ to XML) koleksiyonu alma (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca7a0-102">How to: Retrieve a Collection of Attributes (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="ca7a0-103">Bu konu tanıtır <xref:System.Xml.Linq.XElement.Attributes%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="ca7a0-103">This topic introduces the <xref:System.Xml.Linq.XElement.Attributes%2A> method.</span></span> <span data-ttu-id="ca7a0-104">Bu yöntem, bir öğenin öznitelikleri alır.</span><span class="sxs-lookup"><span data-stu-id="ca7a0-104">This method retrieves the attributes of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca7a0-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="ca7a0-105">Example</span></span>  
 <span data-ttu-id="ca7a0-106">Aşağıdaki örnek, bir öğenin öznitelikleri toplulukta tekrarlama gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="ca7a0-106">The following example shows how to iterate through the collection of attributes of an element.</span></span>  
  
```vb  
Dim val = _  
    <Value ID="1243" Type="int" ConvertableTo="double">100</Value>  
Dim listOfAttributes As IEnumerable(Of XAttribute) = _  
    From att In val.Attributes() _  
    Select att  
For Each att As XAttribute In listOfAttributes  
    Console.WriteLine(att)  
Next  
```  
  
 <span data-ttu-id="ca7a0-107">Bu kod aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="ca7a0-107">This code produces the following output:</span></span>  
  
```  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a><span data-ttu-id="ca7a0-108">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="ca7a0-108">See also</span></span>

- [<span data-ttu-id="ca7a0-109">LINQ to XML eksenleri (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca7a0-109">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
