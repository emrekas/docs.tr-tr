---
title: C# (LINQ to XML) XML ağaçları oluşturma
ms.date: 08/31/2018
ms.assetid: cc74234a-0bac-4327-9c8c-5a2ead15b595
ms.openlocfilehash: 3bac7b62d04c9690cdd08d1993b64db33c4e6ab8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54503176"
---
# <a name="creating-xml-trees-in-c-linq-to-xml"></a><span data-ttu-id="f60d0-102">C# (LINQ to XML) XML ağaçları oluşturma</span><span class="sxs-lookup"><span data-stu-id="f60d0-102">Creating XML trees in C# (LINQ to XML)</span></span>
<span data-ttu-id="f60d0-103">Bu bölümde, C# dilinde XML ağaçları oluşturma hakkında bilgi sağlar.</span><span class="sxs-lookup"><span data-stu-id="f60d0-103">This section provides information about creating XML trees in C#.</span></span>  
  
 <span data-ttu-id="f60d0-104">LINQ sorguları sonuçları içerik için kullanma hakkında bilgi için bir <xref:System.Xml.Linq.XElement>, bkz: [işlevsel oluşturma (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f60d0-104">For information about using the results of LINQ queries as the content for an <xref:System.Xml.Linq.XElement>, see [Functional Construction (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).</span></span>  
  
## <a name="constructing-elements"></a><span data-ttu-id="f60d0-105">Öğeleri oluşturma</span><span class="sxs-lookup"><span data-stu-id="f60d0-105">Constructing elements</span></span>
 <span data-ttu-id="f60d0-106">İmzalarını <xref:System.Xml.Linq.XElement> ve <xref:System.Xml.Linq.XAttribute> oluşturucular içeriği öğe veya öznitelik oluşturucusu için bağımsız değişken olarak geçirmenize olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="f60d0-106">The signatures of the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> constructors let you pass the contents of the element or attribute as arguments to the constructor.</span></span> <span data-ttu-id="f60d0-107">Değişken sayıda bağımsız değişken bir oluşturucular yararlandığı için herhangi bir sayıda alt öğeleri geçirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f60d0-107">Because one of the constructors takes a variable number of arguments, you can pass any number of child elements.</span></span> <span data-ttu-id="f60d0-108">Elbette, bu alt öğelerin her biri kendi alt öğelerini içerebilir.</span><span class="sxs-lookup"><span data-stu-id="f60d0-108">Of course, each of those child elements can contain their own child elements.</span></span> <span data-ttu-id="f60d0-109">Herhangi bir öğe için herhangi bir sayıda öznitelikler ekleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f60d0-109">For any element, you can add any number of attributes.</span></span>  
  
 <span data-ttu-id="f60d0-110">Eklerken <xref:System.Xml.Linq.XNode> (dahil olmak üzere <xref:System.Xml.Linq.XElement>) veya <xref:System.Xml.Linq.XAttribute> nesneler, yeni içerik üstü yoksa, nesneleri yalnızca bağlı XML ağacına.</span><span class="sxs-lookup"><span data-stu-id="f60d0-110">When adding <xref:System.Xml.Linq.XNode> (including <xref:System.Xml.Linq.XElement>) or <xref:System.Xml.Linq.XAttribute> objects, if the new content has no parent, the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="f60d0-111">Yeni içerik zaten üst öğe ve başka bir XML ağacının bir parçası ise, yeni içerik kopyalanmış olan ve yeni kopyalanan içeriği XML ağacına eklenir.</span><span class="sxs-lookup"><span data-stu-id="f60d0-111">If the new content already is parented, and is part of another XML tree, the new content is cloned, and the newly cloned content is attached to the XML tree.</span></span> <span data-ttu-id="f60d0-112">Bu konu Son örnekte bu gösterir.</span><span class="sxs-lookup"><span data-stu-id="f60d0-112">The last example in this topic demonstrates this.</span></span>  
  
 <span data-ttu-id="f60d0-113">Oluşturmak için bir `contacts` <xref:System.Xml.Linq.XElement>, aşağıdaki kodu kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="f60d0-113">To create a `contacts`<xref:System.Xml.Linq.XElement>, you could use the following code:</span></span>  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),   
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 <span data-ttu-id="f60d0-114">Düzgün bir şekilde oluşturmak için kod girintili varsa <xref:System.Xml.Linq.XElement> nesneleri temel alınan XML yapısını çok benzeyen.</span><span class="sxs-lookup"><span data-stu-id="f60d0-114">If indented properly, the code to construct <xref:System.Xml.Linq.XElement> objects closely resembles the structure of the underlying XML.</span></span>  
  
## <a name="xelement-constructors"></a><span data-ttu-id="f60d0-115">XElement oluşturucular</span><span class="sxs-lookup"><span data-stu-id="f60d0-115">XElement constructors</span></span>  
 <span data-ttu-id="f60d0-116"><xref:System.Xml.Linq.XElement> Sınıfı için işlevsel oluşturma şu oluşturuculardan kullanır.</span><span class="sxs-lookup"><span data-stu-id="f60d0-116">The <xref:System.Xml.Linq.XElement> class uses the following constructors for functional construction.</span></span> <span data-ttu-id="f60d0-117">Diğer bazı oluşturucular için olduğunu unutmayın <xref:System.Xml.Linq.XElement>, ancak bunlar listelenmediğinden burada işlevsel oluşturma için kullanılmaz.</span><span class="sxs-lookup"><span data-stu-id="f60d0-117">Note that there are some other constructors for <xref:System.Xml.Linq.XElement>, but because they are not used for functional construction they are not listed here.</span></span>  
  
|<span data-ttu-id="f60d0-118">Oluşturucu</span><span class="sxs-lookup"><span data-stu-id="f60d0-118">Constructor</span></span>|<span data-ttu-id="f60d0-119">Açıklama</span><span class="sxs-lookup"><span data-stu-id="f60d0-119">Description</span></span>|  
|-----------------|-----------------|  
|`XElement(XName name, object content)`|<span data-ttu-id="f60d0-120">Oluşturur bir <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="f60d0-120">Creates an <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="f60d0-121">`name` Parametresi belirtir; öğe adı `content` öğenin içeriğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="f60d0-121">The `name` parameter specifies the name of the element; `content` specifies the content of the element.</span></span>|  
|`XElement(XName name)`|<span data-ttu-id="f60d0-122">Oluşturur bir <xref:System.Xml.Linq.XElement> ile kendi <xref:System.Xml.Linq.XName> belirtilen adla başlatıldı.</span><span class="sxs-lookup"><span data-stu-id="f60d0-122">Creates an <xref:System.Xml.Linq.XElement> with its <xref:System.Xml.Linq.XName> initialized to the specified name.</span></span>|  
|`XElement(XName name, params object[] content)`|<span data-ttu-id="f60d0-123">Oluşturur bir <xref:System.Xml.Linq.XElement> ile kendi <xref:System.Xml.Linq.XName> belirtilen adla başlatıldı.</span><span class="sxs-lookup"><span data-stu-id="f60d0-123">Creates an <xref:System.Xml.Linq.XElement> with its <xref:System.Xml.Linq.XName> initialized to the specified name.</span></span> <span data-ttu-id="f60d0-124">Parametre listesi içeriğinden özniteliklerini ve/veya alt öğeleri oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="f60d0-124">The attributes and/or child elements are created from the contents of the parameter list.</span></span>|  
  
 <span data-ttu-id="f60d0-125">`content` Parametre son derece esnektir.</span><span class="sxs-lookup"><span data-stu-id="f60d0-125">The `content` parameter is extremely flexible.</span></span> <span data-ttu-id="f60d0-126">Tür geçerli bir alt nesneyi destekleyen bir <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="f60d0-126">It supports any type of object that is a valid child of an <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="f60d0-127">Bu parametreye geçirilen nesneleri farklı türleri için aşağıdaki kurallar geçerlidir:</span><span class="sxs-lookup"><span data-stu-id="f60d0-127">The following rules apply to different types of objects passed in this parameter:</span></span>  
  
-   <span data-ttu-id="f60d0-128">Bir dizeyi metin içeriği olarak eklenir.</span><span class="sxs-lookup"><span data-stu-id="f60d0-128">A string is added as text content.</span></span>  
  
-   <span data-ttu-id="f60d0-129">Bir <xref:System.Xml.Linq.XElement> bir alt öğesi eklenir.</span><span class="sxs-lookup"><span data-stu-id="f60d0-129">An <xref:System.Xml.Linq.XElement> is added as a child element.</span></span>  
  
-   <span data-ttu-id="f60d0-130">Bir <xref:System.Xml.Linq.XAttribute> öznitelik olarak eklenir.</span><span class="sxs-lookup"><span data-stu-id="f60d0-130">An <xref:System.Xml.Linq.XAttribute> is added as an attribute.</span></span>  
  
-   <span data-ttu-id="f60d0-131">Bir <xref:System.Xml.Linq.XProcessingInstruction>, <xref:System.Xml.Linq.XComment>, veya <xref:System.Xml.Linq.XText> alt içerik eklenir.</span><span class="sxs-lookup"><span data-stu-id="f60d0-131">An <xref:System.Xml.Linq.XProcessingInstruction>, <xref:System.Xml.Linq.XComment>, or <xref:System.Xml.Linq.XText> is added as child content.</span></span>  
  
-   <span data-ttu-id="f60d0-132">Bir <xref:System.Collections.IEnumerable> numaralandırılmış alan şeklinde ve bu kuralların sonuçları için özyinelemeli olarak uygulanır.</span><span class="sxs-lookup"><span data-stu-id="f60d0-132">An <xref:System.Collections.IEnumerable> is enumerated, and these rules are applied recursively to the results.</span></span>  
  
-   <span data-ttu-id="f60d0-133">Başka herhangi bir tür için kendi `ToString` yöntemi çağrılır ve sonuç metin içeriği eklenir.</span><span class="sxs-lookup"><span data-stu-id="f60d0-133">For any other type, its `ToString` method is called and the result is added as text content.</span></span>  
  
### <a name="creating-an-xelement-with-content"></a><span data-ttu-id="f60d0-134">Bir XElement ile içerik oluşturma</span><span class="sxs-lookup"><span data-stu-id="f60d0-134">Creating an XElement with content</span></span>  
 <span data-ttu-id="f60d0-135">Oluşturabileceğiniz bir <xref:System.Xml.Linq.XElement> içeren tek bir yöntem çağrısı ile basit içerik.</span><span class="sxs-lookup"><span data-stu-id="f60d0-135">You can create an <xref:System.Xml.Linq.XElement> that contains simple content with a single method call.</span></span> <span data-ttu-id="f60d0-136">Bunu yapmak için ikinci parametre olarak, içeriği aşağıdaki gibi belirtin:</span><span class="sxs-lookup"><span data-stu-id="f60d0-136">To do this, specify the content as the second parameter, as follows:</span></span>  
  
```csharp  
XElement n = new XElement("Customer", "Adventure Works");  
Console.WriteLine(n);  
```  
  
 <span data-ttu-id="f60d0-137">Bu örnek aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="f60d0-137">This example produces the following output:</span></span>  
  
```xml  
<Customer>Adventure Works</Customer>  
```  
  
 <span data-ttu-id="f60d0-138">Nesnesinin her türlü içeriği olarak geçirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f60d0-138">You can pass any type of object as the content.</span></span> <span data-ttu-id="f60d0-139">Örneğin, aşağıdaki kod bir değişken içeren bir öğe oluşturur nokta içerik olarak sayısı:</span><span class="sxs-lookup"><span data-stu-id="f60d0-139">For example, the following code creates an element that contains a floating point number as content:</span></span>  
  
```csharp  
XElement n = new XElement("Cost", 324.50);  
Console.WriteLine(n);  
```  
  
 <span data-ttu-id="f60d0-140">Bu örnek aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="f60d0-140">This example produces the following output:</span></span>  
  
```xml  
<Cost>324.5</Cost>  
```  
  
 <span data-ttu-id="f60d0-141">Kayan nokta numarası Kutulu ve oluşturucuya geçirilen.</span><span class="sxs-lookup"><span data-stu-id="f60d0-141">The floating point number is boxed and passed in to the constructor.</span></span> <span data-ttu-id="f60d0-142">Paketlenmiş sayıyı bir dizeye dönüştürülür ve öğenin içeriğini kullanılan.</span><span class="sxs-lookup"><span data-stu-id="f60d0-142">The boxed number is converted to a string and used as the content of the element.</span></span>  
  
### <a name="creating-an-xelement-with-a-child-element"></a><span data-ttu-id="f60d0-143">Bir XElement olan bir alt öğesi oluşturma</span><span class="sxs-lookup"><span data-stu-id="f60d0-143">Creating an XElement with a child element</span></span>  
 <span data-ttu-id="f60d0-144">Örneği geçirirseniz <xref:System.Xml.Linq.XElement> sınıfı Oluşturucu içerik bağımsız değişkeni için olan bir alt öğesi bir öğe oluşturur:</span><span class="sxs-lookup"><span data-stu-id="f60d0-144">If you pass an instance of the <xref:System.Xml.Linq.XElement> class for the content argument, the constructor creates an element with a child element:</span></span>  
  
```csharp  
XElement shippingUnit = new XElement("ShippingUnit",  
    new XElement("Cost", 324.50)  
);  
Console.WriteLine(shippingUnit);  
```  
  
 <span data-ttu-id="f60d0-145">Bu örnek aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="f60d0-145">This example produces the following output:</span></span>  
  
```xml  
<ShippingUnit>  
  <Cost>324.5</Cost>  
</ShippingUnit>  
```  
  
### <a name="creating-an-xelement-with-multiple-child-elements"></a><span data-ttu-id="f60d0-146">Bir XElement ile birden çok alt öğeleri oluşturma</span><span class="sxs-lookup"><span data-stu-id="f60d0-146">Creating an XElement with multiple child elements</span></span>  
 <span data-ttu-id="f60d0-147">Bir süre içinde geçirdiğiniz <xref:System.Xml.Linq.XElement> içerik için nesneleri.</span><span class="sxs-lookup"><span data-stu-id="f60d0-147">You can pass in a number of <xref:System.Xml.Linq.XElement> objects for the content.</span></span> <span data-ttu-id="f60d0-148">Her biri <xref:System.Xml.Linq.XElement> nesneleri bir alt öğesi eklenmiştir.</span><span class="sxs-lookup"><span data-stu-id="f60d0-148">Each of the <xref:System.Xml.Linq.XElement> objects is included as a child element.</span></span>  
  
```csharp  
XElement address = new XElement("Address",  
    new XElement("Street1", "123 Main St"),  
    new XElement("City", "Mercer Island"),  
    new XElement("State", "WA"),  
    new XElement("Postal", "68042")  
);  
Console.WriteLine(address);  
```  
  
 <span data-ttu-id="f60d0-149">Bu örnek aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="f60d0-149">This example produces the following output:</span></span>  
  
```xml  
<Address>  
  <Street1>123 Main St</Street1>  
  <City>Mercer Island</City>  
  <State>WA</State>  
  <Postal>68042</Postal>  
</Address>  
```  
  
 <span data-ttu-id="f60d0-150">Yukarıdaki örnekte genişleterek tüm XML ağacının, şu şekilde oluşturabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="f60d0-150">By extending the above example, you can create an entire XML tree, as follows:</span></span>  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),                                                   
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
Console.WriteLine(contacts);  
```  
  
 <span data-ttu-id="f60d0-151">Bu örnek aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="f60d0-151">This example produces the following output:</span></span>  
  
```xml  
<Contacts>  
  <Contact>  
    <Name>Patrick Hines</Name>  
    <Phone>206-555-0144</Phone>  
    <Address>  
      <Street1>123 Main St</Street1>  
      <City>Mercer Island</City>  
      <State>WA</State>  
      <Postal>68042</Postal>  
    </Address>  
  </Contact>  
