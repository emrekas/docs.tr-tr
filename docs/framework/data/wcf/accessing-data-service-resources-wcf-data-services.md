---
title: Veri hizmeti kaynaklarına erişme (WCF Veri Hizmetleri)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, querying
- getting started, WCF Data Services
- querying the data service [WCF Data Service]
- WCF Data Services, getting started
- WCF Data Services, accessing data
ms.assetid: 9665ff5b-3e3a-495d-bf83-d531d5d060ed
ms.openlocfilehash: eff8d682004bf437a9b5470a4eb91c9bd52bfad5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70791327"
---
# <a name="accessing-data-service-resources-wcf-data-services"></a>Veri hizmeti kaynaklarına erişme (WCF Veri Hizmetleri)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] verilerinizi URI 'ler tarafından adreslenebilir kaynaklarla bir akış olarak ortaya çıkarmak için ' i destekler. Bu kaynaklar [varlık veri modeli](../adonet/entity-data-model.md)varlık ilişkisi kurallarına göre temsil edilir. Bu modelde, varlıklar, bir uygulama etki alanında bulunan, müşteriler, siparişler, öğeler ve ürünler gibi veri türleri olan işletimsel birimleri temsil eder. Varlık verilerine, temsili durum aktarımı (REST) semantiği kullanılarak erişilir ve değiştirilir, özellikle Al, koy, POST ve DELETE için standart HTTP fiilleri.  
  
## <a name="addressing-resources"></a>Kaynakları adresleme  
 ' [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]De, veri modeli tarafından sunulan tüm verileri bir URI kullanarak adresleyebilirsiniz. Örneğin, aşağıdaki URI, müşteri varlık türünün tüm örneklerinin girişlerini içeren Customers varlık kümesi olan bir akış döndürür:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers  
```  
  
 Varlıklarda varlık anahtarları adlı özel özellikler vardır. Varlık anahtarı, bir varlık kümesindeki tek bir varlığı benzersiz bir şekilde tanımlamak için kullanılır. Bu, varlık kümesindeki bir varlık türünün belirli bir örneğini ele almanıza olanak sağlar. Örneğin, aşağıdaki URI, anahtar değeri `ALFKI`olan bir müşteri varlık türünün belirli bir örneği için bir giriş döndürür:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')  
```  
  
 Bir varlık örneğinin ilkel ve karmaşık özellikleri de tek tek adreslenebilir. Örneğin, aşağıdaki URI belirli bir müşterinin `ContactName` özellik değerini içeren bir XML öğesi döndürür:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/ContactName  
```  
  
 `$value` Uç noktasını önceki URI 'ye dahil ettiğinizde, yanıt iletisinde yalnızca ilkel özelliğin değeri döndürülür. Aşağıdaki örnek, XML öğesi olmadan yalnızca "Maria Anders" dizesini döndürür:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/ContactName/$value  
```  
  
 Varlıklar arasındaki ilişkiler veri modelinde ilişkilendirmelere göre tanımlanır. Bu ilişkilendirmeler bir varlık örneğinin gezinti özelliklerini kullanarak ilgili varlıkları adreslemeye olanak tanır. Bir gezinti özelliği, çoktan çoğa bir ilişki olması durumunda tek bir ilgili varlık ya da bire çok ilişki söz konusu olduğunda bir dizi ilgili varlık döndürebilir. Örneğin, aşağıdaki URI belirli bir müşteriyle ilgili tüm siparişlerin kümesi olan bir akış döndürür:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders  
```  
  
 Genellikle çift yönlü olan ilişkiler, bir dizi gezinti özelliği tarafından temsil edilir. Önceki örnekte gösterilen ilişkinin tersi olarak aşağıdaki URI, belirli bir sipariş varlığının ait olduğu müşteri varlığına yönelik bir başvuru döndürür:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Orders(10643)/Customer  
```  
  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]Ayrıca, sorgu ifadelerinin sonuçlarına göre kaynakları adreslemenize de olanak sağlar. Bu, değerlendirilen bir ifadeye göre kaynak kümelerinin filtrelemesine olanak tanır. Örneğin, aşağıdaki URI kaynakları yalnızca, 22 Eylül 1997 tarihinden itibaren sevk edilen belirtilen müşteri için siparişleri döndürecek şekilde filtreliyor:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$filter=ShippedDate gt datetime'1997-09-22T00:00:00'  
```  
  
 Daha fazla bilgi için bkz [. OData: URI kuralları](https://go.microsoft.com/fwlink/?LinkId=185564).  
  
## <a name="system-query-options"></a>Sistem sorgu seçenekleri  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]filtreleme, sıralama ve sayfalama gibi kaynaklarda geleneksel sorgu işlemleri gerçekleştirmek için kullanabileceğiniz bir sistem sorgu seçenekleri kümesi tanımlar. Örneğin, aşağıdaki URI, tüm `Order` varlıkların kümesini, ilgili `Order_Detail` varlıkların yanı bir şekilde `100`sona ermez posta kodlarını döndürür:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Orders?$filter=not endswith(ShipPostalCode,'100')&$expand=Order_Details&$orderby=ShipCity  
```  
  
 Döndürülen akıştaki girişler, siparişlerin ShipCity özelliğinin değeri ile de sıralanır.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]Aşağıdaki [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] sistem sorgu seçeneklerini destekler:  
  
