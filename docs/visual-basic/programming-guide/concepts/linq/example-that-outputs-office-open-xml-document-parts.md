---
title: Office Open XML belge kısımları (Visual Basic) çıkaran örnek
ms.date: 07/20/2015
ms.assetid: a951925b-c985-48ed-b215-2a68b58f1ae5
ms.openlocfilehash: 0ad7dc9d6f68ecde88888b0f0250632f3f946f92
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670257"
---
# <a name="example-that-outputs-office-open-xml-document-parts-visual-basic"></a><span data-ttu-id="409c5-102">Office Open XML belge kısımları (Visual Basic) çıkaran örnek</span><span class="sxs-lookup"><span data-stu-id="409c5-102">Example that Outputs Office Open XML Document Parts (Visual Basic)</span></span>
<span data-ttu-id="409c5-103">Bu konuda, bir Office Open XML belgesi açın ve erişim bölümleri içindeki gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="409c5-103">This topic shows how to open an Office Open XML document and access parts within it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="409c5-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="409c5-104">Example</span></span>  
 <span data-ttu-id="409c5-105">Aşağıdaki örnek, bir Office Open XML belge açılır ve belge ve stil bölümlerini konsola yazdırır.</span><span class="sxs-lookup"><span data-stu-id="409c5-105">The following example opens an Office Open XML document, and prints the document part and the style part to the console.</span></span>  
  
 <span data-ttu-id="409c5-106">Bu örnek WindowsBase derlemesinden sınıfları kullanır.</span><span class="sxs-lookup"><span data-stu-id="409c5-106">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="409c5-107">Türleri kullanan <xref:System.IO.Packaging?displayProperty=nameWithType> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="409c5-107">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```vb  
Const fileName As String = "SampleDoc.docx"  
  
Const documentRelationshipType As String = _  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
Const stylesRelationshipType As String = _  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"  
Const wordmlNamespace As String = _  
  "http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
Dim w As XNamespace = wordmlNamespace  
  
Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)  
    Dim docPackageRelationship As PackageRelationship = _  
      wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
    If docPackageRelationship IsNot Nothing Then  
        Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), _  
          docPackageRelationship.TargetUri)  
        Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
        ' Load the document XML in the part into an XDocument instance.  
        Dim xdoc As XDocument = XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
  
        Console.WriteLine("TargetUri:{0}", docPackageRelationship.TargetUri)  
        Console.WriteLine("==================================================================")  
        Console.WriteLine(xdoc.Root)  
        Console.WriteLine()  
  
        ' Find the styles part. There will only be one.  
        Dim styleRelation As PackageRelationship = _  
          documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()  
        If styleRelation IsNot Nothing Then  
            Dim styleUri As Uri = _  
              PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)  
            Dim stylePart As PackagePart = wdPackage.GetPart(styleUri)  
  
            ' Load the style XML in the part into an XDocument instance.  
            Dim styleDoc As XDocument = XDocument.Load(XmlReader.Create(stylePart.GetStream()))  
  
            Console.WriteLine("TargetUri:{0}", styleRelation.TargetUri)  
            Console.WriteLine("==================================================================")  
            Console.WriteLine(styleDoc.Root)  
            Console.WriteLine()  
        End If  
    End If  
End Using  
```  
  
## <a name="see-also"></a><span data-ttu-id="409c5-108">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="409c5-108">See also</span></span>
- [<span data-ttu-id="409c5-109">Ayrıntılar Office Open XML WordprocessingML belgelerinin (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="409c5-109">Details of Office Open XML WordprocessingML Documents (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md)
