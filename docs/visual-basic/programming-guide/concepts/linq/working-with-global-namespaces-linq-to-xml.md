---
title: Genel ad alanları (Visual Basic) (LINQ to XML) ile çalışma
ms.date: 07/20/2015
ms.assetid: 0a8064d5-e02f-4315-ad48-6deaa443a2f0
ms.openlocfilehash: 0922c6973baeb3e0ca51d984b332fd7a3e0b13f6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733915"
---
# <a name="working-with-global-namespaces-visual-basic-linq-to-xml"></a><span data-ttu-id="11c89-102">Genel ad alanları (Visual Basic) (LINQ to XML) ile çalışma</span><span class="sxs-lookup"><span data-stu-id="11c89-102">Working with Global Namespaces (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="11c89-103">Visual Basic'de XML değişmez değerlerini anahtar özelliklerinden biridir özelliği XML ad alanlarını kullanarak bildirme `Imports` deyimi.</span><span class="sxs-lookup"><span data-stu-id="11c89-103">One of the key features of XML literals in Visual Basic is the capability to declare XML namespaces by using the `Imports` statement.</span></span> <span data-ttu-id="11c89-104">Bu özelliği kullanarak, bir ön ekini kullanan bir XML ad alanı bildirebilir veya varsayılan XML ad alanı bildirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="11c89-104">Using this feature, you can declare an XML namespace that uses a prefix, or you can declare a default XML namespace.</span></span>  
  
 <span data-ttu-id="11c89-105">Bu yetenek, iki durumlarda kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="11c89-105">This capability is useful in two situations.</span></span> <span data-ttu-id="11c89-106">İlk olarak, XML değişmez değerlerine bildirilen ad alanları katıştırılmış ifadeler taşınmaz.</span><span class="sxs-lookup"><span data-stu-id="11c89-106">First, namespaces declared in XML literals do not carry over into embedded expressions.</span></span> <span data-ttu-id="11c89-107">Genel ad alanlarını bildirme katıştırılmış ifadeler ad alanları ile kullanmak için yapmanız gereken iş miktarını azaltır.</span><span class="sxs-lookup"><span data-stu-id="11c89-107">Declaring global namespaces reduces the amount of work that you have to do to use embedded expressions with namespaces.</span></span> <span data-ttu-id="11c89-108">İkinci olarak, ad alanları XML özellikleri ile kullanmak için genel ad alanları belirtmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="11c89-108">Second, you must declare global namespaces in order to use namespaces with XML properties.</span></span>  
  
 <span data-ttu-id="11c89-109">Genel ad alanları proje düzeyinde bildirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="11c89-109">You can declare global namespaces at the project level.</span></span> <span data-ttu-id="11c89-110">Proje düzeyi genel ad alanları geçersiz kılmalar Modül düzeyinde genel ad alanları da bildirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="11c89-110">You can also declare global namespaces at the module level, which overrides the project-level global namespaces.</span></span> <span data-ttu-id="11c89-111">Son olarak, genel ad alanları sabit değeri bir XML geçersiz kılabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="11c89-111">Finally, you can override global namespaces in an XML literal.</span></span>  
  
 <span data-ttu-id="11c89-112">XML sabit değerleri veya genel olarak bildirilen ad alanlarında XML özellikleri kullandığınızda, Visual Studio'da üzerine gelerek genişletilmiş adını XML sabit değerleri veya özellikleri görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="11c89-112">When using XML literals or XML properties that are in globally-declared namespaces, you can see the expanded name of XML literals or properties by hovering over them in Visual Studio.</span></span> <span data-ttu-id="11c89-113">Genişletilmiş adı bir araç ipucu olarak görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="11c89-113">You will see the expanded name in a tooltip.</span></span>  
  
 <span data-ttu-id="11c89-114">Alabileceğiniz bir <xref:System.Xml.Linq.XNamespace> kullanarak bir genel ad karşılık gelen nesne `GetXmlNamespace` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="11c89-114">You can get an <xref:System.Xml.Linq.XNamespace> object that corresponds to a global namespace using the `GetXmlNamespace` method.</span></span>  
  
