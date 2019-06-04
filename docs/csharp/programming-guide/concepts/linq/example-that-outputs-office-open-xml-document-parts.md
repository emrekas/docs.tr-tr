---
title: Office Open XML belge kısımları (C#) çıkaran örnek
ms.date: 07/20/2015
ms.assetid: 6cd37055-89b4-42e8-bf27-5a29717e35f3
ms.openlocfilehash: be4c0ba2ce2a007fa6e19a65d7d86854d85851c4
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66485995"
---
# <a name="example-that-outputs-office-open-xml-document-parts-c"></a><span data-ttu-id="5d813-102">Office Open XML belge kısımları (C#) çıkaran örnek</span><span class="sxs-lookup"><span data-stu-id="5d813-102">Example that Outputs Office Open XML Document Parts (C#)</span></span>
<span data-ttu-id="5d813-103">Bu konuda, bir Office Open XML belgesi açın ve erişim bölümleri içindeki gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="5d813-103">This topic shows how to open an Office Open XML document and access parts within it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d813-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="5d813-104">Example</span></span>  
 <span data-ttu-id="5d813-105">Aşağıdaki örnek, bir Office Open XML belge açılır ve belge ve stil bölümlerini konsola yazdırır.</span><span class="sxs-lookup"><span data-stu-id="5d813-105">The following example opens an Office Open XML document, and prints the document part and the style part to the console.</span></span>  
  
 <span data-ttu-id="5d813-106">Bu örnek WindowsBase derlemesinden sınıfları kullanır.</span><span class="sxs-lookup"><span data-stu-id="5d813-106">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="5d813-107">Türleri kullanan <xref:System.IO.Packaging?displayProperty=nameWithType> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="5d813-107">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```csharp  
const string fileName = "SampleDoc.docx";  
  
const string documentRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string stylesRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles";  
const string wordmlNamespace =  
  "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
using (Package wdPackage = Package.Open(fileName, FileMode.Open, FileAccess.Read))  
{  
    PackageRelationship docPackageRelationship =  
      wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault();  
    if (docPackageRelationship != null)  
    {  
        Uri documentUri = PackUriHelper.ResolvePartUri(new Uri("/", UriKind.Relative),  
          docPackageRelationship.TargetUri);  
        PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
        //  Load the document XML in the part into an XDocument instance.  
        XDocument xdoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
  
        Console.WriteLine("TargetUri:{0}", docPackageRelationship.TargetUri);  
        Console.WriteLine("==================================================================");  
        Console.WriteLine(xdoc.Root);  
        Console.WriteLine();  
  
        //  Find the styles part. There will only be one.  
        PackageRelationship styleRelation =  
          documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault();  
        if (styleRelation != null)  
        {  
            Uri styleUri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);  
            PackagePart stylePart = wdPackage.GetPart(styleUri);  
  
            //  Load the style XML in the part into an XDocument instance.  
            XDocument styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()));  
  
            Console.WriteLine("TargetUri:{0}", styleRelation.TargetUri);  
            Console.WriteLine("==================================================================");  
            Console.WriteLine(styleDoc.Root);  
            Console.WriteLine();  
        }  
    }  
}  
```  
