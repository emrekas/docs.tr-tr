---
title: 'Nasıl yapılır: Namespace ön eklerini denetleme (C#) (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 64de5186-b81a-4ddd-8327-8693df59a01b
ms.openlocfilehash: 37fb604a9b66f4da2b1722808b2c79f8fbf097bf
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66485975"
---
# <a name="how-to-control-namespace-prefixes-c-linq-to-xml"></a>Nasıl yapılır: Namespace ön eklerini denetleme (C#) (LINQ to XML)
Bu konuda bir XML ağacı serileştirilirken ad alanı öneklerini nasıl denetleyebileceğinizi açıklar.  
  
 Çoğu durumda, ad alanı ön ekleri denetlemek gerekli değildir.  
  
 Ancak, belirli bir XML programlama araçları, ad alanı öneklerini belirli denetim gerektirir. Örneğin, bir XSLT stil sayfası veya özel ad alanı öneklerini başvuran katıştırılmış XPath ifadeleri içeren bir XAML belgesi işliyor; Bu durumda, belge bu belirli ön ekler ile seri hale getirilmesi önemlidir.  
  
 Ad alanı ön ekleri denetlemek için en yaygın nedeni budur.  
  
 Ad alanı ön ekleri denetlemek için başka bir yaygın nedeni, XML belgesi el ile düzenlemek için kullanıcıların istediğiniz ve kullanıcıdan için kullanışlı bir ad alanı öneklerini oluşturmak istediğiniz ' dir. Örneğin, bir XSD belgesi oluşturulurken. Şemaları için kuralları önerisi, ya da kullandığınız `xs` veya `xsd` Şema ad alanı ön eki olarak.  
  
 Ad alanı ön ekleri denetlemek için ad alanları belirtmesi öznitelikleri ekleyin. Belirli ön ekler ad alanları bildirirseniz [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ad alanı öneklerini serileştirilirken dikkate dener.  
  
 Bir ad alanı öneki bildiren bir öznitelik oluşturmak için öznitelik adı ad alanı olduğu bir öznitelik oluşturun. <xref:System.Xml.Linq.XNamespace.Xmlns%2A>, ve öznitelik adı ad alanı öneki. Öznitelik ad alanı URI değeridir.  
  
## <a name="example"></a>Örnek  
 Bu örnek iki ad alanları bildirir. Belirtir `http://www.adventure-works.com` ad alanı öneki olan `aw`ve `www.fourthcoffee.com` ad alanı öneki olan `fc`.  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XAttribute(XNamespace.Xmlns + "fc", "www.fourthcoffee.com"),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 Bu örnek aşağıdaki çıktıyı üretir:  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- [XML ad alanları (C#) ile çalışma](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md)
