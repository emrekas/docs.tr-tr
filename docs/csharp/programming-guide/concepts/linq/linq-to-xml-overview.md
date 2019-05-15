---
title: LINQ to XML genel bakış (C#)
ms.date: 10/30/2018
ms.assetid: 716b94d3-0091-4de1-8e05-41bc069fa9dd
ms.openlocfilehash: 2394151d855d75b418616d9fa1a6f69b08cdef86
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65585745"
---
# <a name="linq-to-xml-overview-c"></a>LINQ to XML genel bakış (C#)

XML, yaygın olarak birçok bağlamları verileri biçimlendirme bir yolu olarak benimsenmiştir. Örneğin, yapılandırma dosyalarını, Microsoft Office Word dosyaları ve veritabanlarının Web XML bulabilirsiniz.

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] güncel ve yeniden tasarlanan XML ile programlamaya yaklaşımıdır. Bellek içi belge değiştirme özelliklerini belge nesne modeli (DOM) sağlar ve destekleyen [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] sorgu ifadelerinde. Bu sorgu ifadeleri XPath sözdizimi kurallarına göre farklı olsa da, benzer bir işlevsellik sağlarlar.

## <a name="linq-to-xml-developers"></a>LINQ to XML geliştiriciler

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] geliştiricilerin çeşitli hedefler. Yalnızca bir şey yapmanız, almak isteyen bir ortalama geliştiricinin [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] XML SQL'e benzeyen bir sorgu deneyimi sunarak daha kolay hale getirir. Yalnızca bir bit öğrenim, programcılar kendi seçtiğiniz programlama dilinde birleştiren ve güçlü sorgular yazmak bilgi edinebilirsiniz.

Profesyonel Geliştiriciler [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] üretkenliklerini büyük ölçüde artırmak için. İle [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], bunlar daha ifadesel, daha küçük ve daha güçlü daha az kod yazabilirsiniz. Aynı anda birden çok veri etki alanından bunlar sorgu ifadeleri kullanabilirsiniz.

## <a name="what-is-linq-to-xml"></a>LINQ to XML nedir?

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] .NET Framework XML'de çalışmanızı sağlayan bir LINQ-etkin, bellek içi XML programlama arabirimi programlama dilleri.

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] XML belgesi belleğe getirdiği belge nesne modeli (DOM) gibi olmamasıdır. Sorgulamak ve belgeyi değiştirmesine ve değiştirdikten sonra bir dosyaya kaydedebilir veya bu seri hale getirmek ve Internet üzerinden gönder. Ancak, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] DOM farklıdır: Açık ağırlığı olan yeni bir nesne modeli sağlar ve çalışmak, daha kolay ve dil özelliklerinden alan C#.

En önemli avantajı [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] tümleştirmesi sayesinde olan [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]. Bu tümleştirme, öğeleri ve özniteliklerinin koleksiyonu almak için bellek içi XML belgesi sorgular yazmaya olanak tanır. Sorgu yeteneğini [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] (değil, ancak sözdizimi) işlevselliği karşılaştırılabilir XPath ve XQuery. Tümleştirmesini [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] C# ' de daha güçlü yazım, denetleme ve geliştirilmiş hata ayıklayıcı desteği zamanı sağlar.

Başka bir avantajı [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] sorgu sonuçları için parametre olarak kullanma olanağı <xref:System.Xml.Linq.XElement> ve <xref:System.Xml.Linq.XAttribute> nesne oluşturucuları XML ağaçları oluşturma için güçlü bir yaklaşım sağlar. Adlandırılan bu yaklaşım *işlevsel oluşturma*, geliştiricilerin bir şekilden XML ağaçlarını başka bir kolayca dönüştürüp olanak tanır.

