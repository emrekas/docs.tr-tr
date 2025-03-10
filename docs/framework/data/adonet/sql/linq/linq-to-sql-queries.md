---
title: LINQ to SQL Sorguları
ms.date: 03/30/2017
ms.assetid: f4897aaa-7f44-4c20-a471-b948c2971aae
ms.openlocfilehash: a170beae3a9f0c923502028f5579de1f3916c07d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793006"
---
# <a name="linq-to-sql-queries"></a>LINQ to SQL Sorguları
Sorguları, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] içindeki [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]ile aynı sözdizimini kullanarak tanımlarsınız. Tek fark, sorgularınızda başvurulan nesnelerin bir veritabanındaki öğelerle eşlendiğine ilişkin bir farktır. Daha fazla bilgi için bkz. [LINQ Sorgularına Giriş (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]yazdığınız sorguları eşdeğer SQL sorgularına çevirir ve işlenmek üzere sunucuya gönderir. Özellikle, uygulamanız sorgu yürütmeyi istemek için [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] API 'yi kullanır. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Sağlayıcı daha sonra sorguyu SQL metnine dönüştürür ve ADO sağlayıcısına yürütmeyi devreder. ADO sağlayıcısı sorgu sonuçlarını bir `DataReader`olarak döndürür. Sağlayıcı, ADO sonuçlarını <xref:System.Linq.IQueryable> Kullanıcı nesneleri koleksiyonuna çevirir. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]  
  
> [!NOTE]
> .NET Framework yerleşik türlerinde çoğu Yöntem ve operatör SQL 'e doğrudan Çeviriler sağlar. [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] Bunlar, çalışma zamanı özel durumları çevirmemelidir. Daha fazla bilgi için bkz. [SQL-CLR tür eşleme](sql-clr-type-mapping.md).  
  
 Aşağıdaki tabloda, ve [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] öğeleri arasındaki benzerlikler ve farklar gösterilmektedir.  
  
|Öğe|LINQ sorgusu|[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]Sorgulayamadı|  
|----------|----------------|----------------------------------------------------------------------|  
|Sorguyu tutan yerel değişkenin dönüş türü (diziler döndüren sorgular için)|Yorlar`IEnumerable`|Yorlar`IQueryable`|  
|Veri kaynağını belirtme|(Visual Basic) veya `from` (C#) yan tümcesini kullanır `From`|Naklettiğiniz|  
|Filtreleme|Yantümceyi`Where`kullanır / `where`|Naklettiğiniz|  
|Gruplandırma|Yantümceyi`Group…By`kullanır / `groupby`|Naklettiğiniz|  
|Seçme (yansıtma)|Yantümceyi`Select`kullanır / `select`|Naklettiğiniz|  
|Ertelenmiş ve anında yürütme|Bkz. [LINQ Sorgularına Giriş (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)|Naklettiğiniz|  
|Birleştirmeleri uygulama|Yantümceyi`Join`kullanır / `join`|Yan tümcesini kullanabilir `Join` / , ancak daha etkin bir şekilde <xref:System.Data.Linq.Mapping.AssociationAttribute> özniteliğini kullanır. `join` Daha fazla bilgi için bkz. [Ilişkiler genelinde sorgulama](querying-across-relationships.md).|  
|Uzaktan yerel yürütmeye karşı||Daha fazla bilgi için bkz [. uzak ve Yerel yürütme](remote-vs-local-execution.md).|  
|Akış ve önbelleğe alınmış sorgulama karşılaştırması|Yerel bellek senaryosunda uygulanamaz||  
  
## <a name="see-also"></a>Ayrıca bkz.

- [LINQ Sorgularına Giriş (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)
- [Temel LINQ Sorgu İşlemleri](../../../../../csharp/programming-guide/concepts/linq/basic-linq-query-operations.md)
- [LINQ Sorgu İşlemlerinde Tür İlişkileri](../../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)
- [Sorgu Kavramları](query-concepts.md)
