---
title: 'Nasıl yapılır: Bir dosyadan XML yükleme (C#)'
ms.date: 07/20/2015
ms.assetid: 3ed38487-8028-4209-9872-c8dce0ed4dfe
ms.openlocfilehash: f97e99a3d5fb2dd5628e1dc00909b6608255a967
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667918"
---
# <a name="how-to-load-xml-from-a-file-c"></a><span data-ttu-id="088e9-102">Nasıl yapılır: Bir dosyadan XML yükleme (C#)</span><span class="sxs-lookup"><span data-stu-id="088e9-102">How to: Load XML from a File (C#)</span></span>
<span data-ttu-id="088e9-103">Bu konuda, XML, kullanarak bir URI'den yüklemek gösterilmektedir <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="088e9-103">This topic shows how to load XML from a URI by using the <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="088e9-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="088e9-104">Example</span></span>  
 <span data-ttu-id="088e9-105">Aşağıdaki örnek, bir XML belgesi bir dosyadan yüklemek gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="088e9-105">The following example shows how to load an XML document from a file.</span></span> <span data-ttu-id="088e9-106">Aşağıdaki örnek, books.xml yükler ve konsola XML ağacı çıkarır.</span><span class="sxs-lookup"><span data-stu-id="088e9-106">The following example loads books.xml and outputs the XML tree to the console.</span></span>  
  
 <span data-ttu-id="088e9-107">Bu örnek aşağıdaki XML belgesi kullanır: [Örnek XML dosyası: Kitaplar (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="088e9-107">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```csharp  
XElement booksFromFile = XElement.Load(@"books.xml");  
Console.WriteLine(booksFromFile);  
```  
  
 <span data-ttu-id="088e9-108">Bu kod aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="088e9-108">This code produces the following output:</span></span>  
  
```xml  
<Catalog>  
  <Book id="bk101">  
    <Author>Garghentini, Davide</Author>  
    <Title>XML Developer's Guide</Title>  
    <Genre>Computer</Genre>  
    <Price>44.95</Price>  
    <PublishDate>2000-10-01</PublishDate>  
    <Description>An in-depth look at creating applications   
      with XML.</Description>  
  </Book>  
  <Book id="bk102">  
    <Author>Garcia, Debra</Author>  
    <Title>Midnight Rain</Title>  
    <Genre>Fantasy</Genre>  
    <Price>5.95</Price>  
    <PublishDate>2000-12-16</PublishDate>  
    <Description>A former architect battles corporate zombies,   
      an evil sorceress, and her own childhood to become queen   
      of the world.</Description>  
  </Book>  
</Catalog>  
```  
  
## <a name="see-also"></a><span data-ttu-id="088e9-109">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="088e9-109">See also</span></span>

- [<span data-ttu-id="088e9-110">XML Ayrıştırma (C#)</span><span class="sxs-lookup"><span data-stu-id="088e9-110">Parsing XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)