</Contacts>  
```  

### <a name="creating-an-xelement-with-an-xattribute"></a><span data-ttu-id="f60d0-152">Bir XElement bir XAttribute ile oluşturma</span><span class="sxs-lookup"><span data-stu-id="f60d0-152">Creating an XElement with an XAttribute</span></span>
 <span data-ttu-id="f60d0-153">Örneği geçirirseniz <xref:System.Xml.Linq.XAttribute> sınıfı Oluşturucu içerik bağımsız değişkeni bir öznitelik bir öğe oluşturur:</span><span class="sxs-lookup"><span data-stu-id="f60d0-153">If you pass an instance of the <xref:System.Xml.Linq.XAttribute> class for the content argument, the constructor creates an element with an attribute:</span></span>

```csharp  
XElement phone = new XElement("Phone",  
    new XAttribute("Type", "Home"),  
    "555-555-5555");  
Console.WriteLine(phone);  
```  
  
 <span data-ttu-id="f60d0-154">Bu örnek aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="f60d0-154">This example produces the following output:</span></span>  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>
```   

### <a name="creating-an-empty-element"></a><span data-ttu-id="f60d0-155">Boş bir öğe oluşturma</span><span class="sxs-lookup"><span data-stu-id="f60d0-155">Creating an empty element</span></span>  
 <span data-ttu-id="f60d0-156">Boş bir oluşturmak için <xref:System.Xml.Linq.XElement>, oluşturucuya herhangi bir içerik geçirmeyin.</span><span class="sxs-lookup"><span data-stu-id="f60d0-156">To create an empty <xref:System.Xml.Linq.XElement>, you do not pass any content to the constructor.</span></span> <span data-ttu-id="f60d0-157">Aşağıdaki örnek, boş bir öğe oluşturur:</span><span class="sxs-lookup"><span data-stu-id="f60d0-157">The following example creates an empty element:</span></span>  
  