## <a name="examples-of-global-namespaces"></a><span data-ttu-id="11c89-115">Genel ad alanları örnekleri</span><span class="sxs-lookup"><span data-stu-id="11c89-115">Examples of Global Namespaces</span></span>  
 <span data-ttu-id="11c89-116">Aşağıdaki örnek, kullanarak varsayılan genel bir ad bildirir `Imports` deyimi ve sonra başlatmak için kullandığı bir XML değişmez bir <xref:System.Xml.Linq.XElement> nesne bu ad alanındaki:</span><span class="sxs-lookup"><span data-stu-id="11c89-116">The following example declares a default global namespace by using the `Imports` statement, and then uses an XML literal to initialize an <xref:System.Xml.Linq.XElement> object in that namespace:</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <Root/>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="11c89-117">Bu örnek aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="11c89-117">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com" />  
```  
  
 <span data-ttu-id="11c89-118">Aşağıdaki örnek bir genel ad alanı öneki ile bildirir ve ardından bir öğe başlatmak için bir XML değişmez değer kullanır:</span><span class="sxs-lookup"><span data-stu-id="11c89-118">The following example declares a global namespace with a prefix, and then uses an XML literal to initialize an element:</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root/>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="11c89-119">Bu örnek aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="11c89-119">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" />  
```  
  
## <a name="global-namespaces-and-embedded-expressions"></a><span data-ttu-id="11c89-120">Genel ad alanları ve katıştırılmış ifadeler</span><span class="sxs-lookup"><span data-stu-id="11c89-120">Global Namespaces and Embedded Expressions</span></span>  
 <span data-ttu-id="11c89-121">XML değişmez değerlerine bildirilen ad alanları katıştırılmış ifadeler taşınmaz.</span><span class="sxs-lookup"><span data-stu-id="11c89-121">Namespaces that are declared in XML literals do not carry over into embedded expressions.</span></span> <span data-ttu-id="11c89-122">Aşağıdaki örnek, bir varsayılan ad alanı bildirir.</span><span class="sxs-lookup"><span data-stu-id="11c89-122">The following example declares a default namespace.</span></span> <span data-ttu-id="11c89-123">Katıştırılmış bir ifade kullanır `Child` öğesi.</span><span class="sxs-lookup"><span data-stu-id="11c89-123">It then uses an embedded expression for the `Child` element.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <%= <Child/> %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="11c89-124">Bu örnek aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="11c89-124">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child xmlns="" />  
</Root>  
```  
  
 <span data-ttu-id="11c89-125">Gördüğünüz gibi elde edilen XML varsayılan ad alanı bildirimini içerir. böylece `Child` hiçbir ad alanında bir öğedir.</span><span class="sxs-lookup"><span data-stu-id="11c89-125">As you can see, the resulting XML includes a declaration of a default namespace so that the `Child` element is in no namespace.</span></span>  
  
 <span data-ttu-id="11c89-126">Ad alanında bir katıştırılmış deyim şu şekilde yeniden bildirebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="11c89-126">You could re-declare the namespace in the embedded expression, as follows:</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <%= <Child xmlns="http://www.adventure-works.com"/> %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="11c89-127">Bu örnek aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="11c89-127">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child xmlns="http://www.adventure-works.com" />  
</Root>  
```  
  
 <span data-ttu-id="11c89-128">Ancak, bu daha iyi bir yaklaşım genel varsayılan ad alanını kullanmak için daha kullanışsız olur.</span><span class="sxs-lookup"><span data-stu-id="11c89-128">However, this is more cumbersome to use than the global default namespace, which is a better approach.</span></span> <span data-ttu-id="11c89-129">Genel varsayılan ad alanı ile ad alanlarını bildirme olmadan XML sabit değerleri kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="11c89-129">With the global default namespace, you can use XML literals without declaring namespaces.</span></span> <span data-ttu-id="11c89-130">Elde edilen XML içinde genel olarak bildirilen varsayılan ad alanı olacaktır.</span><span class="sxs-lookup"><span data-stu-id="11c89-130">The resulting XML will be in the globally-declared default namespace.</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <Root>  
                                   <%= <Child/> %>  
                               </Root>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="11c89-131">Bu örnek aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="11c89-131">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child />  
