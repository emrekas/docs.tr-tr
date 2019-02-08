---
title: DataView
ms.date: 03/30/2017
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
ms.openlocfilehash: bcf370e30c50bf5d992279c7abe02bfc6262ea40
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825881"
---
# <a name="dataviews"></a>DataView
A <xref:System.Data.DataView> depolanan veriler alanının farklı görünümlerini oluşturmanızı sağlayan bir <xref:System.Data.DataTable>, veri bağlama uygulamalarda sık kullanılan bir özellik. Kullanarak bir **DataView**sıralamalar farklı olan bir tabloda verilerini açığa çıkarabilir ve verileri satır durum ya da bir filtre ifadesi temelinde göre filtre uygulayabilirsiniz.  
  
 A **DataView** temel alınan verileri dinamik bir görünümünü sağlar **DataTable**: oluşunca içerik, sıralama ve üyelik değişiklikleri yansıtacak. Bu davranışı farklıdır **seçin** yöntemi **DataTable**, döndüren bir <xref:System.Data.DataRow> alan bir tablodaki dizisi üzerinde belirli bir filtre ve/veya sıralama düzeni: Bu içeriği değişiklikleri yansıtır. Tablo, ancak üyeliğini temel alınan ve sıralama statik kalır. Dinamik yeteneklerini **DataView** veri bağlama uygulamalar için ideal bir çözüm oluşturur.  
  
 A **DataView** dinamik veri için uygulayabileceğiniz farklı sıralama ve filtreleme ölçütlerini çok veritabanı görünümü, tek bir dizi görünümünü sağlar. Ancak, bir veritabanı görünümü aksine bir **DataView** tablo olarak işlenemiyorsa ve birleştirilmiş tablolar görünümünü sağlayamaz. Ayrıca kaynak tablosunda mevcut sütunları hariç tutamazsınız ya da kaynak tablosunda bulunmayan hesaplama sütunlar gibi bir sütun ekleyebilirsiniz.  
  
 Kullanabileceğiniz bir <xref:System.Data.DataView.DataViewManager%2A> tüm tablolarda görünüm ayarlarını yönetmek için bir **veri kümesi**. **DataViewManager** her tablo için varsayılan görünüm ayarlarını yönetmek için kullanışlı bir yol sağlar. Bir denetim için birden fazla tablonun bağlanırken bir **veri kümesi**, bağlayıcı için bir **DataViewManager** ideal bir seçenektir.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [DataView Oluşturma](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataview.md)  
 Nasıl oluşturulacağını açıklar bir **DataView** için bir **DataTable**.  
  
 [Verileri Sıralama ve Filtreleme](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 Özelliklerini ayarlama işlemi açıklanmaktadır bir **DataView** veri satırları kümelerine filtre belirli ölçütlere geri dönmek için ya da belirli sıralama düzeninde verileri döndürür.  
  
 [DataRows ve DataRowViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarows-and-datarowviews.md)  
 Tarafından kullanıma sunulan veri erişim açıklar **DataView**.  
  
 [Satırları Bulma](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)  
 Belirli bir satır bulun açıklar bir **DataView**.  
  
 [ChildViews ve İlişkileri](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/childviews-and-relations.md)  
 Veri görünümlerini kullanarak bir üst-alt ilişkisi oluşturmayı açıklar bir **DataView**.  
  
 [DataView Değiştirme](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/modifying-dataviews.md)  
 Açıklar temel alınan verilerde değişiklik yapma **DataTable** aracılığıyla **DataView**güncelleştirmelerini devre dışı bırakma veya etkinleştirme dahil olmak üzere.  
  
 [DataView Olaylarını İşleme](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataview-events.md)  
 Nasıl kullanılacağını açıklar **ListChanged** bildirim almak için bir olay olduğunda içeriği veya sırasını bir **DataView** güncelleştiriliyor.  
  
 [DataView Yönetme](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/managing-dataviews.md)  
 Nasıl kullanılacağını açıklayan bir **DataViewManager** yönetmek için **DataView** her tablo için ayarları bir **veri kümesi**.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [ASP.NET Web Uygulamaları](https://docs.microsoft.com/previous-versions/655cec97(v=vs.100))  
 ASP.NET uygulamaları, Web Forms ve Web hizmetleri oluşturmak için genel bakışın yanı sıra ayrıntılı, adım adım yordamlar sağlar.  
  
 [Windows uygulamaları](https://docs.microsoft.com/previous-versions/ms184421(v=vs.100))  
 Windows Forms ve konsol uygulamaları ile çalışma hakkında ayrıntılı bilgiler sağlar.  
  
 [DataSets, DataTables ve DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Açıklar **veri kümesi** nesne ve uygulama verilerini yönetmek için nasıl kullanabilirsiniz.  
  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 Açıklar **DataTable** nesne ve tek başına veya bir parçası olarak uygulama verilerini yönetmek için kullanma hakkında bir **veri kümesi**.  
  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 ADO.NET açıklar mimarisi ve bileşenleri ve mevcut veri kaynaklarına erişim ve uygulama verilerini yönetmek için ADO.NET kullanma.  
  
## <a name="see-also"></a>Ayrıca bkz.
- [ADO.NET yönetilen sağlayıcıları ve DataSet Geliştirici Merkezi](https://go.microsoft.com/fwlink/?LinkId=217917)