```csharp  
XElement n = new XElement("Customer");  
Console.WriteLine(n);  
```  
  
 <span data-ttu-id="f60d0-158">Bu örnek aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="f60d0-158">This example produces the following output:</span></span>  
  
```xml  
<Customer />  
```  
  
### <a name="attaching-vs-cloning"></a><span data-ttu-id="f60d0-159">Ekleme ve kopyalama</span><span class="sxs-lookup"><span data-stu-id="f60d0-159">Attaching vs. cloning</span></span>  
 <span data-ttu-id="f60d0-160">Eklerken daha önce de belirtildiği <xref:System.Xml.Linq.XNode> (dahil olmak üzere <xref:System.Xml.Linq.XElement>) veya <xref:System.Xml.Linq.XAttribute> nesneler, yeni içerik üstü yoksa, nesneleri yalnızca bağlı XML ağacına.</span><span class="sxs-lookup"><span data-stu-id="f60d0-160">As mentioned previously, when adding <xref:System.Xml.Linq.XNode> (including <xref:System.Xml.Linq.XElement>) or <xref:System.Xml.Linq.XAttribute> objects, if the new content has no parent, the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="f60d0-161">Yeni içerik zaten üst öğe ve başka bir XML ağacının bir parçası ise, yeni içerik kopyalanmış olan ve yeni kopyalanan içeriği XML ağacına eklenir.</span><span class="sxs-lookup"><span data-stu-id="f60d0-161">If the new content already is parented and is part of another XML tree, the new content is cloned, and the newly cloned content is attached to the XML tree.</span></span>  

