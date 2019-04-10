---
title: LINQ to Objects'in (Visual Basic)
ms.date: 07/20/2015
ms.assetid: dd4c30bc-1c9b-4781-a482-b5eada38deb2
ms.openlocfilehash: c1e2e8fbaaf984fec69322a459fc7c55890965ad
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59326885"
---
# <a name="linq-to-objects-visual-basic"></a>LINQ to Objects'in (Visual Basic)
Tüm sorgular "LINQ için nesneler" LINQ kullanımı ifade eder <xref:System.Collections.IEnumerable> veya <xref:System.Collections.Generic.IEnumerable%601> koleksiyon Ara LINQ sağlayıcısı veya API gibi kullanmadan, doğrudan [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) veya [LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md). LINQ gibi herhangi bir sıralanabilir koleksiyonu sorgulamak için kullanabileceğiniz <xref:System.Collections.Generic.List%601>, <xref:System.Array>, veya <xref:System.Collections.Generic.Dictionary%602>. Koleksiyon veya bir .NET Framework API tarafından döndürülen kullanıcı tanımlı olabilir.  
  
 Temel bir anlamda, LINQ to Objects'in koleksiyonları yeni bir yaklaşımı temsil eder. Karmaşık yazmanız gerekirdi eski biçimde `For Each` belirtilen bir koleksiyondaki verileri alma döngüleri. LINQ yaklaşımda almak istediğiniz açıklayan bildirim temelli bir kod yazın.  
  
 Ayrıca, LINQ sorguları üç ana avantajları geleneksel teklif `For Each` döngüleri:  
  
1. Özellikle birden çok koşulu filtrelerken daha kısa süren ve okunabilir, değildirler.  
  
2. Güçlü filtreleme, sıralama ve Gruplama yetenekler uygulama kodu en az sağlarlar.  
  
3. Bunlar çok az kayıpla veya hiç değişiklik diğer veri kaynaklarıyla için unity'nin.  
  
 Genel olarak, daha karmaşık fark geleneksel yineleme teknikleri yerine LINQ kullanarak daha fazla avantaj, verilerle ilgili gerçekleştirmek istediğiniz işlem.  
  
 Bu bölümün amacı, select bazı örnekler LINQ yaklaşımıyla göstermektir. Testin daha kapsamlı olmasını sağlamak için tasarlanmamıştır.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [LINQ ve dizeler (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 LINQ Sorgu dizeleri ve dizelerden oluşan koleksiyonları dönüştürmek için nasıl kullanılabileceğini açıklar. Ayrıca, bu ilkeyi gösteren konulara bağlantılar içerir.  
  
 [LINQ ve yansıma (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-reflection.md)  
 LINQ yansıma nasıl kullandığını gösteren bir örnek bağlar.  
  
 [LINQ ve dosya dizinleri (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)  
 Dosya sistemleri ile etkileşimde bulunmak için LINQ'ın nasıl kullanılabileceğini açıklar. Ayrıca bu kavramları göstermeye konulara bağlantılar içerir.  
  
 [Nasıl yapılır: (Visual Basic) LINQ ile ArrayList sorgulama](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)  
 C# ArrayList sorgulama işlemi gösterilmektedir.  
  
 [Nasıl yapılır: LINQ sorguları (Visual Basic) için özel yöntemler](../../../../visual-basic/programming-guide/concepts/linq/how-to-add-custom-methods-for-linq-queries.md)  
 İçin genişletme yöntemleri ekleyerek LINQ sorguları için kullanabileceğiniz yöntemler kümesi genişletmek açıklanmaktadır <xref:System.Collections.Generic.IEnumerable%601> arabirimi.  
  
 [Dil ile tümleşik sorgu (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 LINQ açıklamak ve sorguları gerçekleştirme kod örnekleri sağlayan konulara bağlantılar sağlar.
