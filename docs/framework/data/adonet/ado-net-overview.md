---
title: ADO.NET’e Genel Bakış
ms.date: 03/30/2017
ms.assetid: ee3bc1d8-11db-4be4-89eb-c708cf04117d
ms.openlocfilehash: 2d21e5b73757280b679a9c5cd04a56339e7e967e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785102"
---
# <a name="adonet-overview"></a>ADO.NET’e Genel Bakış
ADO.NET, SQL Server ve XML gibi veri kaynaklarına ve OLE DB ve ODBC aracılığıyla sunulan veri kaynaklarına tutarlı erişim sağlar. Veri paylaşımı tüketici uygulamaları, bu veri kaynaklarına bağlanmak ve içerdikleri verileri almak, işlemek ve güncelleştirmek için ADO.NET kullanabilir.  
  
 ADO.NET veri işlemesini, ayrı ayrı veya art arda kullanılabilecek ayrı bileşenlere ayırır. ADO.NET, bir veritabanına bağlanmak, komutları yürütmek ve sonuçları almak için .NET Framework veri sağlayıcıları içerir. Bu sonuçlar doğrudan işlenirler, bir ADO.net nesnesine yerleştirilmiş, <xref:System.Data.DataSet> birden fazla kaynaktaki verilerle birleştirilmiş veya katmanlar arasında geçilen bir nesnesine yerleştirildi. Bu `DataSet` nesne ayrıca bir .NET Framework veri sağlayıcısından bağımsız olarak, uygulamadaki yerel verileri yönetmek için veya XML 'den kaynaklıdır.  
  
 ADO.NET sınıfları System. Data. dll içinde bulunur ve System. xml. dll dosyasında bulunan XML sınıflarıyla tümleşiktir. Veritabanına bağlanan, verileri alan ve ardından bir konsol penceresinde görüntüleyen örnek kod için, bkz. [ADO.net Code Examples](ado-net-code-examples.md).  
  
 ADO.NET, yerel bileşen nesne modeli (COM) geliştiricilerine ActiveX Data Objects (ADO) tarafından sağlanan işlevselliğe benzer şekilde yönetilen kod yazan geliştiricilere işlevsellik sağlar. .NET uygulamalarınızda verilere erişmek için ADO değil ADO.NET kullanmanızı öneririz.  
  
 ADO.NET, .NET Framework içinde en doğrudan veri erişimi yöntemini sağlar. Uygulamaların temel depolama modeli yerine kavramsal bir modelde çalışmasına izin veren üst düzey bir soyutlama için, bkz. [ADO.NET Entity Framework](./ef/index.md).  
  
 **Gizlilik bildirimi**: System. Data. dll, System. Data. Design. dll, System. Data. OracleClient. dll, System. Data. SqlXml. dll, System. Data. LINQ. dll, System. Data. SqlServerCe. dll ve System. Data. Datasebir User. dll derlemeleri bir kullanıcının özel veriler ve özel olmayan veriler.  Bu derlemeler kullanıcının özel verilerini toplamaz, depolamaz veya taşımıyor. Ancak, üçüncü taraf uygulamalar bu derlemeleri kullanarak bir kullanıcının özel verilerini toplayabilir, saklayabilir veya taşıbilirler.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [ADO.NET Mimarisi](ado-net-architecture.md)  
 ADO.NET mimarisi ve bileşenlerine genel bir bakış sağlar.  
  
 [ADO.NET Teknoloji Seçenekleri ve Yönergeleri](ado-net-technology-options-and-guidelines.md)  
 Varlık veri platformuna dahil olan ürünleri ve teknolojileri açıklar.  
  
 [LINQ ve ADO.NET](linq-and-ado-net.md)  
 Dil ile tümleşik sorgunun (LINQ) ADO.NET 'de nasıl uygulandığını ve ilgili konuların bağlantılarını sağladığını açıklar.  
  
 [.NET Framework Veri Sağlayıcıları](data-providers.md)  
 .NET Framework veri sağlayıcısının tasarımına ve ADO.NET ile birlikte bulunan .NET Framework veri sağlayıcılarına genel bir bakış sağlar.  
  
 [ADO.NET Veri Kümeleri](ado-net-datasets.md)  
 `DataSet` Tasarıma ve bileşenlere genel bir bakış sağlar.  
  
 [ADO.NET’te Yan Yana Yürütme](side-by-side-execution.md)  
 ADO.NET sürümlerindeki farklılıkları ve yan yana yürütme ve uygulama uyumluluğuna ilişkin etkilerini açıklar.  
  
 [ADO.NET Kod Örnekleri](ado-net-code-examples.md)  
 ADO.NET veri sağlayıcılarını kullanarak veri alan kod örnekleri sağlar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [ADO.NET’teki Yenilikler](whats-new.md)  
 ADO.NET ' de yeni olan özellikleri tanıtır.  
  
 [ADO.NET Uygulamalarının Güvenliğini Sağlama](securing-ado-net-applications.md)  
 ADO.NET kullanılırken güvenli kodlama uygulamalarını açıklar.  
  
 [ADO.NET’te Veri Türü Eşlemeleri](data-type-mappings-in-ado-net.md)  
 .NET Framework veri türleri ve .NET Framework veri sağlayıcıları arasındaki veri türü eşlemelerini açıklar.  
  
 [ADO.NET’te Veri Alma ve Değiştirme](retrieving-and-modifying-data.md)  
 Bir veri kaynağına bağlanmayı, verileri almayı ve verileri değiştirmeyi açıklar. Bu ve `DataReaders` `DataAdapters`içerir.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [ADO.NET](index.md)
- [Visual Studio'da verilere erişime](/visualstudio/data-tools/accessing-data-in-visual-studio)
