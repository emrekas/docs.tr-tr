---
title: 'Nasıl yapılır: Alt öğeler yöntemini (C#) kullanarak tek bir alt öğe bulma'
ms.date: 07/20/2015
ms.assetid: 6f735be9-0293-4680-8007-ca9d96bfebed
ms.openlocfilehash: 29cac5a666f7e9a560c550ad20a5bb68d02ee1ea
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70253792"
---
# <a name="how-to-find-a-single-descendant-using-the-descendants-method-c"></a><span data-ttu-id="65edb-102">Nasıl yapılır: Alt öğeler yöntemini (C#) kullanarak tek bir alt öğe bulma</span><span class="sxs-lookup"><span data-stu-id="65edb-102">How to: Find a Single Descendant Using the Descendants Method (C#)</span></span>
<span data-ttu-id="65edb-103">Tek bir benzersiz şekilde <xref:System.Xml.Linq.XContainer.Descendants%2A> adlandırılmış öğe bulmak için bir kodu hızlı bir şekilde yazmak üzere eksen yöntemini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="65edb-103">You can use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis method to quickly write code to find a single uniquely named element.</span></span> <span data-ttu-id="65edb-104">Bu teknik özellikle belirli bir ada sahip belirli bir alt öğe bulmak istediğinizde yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="65edb-104">This technique is especially useful when you want to find a particular descendant with a specific name.</span></span> <span data-ttu-id="65edb-105">İstenen öğeye gitmek için kodu yazabilirsiniz, ancak <xref:System.Xml.Linq.XContainer.Descendants%2A> eksen kullanılarak kodun yazılması genellikle daha hızlı ve kolaydır.</span><span class="sxs-lookup"><span data-stu-id="65edb-105">You could write the code to navigate to the desired element, but it is often faster and easier to write the code using the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65edb-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="65edb-106">Example</span></span>  
 <span data-ttu-id="65edb-107">Bu örnek, <xref:System.Linq.Enumerable.First%2A> standart sorgu işlecini kullanır.</span><span class="sxs-lookup"><span data-stu-id="65edb-107">This example uses the <xref:System.Linq.Enumerable.First%2A> standard query operator.</span></span>  
  
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
  
 <span data-ttu-id="65edb-108">Bu kod aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="65edb-108">This code produces the following output:</span></span>  
  
```output  
GC3 Value  
```  
  
## <a name="example"></a><span data-ttu-id="65edb-109">Örnek</span><span class="sxs-lookup"><span data-stu-id="65edb-109">Example</span></span>  
 <span data-ttu-id="65edb-110">Aşağıdaki örnek, bir ad alanında bulunan XML için aynı sorguyu gösterir.</span><span class="sxs-lookup"><span data-stu-id="65edb-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="65edb-111">Daha fazla bilgi için bkz. [ad alanlarına genel bakış (C#LINQ to XML) ()](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="65edb-111">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="65edb-112">Bu kod aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="65edb-112">This code produces the following output:</span></span>  
  
```output  
GC3 Value  
```  
