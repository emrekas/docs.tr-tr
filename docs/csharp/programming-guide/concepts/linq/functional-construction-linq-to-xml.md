---
title: İşlevsel oluşturma (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 57a82bcf-de03-4f1c-a0c8-9a76e989d542
ms.openlocfilehash: 46cf4dbaf190182467cbbe1094070b2da0854c68
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486044"
---
# <a name="functional-construction-linq-to-xml-c"></a><span data-ttu-id="dd93d-102">İşlevsel oluşturma (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="dd93d-102">Functional Construction (LINQ to XML) (C#)</span></span>
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="dd93d-103">adlı XML öğeleri oluşturmak için güçlü bir yol sağlar *işlevsel oluşturma*.</span><span class="sxs-lookup"><span data-stu-id="dd93d-103">provides a powerful way to create XML elements called *functional construction*.</span></span> <span data-ttu-id="dd93d-104">Tek bir deyimde bir XML ağacı oluşturma olanağı işlevsel yapısıdır.</span><span class="sxs-lookup"><span data-stu-id="dd93d-104">Functional construction is the ability to create an XML tree in a single statement.</span></span>  
  
 <span data-ttu-id="dd93d-105">Birkaç temel özellikleri vardır [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] işlevsel oluşturma sağlayan bir programlama arabirimi:</span><span class="sxs-lookup"><span data-stu-id="dd93d-105">There are several key features of the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] programming interface that enable functional construction:</span></span>  
  
- <span data-ttu-id="dd93d-106"><xref:System.Xml.Linq.XElement> Oluşturucusu, çeşitli içerik için bağımsız değişkenleri alır.</span><span class="sxs-lookup"><span data-stu-id="dd93d-106">The <xref:System.Xml.Linq.XElement> constructor takes various types of arguments for content.</span></span> <span data-ttu-id="dd93d-107">Örneğin, başka bir geçirebilirsiniz <xref:System.Xml.Linq.XElement> bir alt öğesi olan nesne.</span><span class="sxs-lookup"><span data-stu-id="dd93d-107">For example, you can pass another <xref:System.Xml.Linq.XElement> object, which becomes a child element.</span></span> <span data-ttu-id="dd93d-108">Geçirebilirsiniz bir <xref:System.Xml.Linq.XAttribute> öğesinin bir özniteliği olan nesne.</span><span class="sxs-lookup"><span data-stu-id="dd93d-108">You can pass an <xref:System.Xml.Linq.XAttribute> object, which becomes an attribute of the element.</span></span> <span data-ttu-id="dd93d-109">Veya başka türde bir nesne bir dizeye dönüştürülür ve öğenin metin içeriğini olur geçirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="dd93d-109">Or you can pass any other type of object, which is converted to a string and becomes the text content of the element.</span></span>  
  
- <span data-ttu-id="dd93d-110"><xref:System.Xml.Linq.XElement> Oluşturucusu alır bir `params` türünde dizi <xref:System.Object>, böylece herhangi bir sayıda nesneleri için oluşturucu geçirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="dd93d-110">The <xref:System.Xml.Linq.XElement> constructor takes a `params` array of type <xref:System.Object>, so that you can pass any number of objects to the constructor.</span></span> <span data-ttu-id="dd93d-111">Bu, karmaşık içeriğe sahip bir öğe oluşturmanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="dd93d-111">This enables you to create an element that has complex content.</span></span>  
  
- <span data-ttu-id="dd93d-112">Bir nesne uyguluyorsa <xref:System.Collections.Generic.IEnumerable%601>, koleksiyon nesnesi içinde listelenmiş ve koleksiyondaki tüm öğelerin eklenir.</span><span class="sxs-lookup"><span data-stu-id="dd93d-112">If an object implements <xref:System.Collections.Generic.IEnumerable%601>, the collection in the object is enumerated, and all items in the collection are added.</span></span> <span data-ttu-id="dd93d-113">Koleksiyon içeriyorsa <xref:System.Xml.Linq.XElement> veya <xref:System.Xml.Linq.XAttribute> nesneler, koleksiyondaki her öğe ayrı olarak eklenir.</span><span class="sxs-lookup"><span data-stu-id="dd93d-113">If the collection contains <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, each item in the collection is added separately.</span></span> <span data-ttu-id="dd93d-114">Sonuçlarını geçirmenize izin verdiğinden, bu önemli bir [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Sorgu Oluşturucusu.</span><span class="sxs-lookup"><span data-stu-id="dd93d-114">This is important because it lets you pass the results of a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query to the constructor.</span></span>  
  
 <span data-ttu-id="dd93d-115">Bu özellikleri bir XML ağacı oluşturmak için kod yazmanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="dd93d-115">These features enable you to write code to create an XML tree.</span></span> <span data-ttu-id="dd93d-116">Bir örnek verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="dd93d-116">The following is an example:</span></span>  
  
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
  
 <span data-ttu-id="dd93d-117">Bu özellikler ayrıca sonuçlarını kullanan kod yazmanıza etkinleştirme [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] sorgular ne zaman bir XML ağacı şu şekilde oluşturun:</span><span class="sxs-lookup"><span data-stu-id="dd93d-117">These features also enable you to write code that uses the results of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries when you create an XML tree, as follows:</span></span>  
  
```csharp  
XElement srcTree = new XElement("Root",  
    new XElement("Element", 1),  
    new XElement("Element", 2),  
    new XElement("Element", 3),  
    new XElement("Element", 4),  
    new XElement("Element", 5)  
);  
XElement xmlTree = new XElement("Root",  
    new XElement("Child", 1),  
    new XElement("Child", 2),  
    from el in srcTree.Elements()  
    where (int)el > 2  
    select el  
);  
Console.WriteLine(xmlTree);  
```  
  
 <span data-ttu-id="dd93d-118">Bu örnek aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="dd93d-118">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  