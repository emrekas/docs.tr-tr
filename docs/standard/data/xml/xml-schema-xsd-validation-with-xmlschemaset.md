---
title: XmlSchemaSet ile XML Şeması (XSD) Doğrulaması
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 359b10eb-ec05-4cc6-ac96-c2b060afc4de
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9bdcfe785d6f5f81d721acd45eebb580b08b2d14
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916068"
---
# <a name="xml-schema-xsd-validation-with-xmlschemaset"></a><span data-ttu-id="2f939-102">XmlSchemaSet ile XML Şeması (XSD) Doğrulaması</span><span class="sxs-lookup"><span data-stu-id="2f939-102">XML Schema (XSD) Validation with XmlSchemaSet</span></span>
<span data-ttu-id="2f939-103">XML belgeleri, bir <xref:System.Xml.Schema.XmlSchemaSet>XML şeması tanım dili (xsd) şemasına göre doğrulanabilir.</span><span class="sxs-lookup"><span data-stu-id="2f939-103">XML documents can be validated against an XML schema definition language (XSD) schema in an <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
## <a name="validating-xml-documents"></a><span data-ttu-id="2f939-104">XML belgelerini doğrulama</span><span class="sxs-lookup"><span data-stu-id="2f939-104">Validating XML Documents</span></span>  
 <span data-ttu-id="2f939-105">XML belgeleri, <xref:System.Xml.XmlReader.Create%2A> <xref:System.Xml.XmlReader> sınıfının yöntemi tarafından onaylanır.</span><span class="sxs-lookup"><span data-stu-id="2f939-105">XML documents are validated by the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> class.</span></span> <span data-ttu-id="2f939-106">XML belgesini doğrulamak için, XML belgesi doğrulanacak <xref:System.Xml.XmlReaderSettings> bir XML şeması tanım dili (xsd) şeması içeren bir nesne oluşturun.</span><span class="sxs-lookup"><span data-stu-id="2f939-106">To validate an XML document, construct an <xref:System.Xml.XmlReaderSettings> object that contains an XML schema definition language (XSD) schema with which to validate the XML document.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2f939-107">Ad <xref:System.Xml.Schema> alanı, [LINQ to XMLC#()](../../../csharp/programming-guide/concepts/linq/linq-to-xml.md) ve [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)kullanırken bir xml ağacının xsd dosyasına karşı doğrulanmasını kolaylaştıran uzantı yöntemleri içerir.</span><span class="sxs-lookup"><span data-stu-id="2f939-107">The <xref:System.Xml.Schema> namespace contains extension methods that make it easy to validate an XML tree against an XSD file when using [LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml.md) and [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md).</span></span> <span data-ttu-id="2f939-108">LINQ to XML ile XML belgelerinin doğrulanması hakkında daha fazla bilgi için bkz [. nasıl yapılır: XSD (LINQ to XML) (C#)](../../../csharp/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md) kullanarak doğrulayın ve [şunları yapın: XSD kullanarak doğrulayın (LINQ to XML) (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="2f939-108">For more information on validating XML documents with LINQ to XML, see [How to: Validate Using XSD (LINQ to XML) (C#)](../../../csharp/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md) and [How to: Validate Using XSD (LINQ to XML) (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="2f939-109">Tek bir şema veya bir şema kümesi ( <xref:System.Xml.Schema.XmlSchemaSet>olarak) <xref:System.Xml.Schema.XmlSchemaSet> öğesine bir <xref:System.Xml.Schema.XmlSchemaSet>parametre <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> olarak bir parametresi geçirerek öğesine eklenebilir.</span><span class="sxs-lookup"><span data-stu-id="2f939-109">An individual schema or a set of schemas (as an <xref:System.Xml.Schema.XmlSchemaSet>) can be added to an <xref:System.Xml.Schema.XmlSchemaSet> by passing either one as a parameter to the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method of <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="2f939-110">Bir belge doğrulanırken belgenin hedef ad alanının şema kümesindeki şemanın hedef ad alanıyla eşleşmesi gerektiğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="2f939-110">Note that when validating a document the target namespace of the document must match the target namespace of the schema in the schema set.</span></span>  
  
 <span data-ttu-id="2f939-111">Aşağıda örnek bir XML belgesi verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="2f939-111">The following is an example XML document.</span></span>  
  
 [!code-xml[XSDInference Examples#5](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xml#5)]  
  
 <span data-ttu-id="2f939-112">Örnek XML belgesini doğrulayan şema aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="2f939-112">The following is the schema that validates the example XML document.</span></span>  
  
 [!code-xml[XSDInference Examples#6](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xsd#6)]  
  
 <span data-ttu-id="2f939-113">Aşağıdaki kod örneğinde, yukarıdaki şema <xref:System.Xml.Schema.XmlSchemaSet> <xref:System.Xml.XmlReaderSettings> nesnenin <xref:System.Xml.XmlReaderSettings.Schemas%2A> özelliğine eklenir.</span><span class="sxs-lookup"><span data-stu-id="2f939-113">In the code example that follows, the schema above is added to the <xref:System.Xml.Schema.XmlSchemaSet><xref:System.Xml.XmlReaderSettings.Schemas%2A> property of the <xref:System.Xml.XmlReaderSettings> object.</span></span> <span data-ttu-id="2f939-114">Nesnesi, yukarıdaki XML belgesini doğrulayan <xref:System.Xml.XmlReader> nesnesinin <xref:System.Xml.XmlReader.Create%2A> yöntemine bir parametre olarak geçirilir. <xref:System.Xml.XmlReaderSettings></span><span class="sxs-lookup"><span data-stu-id="2f939-114">The <xref:System.Xml.XmlReaderSettings> object is passed as a parameter to the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> object, which validates the XML document above.</span></span>  
  
 <span data-ttu-id="2f939-115"><xref:System.Xml.XmlReaderSettings.ValidationType%2A> <xref:System.Xml.XmlReader.Create%2A> Nesnesinin özelliği ,nesne<xref:System.Xml.XmlReader> yöntemi tarafından XML belgesinin `Schema` doğrulanmasını zorlamak için olarak ayarlanır. <xref:System.Xml.XmlReaderSettings></span><span class="sxs-lookup"><span data-stu-id="2f939-115">The <xref:System.Xml.XmlReaderSettings.ValidationType%2A> property of the <xref:System.Xml.XmlReaderSettings> object is set to `Schema` to enforce validation of the XML document by the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="2f939-116">, <xref:System.Xml.Schema.ValidationEventHandler> Hem XML belgesi hem <xref:System.Xml.XmlReaderSettings> de şemanın doğrulama işlemi sırasında <xref:System.Xml.Schema.XmlSeverityType.Error> bulunan hatalara göre oluşan herhangi <xref:System.Xml.Schema.XmlSeverityType.Warning> bir veya olayı işlemek için nesnesine eklenir.</span><span class="sxs-lookup"><span data-stu-id="2f939-116">A <xref:System.Xml.Schema.ValidationEventHandler> is added to the <xref:System.Xml.XmlReaderSettings> object to handle any <xref:System.Xml.Schema.XmlSeverityType.Warning> or <xref:System.Xml.Schema.XmlSeverityType.Error> events raised by errors found during the validation process of both the XML document and the schema.</span></span>  
  
 [!code-cpp[XmlSchemaSetOverall Example#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaSetOverall Example/CPP/xmlschemasetexample.cpp#1)]
 [!code-csharp[XmlSchemaSetOverall Example#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaSetOverall Example/CS/xmlschemasetexample.cs#1)]
 [!code-vb[XmlSchemaSetOverall Example#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaSetOverall Example/VB/xmlschemasetexample.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2f939-117">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="2f939-117">See also</span></span>

- [<span data-ttu-id="2f939-118">Şema Derleme için XmlSchemaSet</span><span class="sxs-lookup"><span data-stu-id="2f939-118">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="2f939-119">XML Şemalarıyla Çalışma</span><span class="sxs-lookup"><span data-stu-id="2f939-119">Working with XML Schemas</span></span>](../../../../docs/standard/data/xml/working-with-xml-schemas.md)
