---
title: Kurallı İşlevler
ms.date: 03/30/2017
ms.assetid: bbcc9928-36ea-4dff-9e31-96549ffed958
ms.openlocfilehash: 8949735ba4712b721460335b4579f0a268c91aea
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251269"
---
# <a name="canonical-functions"></a>Kurallı İşlevler
Bu bölümde tüm veri sağlayıcıları tarafından desteklenen ve tüm sorgulama teknolojileri tarafından kullanılabilen kurallı işlevler ele alınmaktadır. Kurallı işlevler bir sağlayıcı tarafından genişletilemez.  
  
 Bu kurallı işlevler, sağlayıcı için karşılık gelen veri kaynağı işlevselliğine çevrilir. Bu, veri kaynakları genelinde ortak bir biçimde ifade edilen işlev etkinleştirmeleri için izin verir.  
  
 Bu kurallı işlevler veri kaynaklarından bağımsız olduğundan, kurallı işlevlerin bağımsız değişkeni ve dönüş türleri kavramsal modeldeki türler bakımından tanımlanmıştır. Ancak, bazı veri kaynakları kavramsal modeldeki tüm türleri desteklemeyebilir.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Sorguda kurallı işlevler kullanıldığında, uygun işlev veri kaynağında çağrılır.  
  
 Tüm kurallı işlevlerde hem null girişi davranışı hem de hata koşulları açıkça belirtilmiştir. Mağaza sağlayıcılarının bu davranışla uyumlu olması gerekir, ancak [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] bu davranışı zorlamaz.  
  
 LINQ senaryolarında, clr yöntemlerini temel alınan [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] veri kaynağındaki yöntemlere eşleme ile ilgili sorgular. CLR yöntemleri kurallı işlevlere eşlenir, böylece veri kaynağından bağımsız olarak belirli bir yöntem kümesinin doğru şekilde eşlenmesi sağlanır.  
  
## <a name="canonical-functions-namespace"></a>Kurallı Işlevler ad alanı  
 Kurallı işlev <xref:System.Data.Metadata.Edm>için ad alanı. <xref:System.Data.Metadata.Edm> Ad alanı tüm sorgulara otomatik olarak eklenir. Ancak, kurallı bir işlevle aynı ada sahip bir işlev içeren başka bir ad alanı içeri aktarılmışsa ( <xref:System.Data.Metadata.Edm> ad alanında), ad alanını belirtmeniz gerekir.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Toplu Kurallı İşlevler](aggregate-canonical-functions.md)  
 Birleşik [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kurallı işlevleri açıklar.  
  
 [Kurallı Matematik İşlevleri](math-canonical-functions.md)  
 Matematik [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kurallı işlevlerini açıklar.  
  
 [Kurallı Dize İşlevleri](string-canonical-functions.md)  
 Kurallı dize [!INCLUDE[esql](../../../../../../includes/esql-md.md)] işlevlerini açıklar.  
  
 [Kurallı Tarih ve Saat İşlevleri](date-and-time-canonical-functions.md)  
 Tarih ve saat [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kurallı işlevleri ele alır.  
  
 [Bit Düzeyinde Kurallı İşlevler](bitwise-canonical-functions.md)  
 Bit düzeyinde [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kurallı işlevleri açıklar.  
  
 [Uzamsal İşlevler](spatial-functions.md)  
 Uzamsal [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kurallı işlevleri açıklar.  
  
 [Diğer Kurallı İşlevler](other-canonical-functions.md)  
 Bit düzeyinde, tarih/saat, dize, matematik veya toplama olarak sınıflandırılmayan işlevleri açıklar.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Entity SQL’e Genel Bakış](entity-sql-overview.md)
- [Entity SQL Başvurusu](entity-sql-reference.md)
- [SQL Server İşlevleri ile Kurallı Kavramsal Model Eşlemesi](../conceptual-model-canonical-to-sql-server-functions-mapping.md)
- [Kullanıcı Tanımlı İşlevler](user-defined-functions-entity-sql.md)
