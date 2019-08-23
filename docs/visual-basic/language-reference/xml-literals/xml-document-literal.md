---
title: XML Belgesi Değişmez Değeri (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralDocument
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
ms.openlocfilehash: 8a489be46295c213b7a8b355eb3c9786d49dd8f1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958509"
---
# <a name="xml-document-literal-visual-basic"></a><span data-ttu-id="d4f9a-102">XML Belgesi Değişmez Değeri (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4f9a-102">XML Document Literal (Visual Basic)</span></span>
<span data-ttu-id="d4f9a-103">Bir <xref:System.Xml.Linq.XDocument> nesneyi temsil eden sabit değer.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-103">A literal representing an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4f9a-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="d4f9a-104">Syntax</span></span>  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a><span data-ttu-id="d4f9a-105">Bölümler</span><span class="sxs-lookup"><span data-stu-id="d4f9a-105">Parts</span></span>  
  
|<span data-ttu-id="d4f9a-106">Terim</span><span class="sxs-lookup"><span data-stu-id="d4f9a-106">Term</span></span>|<span data-ttu-id="d4f9a-107">Tanım</span><span class="sxs-lookup"><span data-stu-id="d4f9a-107">Definition</span></span>|  
|---|---|  
|`encoding`|<span data-ttu-id="d4f9a-108">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-108">Optional.</span></span> <span data-ttu-id="d4f9a-109">Belgenin hangi kodlamayla kullandığını bildiren değişmez metin.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-109">Literal text declaring which encoding the document uses.</span></span>|  
|`standalone`|<span data-ttu-id="d4f9a-110">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-110">Optional.</span></span> <span data-ttu-id="d4f9a-111">Değişmez değer metni.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-111">Literal text.</span></span> <span data-ttu-id="d4f9a-112">"Yes" veya "No" olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-112">Must be "yes" or "no".</span></span>|  
|`piCommentList`|<span data-ttu-id="d4f9a-113">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-113">Optional.</span></span> <span data-ttu-id="d4f9a-114">XML işleme yönergelerinin ve XML açıklamalarının listesi.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-114">List of XML processing instructions and XML comments.</span></span> <span data-ttu-id="d4f9a-115">Aşağıdaki biçimi alır:</span><span class="sxs-lookup"><span data-stu-id="d4f9a-115">Takes the following format:</span></span><br /><br /> <span data-ttu-id="d4f9a-116">`piComment [` `piComment` `... ]`</span><span class="sxs-lookup"><span data-stu-id="d4f9a-116">`piComment [` `piComment` `... ]`</span></span><br /><br /> <span data-ttu-id="d4f9a-117">Her `piComment` biri aşağıdakilerden biri olabilir:</span><span class="sxs-lookup"><span data-stu-id="d4f9a-117">Each `piComment` can be one of the following:</span></span><br /><br /> <span data-ttu-id="d4f9a-118">-   [XML Işleme yönergesi sabit değeri](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="d4f9a-118">-   [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span><br /><span data-ttu-id="d4f9a-119">-   [XML açıklama değişmez değeri](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="d4f9a-119">-   [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>|  
|`rootElement`|<span data-ttu-id="d4f9a-120">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-120">Required.</span></span> <span data-ttu-id="d4f9a-121">Belgenin kök öğesi.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-121">Root element of the document.</span></span> <span data-ttu-id="d4f9a-122">Biçim aşağıdakilerden biridir:</span><span class="sxs-lookup"><span data-stu-id="d4f9a-122">The format is one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="d4f9a-123">[XML öğesi değişmez değeri](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="d4f9a-123">[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span></li><li><span data-ttu-id="d4f9a-124">Formun `<%=` `elementExp` katıştırılmış ifadesi. `%>`</span><span class="sxs-lookup"><span data-stu-id="d4f9a-124">Embedded expression of the form `<%=` `elementExp` `%>`.</span></span> <span data-ttu-id="d4f9a-125">, `elementExp` Aşağıdakilerden birini döndürür:</span><span class="sxs-lookup"><span data-stu-id="d4f9a-125">The `elementExp` returns one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="d4f9a-126">Bir <xref:System.Xml.Linq.XElement> nesne.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-126">An <xref:System.Xml.Linq.XElement> object.</span></span></li><li><span data-ttu-id="d4f9a-127">Bir <xref:System.Xml.Linq.XElement> nesne ve herhangi bir <xref:System.Xml.Linq.XProcessingInstruction> sayıda ve <xref:System.Xml.Linq.XComment> nesne içeren bir koleksiyon.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-127">A collection that contains one <xref:System.Xml.Linq.XElement> object and any number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects.</span></span></li></ul></li></ul><br /> <span data-ttu-id="d4f9a-128">Daha fazla bilgi için bkz. [XML 'de katıştırılmış ifadeler](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="d4f9a-128">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="d4f9a-129">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="d4f9a-129">Return Value</span></span>  
 <span data-ttu-id="d4f9a-130">Bir <xref:System.Xml.Linq.XDocument> nesne.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-130">An <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4f9a-131">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d4f9a-131">Remarks</span></span>  
 <span data-ttu-id="d4f9a-132">XML belgesi değişmez değeri, değişmez değerin başlangıcında XML bildirimi tarafından tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-132">An XML document literal is identified by the XML declaration at the start of the literal.</span></span> <span data-ttu-id="d4f9a-133">Her XML belgesi değişmez değeri tam olarak bir kök XML öğesi içermelidir, ancak herhangi bir sayıda XML işleme yönergesi ve XML açıklaması olabilir.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-133">Although each XML document literal must have exactly one root XML element, it can have any number of XML processing instructions and XML comments.</span></span>  
  
 <span data-ttu-id="d4f9a-134">XML belgesi değişmez değeri bir XML öğesinde görünemez.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-134">An XML document literal cannot appear in an XML element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d4f9a-135">Bir XML sabit değeri, satır devamlılık karakterleri kullanmadan birden fazla satıra yayılabilir.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-135">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="d4f9a-136">Bu sayede bir XML belgesinden içerik kopyalayabilir ve doğrudan bir Visual Basic programına yapıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-136">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="d4f9a-137">Visual Basic derleyici, XML belgesi değişmez değerini <xref:System.Xml.Linq.XDocument.%23ctor%2A> ve <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> oluşturuculara çağrılarına dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-137">The Visual Basic compiler converts the XML document literal into calls to the <xref:System.Xml.Linq.XDocument.%23ctor%2A> and <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4f9a-138">Örnek</span><span class="sxs-lookup"><span data-stu-id="d4f9a-138">Example</span></span>  
 <span data-ttu-id="d4f9a-139">Aşağıdaki örnek, bir XML bildirimi, işleme yönergesi, açıklama ve başka bir öğesi içeren bir öğesi olan bir XML belgesi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-139">The following example creates an XML document that has an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
 [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="d4f9a-140">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d4f9a-140">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- <xref:System.Xml.Linq.XProcessingInstruction>
- <xref:System.Xml.Linq.XComment>
- <xref:System.Xml.Linq.XDocument>
- [<span data-ttu-id="d4f9a-141">XML İşleme Talimatı Değişmez Değeri</span><span class="sxs-lookup"><span data-stu-id="d4f9a-141">XML Processing Instruction Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)
- [<span data-ttu-id="d4f9a-142">XML Açıklama Değişmez Değeri</span><span class="sxs-lookup"><span data-stu-id="d4f9a-142">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [<span data-ttu-id="d4f9a-143">XML Öğesi Değişmez Değeri</span><span class="sxs-lookup"><span data-stu-id="d4f9a-143">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="d4f9a-144">XML Değişmez Değerleri</span><span class="sxs-lookup"><span data-stu-id="d4f9a-144">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="d4f9a-145">Visual Basic XML oluşturma</span><span class="sxs-lookup"><span data-stu-id="d4f9a-145">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="d4f9a-146">XML'de Katıştırılmış İfadeler</span><span class="sxs-lookup"><span data-stu-id="d4f9a-146">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
