---
title: DataRelations İçinde Gezinme
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
ms.openlocfilehash: 412f133c7cf23642ba92d54272287cb708dddc92
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784355"
---
# <a name="navigating-datarelations"></a>DataRelations İçinde Gezinme
' A <xref:System.Data.DataRelation> ait birincil işlevlerden biri, bir <xref:System.Data.DataSet>' ın içinde diğerine gezinmesine <xref:System.Data.DataTable> izin verdir. Bu, ilgili bir **DataTable**nesnesinden tek bir <xref:System.Data.DataRow> **DataRow** verildiğinde ilgili tüm nesneleri bir **DataTable** içinde almanıza olanak sağlar. Örneğin, bir müşteri tablosu ve sipariş tablosu arasında bir **DataRelation** oluşturduktan sonra, **GetChildRows**kullanarak belirli bir müşteri satırı için tüm sipariş satırlarını alabilirsiniz.  
  
 Aşağıdaki kod örneği, bir **veri kümesinin** **Customers** tablosu ve **Orders** tablosu arasında bir **DataRelation** oluşturur ve her müşteri için tüm siparişleri döndürür.  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 Sonraki örnek, dört tablo ile ilişkili ve bu ilişkilerle birlikte gelen örnek üzerinde oluşturulur. Önceki örnekte olduğu gibi, **MüşteriNo** , **Customers** tablosunu **Orders** tablosuyla ilişkilendirir. **Müşteriler** tablosundaki her müşteri Için, **siparişler** tablosundaki tüm alt satırlar, belirli bir müşterinin sahip olduğu siparişlerin sayısını ve bunların **OrderID** değerlerini döndürmek için belirlenir.  
  
 Genişletilmiş örnek, **OrderDetails** ve **Products** tablolarından değerleri de döndürür. **Siparişler** tablosu, her müşteri siparişi, hangi ürünlerin ve miktarların sıralandığı hakkında bilgi edinmek için **OrderDetails** **tablosu ile ilgilidir** . **OrderDetails** tablosu yalnızca sıralı bir ürünün **ProductID** 'Sini içerdiğinden, **OrderDetails** , **ProductName**'i döndürmek için **ProductID** kullanan **ürünlerle** ilgilidir. Bu ilişkide, **Ürünler** tablosu üst ve **sipariş ayrıntıları** tablosu alt öğesidir. Sonuç olarak, **OrderDetails** tablosu üzerinden yineleme yaparken, ilgili **ProductName** değerini almak için **GetParentRow** çağırılır.  
  
 **Müşteriler** ve **siparişler** tabloları Için **DataRelation** oluşturulduğunda, **createkısıtlamalar** bayrağı için hiçbir değer belirtildiğine dikkat edin (varsayılan değer **true**'dur). Bu, **Orders** tablosundaki tüm satırların, ana **müşteriler** tablosunda bulunan bir **CustomerID** değeri olduğunu varsayar. **Siparişler** tablosunda **müşteriler** tablosunda bulunmayan bir <xref:System.Data.ForeignKeyConstraint> **CustomerID** varsa, bir özel durumun oluşturulmasına neden olur.  
  
 Alt sütun üst sütunun içermediği değerleri içeriyorsa, **DataRelation**'ı eklerken **createkısıtlamalar** bayrağını **false** olarak ayarlayın. Örnekte, **Orders** tablosu ve **OrderDetails** tablosu arasındaki **DataRelation** için **createkısıtlamalar** bayrağı **false** olarak ayarlanır. Bu, uygulamanın **OrderDetails** tablosundan tüm kayıtları ve bir çalışma zamanı özel durumu oluşturmadan **siparişler** tablosundan yalnızca bir kayıt alt kümesini döndürmesini sağlar. Genişletilmiş örnek, çıktıyı aşağıdaki biçimde oluşturur.  
  
```  
Customer ID: NORTS  
  Order ID: 10517  
        Order Date: 4/24/1997 12:00:00 AM  
           Product: Filo Mix  
          Quantity: 6  
           Product: Raclette Courdavault  
          Quantity: 4  
           Product: Outback Lager  
          Quantity: 6  
  Order ID: 11057  
        Order Date: 4/29/1998 12:00:00 AM  
           Product: Outback Lager  
          Quantity: 3  
```  
  
 Aşağıdaki kod örneği, sipariş **ayrıntıları** ve **ürün** tablolarından alınan değerlerin, yalnızca döndürülmekte olan **siparişler** tablosundaki kayıtların bir alt kümesiyle döndürüldüğü genişletilmiş bir örnektir.  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [DataSets, DataTables ve DataViews](index.md)
- [ADO.NET’e Genel Bakış](../ado-net-overview.md)
