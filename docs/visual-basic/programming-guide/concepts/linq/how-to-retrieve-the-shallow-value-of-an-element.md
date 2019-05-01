---
title: 'Nasıl yapılır: (Visual Basic) öğenin yüzeysel değerini alma'
ms.date: 07/20/2015
ms.assetid: 730a6670-fb8c-41fc-8a1b-eb97a837e432
ms.openlocfilehash: 69e85c3b87ef1052bbb3eab832f93774fa35066f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918092"
---
# <a name="how-to-retrieve-the-shallow-value-of-an-element-visual-basic"></a><span data-ttu-id="3b958-102">Nasıl yapılır: (Visual Basic) öğenin yüzeysel değerini alma</span><span class="sxs-lookup"><span data-stu-id="3b958-102">How to: Retrieve the Shallow Value of an Element (Visual Basic)</span></span>

<span data-ttu-id="3b958-103">Bu konuda, bir öğenin yüzeysel değerini alma gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="3b958-103">This topic shows how to get the shallow value of an element.</span></span> <span data-ttu-id="3b958-104">Basit yalnızca belirli öğenin değeri tek bir dize olarak birleştirilmiş tüm alt öğe değerlerini içeren ayrıntılı değer aksine değerdir.</span><span class="sxs-lookup"><span data-stu-id="3b958-104">The shallow value is the value of the specific element only, as opposed to the deep value, which includes the values of all descendent elements concatenated into a single string.</span></span>

<span data-ttu-id="3b958-105">Ya da bir çevrim kullanarak bir öğe değeri aldığınızda veya <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> özelliği, derin değeri alın.</span><span class="sxs-lookup"><span data-stu-id="3b958-105">When you retrieve an element value by using either casting or the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property, you retrieve the deep value.</span></span> <span data-ttu-id="3b958-106">Yüzeysel değerini almak için kullanabileceğiniz `ShallowValue` genişletme yöntemi, aşağıdaki örnekte gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="3b958-106">To retrieve the shallow value, you can use the `ShallowValue` extension method, as shown in the following example.</span></span> <span data-ttu-id="3b958-107">Yüzeysel değerini alma içeriklerine göre öğeleri seçmek istediğinizde yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="3b958-107">Retrieving the shallow value is useful when you want to select elements based on their content.</span></span>

<span data-ttu-id="3b958-108">Aşağıdaki örnek, bir öğenin yüzeysel değerini alır. bir genişletme yöntemi bildirir.</span><span class="sxs-lookup"><span data-stu-id="3b958-108">The following example declares an extension method that retrieves the shallow value of an element.</span></span> <span data-ttu-id="3b958-109">Ardından, hesaplanan değeri içeren tüm öğeleri listelemek için genişletme yöntemi bir sorguda kullanır.</span><span class="sxs-lookup"><span data-stu-id="3b958-109">It then uses the extension method in a query to list all elements that contain a calculated value.</span></span>

## <a name="example"></a><span data-ttu-id="3b958-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="3b958-110">Example</span></span>

<span data-ttu-id="3b958-111">Aşağıdaki metin dosyası Report.xml, bu örnekte kaynağıdır.</span><span class="sxs-lookup"><span data-stu-id="3b958-111">The following text file, Report.xml, is the source for this example.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Report>
  <Section>
    <Heading>
      <Column Name="CustomerId">=Customer.CustomerId.Heading</Column>
      <Column Name="Name">=Customer.Name.Heading</Column>
    </Heading>
    <Detail>
      <Column Name="CustomerId">=Customer.CustomerId</Column>
      <Column Name="Name">=Customer.Name</Column>
    </Detail>
  </Section>
</Report>
```

```vb
Module Module1
    <System.Runtime.CompilerServices.Extension()> _
    Public Function ShallowValue(ByVal xe As XElement)
        Return xe _
               .Nodes() _
               .OfType(Of XText)() _
               .Aggregate(New StringBuilder(), _
                              Function(s, c) s.Append(c), _
                              Function(s) s.ToString())
    End Function

    Sub Main()
        Dim root As XElement = XElement.Load("Report.xml")

        Dim query As IEnumerable(Of XElement) = _
            From el In root.Descendants() _
            Where (el.ShallowValue().StartsWith("=")) _
            Select el

        For Each q As XElement In query
            Console.WriteLine("{0}{1}{2}", _
                q.Name.ToString().PadRight(8), _
                q.Attribute("Name").ToString().PadRight(20), _
                q.ShallowValue())
        Next
    End Sub
End Module
```

<span data-ttu-id="3b958-112">Bu örnek aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="3b958-112">This example produces the following output:</span></span>

```
Column  Name="CustomerId"   =Customer.CustomerId.Heading
Column  Name="Name"         =Customer.Name.Heading
Column  Name="CustomerId"   =Customer.CustomerId
Column  Name="Name"         =Customer.Name
```

## <a name="see-also"></a><span data-ttu-id="3b958-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="3b958-113">See also</span></span>

- [<span data-ttu-id="3b958-114">LINQ to XML eksenleri (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3b958-114">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
