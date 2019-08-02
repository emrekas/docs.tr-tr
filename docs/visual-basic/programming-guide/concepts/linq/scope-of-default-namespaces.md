---
title: Visual Basic varsayılan ad alanlarının kapsamı
ms.date: 07/20/2015
ms.assetid: d4cce80c-342f-4097-be8b-40ab0bfa90ba
ms.openlocfilehash: af868454c9d1dce7d8bf5a1902f64eff8db8780c
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710351"
---
# <a name="scope-of-default-namespaces-in-visual-basic"></a><span data-ttu-id="e6b23-102">Visual Basic varsayılan ad alanlarının kapsamı</span><span class="sxs-lookup"><span data-stu-id="e6b23-102">Scope of Default Namespaces in Visual Basic</span></span>
<span data-ttu-id="e6b23-103">XML ağacında temsil edilen varsayılan ad alanları sorgular kapsamında değildir.</span><span class="sxs-lookup"><span data-stu-id="e6b23-103">Default namespaces as represented in the XML tree are not in scope for queries.</span></span> <span data-ttu-id="e6b23-104">Varsayılan bir ad alanında olan XML varsa, sorguda kullanılacak nitelikli bir ad oluşturmak için bir <xref:System.Xml.Linq.XNamespace> değişken bildirmeniz ve bunu yerel adla birleştirmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="e6b23-104">If you have XML that is in a default namespace, you still must declare an <xref:System.Xml.Linq.XNamespace> variable, and combine it with the local name to make a qualified name to be used in the query.</span></span>  
  
 <span data-ttu-id="e6b23-105">XML ağaçlarını sorgularken en yaygın sorunlardan biri, XML ağacının varsayılan bir ad alanına sahip olması ve geliştiricinin bazen sorguyu bir ad alanında olmamasına rağmen yazar.</span><span class="sxs-lookup"><span data-stu-id="e6b23-105">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>  
  
 <span data-ttu-id="e6b23-106">Bu konudaki ilk örnek kümesi, varsayılan bir ad alanındaki XML 'nin yüklendiği, ancak yanlış sorgulandığı tipik bir yöntemi gösterir.</span><span class="sxs-lookup"><span data-stu-id="e6b23-106">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, but is queried improperly.</span></span>  
  
 <span data-ttu-id="e6b23-107">İkinci örnek kümesinde, bir ad alanında XML 'yi sorgulayabilmeniz için gerekli düzeltmeler gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="e6b23-107">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6b23-108">Örnek</span><span class="sxs-lookup"><span data-stu-id="e6b23-108">Example</span></span>  
 <span data-ttu-id="e6b23-109">Bu örnek, bir ad alanında XML oluşturmayı ve boş bir sonuç kümesi döndüren bir sorguyu gösterir.</span><span class="sxs-lookup"><span data-stu-id="e6b23-109">This example shows the creation of XML in a namespace, and a query that returns an empty result set.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e6b23-110">Kod</span><span class="sxs-lookup"><span data-stu-id="e6b23-110">Code</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root xmlns='http://www.adventure-works.com'>  
                <Child>1</Child>  
                <Child>2</Child>  
                <Child>3</Child>  
                <AnotherChild>4</AnotherChild>  
                <AnotherChild>5</AnotherChild>  
                <AnotherChild>6</AnotherChild>  
            </Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
                From el In root.<Child> _  
                Select el  
        Console.WriteLine("Result set follows:")  
        For Each el As XElement In c1  
            Console.WriteLine(CInt(el))  
        Next  
        Console.WriteLine("End of result set")  
    End Sub  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="e6b23-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e6b23-111">Comments</span></span>  
 <span data-ttu-id="e6b23-112">Bu örnek aşağıdaki sonucu üretir:</span><span class="sxs-lookup"><span data-stu-id="e6b23-112">This example produces the following result:</span></span>  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a><span data-ttu-id="e6b23-113">Örnek</span><span class="sxs-lookup"><span data-stu-id="e6b23-113">Example</span></span>  
 <span data-ttu-id="e6b23-114">Bu örnek, bir ad alanında XML oluşturmayı ve düzgün kodlanmış bir sorguyu gösterir.</span><span class="sxs-lookup"><span data-stu-id="e6b23-114">This example shows the creation of XML in a namespace, and a query that is coded properly.</span></span>  
  
 <span data-ttu-id="e6b23-115">Yukarıdaki yanlış kodlanmış örneğin aksine, Visual Basic kullanırken doğru yaklaşım genel bir varsayılan ad alanını bildirmek ve başlatmak olur.</span><span class="sxs-lookup"><span data-stu-id="e6b23-115">In contrast to the incorrectly coded example above, the correct approach when using Visual Basic is to declare and initialize a global default namespace.</span></span> <span data-ttu-id="e6b23-116">Bu, tüm XML özelliklerini varsayılan ad alanına koyar.</span><span class="sxs-lookup"><span data-stu-id="e6b23-116">This places all XML properties in the default namespace.</span></span> <span data-ttu-id="e6b23-117">Doğru çalışması için örnek için başka bir değişiklik yapmanız gerekmez.</span><span class="sxs-lookup"><span data-stu-id="e6b23-117">No other modifications are required to the example to make it work properly.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e6b23-118">Kod</span><span class="sxs-lookup"><span data-stu-id="e6b23-118">Code</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root xmlns='http://www.adventure-works.com'>  
                <Child>1</Child>  
                <Child>2</Child>  
                <Child>3</Child>  
                <AnotherChild>4</AnotherChild>  
                <AnotherChild>5</AnotherChild>  
                <AnotherChild>6</AnotherChild>  
            </Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
                From el In root.<Child> _  
                Select el  
        Console.WriteLine("Result set follows:")  
        For Each el As XElement In c1  
            Console.WriteLine(el.Value)  
        Next  
        Console.WriteLine("End of result set")  
    End Sub  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="e6b23-119">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e6b23-119">Comments</span></span>  
 <span data-ttu-id="e6b23-120">Bu örnek aşağıdaki sonucu üretir:</span><span class="sxs-lookup"><span data-stu-id="e6b23-120">This example produces the following result:</span></span>  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6b23-121">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="e6b23-121">See also</span></span>

- [<span data-ttu-id="e6b23-122">Ad alanlarına genel bakış (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6b23-122">Namespaces Overview (LINQ to XML) (Visual Basic)</span></span>](namespaces-overview-linq-to-xml.md)
