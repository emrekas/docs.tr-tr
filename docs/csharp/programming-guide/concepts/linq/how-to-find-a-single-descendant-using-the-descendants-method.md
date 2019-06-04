---
title: 'Nasıl yapılır: Descendants yöntemini kullanarak tek bir alt öğe bulma (C#)'
ms.date: 07/20/2015
ms.assetid: 6f735be9-0293-4680-8007-ca9d96bfebed
ms.openlocfilehash: 1979814a2a1485938b584d7774b76a020c885f0c
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486833"
---
# <a name="how-to-find-a-single-descendant-using-the-descendants-method-c"></a><span data-ttu-id="8ca47-102">Nasıl yapılır: Descendants yöntemini kullanarak tek bir alt öğe bulma (C#)</span><span class="sxs-lookup"><span data-stu-id="8ca47-102">How to: Find a Single Descendant Using the Descendants Method (C#)</span></span>
<span data-ttu-id="8ca47-103">Kullanabileceğiniz <xref:System.Xml.Linq.XContainer.Descendants%2A> adlı öğesi hızlı bir şekilde tek bir benzersiz bir şekilde bulmak için kod yazma eksen yöntemi.</span><span class="sxs-lookup"><span data-stu-id="8ca47-103">You can use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis method to quickly write code to find a single uniquely named element.</span></span> <span data-ttu-id="8ca47-104">Belirli bir ada sahip belirli bir alt öğesi bulmak istediğinizde bu özellikle yararlı bir tekniktir.</span><span class="sxs-lookup"><span data-stu-id="8ca47-104">This technique is especially useful when you want to find a particular descendant with a specific name.</span></span> <span data-ttu-id="8ca47-105">İstenen öğesine gitmek için kod yazabilirsiniz, ancak genellikle daha hızlı ve kolay kullanarak kod yazmak <xref:System.Xml.Linq.XContainer.Descendants%2A> ekseni.</span><span class="sxs-lookup"><span data-stu-id="8ca47-105">You could write the code to navigate to the desired element, but it is often faster and easier to write the code using the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ca47-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="8ca47-106">Example</span></span>  
 <span data-ttu-id="8ca47-107">Bu örnekte <xref:System.Linq.Enumerable.First%2A> standart sorgu işleci.</span><span class="sxs-lookup"><span data-stu-id="8ca47-107">This example uses the <xref:System.Linq.Enumerable.First%2A> standard query operator.</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<Root>  
  <Child1>  
    <GrandChild1>GC1 Value</GrandChild1>  
  </Child1>  
  <Child2>  
    <GrandChild2>GC2 Value</GrandChild2>  
  </Child2>  
  <Child3>  
    <GrandChild3>GC3 Value</GrandChild3>  
  </Child3>  
  <Child4>  
    <GrandChild4>GC4 Value</GrandChild4>  
  </Child4>  
</Root>");  
string grandChild3 = (string)  
    (from el in root.Descendants("GrandChild3")  
    select el).First();  
Console.WriteLine(grandChild3);  
```  
  
 <span data-ttu-id="8ca47-108">Bu kod aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="8ca47-108">This code produces the following output:</span></span>  
  
```  
GC3 Value  
```  
  
## <a name="example"></a><span data-ttu-id="8ca47-109">Örnek</span><span class="sxs-lookup"><span data-stu-id="8ca47-109">Example</span></span>  
 <span data-ttu-id="8ca47-110">Aşağıdaki örnek, aynı sorgu için bir ad alanındaki XML gösterir.</span><span class="sxs-lookup"><span data-stu-id="8ca47-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="8ca47-111">Daha fazla bilgi için [(C#) XML ad alanları ile çalışma](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="8ca47-111">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<aw:Root xmlns:aw='http://www.adventure-works.com'>  
  <aw:Child1>  
    <aw:GrandChild1>GC1 Value</aw:GrandChild1>  
  </aw:Child1>  
  <aw:Child2>  
    <aw:GrandChild2>GC2 Value</aw:GrandChild2>  
  </aw:Child2>  
  <aw:Child3>  
    <aw:GrandChild3>GC3 Value</aw:GrandChild3>  
  </aw:Child3>  
  <aw:Child4>  
    <aw:GrandChild4>GC4 Value</aw:GrandChild4>  
  </aw:Child4>  
</aw:Root>");  
XNamespace aw = "http://www.adventure-works.com";  
string grandChild3 = (string)  
    (from el in root.Descendants(aw + "GrandChild3")  
     select el).First();  
Console.WriteLine(grandChild3);  
```  
  
 <span data-ttu-id="8ca47-112">Bu kod aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="8ca47-112">This code produces the following output:</span></span>  
  
```  
GC3 Value  
```  