|Sorgu seçeneği|Açıklama|  
|------------------|-----------------|  
|`$orderby`|Döndürülen akıştaki varlıklar için varsayılan bir sıralama düzeni tanımlar. Aşağıdaki sorgu, verilen müşteriler akışını ilçe ve şehre göre sıralar:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$orderby=Country,City`<br /><br /> Daha fazla bilgi için bkz [. OData: OrderBy sistem sorgu seçeneği ($orderby)](https://go.microsoft.com/fwlink/?LinkId=186968).|  
|`$top`|Döndürülen akışa eklenecek varlıkların sayısını belirtir. Aşağıdaki örnek ilk 10 müşteriyi atlar ve sonraki 10 ' u döndürür:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$skip=10&$top=10`<br /><br /> Daha fazla bilgi için bkz [. OData: Üst sistem sorgu seçeneği ($top)](https://go.microsoft.com/fwlink/?LinkId=186969).|  
|`$skip`|Akıştaki varlıkları döndürmeye başlamadan önce atlanacak varlık sayısını belirtir. Aşağıdaki örnek ilk 10 müşteriyi atlar ve sonraki 10 ' u döndürür:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$skip=10&$top=10`<br /><br /> Daha fazla bilgi için bkz [. OData: Sistem sorgu seçeneğini atlayın ($skip)](https://go.microsoft.com/fwlink/?LinkId=186971).|  
|`$filter`|Belirli ölçütlere göre akışta döndürülen varlıkları filtreleyen bir ifade tanımlar. Bu sorgu seçeneği, filtre ifadesini değerlendirmek için kullanılan bir mantıksal karşılaştırma işleçleri, aritmetik işleçler ve önceden tanımlanmış sorgu işlevleri kümesini destekler. Aşağıdaki örnek, 100 ' de bitolmayan posta kodlarının tüm siparişlerini döndürür:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Orders?$filter=not endswith(ShipPostalCode,'100')`<br /><br /> Daha fazla bilgi için bkz [. OData: Filtre sistem sorgu seçeneği ($filter)](https://go.microsoft.com/fwlink/?LinkId=186972).|  
|`$expand`|Sorgu tarafından hangi ilgili varlıkların döndürüleceğini belirtir. İlgili varlıklar, sorgu tarafından döndürülen varlıkla birlikte bir akış veya bir giriş olarak yer alır. Aşağıdaki örnek, her bir siparişin öğe ayrıntılarıyla birlikte ' ALFKI ' müşterisi için sırayı döndürür:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$expand=Order_Details`<br /><br /> Daha fazla bilgi için bkz [. OData: Sistem sorgu seçeneğini genişletin ($expand)](https://go.microsoft.com/fwlink/?LinkId=186973).|  
|`$select`|Varlığın özelliklerini tanımlayan projeksiyonun projeksiyonde döndürüleceğini belirtir. Varsayılan olarak, bir varlığın tüm özellikleri bir akışta döndürülür. Aşağıdaki sorgu `Customer` varlığın yalnızca üç özelliğini döndürür:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$select=CustomerID,CompanyName,City`<br /><br /> Daha fazla bilgi için bkz [. OData: Sistem sorgu seçeneğini belirleyin ($select)](https://go.microsoft.com/fwlink/?LinkID=186076).|  
|`$inlinecount`|Akışta döndürülen varlık sayısı sayısının akışa dahil edilmesini ister. Daha fazla bilgi için bkz [. OData: Inlinecount sistem sorgu seçeneği ($inlinecount)](https://go.microsoft.com/fwlink/?LinkId=186975).|  
  
## <a name="addressing-relationships"></a>Adresleme Ilişkileri  
 Varlık kümelerinin ve varlık örneklerinin ele eklenmesine ek olarak, [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] varlıklar arasındaki ilişkileri temsil eden ilişkilendirmeleri ele almanıza de olanak sağlar. Bu işlevsellik, Northwind örnek veritabanındaki belirli bir siparişle ilişkili olan nakliyecinin gibi iki varlık örneği arasında bir ilişki oluşturabilmesinin veya değiştirebilmesi için gereklidir. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]varlıklar arasındaki `$link` ilişkilendirmeleri özel olarak ele almak için bir işleci destekler. Örneğin, aşağıdaki URI, belirtilen sipariş için nakliyeci yeni bir nakliyeci değiştirmek üzere bir HTTP PUT isteği iletisinde belirtilmiştir.  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Orders(10643)/$links/Shipper  
```  
  
 Daha fazla bilgi için bkz [. OData: Girdiler](https://go.microsoft.com/fwlink/?LinkId=187351)arasındaki bağlantıları adresleme.  
  
## <a name="consuming-the-returned-feed"></a>Döndürülen akışı kullanma  
 Bir [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] kaynağın URI 'si, hizmet tarafından sunulan varlık verilerini adreslemenize olanak sağlar. Bir Web tarayıcısının adres alanına bir URI girdiğinizde, [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] istenen kaynağın akış temsili döndürülür. Daha fazla bilgi için [WCF veri hizmetleri hızlı başlangıç](quickstart-wcf-data-services.md)bölümüne bakın. Bir veri hizmeti kaynağının beklenen verileri döndürdüğü test için bir Web tarayıcısı yararlı olsa da, veri oluşturma, güncelleştirme ve silmeye yönelik üretim verileri Hizmetleri, genellikle bir Web sayfasındaki uygulama kodu veya komut dosyası dilleri tarafından erişilir. Daha fazla bilgi için bkz. [Istemci uygulamasında veri hizmeti kullanma](using-a-data-service-in-a-client-application-wcf-data-services.md).  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Veri Protokolü Web sitesini aç](https://go.microsoft.com/fwlink/?LinkID=182204)
