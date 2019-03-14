---
title: ADO.NET'e LINQ (Portal Sayfası)
ms.date: 07/20/2015
ms.assetid: 6bd269b4-3509-4688-b672-836008704182
ms.openlocfilehash: 51bca1cae25cf20244b183946964a3de14a2d796
ms.sourcegitcommit: 5d9f4b805787f890ca6e0dc7ea30a43018bc9cbb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/13/2019
ms.locfileid: "54502019"
---
# <a name="linq-to-adonet-portal-page"></a>ADO.NET'e LINQ (Portal Sayfası)
[!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)] içinde herhangi bir numaralandırma nesnesi üzerinde sorgulama sayesinde [!INCLUDE[vstecado](~/includes/vstecado-md.md)] kullanarak [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] programlama modeli.  
  
> [!NOTE]
>  [!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)] Belgeleri, ADO.NET .NET Framework SDK bölümünde bulunur: [LINQ ve ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md).  
  
 Üç ayrı ADO.NET vardır [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] teknolojileri: [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)], [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], ve [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)]. [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)] daha zengin, en iyi duruma getirilmiş üzerinde sorgulama sağlar <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] veritabanı şemalarını SQL Server, doğrudan sorgu sağlar ve [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)] sorgu sağlar bir [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)].  
  
## <a name="linq-to-dataset"></a>LINQ - DataSet  
 <xref:System.Data.DataSet> En yaygın olarak kullanılan bileşenler biri [!INCLUDE[vstecado](~/includes/vstecado-md.md)], ve olan bağlantısı kesilmiş programlama anahtar öğesi modeli [!INCLUDE[vstecado](~/includes/vstecado-md.md)] üzerine kurulmuştur. Bu teklifleriyle, ancak rağmen <xref:System.Data.DataSet> sorgu özellikleri sınırlıdır.  
  
 [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)] daha zengin sorgu özellikleri oluşturmanızı sağlayan <xref:System.Data.DataSet> diğer birçok veri kaynakları için sunulan sorgu işlevini kullanarak.  
  
 Daha fazla bilgi için [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).  
  
## <a name="linq-to-sql"></a>LINQ - SQL  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] İlişkisel verileri nesne gibi yönetmek için bir çalışma zamanı altyapısı sağlar. İçinde [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], ilişkisel veritabanı veri modeli, geliştiricinin programlama dilinde ifade nesne modeli eşlenir. Uygulamayı çalıştırdığınızda [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] dil ile tümleşik sorgu nesne modelinde SQL'e çevirir ve yürütme için veritabanı gönderir. Veritabanı sonuçları döndürdüğünde [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] bunları yeniden düzenleyebilirsiniz nesnelerine çevirir.  
  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] nesne modelinde devralma ve saklı yordamları ve kullanıcı tanımlı işlevleri veritabanında için destek içerir.  
  
 Daha fazla bilgi için [LINQ to SQL](../../../../../docs/framework/data/adonet/sql/linq/index.md).  
  
## <a name="linq-to-entities"></a>LINQ - Varlıklar  
 Aracılığıyla [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)], ilişkisel veri, .NET ortamını nesneler olarak gösterilir. Bu nesne için ideal bir hedef katman sağlar [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] geliştiriciler, iş mantığı oluşturmak için kullanılan dil veritabanından karşı sorgular formüle etmek destek. Bu özellik olarak da bilinen [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)]. Bkz: [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md) daha fazla bilgi için.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [LINQ ve ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md)
- [Dil ile tümleşik sorgu (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/index.md)