</Root>  
```  
  
## <a name="using-namespaces-with-xml-properties"></a><span data-ttu-id="11c89-132">XML özellikleri ile ad alanlarını kullanma</span><span class="sxs-lookup"><span data-stu-id="11c89-132">Using Namespaces with XML Properties</span></span>  
 <span data-ttu-id="11c89-133">XML özellikleri de doğru isim uzayında olacaktır, böylece bir ad alanındaki bir XML ağacı çalıştığınız ve XML özellikleri kullanırsanız, genel bir ad kullanmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="11c89-133">If you are working with an XML tree that is in a namespace, and you use XML properties, then you must use a global namespace so that the XML properties will also be in the correct namespace.</span></span> <span data-ttu-id="11c89-134">Aşağıdaki örnek, bir XML ağacının ad bildirir.</span><span class="sxs-lookup"><span data-stu-id="11c89-134">The following example declares an XML tree in a namespace.</span></span> <span data-ttu-id="11c89-135">Ardından sayısı yazdırır `Child` öğeleri.</span><span class="sxs-lookup"><span data-stu-id="11c89-135">It then prints the count of `Child` elements.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <Child>content</Child>  
    </Root>  
Console.WriteLine(root.<Child>.Count())  
```  
  
 <span data-ttu-id="11c89-136">Bu örnek olduğunu gösterir. hiçbir `Child` öğeleri.</span><span class="sxs-lookup"><span data-stu-id="11c89-136">This example indicates that there are no `Child` elements.</span></span> <span data-ttu-id="11c89-137">Bu, aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="11c89-137">It produces the following output:</span></span>  
  
```  
0  
```  
  
 <span data-ttu-id="11c89-138">Ardından ancak varsayılan genel ad alanı bildirirseniz, XML değişmez değer hem XML özelliği varsayılan genel ad alanında şunlardır:</span><span class="sxs-lookup"><span data-stu-id="11c89-138">If, however, you declare a default global namespace, then both the XML literal and the XML property are in the default global namespace:</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child>content</Child>  
            </Root>  
        Console.WriteLine(root.<Child>.Count())  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="11c89-139">Bu örnek olduğunu belirten `Child` öğesi.</span><span class="sxs-lookup"><span data-stu-id="11c89-139">This example indicates that there is one `Child` element.</span></span> <span data-ttu-id="11c89-140">Bu, aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="11c89-140">It produces the following output:</span></span>  
  
```  
1  
```  
  
 <span data-ttu-id="11c89-141">Bir ön ekine sahip bir genel ad alanı olarak bildirirseniz, XML değişmez değerleri ve XML özellikleri için ön ek kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="11c89-141">If you declare a global namespace that has a prefix, you can use the prefix for both XML literals and XML properties:</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child>content</aw:Child>  
            </aw:Root>  
        Console.WriteLine(root.<aw:Child>.Count())  
    End Sub  
End Module  
```  
  
## <a name="xnamespace-and-global-namespaces"></a><span data-ttu-id="11c89-142">XNamespace ve genel ad alanları</span><span class="sxs-lookup"><span data-stu-id="11c89-142">XNamespace and Global Namespaces</span></span>  
 <span data-ttu-id="11c89-143">Alabileceğiniz bir <xref:System.Xml.Linq.XNamespace> kullanarak nesne `GetXmlNamespace` yöntemi:</span><span class="sxs-lookup"><span data-stu-id="11c89-143">You can get an <xref:System.Xml.Linq.XNamespace> object by using the `GetXmlNamespace` method:</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root/>  
        Dim xn As XNamespace = GetXmlNamespace(aw)  
        Console.WriteLine(xn)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="11c89-144">Bu örnek aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="11c89-144">This example produces the following output:</span></span>  
  
```  
http://www.adventure-works.com  
```  
  
## <a name="see-also"></a><span data-ttu-id="11c89-145">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="11c89-145">See also</span></span>
- [<span data-ttu-id="11c89-146">XML ad alanları (Visual Basic) ile çalışma</span><span class="sxs-lookup"><span data-stu-id="11c89-146">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
