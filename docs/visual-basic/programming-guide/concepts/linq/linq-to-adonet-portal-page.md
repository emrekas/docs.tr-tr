---
title: ADO.NET'e LINQ (Portal Sayfası)
ms.date: 07/20/2015
ms.assetid: bbbd7c76-2981-4b91-b8d2-437547181f52
ms.openlocfilehash: 7713d134650305c4e2d930a43c8b443b86448786
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882543"
---
# <a name="linq-to-adonet-portal-page"></a>ADO.NET'e LINQ (Portal Sayfası)
[!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)] ADO.NET'te numaralandırılabilir herhangi bir nesne üzerinde kullanarak sorgulama sayesinde [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] programlama modeli.  
  
> [!NOTE]
>  [!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)] Belgeleri, ADO.NET .NET Framework SDK bölümünde bulunur: [LINQ ve ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md).
  
 Üç ayrı ADO.NET vardır [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] teknolojileri: [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)], [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], ve [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)]. [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)] daha zengin, en iyi duruma getirilmiş üzerinde sorgulama sağlar <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] veritabanı şemalarını SQL Server, doğrudan sorgu sağlar ve [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)] sorgu sağlar bir [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)].  
  
## <a name="linq-to-dataset"></a>LINQ - DataSet  
 <xref:System.Data.DataSet> ADO.NET en yaygın olarak kullanılan bileşenler biridir ve ADO.NET yerleşik olan bağlantısı kesilmiş programlama modelinin önemli bir öğedir. Bu teklifleriyle, ancak rağmen <xref:System.Data.DataSet> sorgu özellikleri sınırlıdır.  
  
 [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)] daha zengin sorgu özellikleri oluşturmanızı sağlayan <xref:System.Data.DataSet> diğer birçok veri kaynakları için sunulan sorgu işlevini kullanarak.  
  
 Daha fazla bilgi için [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).  
  
## <a name="linq-to-sql"></a>LINQ - SQL  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] İlişkisel verileri nesne gibi yönetmek için bir çalışma zamanı altyapısı sağlar. İçinde [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], ilişkisel veritabanı veri modeli, geliştiricinin programlama dilinde ifade nesne modeli eşlenir. Uygulamayı çalıştırdığınızda [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] dil ile tümleşik sorgu nesne modelinde SQL'e çevirir ve yürütme için veritabanı gönderir. Veritabanı sonuçları döndürdüğünde [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] bunları yeniden düzenleyebilirsiniz nesnelerine çevirir.  
  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] nesne modelinde devralma ve saklı yordamları ve kullanıcı tanımlı işlevleri veritabanında için destek içerir.  
  
 Daha fazla bilgi için [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md).  
  
## <a name="linq-to-entities"></a>LINQ - Varlıklar  
 Aracılığıyla [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)], ilişkisel veri, .NET ortamını nesneler olarak gösterilir. Bu nesne için ideal bir hedef katman sağlar [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] geliştiriciler, iş mantığı oluşturmak için kullanılan dil veritabanından karşı sorgular formüle etmek destek. Bu özellik olarak da bilinen [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)]. Bkz: [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md) daha fazla bilgi için.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [LINQ ve ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md)
- [Dil ile tümleşik sorgu (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
