---
title: XslTransform’a XmlDocument Girişi
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 97115892-410a-4657-ab47-1e14dfba73f8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5349b6476e204606fb1ec63144a1fccb0677d9d0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026836"
---
# <a name="xmldocument-input-to-xsltransform"></a>XslTransform’a XmlDocument Girişi
<xref:System.Xml.XmlDocument> Sınıf bir XML belgesi için düzenleme özellikleri sağlar. XML düzenlenmesine veya için gönderilmeden önce değiştirilen gerekip gerekmediğini <xref:System.Xml.Xsl.XslTransform.Transform%2A> yöntemi, XML verilerinin yük bir <xref:System.Xml.XmlDocument>, düzenlemek ve içinde göndermek <xref:System.Xml.Xsl.XslTransform>.  
  
> [!NOTE]
>  <xref:System.Xml.Xsl.XslTransform> Sınıftır eski [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]. Genişletilebilir Stil Sayfası Dil Dönüşümleri (XSLT) dönüştürmeleri için kullanarak gerçekleştirebileceğiniz <xref:System.Xml.Xsl.XslCompiledTransform> sınıfı. Bkz: [XslCompiledTransform sınıfını kullanma](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) ve [geçirme gelen XslTransform sınıfı](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) daha fazla bilgi için.  
  
 <xref:System.Xml.XmlDocument> Uygulayan <xref:System.Xml.XPath.IXPathNavigable> belge geçirilebilir için arabirim <xref:System.Xml.Xsl.XslTransform.Transform%2A> düzenleme sonra yöntemi.  
  
 Düzenleme yeteneğini nedeniyle <xref:System.Xml.XmlDocument>kullanarak <xref:System.Xml.XmlDocument> sınıf dönüştürme için giriş kullanmaktan daha yavaş olduğu gibi bir <xref:System.Xml.XPath.XPathDocument> Genişletilebilir Stil Sayfası Dil Dönüşümleri (XSLT) dönüşümlere olarak <xref:System.Xml.XPath.XPathDocument> olduğu İç Depolama nedeniyle XML Path Language (XPath) sorgular için en iyi duruma getirilmiş.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği nasıl kod bir <xref:System.Xml.XmlDocument> için sağlanan <xref:System.Xml.Xsl.XslTransform>, gönderilen çıktıyla bir <xref:System.Xml.XmlReader>.  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.Load("books.xml")  
Dim trans As XslTransform = new XslTransform()  
trans.Load("book.xsl")  
Dim rdr As XmlReader = trans.Transform(doc, Nothing, Nothing)  
while (rdr.Read())  
end while  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.Load("books.xml");  
XslTransform trans = new XslTransform();  
trans.Load("book.xsl");  
XmlReader rdr = trans.Transform(doc, null, null);  
while (rdr.Read()) {}  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Xml.XmlDocument>
- [XslTransform Sınıfı ile XSLT Dönüşümleri](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)
- [XslTransform Sınıfı XSLT İşlemcisini Uygular](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
- [Dönüşümlerde XPathNavigator](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)
- [Dönüşümlerde XPathNodeIterator](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)
- [XslTransform’a XPathDocument Girişi](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)
- [XslTransform’a XmlDataDocument Girişi](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)
