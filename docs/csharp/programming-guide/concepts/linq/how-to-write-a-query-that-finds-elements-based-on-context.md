---
title: 'Nasıl yapılır: Bağlama göre öğeleri bulan bir sorgu yazma (C#)'
ms.date: 07/20/2015
ms.assetid: 3ff79ef0-fc8b-42fe-8cc0-10dc32b06b4e
ms.openlocfilehash: 92cbed3edc62b06be65fdd458e509108343d9e59
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66484647"
---
# <a name="how-to-write-a-query-that-finds-elements-based-on-context-c"></a><span data-ttu-id="603e0-102">Nasıl yapılır: Bağlama göre öğeleri bulan bir sorgu yazma (C#)</span><span class="sxs-lookup"><span data-stu-id="603e0-102">How to: Write a Query that Finds Elements Based on Context (C#)</span></span>
<span data-ttu-id="603e0-103">Bazen, bağlama göre öğeleri seçen bir sorgu yazmak zorunda kalabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="603e0-103">Sometimes you might have to write a query that selects elements based on their context.</span></span> <span data-ttu-id="603e0-104">Bağlı olarak önceki veya Eşdüzey öğeleri aşağıdaki filtreleme isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="603e0-104">You might want to filter based on preceding or following sibling elements.</span></span> <span data-ttu-id="603e0-105">Temel alınarak alt veya üst öğeleri filtrelemek isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="603e0-105">You might want to filter based on child or ancestor elements.</span></span>  
  
 <span data-ttu-id="603e0-106">Bir sorgu yazma ve sorgu sonuçlarının kullanarak bunu yapabilirsiniz `where` yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="603e0-106">You can do this by writing a query and using the results of the query in the `where` clause.</span></span> <span data-ttu-id="603e0-107">İlk null karşı test etmeyi ve ardından değeri test varsa, sorgu yapılacağı daha kullanışlı bir `let` yan tümcesi ve ardından sonuçları `where` yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="603e0-107">If you have to first test against null, and then test the value, it is more convenient to do the query in a `let` clause, and then use the results in the `where` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="603e0-108">Örnek</span><span class="sxs-lookup"><span data-stu-id="603e0-108">Example</span></span>  
 <span data-ttu-id="603e0-109">Aşağıdaki örnekte tüm seçer `p` tarafından hemen ardından öğeleri bir `ul` öğesi.</span><span class="sxs-lookup"><span data-stu-id="603e0-109">The following example selects all `p` elements that are immediately followed by a `ul` element.</span></span>  
  
```csharp  
XElement doc = XElement.Parse(@"<Root>  
    <p id=""1""/>  
    <ul>abc</ul>  
    <Child>  
        <p id=""2""/>  
        <notul/>  
        <p id=""3""/>  
        <ul>def</ul>  
        <p id=""4""/>  
    </Child>  
    <Child>  
        <p id=""5""/>  
        <notul/>  
        <p id=""6""/>  
        <ul>abc</ul>  
        <p id=""7""/>  
    </Child>  
</Root>");  
  
IEnumerable<XElement> items =  
    from e in doc.Descendants("p")  
    let z = e.ElementsAfterSelf().FirstOrDefault()  
    where z != null && z.Name.LocalName == "ul"  
    select e;  
  
foreach (XElement e in items)  
    Console.WriteLine("id = {0}", (string)e.Attribute("id"));  
```  
  
 <span data-ttu-id="603e0-110">Bu kod aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="603e0-110">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="example"></a><span data-ttu-id="603e0-111">Örnek</span><span class="sxs-lookup"><span data-stu-id="603e0-111">Example</span></span>  
 <span data-ttu-id="603e0-112">Aşağıdaki örnek, aynı sorgu için bir ad alanındaki XML gösterir.</span><span class="sxs-lookup"><span data-stu-id="603e0-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="603e0-113">Daha fazla bilgi için [(C#) XML ad alanları ile çalışma](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="603e0-113">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XElement doc = XElement.Parse(@"<Root xmlns='http://www.adatum.com'>  
    <p id=""1""/>  
    <ul>abc</ul>  
    <Child>  
        <p id=""2""/>  
        <notul/>  
        <p id=""3""/>  
        <ul>def</ul>  
        <p id=""4""/>  
    </Child>  
    <Child>  
        <p id=""5""/>  
        <notul/>  
        <p id=""6""/>  
        <ul>abc</ul>  
        <p id=""7""/>  
    </Child>  
</Root>");  
  
XNamespace ad = "http://www.adatum.com";  
  
IEnumerable<XElement> items =  
    from e in doc.Descendants(ad + "p")  
    let z = e.ElementsAfterSelf().FirstOrDefault()  
    where z != null && z.Name == ad.GetName("ul")  
    select e;  
  
foreach (XElement e in items)  
    Console.WriteLine("id = {0}", (string)e.Attribute("id"));  
```  
  
 <span data-ttu-id="603e0-114">Bu kod aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="603e0-114">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="see-also"></a><span data-ttu-id="603e0-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="603e0-115">See also</span></span>

- <xref:System.Xml.Linq.XElement.Parse%2A>
- <xref:System.Xml.Linq.XContainer.Descendants%2A>
- <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>
- <xref:System.Linq.Enumerable.FirstOrDefault%2A>