Örneğin, satınalma siparişi açıklandığı gibi tipik bir XML olabilir [örnek XML dosyası: Tipik satın alma siparişi (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml-1.md). Kullanarak [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], satın alma siparişi her öğe öğe için bölüm numarası özniteliği değeri elde etmek için şu sorguyu çalıştırabilirsiniz:

```csharp
// Load the XML file from our project directory containing the purchase orders
var filename = "PurchaseOrder.xml";
var currentDirectory = Directory.GetCurrentDirectory();
var purchaseOrderFilepath = Path.Combine(currentDirectory, filename);

XElement purchaseOrder = XElement.Load($"{purchaseOrderFilepath}");

IEnumerable<string> partNos =  from item in purchaseOrder.Descendants("Item")
                               select (string) item.Attribute("PartNumber");
```

Bu yöntem sözdizimi formunda yazılabilir:

```csharp
IEnumerable<string> partNos = purchaseOrder.Descendants("Item").Select(x => (string) x.Attribute("PartNumber"));
```

Başka bir örnek olarak $100'den büyük bir değer ile öğelerinin parça numarası tarafından sıralanan bir liste isteyebilirsiniz. Bu bilgiler edinmek için şu sorguyu çalıştırabilirsiniz:

```csharp
// Load the XML file from our project directory containing the purchase orders
var filename = "PurchaseOrder.xml";
var currentDirectory = Directory.GetCurrentDirectory();
var purchaseOrderFilepath = Path.Combine(currentDirectory, filename);

XElement purchaseOrder = XElement.Load($"{purchaseOrderFilepath}");

IEnumerable<XElement> pricesByPartNos =  from item in purchaseOrder.Descendants("Item")
                                 where (int) item.Element("Quantity") * (decimal) item.Element("USPrice") > 100
                                 orderby (string)item.Element("PartNumber")
                                 select item;
```

Yeniden, bu yöntem sözdizimi formunda yazılabilir:

```csharp
IEnumerable<XElement> pricesByPartNos = purchaseOrder.Descendants("Item")
                                        .Where(item => (int)item.Element("Quantity") * (decimal)item.Element("USPrice") > 100)
                                        .OrderBy(order => order.Element("PartNumber"));
```

Bunların yanı sıra [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] yeteneklerini [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] geliştirilmiş bir XML programlama arabirimi sağlar. Kullanarak [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], şunları yapabilirsiniz:

- XML'den yük [dosyaları](how-to-load-xml-from-a-file.md) veya [akışları](how-to-stream-xml-fragments-from-an-xmlreader.md).

- XML dosyaları ya da akış serileştirir.

- XML işlevsel oluşturma kullanarak sıfırdan oluşturun.

- Sorgu XPath benzeri eksen kullanılarak XML.

- Bellek içi XML ağacı yöntemleri kullanarak işleme <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>, ve <xref:System.Xml.Linq.XElement.SetValue%2A>.

- XML ağaçlarını XSD kullanarak doğrulama.

- Başka bir şekilden XML ağaçlarını dönüştürmek için bu özellikleri bir birleşimini kullanın.

## <a name="creating-xml-trees"></a>XML Ağaçları Oluşturma

Programlama ile en önemli avantajlarından biri [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] XML ağaçları oluşturma kolay olmasıdır. Örneğin, küçük bir XML ağacı oluşturmak için kod şu şekilde yazabilirsiniz:

```csharp
XElement contacts =
new XElement("Contacts",
    new XElement("Contact",
        new XElement("Name", "Patrick Hines"),
        new XElement("Phone", "206-555-0144",
            new XAttribute("Type", "Home")),
        new XElement("phone", "425-555-0145",
            new XAttribute("Type", "Work")),
        new XElement("Address",
            new XElement("Street1", "123 Main St"),
            new XElement("City", "Mercer Island"),
            new XElement("State", "WA"),
            new XElement("Postal", "68042")
        )
    )
);
```

Daha fazla bilgi için [XML ağaçları oluşturma (C#)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md).

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Xml.Linq>
- [Başlarken (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/getting-started-linq-to-xml.md)
