---
title: XML şemaları yazma ve okuma
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: b5757c4a-ea59-467e-ac62-be2bfe24eb77
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f80157ddf394fdd058793830bfe3052b41ad1e40
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576492"
---
# <a name="reading-and-writing-xml-schemas"></a><span data-ttu-id="5b8a0-102">XML şemaları yazma ve okuma</span><span class="sxs-lookup"><span data-stu-id="5b8a0-102">Reading and Writing XML Schemas</span></span>
<span data-ttu-id="5b8a0-103">Şema nesne modeli (SOM) API okuyup dosyaları veya diğer kaynakları XML Şeması Tanım Dili (XSD) şemaları yazma ve XML şemaları sınıfları kullanarak bellek içi derleme için kullanılabilir <xref:System.Xml.Schema?displayProperty=nameWithType> dünyada tanımlanan yapıları eşleyen ad alanı Wide Web Consortium (W3C) XML Şeması öneri.</span><span class="sxs-lookup"><span data-stu-id="5b8a0-103">The Schema Object Model (SOM) API can be used to read and write XML Schema definition language (XSD) schemas from files or other sources and build XML schemas in-memory using the classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace that map to the structures defined in the World Wide Web Consortium (W3C) XML Schema Recommendation.</span></span>  
  
## <a name="reading-and-writing-xml-schemas"></a><span data-ttu-id="5b8a0-104">XML şemaları yazma ve okuma</span><span class="sxs-lookup"><span data-stu-id="5b8a0-104">Reading and Writing XML Schemas</span></span>  
 <span data-ttu-id="5b8a0-105"><xref:System.Xml.Schema.XmlSchema> Sağlar sınıfını <xref:System.Xml.Schema.XmlSchema.Read%2A> ve <xref:System.Xml.Schema.XmlSchema.Write%2A> okuma ve yazma XML şemaları için yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="5b8a0-105">The <xref:System.Xml.Schema.XmlSchema> class provides the <xref:System.Xml.Schema.XmlSchema.Read%2A> and <xref:System.Xml.Schema.XmlSchema.Write%2A> methods to read and write XML schemas.</span></span> <span data-ttu-id="5b8a0-106"><xref:System.Xml.Schema.XmlSchema.Read%2A> Yöntemi döndürür bir <xref:System.Xml.Schema.XmlSchema> XML şemasını temsil eden nesne ve isteğe bağlı alan <xref:System.Xml.Schema.ValidationEventHandler> şema doğrulama uyarıları ve bir XML Şeması okurken hatayla karşılaştı hataları işlemek için bir parametre olarak.</span><span class="sxs-lookup"><span data-stu-id="5b8a0-106">The <xref:System.Xml.Schema.XmlSchema.Read%2A> method returns an <xref:System.Xml.Schema.XmlSchema> object representing the XML schema and takes an optional <xref:System.Xml.Schema.ValidationEventHandler> as a parameter to handle schema validation warnings and errors encountered while reading an XML schema.</span></span>  
  
 <span data-ttu-id="5b8a0-107"><xref:System.Xml.Schema.XmlSchema.Write%2A> Yöntemi yazar için XML şemaları <xref:System.IO.Stream>, <xref:System.IO.TextWriter> ve <xref:System.Xml.XmlWriter> nesneleri ve isteğe bağlı olarak alabilir <xref:System.Xml.XmlNamespaceManager> bir parametre olarak nesne.</span><span class="sxs-lookup"><span data-stu-id="5b8a0-107">The <xref:System.Xml.Schema.XmlSchema.Write%2A> method writes XML schemas to <xref:System.IO.Stream>, <xref:System.IO.TextWriter> and <xref:System.Xml.XmlWriter> objects and can take an optional <xref:System.Xml.XmlNamespaceManager> object as a parameter.</span></span> <span data-ttu-id="5b8a0-108">Bir <xref:System.Xml.XmlNamespaceManager> ad alanları XML şemasından karşılaştı işlemek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="5b8a0-108">An <xref:System.Xml.XmlNamespaceManager> is used to handle namespaces encountered in an XML schema.</span></span> <span data-ttu-id="5b8a0-109">Hakkında daha fazla bilgi için <xref:System.Xml.XmlNamespaceManager> sınıfı [yönetme ad alanları XML belgesinde](../../../../docs/standard/data/xml/managing-namespaces-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="5b8a0-109">For more information about the <xref:System.Xml.XmlNamespaceManager> class, see [Managing Namespaces in an XML Document](../../../../docs/standard/data/xml/managing-namespaces-in-an-xml-document.md).</span></span>  
  
 <span data-ttu-id="5b8a0-110">Aşağıdaki kod örneği, gelen ve bir dosyaya XML şemaları yazma ve okuma gösterir.</span><span class="sxs-lookup"><span data-stu-id="5b8a0-110">The following code example illustrates reading and writing XML schemas from and to a file.</span></span> <span data-ttu-id="5b8a0-111">Kod örneği alır `example.xsd` dosyası içine okur bir <xref:System.Xml.Schema.XmlSchema> kullanarak nesne `static` <xref:System.Xml.Schema.XmlSchema.Read%2A> yöntemi ve ardından konsolu ve yeni bir dosya Yazar `new.xsd` dosya.</span><span class="sxs-lookup"><span data-stu-id="5b8a0-111">The code example takes the `example.xsd` file, reads it into an <xref:System.Xml.Schema.XmlSchema> object using the `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> method, and then writes the file to the console and a new `new.xsd` file.</span></span> <span data-ttu-id="5b8a0-112">Kod örneği de sağlar bir <xref:System.Xml.Schema.ValidationEventHandler> bir parametre olarak `static` <xref:System.Xml.Schema.XmlSchema.Read%2A> şema doğrulama uyarıları veya hataları XML Şeması okurken hatayla karşılaştı işlemek için yöntemi.</span><span class="sxs-lookup"><span data-stu-id="5b8a0-112">The code example also provides a <xref:System.Xml.Schema.ValidationEventHandler> as a parameter to the `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> method to handle any schema validation warnings or errors encountered while reading the XML schema.</span></span> <span data-ttu-id="5b8a0-113">Varsa <xref:System.Xml.Schema.ValidationEventHandler> belirtilmemiş (`null`), uyarı veya hata bildirdi.</span><span class="sxs-lookup"><span data-stu-id="5b8a0-113">If the <xref:System.Xml.Schema.ValidationEventHandler> is not specified (`null`), no warnings or errors are reported.</span></span>  
  
 [!code-cpp[XmlSchemaReadWriteExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaReadWriteExample/CPP/XmlSchemaReadWriteExample.cpp#1)]
 [!code-csharp[XmlSchemaReadWriteExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaReadWriteExample/CS/XmlSchemaReadWriteExample.cs#1)]
 [!code-vb[XmlSchemaReadWriteExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaReadWriteExample/VB/XmlSchemaReadWriteExample.vb#1)]  
  
 <span data-ttu-id="5b8a0-114">Örnek alan `example.xsd` giriş olarak.</span><span class="sxs-lookup"><span data-stu-id="5b8a0-114">The example takes the `example.xsd` as input.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<xs:schema id="play" targetNamespace="http://tempuri.org/play.xsd" elementFormDefault="qualified" xmlns="http://tempuri.org/play.xsd" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:element name='myShoeSize'>  
        <xs:complexType>  
            <xs:simpleContent>  
                <xs:extension base='xs:decimal'>  
                    <xs:attribute name='sizing' type='xs:string' />  
                </xs:extension>  
            </xs:simpleContent>  
        </xs:complexType>  
    </xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5b8a0-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="5b8a0-115">See also</span></span>

- [<span data-ttu-id="5b8a0-116">XML Şema Nesne Modeline (SOM) Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="5b8a0-116">XML Schema Object Model Overview</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)
- [<span data-ttu-id="5b8a0-117">XML Şemaları Derleme</span><span class="sxs-lookup"><span data-stu-id="5b8a0-117">Building XML Schemas</span></span>](../../../../docs/standard/data/xml/building-xml-schemas.md)
- [<span data-ttu-id="5b8a0-118">XML Şemalarını Çapraz Geçirme</span><span class="sxs-lookup"><span data-stu-id="5b8a0-118">Traversing XML Schemas</span></span>](../../../../docs/standard/data/xml/traversing-xml-schemas.md)
- [<span data-ttu-id="5b8a0-119">XML Şemalarını Düzenleme</span><span class="sxs-lookup"><span data-stu-id="5b8a0-119">Editing XML Schemas</span></span>](../../../../docs/standard/data/xml/editing-xml-schemas.md)
- [<span data-ttu-id="5b8a0-120">XML Şemalarını Dahil Etme veya İçeri Aktarma</span><span class="sxs-lookup"><span data-stu-id="5b8a0-120">Including or Importing XML Schemas</span></span>](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)
- [<span data-ttu-id="5b8a0-121">Şema Derleme için XmlSchemaSet</span><span class="sxs-lookup"><span data-stu-id="5b8a0-121">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="5b8a0-122">Şema Derleme Sonrası Bilgi Kümesi</span><span class="sxs-lookup"><span data-stu-id="5b8a0-122">Post-Schema Compilation Infoset</span></span>](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)
- [<span data-ttu-id="5b8a0-123">XML Belgesinde Ad Alanlarını Yönetme</span><span class="sxs-lookup"><span data-stu-id="5b8a0-123">Managing Namespaces in an XML Document</span></span>](../../../../docs/standard/data/xml/managing-namespaces-in-an-xml-document.md)
