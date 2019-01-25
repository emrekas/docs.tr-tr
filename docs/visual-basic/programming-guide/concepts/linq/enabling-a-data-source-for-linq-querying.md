---
title: Veri kaynağı için LINQ Querying2 etkinleştirme
ms.date: 07/20/2015
ms.assetid: c412f0cf-ff0e-4993-ab3d-1b49e23f00f8
ms.openlocfilehash: f705db90f4838479621117bd9303f5a374d33d4d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676503"
---
# <a name="enabling-a-data-source-for-linq-querying"></a>LINQ Sorgusu için Veri Kaynağı Etkinleştirme

Genişletmenin çeşitli yolları vardır [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] sorgulanmasını herhangi bir veri kaynağı etkinleştirmek için [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] deseni. Veri kaynağı örneğin bir veri yapısı, Web hizmeti, dosya sistemi veya veritabanı olabilir. [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Kolaylaştırır istemcilerin bir veri kaynağı için sorgu [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] sorgulamanın etkin olduğu, sözdizimi ve sorgu düzeni değişmediği. Yöntemler [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Genişletilebilir bu veri kaynakları şunları içerir:

-   Uygulama <xref:System.Collections.Generic.IEnumerable%601> etkinleştirmek için bu türden arabiriminde [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] nesneleri sorgulamasını için.

-   Standart sorgu işleci yöntemleri gibi oluşturma <xref:System.Linq.Enumerable.Where%2A> ve <xref:System.Linq.Enumerable.Select%2A> özel etkinleştirmek için bir türü genişletmek [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] sorgulamasını.

-   Uygulayan veri kaynağınız için bir sağlayıcı oluşturma <xref:System.Linq.IQueryable%601> arabirimi. Bu arabirimi uygulayan sağlayıcı alır [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] özel bir şekilde, örneğin uzaktan yürütebilirsiniz ifade ağaçları biçiminde sorgular.

-   Yararlanır, varolan bir veri kaynağınız için bir sağlayıcı oluşturma [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] teknoloji. Böyle bir sağlayıcı, yalnızca sorgulamayı etkinleştirmez, aynı zamanda kullanıcı tanımlı türlere yönelik işlemleri ve eşleştirmeyi de ekler, güncelleştirir ve siler.

Bu konuda, bu seçenekler açıklanmaktadır.

## <a name="how-to-enable-linq-querying-of-your-data-source"></a>Veri Kaynağınızın LINQ Sorgulamasını Etkinleştirme

### <a name="in-memory-data"></a>Bellek İçi Veriler
 İki yolla etkinleştirebilirsiniz [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] bellek içi verileri sorgulama. Veriler uygulayan bir tür ise <xref:System.Collections.Generic.IEnumerable%601>, kullanarak verileri sorgulayabilir [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] nesneleri. Uygulanarak türünüzün numaralandırmasını etkinleştirmek için anlamlı yapmaz, <xref:System.Collections.Generic.IEnumerable%601> arabirimi tanımlayabilirsiniz [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] standart sorgu işleci yöntemleri bu türde veya oluşturma [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] türü genişleten standart sorgu işleci yöntemleri. Standart sorgu işleçlerinin özel uygulamaları, sonuçları döndürmek için ertelenmiş yürütme kullanmalıdır.

### <a name="remote-data"></a>Uzak Veriler
 Etkinleştirmek için en iyi seçenek [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] uygulamak için olan bir uzak veri kaynağının sorgulama <xref:System.Linq.IQueryable%601> arabirimi. Ancak bu sağlayıcı gibi genişletilmesinden farklıdır [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] bir veri kaynağı için. Varolan genişletmek için sağlayıcı modeli yoktur [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] teknolojileri gibi [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], veri kaynağının diğer türleri, Visual Studio 2008'de kullanılabilir.

## <a name="iqueryable-linq-providers"></a>IQueryable LINQ Sağlayıcıları
 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Uygulama sağlayıcıları <xref:System.Linq.IQueryable%601> yaygın olarak farklı. Bu bölümde, farklı karmaşıklık düzeyleri açıklanmaktadır.

 Daha az karmaşık `IQueryable` sağlayıcısı, tek bir Web hizmeti yöntemi ile arabirim. Bu türden bir sağlayıcı, işlediği sorgularda belirli bilgiler beklediği için çok özeldir. Muhtemelen tek bir sonuç türü ortaya çıkaran kapalı bir tür sistemi vardır. Örneğin kullanarak sorgu yürütmesini çoğu yerel olarak gerçekleşir <xref:System.Linq.Enumerable> standart sorgu işleçlerinin uygulamaları. Daha az karmaşık olan bir sağlayıcı, sorguyu temsil eden ifade ağacında yalnızca bir yöntem çağrısı ifadesi inceleyebilir ve kalan sorgu mantığının başka bir yerde işlenmesine izin verebilir.

 Bir `IQueryable` orta düzeyde karmaşıklığa sağlayıcısı kısmi ifade sorgusu diline sahip bir veri kaynağını hedefleyebilir. Bir Web hizmetini hedefliyorsa, Web hizmetinin birden fazla yöntemiyle arabirim oluşturabilir ve sorgunun sorduğu soruya göre bir çağrı yöntemi seçebilir. Orta düzeyde karmaşıklığa sahip bir sağlayıcının basit bir sağlayıcıya göre daha zengin bir tür sistemi vardır, ancak yine de sabit bir tür sistemidir. Örneğin, sağlayıcı ters çevrilebilen bire çok ilişkilerine sahip türleri kullanabilir, ancak kullanıcı tanımlı türler için eşleştirme teknolojisi sağlamaz.

 Karmaşık `IQueryable` sağlayıcısı gibi [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] sağlayıcısı çevirebilir [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] , SQL gibi ifade sorgusu diline sorgular. Karmaşık bir sağlayıcı, sorguda çok çeşitli soruları işleyebileceği için daha az karmaşık olan bir sağlayıcıya göre daha geneldir. Ayrıca, açık bir tür sistemine de sahiptir ve bu nedenle kullanıcı tanımlı türleri eşleştirmek için kapsamlı bir altyapı içermelidir. Karmaşık bir sağlayıcının geliştirilmesi için önemli ölçüde çaba gerekir.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Linq.IQueryable%601>
- <xref:System.Collections.Generic.IEnumerable%601>
- <xref:System.Linq.Enumerable>
- [Standart sorgu işleçlerine genel bakış (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [LINQ to Objects'in (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)