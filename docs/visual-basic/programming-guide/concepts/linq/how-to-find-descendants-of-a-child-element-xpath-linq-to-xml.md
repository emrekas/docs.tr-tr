---
title: 'Nasıl yapılır: Bir alt öğesi (XPath-LINQ to XML) alt öğeleri bulma (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: a958af40-f754-4409-85f9-7746978d4cb3
ms.openlocfilehash: 178729640898556244657e6e2917373825a4e51e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61780519"
---
# <a name="how-to-find-descendants-of-a-child-element-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="d4f22-102">Nasıl yapılır: Bir alt öğesi (XPath-LINQ to XML) alt öğeleri bulma (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4f22-102">How to: Find Descendants of a Child Element (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="d4f22-103">Bu konuda, belirli bir ada sahip bir alt öğenin alt öğeleri almak gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="d4f22-103">This topic shows how to get the descendant elements of a child element with a particular name.</span></span>  
  
 <span data-ttu-id="d4f22-104">XPath ifadesidir:</span><span class="sxs-lookup"><span data-stu-id="d4f22-104">The XPath expression is:</span></span>  
  
 `./Paragraph//Text/text()`  
  
## <a name="example"></a><span data-ttu-id="d4f22-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="d4f22-105">Example</span></span>  
 <span data-ttu-id="d4f22-106">Bu örnek, bir sözcük işleme belgesi bir XML gösteriminden metin ayıklama sorunları benzetimini yapar.</span><span class="sxs-lookup"><span data-stu-id="d4f22-106">This example simulates the problems of extracting text from an XML representation of a word processing document.</span></span> <span data-ttu-id="d4f22-107">Bu ilk tüm seçer `Paragraph` öğeleri ve ardından tüm seçer `Text` her alt öğeleri `Paragraph` öğesi.</span><span class="sxs-lookup"><span data-stu-id="d4f22-107">It first selects all `Paragraph` elements, and then it selects all `Text` descendant elements of each `Paragraph` element.</span></span> <span data-ttu-id="d4f22-108">Bu alt seçemiyorum `Text` öğelerini `Comment` öğesi.</span><span class="sxs-lookup"><span data-stu-id="d4f22-108">This doesn't select the descendant `Text` elements of the `Comment` element.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Paragraph>  
            <Text>This is the start of</Text>  
        </Paragraph>  
        <Comment>  
            <Text>This comment is not part of the paragraph text.</Text>  
        </Comment>  
        <Paragraph>  
            <Annotation Emphasis='true'>  
                <Text> a sentence.</Text>  
            </Annotation>  
        </Paragraph>  
        <Paragraph>  
            <Text>  This is a second sentence.</Text>  
        </Paragraph>  
    </Root>  
  
' LINQ to XML query  
Dim str1 As String = _  
    root.<Paragraph>...<Text>.Select(Function(ByVal s) s.Value). _  
    Aggregate( _  
        New StringBuilder(), _  
        Function(ByVal s, ByVal i) s.Append(i), _  
        Function(ByVal s) s.ToString())  
  
' XPath expression  
Dim str2 As String = DirectCast(root.XPathEvaluate("./Paragraph//Text/text()"), IEnumerable) _  
    .Cast(Of XText)().Select(Function(ByVal s) s.Value) _  
    .Aggregate( _  
        New StringBuilder(), _  
        Function(ByVal s, ByVal i) s.Append(i), _  
        Function(ByVal s) s.ToString())  
  
If str1 = str2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(str2)  
```  
  
 <span data-ttu-id="d4f22-109">Bu örnek aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="d4f22-109">This example produces the following output:</span></span>  
  
```  
Results are identical  
This is the start of a sentence.  This is a second sentence.  
```  
  
## <a name="see-also"></a><span data-ttu-id="d4f22-110">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d4f22-110">See also</span></span>

- [<span data-ttu-id="d4f22-111">LINQ to XML için XPath kullanıcıları (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4f22-111">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
