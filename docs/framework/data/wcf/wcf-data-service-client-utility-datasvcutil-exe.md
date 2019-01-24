---
title: WCF veri hizmeti istemci yardımcı programı (DataSvcUtil.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, generating client data classes
- WCF Data Services, client library
- WCF Data Services, consuming
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
ms.openlocfilehash: 3442142eb249d04dabba455a57f02f3cdc7f4b91
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54731757"
---
# <a name="wcf-data-service-client-utility-datasvcutilexe"></a>WCF veri hizmeti istemci yardımcı programı (DataSvcUtil.exe)

DataSvcUtil.exe kullanan WCF Veri Hizmetleri tarafından sağlanan bir komut satırı aracı olan bir [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] akışı ve bir .NET Framework istemci uygulamadan bir veri hizmetine erişmek için gerekli olan istemci veri hizmeti sınıfları oluşturur. Bu yardımcı programı, aşağıdaki meta veri kaynaklarını kullanarak veri sınıfları oluşturabilirsiniz:

-   Kök veri hizmetinin URI'si. Yardımcı programı, veri hizmeti tarafından kullanıma sunulan veri modelini açıklar hizmet meta verileri belgesi ister. Daha fazla bilgi için [OData: Meta veri belgesi hizmet](https://go.microsoft.com/fwlink/?LinkId=186070).

-   Tanımlanan sınıfında tanımlandığı gibi kavramsal şema tanım dili (CSDL) kullanarak bir veri modeli dosyası (.csdl) [ \[MC CSDL\]: Kavramsal şema tanım dosyası biçimi](https://go.microsoft.com/fwlink/?LinkID=159072) belirtimi.

-   Entity Framework ile sağlanan varlık veri modeli araçları kullanılarak oluşturulan bir .edmx dosyası. Daha fazla bilgi için [ \[MC EDMX\]: Varlık veri modeli için veri hizmetlerini paketleme biçimini](https://go.microsoft.com/fwlink/?LinkID=178833) belirtimi.

Daha fazla bilgi için [nasıl yapılır: El ile istemci veri hizmeti sınıfları oluşturma](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).

DataSvcUtil.exe aracına [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] dizin. Çoğu durumda, bu bulunan *C:\Windows\Microsoft.NET\Framework\v4.0*. 64-bit sistemler için bu bulunan *C:\Windows\Microsoft.NET\Framework64\v4.0*. Visual Studio için geliştirici Komut İstemi'nden DataSvcUtil.exe Aracı'nı da erişebilirsiniz.

## <a name="syntax"></a>Sözdizimi

```
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]
```

### <a name="parameters"></a>Parametreler

|Seçenek|Açıklama|
|------------|-----------------|
|`/dataservicecollection`|Nesneleri denetimlere bağlamak için gerekli kodu aynı zamanda oluşturulduğunu belirtir.|
|`/help`<br /><br /> -veya-<br /><br /> `/?`|Araç için komut sözdizimini ve seçenekleri görüntüler.|
|`/in:` *\<Dosya >*|.Csdl veya .edmx dosyası veya dosyanın bulunduğu dizini belirtir.|
|`/language:`[VB&#124;CSharp]|Oluşturulan kaynak kodu dosyaları dilini belirtir. C# dil Varsayılanları.|
|`/nologo`|Telif hakkı iletisini görüntülenmesini bastırır.|
|`/out:` *\<Dosya >*|Oluşturulan istemci veri hizmeti sınıfları içeren kaynak kodu dosyasının adını belirtir.|
|`/uri:` *\<dize >*|OData akışı URI'si.|
|`/version:`[1.0&#124;2.0]|OData kabul edilen en yüksek sürümü belirtir. Sürüme göre belirlenir `DataServiceVersion` döndürülen veri hizmeti meta verilerinde DataService öğesinin özniteliği. Daha fazla bilgi için [veri hizmeti sürümü oluşturma](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md). Belirttiğinizde `/dataservicecollection` parametresini de belirtmeniz gerekir `/version:2.0` veri bağlamayı etkinleştirmek için.|

## <a name="see-also"></a>Ayrıca bkz.

- [Veri Hizmeti İstemci Kitaplığı Oluşturma](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)
- [Nasıl yapılır: Bir veri hizmeti başvurusu ekleme](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)