<span data-ttu-id="f60d0-162">Aşağıdaki örnek, bir ağaca üst öğeye sahip bir öğe eklediğinizde ve bir ağaca hiçbir üst öğesi ile bir öğe eklediğinizde davranış gösterir.</span><span class="sxs-lookup"><span data-stu-id="f60d0-162">The following example demonstrates the behavior when you add a parented element to a tree, and when you add an element with no parent to a tree.</span></span>

```csharp  
// Create a tree with a child element.  
XElement xmlTree1 = new XElement("Root",  
    new XElement("Child1", 1)  
);  
  
// Create an element that is not parented.  
XElement child2 = new XElement("Child2", 2);  
  
// Create a tree and add Child1 and Child2 to it.  
XElement xmlTree2 = new XElement("Root",  
    xmlTree1.Element("Child1"),  
    child2  
);  
  
// Compare Child1 identity.  
Console.WriteLine("Child1 was {0}",  
    xmlTree1.Element("Child1") == xmlTree2.Element("Child1") ?  
    "attached" : "cloned");  
  
// Compare Child2 identity.  
Console.WriteLine("Child2 was {0}",  
    child2 == xmlTree2.Element("Child2") ?  
    "attached" : "cloned");  

// The example displays the following output:  
//    Child1 was cloned  
//    Child2 was attached  
```

## <a name="see-also"></a><span data-ttu-id="f60d0-163">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="f60d0-163">See also</span></span>

- [<span data-ttu-id="f60d0-164">XML ağaçları oluşturma (C#)</span><span class="sxs-lookup"><span data-stu-id="f60d0-164">Creating XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)
