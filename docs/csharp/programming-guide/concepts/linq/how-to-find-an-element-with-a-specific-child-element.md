---
title: 'Nasıl yapılır: Belirli bir alt öğeye sahip öğeyi bulma (C#)'
ms.date: 07/20/2015
ms.assetid: 00cf5555-374e-4369-bf93-7bd2e7f21db3
ms.openlocfilehash: 71068774b93581fdd82a0fe57651bc7780ca1ef1
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66485577"
---
# <a name="how-to-find-an-element-with-a-specific-child-element-c"></a><span data-ttu-id="2a433-102">Nasıl yapılır: Belirli bir alt öğeye sahip öğeyi bulma (C#)</span><span class="sxs-lookup"><span data-stu-id="2a433-102">How to: Find an Element with a Specific Child Element (C#)</span></span>
<span data-ttu-id="2a433-103">Bu konuda, belirli bir değere sahip bir alt öğesi olan belirli bir öğeyi bulmak gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="2a433-103">This topic shows how to find a particular element that has a child element with a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a433-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="2a433-104">Example</span></span>  
 <span data-ttu-id="2a433-105">Örnek bulur `Test` sahip öğe bir `CommandLine` "Examp2.EXE" değeri olan alt öğesi.</span><span class="sxs-lookup"><span data-stu-id="2a433-105">The example finds the `Test` element that has a `CommandLine` child element with the value of "Examp2.EXE".</span></span>  
  
 <span data-ttu-id="2a433-106">Bu örnek aşağıdaki XML belgesi kullanır: [Örnek XML dosyası: Test yapılandırması (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="2a433-106">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfig.xml");  
IEnumerable<XElement> tests =  
    from el in root.Elements("Test")  
    where (string)el.Element("CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="2a433-107">Bu kod aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="2a433-107">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
## <a name="example"></a><span data-ttu-id="2a433-108">Örnek</span><span class="sxs-lookup"><span data-stu-id="2a433-108">Example</span></span>  
 <span data-ttu-id="2a433-109">Aşağıdaki örnek, aynı sorgu için bir ad alanındaki XML gösterir.</span><span class="sxs-lookup"><span data-stu-id="2a433-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="2a433-110">Daha fazla bilgi için [(C#) XML ad alanları ile çalışma](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="2a433-110">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="2a433-111">Bu örnek aşağıdaki XML belgesi kullanır: [Örnek XML dosyası: Test yapılandırması bir Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace1.md).</span><span class="sxs-lookup"><span data-stu-id="2a433-111">This example uses the following XML document: [Sample XML File: Test Configuration in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace1.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfigInNamespace.xml");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<XElement> tests =  
    from el in root.Elements(ad + "Test")  
    where (string)el.Element(ad + "CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="2a433-112">Bu kod aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="2a433-112">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
## <a name="see-also"></a><span data-ttu-id="2a433-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="2a433-113">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="2a433-114">Standart sorgu işleçlerine genel bakış (C#)</span><span class="sxs-lookup"><span data-stu-id="2a433-114">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="2a433-115">Projeksiyon işlemleri (C#)</span><span class="sxs-lookup"><span data-stu-id="2a433-115">Projection Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)
