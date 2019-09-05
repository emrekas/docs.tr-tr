---
title: 'Nasıl yapılır: Belirli bir alt öğe (C#) Içeren bir öğe bul'
ms.date: 07/20/2015
ms.assetid: 00cf5555-374e-4369-bf93-7bd2e7f21db3
ms.openlocfilehash: f007bddcbecc1cb938d05c7d444d29b6047749e8
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70253751"
---
# <a name="how-to-find-an-element-with-a-specific-child-element-c"></a><span data-ttu-id="ff28c-102">Nasıl yapılır: Belirli bir alt öğe (C#) Içeren bir öğe bul</span><span class="sxs-lookup"><span data-stu-id="ff28c-102">How to: Find an Element with a Specific Child Element (C#)</span></span>
<span data-ttu-id="ff28c-103">Bu konu, belirli bir değere sahip bir alt öğesi olan belirli bir öğenin nasıl bulunacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="ff28c-103">This topic shows how to find a particular element that has a child element with a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff28c-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="ff28c-104">Example</span></span>  
 <span data-ttu-id="ff28c-105">Örnek, "Examp2 `Test` . exe" değerine `CommandLine` sahip bir alt öğesi olan öğesini bulur.</span><span class="sxs-lookup"><span data-stu-id="ff28c-105">The example finds the `Test` element that has a `CommandLine` child element with the value of "Examp2.EXE".</span></span>  
  
 <span data-ttu-id="ff28c-106">Bu örnek aşağıdaki XML belgesini kullanır: [Örnek XML dosyası: Test yapılandırması (LINQ to XML)](./sample-xml-file-test-configuration-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="ff28c-106">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](./sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfig.xml");  
IEnumerable<XElement> tests =  
    from el in root.Elements("Test")  
    where (string)el.Element("CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="ff28c-107">Bu kod aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="ff28c-107">This code produces the following output:</span></span>  
  
```output  
0002  
0006  
```  
  
## <a name="example"></a><span data-ttu-id="ff28c-108">Örnek</span><span class="sxs-lookup"><span data-stu-id="ff28c-108">Example</span></span>  
 <span data-ttu-id="ff28c-109">Aşağıdaki örnek, bir ad alanında bulunan XML için aynı sorguyu gösterir.</span><span class="sxs-lookup"><span data-stu-id="ff28c-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="ff28c-110">Daha fazla bilgi için bkz. [ad alanlarına genel bakış (C#LINQ to XML) ()](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="ff28c-110">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="ff28c-111">Bu örnek aşağıdaki XML belgesini kullanır: [Örnek XML dosyası: Bir ad alanında](./sample-xml-file-test-configuration-in-a-namespace1.md)test yapılandırması.</span><span class="sxs-lookup"><span data-stu-id="ff28c-111">This example uses the following XML document: [Sample XML File: Test Configuration in a Namespace](./sample-xml-file-test-configuration-in-a-namespace1.md).</span></span>  
  
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
  
 <span data-ttu-id="ff28c-112">Bu kod aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="ff28c-112">This code produces the following output:</span></span>  
  
```output  
0002  
0006  
```  
  
## <a name="see-also"></a><span data-ttu-id="ff28c-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="ff28c-113">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="ff28c-114">Standart sorgu Işleçlerine genelC#bakış ()</span><span class="sxs-lookup"><span data-stu-id="ff28c-114">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="ff28c-115">Projeksiyon Işlemleri (C#)</span><span class="sxs-lookup"><span data-stu-id="ff28c-115">Projection Operations (C#)</span></span>](./projection-operations.md)
