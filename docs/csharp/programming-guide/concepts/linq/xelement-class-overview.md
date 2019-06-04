---
title: XElement sınıfına genel bakış (C#)
ms.date: 07/20/2015
ms.assetid: 2b9f0cd8-a1d1-4037-accf-0f38a410fa11
ms.openlocfilehash: 815b7b6523afe7106fcdcbe242d667c5ad6aa56e
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66487010"
---
# <a name="xelement-class-overview-c"></a>XElement sınıfına genel bakış (C#)
<xref:System.Xml.Linq.XElement> Sınıfın temel sınıflarında biridir [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Bu, bir XML öğesi temsil eder. Bu sınıf, öğeleri oluşturmak için kullanabilirsiniz; öğenin içeriğini değiştirmek; ekleme, değiştirme veya alt öğeleri silin; öznitelik, bir öğeye ekleyin; ya da metin biçiminde bir öğenin içeriği seri hale getirme. İçindeki diğer sınıflarla çalışabilirler <xref:System.Xml?displayProperty=nameWithType>, gibi <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, ve <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
Bu konu tarafından sağlanan işlevselliği açıklar <xref:System.Xml.Linq.XElement> sınıfı.  
  
## <a name="constructing-xml-trees"></a>XML ağaçları oluşturma  
 XML ağaçlarını aşağıdakiler dahil olmak üzere çeşitli oluşturabilirsiniz:  
  
- Bir XML ağacı kod oluşturabilirsiniz. Daha fazla bilgi için [XML ağaçları oluşturma (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md).  
  
- XML dahil olmak üzere çeşitli kaynaklardan ayrıştırabilirsiniz bir <xref:System.IO.TextReader>, metin dosyaları veya bir Web adresi (URL). Daha fazla bilgi için [XML Ayrıştırma (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-parse-a-string.md).  
  
- Kullanabileceğiniz bir <xref:System.Xml.XmlReader> ağacını doldurmak için. Daha fazla bilgi için bkz. <xref:System.Xml.Linq.XNode.ReadFrom%2A>.  
  
- İçeriği yazabilen bir modül varsa bir <xref:System.Xml.XmlWriter>, kullanabileceğiniz <xref:System.Xml.Linq.XContainer.CreateWriter%2A> bir yazıcısı oluşturmak, yazıcı modülü geçirin ve ardından yazılan içeriği yöntemi <xref:System.Xml.XmlWriter> XML ağacını doldurmak için.  
  
 Ancak, bir XML ağacı oluşturmak için en yaygın yolu şu şekildedir:  
  
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
  
 Bir XML ağacı oluşturmak için başka bir yaygın yöntem sonuçlarını kullanılmasına bir [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] aşağıdaki örnekte gösterildiği gibi bir XML ağacı doldurma için sorgu:  
  
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
  
 Bu örnek aşağıdaki çıktıyı üretir:  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
## <a name="serializing-xml-trees"></a>XML Ağaçlarını Serileştirme  
 XML ağacına serileştirebilen bir <xref:System.IO.File>, <xref:System.IO.TextWriter>, veya bir <xref:System.Xml.XmlWriter>.  
  
 Daha fazla bilgi için [XML ağaçlarını serileştirme (C#)](../../../../csharp/programming-guide/concepts/linq/preserving-white-space-while-serializing.md).  
  
## <a name="retrieving-xml-data-via-axis-methods"></a>Eksen yöntemleri aracılığıyla XML verilerini alma  
 Eksen yöntemleri, öznitelikler, alt öğeleri, alt ve üst öğeleri almak için kullanabilirsiniz. [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] sorgular, eksen yöntemleri üzerinde çalışır ve gezinmek ve bir XML ağacı işlemek için çeşitli esnek ve güçlü yollarını sağlar.  
  
 Daha fazla bilgi için [LINQ to XML eksenleri (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes-overview.md).  
  
## <a name="querying-xml-trees"></a>XML Ağaçlarını Sorgulama  
 Yazabileceğiniz [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] XML ağacından verileri ayıklamak sorgular.  
  
 Daha fazla bilgi için [XML ağaçlarını sorgulama (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-an-element-with-a-specific-attribute.md).  
  
## <a name="modifying-xml-trees"></a>XML ağaçlarını değiştirme  
 Bir öğeyi kendi içerik veya öznitelikleri değiştirme dahil olmak üzere çeşitli değiştirebilirsiniz. Ayrıca, bir öğenin üst öğesinden kaldırabilirsiniz.  
  
 Daha fazla bilgi için [XML ağaçlarını değiştirme (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).  
  
## <a name="see-also"></a>Ayrıca bkz.

- [LINQ to XML programlamaya genel bakış (C#)](serializing-to-files-textwriters-and-xmlwriters.md)
