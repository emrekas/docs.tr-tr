---
title: WordprocessingML belgesinin Styles3 ile
ms.date: 07/20/2015
ms.assetid: 40e35de6-ac93-4bba-88ab-a018cbe93873
ms.openlocfilehash: 1dc7f30bfdef66c31b5c262fd6d1a2c3f4365634
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61710920"
---
# <a name="wordprocessingml-document-with-styles"></a><span data-ttu-id="a5c03-102">Stillerle WordprocessingML Belgesi</span><span class="sxs-lookup"><span data-stu-id="a5c03-102">WordprocessingML Document with Styles</span></span>
<span data-ttu-id="a5c03-103">Daha karmaşık WordprocessingML belgelerinin stilleri ile biçimlendirilmiş paragrafları vardır.</span><span class="sxs-lookup"><span data-stu-id="a5c03-103">More complicated WordprocessingML documents have paragraphs that are formatted with styles.</span></span>  
  
 <span data-ttu-id="a5c03-104">WordprocessingML belgelerinin düzenini ilgili birkaç Not yararlı olur.</span><span class="sxs-lookup"><span data-stu-id="a5c03-104">A few notes about the makeup of WordprocessingML documents are helpful.</span></span> <span data-ttu-id="a5c03-105">WordprocessingML belgelerinin paketlerinde depolanır.</span><span class="sxs-lookup"><span data-stu-id="a5c03-105">WordprocessingML documents are stored in packages.</span></span> <span data-ttu-id="a5c03-106">Paketleriniz varsa birden fazla bölümü (bölümden paketleri bağlamında kullanıldığında açık bir anlamı; bir paket oluşturmak üzere birlikte sıkıştırılmış dosyalar esas olarak, bazı bölümleri).</span><span class="sxs-lookup"><span data-stu-id="a5c03-106">Packages have multiple parts (parts have an explicit meaning when used in the context of packages; essentially, parts are files that are zipped together to comprise a package).</span></span> <span data-ttu-id="a5c03-107">Bir belge stilleri ile biçimlendirilmiş paragrafları içeriyorsa, stil uygulanmış olan paragraf içeren bir belge bölümü olacaktır.</span><span class="sxs-lookup"><span data-stu-id="a5c03-107">If a document contains paragraphs that are formatted with styles, there will be a document part that contains paragraphs that have styles applied to them.</span></span> <span data-ttu-id="a5c03-108">Belgeye göre adlandırılır stilleri içeren bir stil bölümü olacaktır.</span><span class="sxs-lookup"><span data-stu-id="a5c03-108">There will also be a style part that contains the styles that are referred to by the document.</span></span>  
  
 <span data-ttu-id="a5c03-109">Paketleri erişirken, rastgele bir yol kullanmak yerine parçaları arasındaki ilişkileri aracılığıyla yapmanız önemlidir.</span><span class="sxs-lookup"><span data-stu-id="a5c03-109">When accessing packages, it is important that you do so through the relationships between parts, rather than using an arbitrary path.</span></span> <span data-ttu-id="a5c03-110">Bu sorunu, içerik düzenleme kapsamı dışındadır WordprocessingML belgesinin öğreticide olmakla birlikte, bu öğreticide bulunan örnek programların doğru yaklaşımı gösterir.</span><span class="sxs-lookup"><span data-stu-id="a5c03-110">This issue is beyond the scope of the Manipulating Content in a WordprocessingML Document tutorial, but the example programs that are included in this tutorial demonstrate the correct approach.</span></span>  
  
