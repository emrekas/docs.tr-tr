---
title: Tür sistemi (varlık SQL)
ms.date: 03/30/2017
ms.assetid: 818a505b-a196-41dd-aaac-2ccd5f7a2f1a
ms.openlocfilehash: 1831028f9e659dab90ca3c8689d7ff2d5c0ee36a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554341"
---
# <a name="type-system-entity-sql"></a>Tür sistemi (varlık SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] bir dizi türlerini destekler:  
  
-   (Basit) temel türler gibi `Int32` ve `String.`  
  
-   Şemada gibi tanımlı nominal türlerinden <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType>, ve <xref:System.Data.Metadata.Edm.RelationshipType>.  
  
-   Şema içinde açıkça tanımlanmayan anonim türler: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType>, ve <xref:System.Data.Metadata.Edm.RefType>.  
  
 Bu bölümde, ancak tarafından desteklenen şema içinde açıkça tanımlanmayan anonim türleri ele alınmaktadır [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. Basit ve nominal türleri hakkında daha fazla bilgi için bkz. [kavramsal Model türleri (CSDL)](https://msdn.microsoft.com/library/987b995f-e429-4569-9559-b4146744def4).  
  
## <a name="rows"></a>Satırları  
 Satır oluşan yazılı ve adlandırılmış üyelerinin sırasını bir satırı yapısını bağlıdır. Satır türü kimliksiz sahiptir ve öğesinden devralınamaz. Üye sırasıyla eşdeğer ise aynı satır türü örneklerini eşdeğerdir. Satırları, yapısal denklik ötesinde davranışı yok ve ortak dil çalışma zamanı'nda eşdeğeri sahiptir. Satır veya satır koleksiyonu içeren yapıları, sorguları neden olabilir. API bağlama arasında [!INCLUDE[esql](../../../../../../includes/esql-md.md)] sorgular ve konak dil tanımlar satırları bir sonuç getirdi sorguda nasıl gerçekleşir. Bir satır örneği oluşturma hakkında daha fazla bilgi için bkz: [oluşturma türleri](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).  
  
## <a name="collections"></a>Koleksiyonlar  
 Koleksiyon türleri, sıfır veya daha fazla diğer nesnelerin örneklerini temsil eder. Koleksiyon oluşturma hakkında daha fazla bilgi için bkz: [oluşturma türleri](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).  
  
## <a name="references"></a>Referanslar  
 Bir başvuru, bir özel varlık kümesinde belirli bir varlığa mantıksal bir işaretçisidir.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] oluşturun, ayrıştırma ve başvurular arasında gitmek için aşağıdaki işleçleri destekler:  
  
-   [REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)  
  
-   [CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
  
-   [KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
  
-   [DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)  
  
 Üye erişim (nokta) işlecini kullanarak başvuru gidebilirsiniz (`.`). Aşağıdaki kod parçacığı r (başvuru) özelliği üzerinden giderek (sıra), kimlik özelliği ayıklar.  
  
```  
select o2.r.Id   
from (select ref(o) as r from LOB.Orders as o) as o2   
```  
  
 Başvuru değeri null ise veya başvuru hedefinin yoksa sonuç NULL'dur.  
  
## <a name="see-also"></a>Ayrıca bkz.
- [Entity SQL’e Genel Bakış](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [Entity SQL Başvurusu](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [CAST](../../../../../../docs/framework/data/adonet/ef/language-reference/cast-entity-sql.md)
- [CSDL, SSDL ve MSL Belirtimleri](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
