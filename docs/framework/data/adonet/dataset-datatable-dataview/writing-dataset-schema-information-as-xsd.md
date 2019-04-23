---
title: XSD Olarak DataSet Schema Bilgilerini Yazma
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
ms.openlocfilehash: 8403f9d9be88f34e473fd3512f5499193245d227
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59099449"
---
# <a name="writing-dataset-schema-information-as-xsd"></a>XSD Olarak DataSet Schema Bilgilerini Yazma
Şemasını yazabileceğiniz bir <xref:System.Data.DataSet> olarak XML Şeması Tanım Dili (XSD) şemaya, böylece onu içeren veya içermeyen bir XML belgesi ilgili verileri taşıyabilir. XML şeması bir dosyaya, bir akışa yazılabilir bir <xref:System.Xml.XmlWriter>, veya bir dize; türü kesin belirlenmiş oluşturmada yararlıdır **veri kümesi**. Hakkında daha fazla bilgi için türü kesin belirlenmiş **veri kümesi** nesneleri bkz [yazılan veri kümeleri](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).  
  
 Bir tablo sütunu XML Şeması ' nasıl temsil edildiğini belirtebilirsiniz kullanarak **Columnmapping'in** özelliği <xref:System.Data.DataColumn> nesne. Daha fazla bilgi için bkz: "Metin XML öğeleri ve öznitelikleri sütun eşleme" [XML verileri olarak DataSet içeriği yazma](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).  
  
 Şemasını yazmak için bir **veri kümesi** bir dosyaya bir XML şeması olarak akışı veya **XmlWriter**, kullanın **WriteXmlSchema** yöntemi **veri kümesi**. **WriteXmlSchema** elde edilen XML Şeması hedef belirten bir parametre alır. Aşağıdaki kod örnekleri XML şemasını yazma işlemini göstermek bir **veri kümesi** bir dosyaya, bir dosya adı içeren bir dize geçirerek ve <xref:System.IO.StreamWriter> nesne.  
  
```vb  
dataSet.WriteXmlSchema("Customers.xsd")  
```  
  
```csharp  
dataSet.WriteXmlSchema("Customers.xsd");  
```  
  
```vb  
Dim writer As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xsd")  
dataSet.WriteXmlSchema(writer)  
writer.Close()  
```  
  
```csharp  
System.IO.StreamWriter writer = new System.IO.StreamWriter("Customers.xsd");  
dataSet.WriteXmlSchema(writer);  
writer.Close();  
```  
  
 Şemasını almak için bir **veri kümesi** ve bir XML Şeması dize olarak yazın, kullanın **GetXmlSchema** yöntemi, aşağıdaki örnekte gösterildiği gibi.  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- [DataSet içinde XML kullanma](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [XML Verileri Olarak DataSet İçeriği Yazma](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)
- [Türü Belirtilmiş DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)
- [DataSets, DataTables ve DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [ADO.NET yönetilen sağlayıcıları ve DataSet Geliştirici Merkezi](https://go.microsoft.com/fwlink/?LinkId=217917)