## <a name="a-document-that-uses-styles"></a><span data-ttu-id="a5c03-111">Stilleri kullanan bir belge</span><span class="sxs-lookup"><span data-stu-id="a5c03-111">A Document that Uses Styles</span></span>  
 <span data-ttu-id="a5c03-112">WordML örnek içinde sunulan [şekli, WordprocessingML belgelerinin (C#)](../../../../csharp/programming-guide/concepts/linq/shape-of-wordprocessingml-documents.md) çok basit bir konudur.</span><span class="sxs-lookup"><span data-stu-id="a5c03-112">The WordML example presented in the [Shape of WordprocessingML Documents (C#)](../../../../csharp/programming-guide/concepts/linq/shape-of-wordprocessingml-documents.md) topic is a very simple one.</span></span> <span data-ttu-id="a5c03-113">Aşağıdaki belge daha karmaşık bir işlemdir: Stilleri ile biçimlendirilmiş paragrafları var.</span><span class="sxs-lookup"><span data-stu-id="a5c03-113">The following document is more complicated: It has paragraphs that are formatted with styles.</span></span> <span data-ttu-id="a5c03-114">Bir Office Open XML belgesi yapan bir XML olup çalıştırmak için en kolay yolu [örnek bu çıkışları Office Open XML belge kısımları (C#)](../../../../csharp/programming-guide/concepts/linq/example-that-outputs-office-open-xml-document-parts.md).</span><span class="sxs-lookup"><span data-stu-id="a5c03-114">The easiest way to see the XML that makes up an Office Open XML document is to run the [Example that Outputs Office Open XML Document Parts (C#)](../../../../csharp/programming-guide/concepts/linq/example-that-outputs-office-open-xml-document-parts.md).</span></span>  
  
 <span data-ttu-id="a5c03-115">Aşağıdaki belgede, ilk paragrafa stilde `Heading1`.</span><span class="sxs-lookup"><span data-stu-id="a5c03-115">In the following document, the first paragraph has the style `Heading1`.</span></span> <span data-ttu-id="a5c03-116">Varsayılan Stil paragraflar vardır.</span><span class="sxs-lookup"><span data-stu-id="a5c03-116">There are a number of paragraphs that have the default style.</span></span> <span data-ttu-id="a5c03-117">Ayrıca birkaç stil paragraf vardır `Code`.</span><span class="sxs-lookup"><span data-stu-id="a5c03-117">There are also a number of paragraphs that have the style `Code`.</span></span> <span data-ttu-id="a5c03-118">Bu göreli karmaşıklığı nedeniyle, LINQ to XML ile ayrıştırmak için daha çok ilginizi çeken bir belge budur.</span><span class="sxs-lookup"><span data-stu-id="a5c03-118">Because of this relative complexity, this is a more interesting document to parse with LINQ to XML.</span></span>  
  
 <span data-ttu-id="a5c03-119">Varsayılan olmayan stilde bu paragraflarda paragraf öğeleri adlı bir alt öğesi olan `w:pPr`, sırayla olan bir alt öğesi `w:pStyle`.</span><span class="sxs-lookup"><span data-stu-id="a5c03-119">In those paragraphs with non-default styles, the paragraph elements have a child element named `w:pPr`, which in turn has a child element `w:pStyle`.</span></span> <span data-ttu-id="a5c03-120">Bu öğeye bir öznitelik sahip `w:val`, stil adı içerir.</span><span class="sxs-lookup"><span data-stu-id="a5c03-120">That element has an attribute, `w:val`, which contains the style name.</span></span> <span data-ttu-id="a5c03-121">Paragraf varsayılan stilde, paragraf öğesini yok demektir bir `w:p.Pr` alt öğesi.</span><span class="sxs-lookup"><span data-stu-id="a5c03-121">If the paragraph has the default style, it means that the paragraph element does not have a `w:p.Pr` child element.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<w:document  
    xmlns:ve="http://schemas.openxmlformats.org/markup-compatibility/2006"  
    xmlns:o="urn:schemas-microsoft-com:office:office"  
    xmlns:r="http://schemas.openxmlformats.org/officeDocument/2006/relationships"  
    xmlns:m="http://schemas.openxmlformats.org/officeDocument/2006/math"  
    xmlns:v="urn:schemas-microsoft-com:vml"  
    xmlns:wp="http://schemas.openxmlformats.org/drawingml/2006/wordprocessingDrawing"  
    xmlns:w10="urn:schemas-microsoft-com:office:word"  
    xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
    xmlns:wne="http://schemas.microsoft.com/office/word/2006/wordml">  
  <w:body>  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Heading1" />  
      </w:pPr>  
      <w:r>  
        <w:t>Parsing WordprocessingML with LINQ to XML</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" />  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0">  
      <w:r>  
        <w:t>The following example prints to the console.</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" />  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r>  
        <w:t>using System;</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRPr="00876F34" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r w:rsidRPr="00876F34">  
        <w:t>class Program {</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRPr="00876F34" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r w:rsidRPr="00876F34">  
        <w:t xml:space="preserve">    public static void </w:t>  
      </w:r>  
      <w:smartTag w:uri="urn:schemas-microsoft-com:office:smarttags" w:element="place">  
        <w:r w:rsidRPr="00876F34">  
          <w:t>Main</w:t>  
        </w:r>  
      </w:smartTag>  
      <w:r w:rsidRPr="00876F34">  
        <w:t>(string[] args) {</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRPr="00876F34" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r w:rsidRPr="00876F34">  
        <w:t xml:space="preserve">        Console.WriteLine("Hello World");</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRPr="00876F34" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r w:rsidRPr="00876F34">  
        <w:t xml:space="preserve">    }</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRPr="00876F34" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r w:rsidRPr="00876F34">  
        <w:t>}</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" />  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0">  
      <w:r>  
        <w:t>This example produces the following output:</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" />  
    <w:p w:rsidR="00A75AE0" w:rsidRDefault="00A75AE0" w:rsidP="006027C7">  
      <w:pPr>  
        <w:pStyle w:val="Code" />  
      </w:pPr>  
      <w:r>  
        <w:t>Hello World</w:t>  
      </w:r>  
    </w:p>  
    <w:sectPr w:rsidR="00A75AE0" w:rsidSect="00A75AE0">  
      <w:pgSz w:w="12240" w:h="15840" />  
      <w:pgMar w:top="1440" w:right="1800" w:bottom="1440" w:left="1800" w:header="720" w:footer="720" w:gutter="0" />  
      <w:cols w:space="720" />  
      <w:docGrid w:linePitch="360" />  
    </w:sectPr>  
  </w:body>  
</w:document>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a5c03-122">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="a5c03-122">See also</span></span>

- [<span data-ttu-id="a5c03-123">Ayrıntılar Office Open XML WordprocessingML belgelerinin (C#)</span><span class="sxs-lookup"><span data-stu-id="a5c03-123">Details of Office Open XML WordprocessingML Documents (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md)
