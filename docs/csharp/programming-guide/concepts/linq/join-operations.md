---
title: Birleştirme işlemleri (C#)
ms.date: 07/20/2015
ms.assetid: 5105e0da-1267-4c00-837a-f0e9602279b8
ms.openlocfilehash: d8753ef0563a665767204c1ebc0af4e4a23b4455
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54537952"
---
# <a name="join-operations-c"></a>Birleştirme işlemleri (C#)
A *birleştirme* iki veri kaynaklarının bir veri kaynağı nesneleri başka bir veri kaynağındaki ortak bir özniteliği paylaşan nesnelerle işbirliğidir.  
  
 Birleştirme, veri kaynakları birbirleriyle ilişkilerini doğrudan izlenemiyor hedef sorgularda önemli bir işlemdir. Bu, aşağıdakiler gibi modellenmiştir olmayan nesneler arasında bir bağıntı gelebilir nesne yönelimli programlama, geriye doğru tek yönlü bir ilişkinin yönü. Tek yönlü bir ilişkinin bir özellik türü şehri olan bir müşteri sınıf örneğidir ancak Şehir sınıfı müşteri nesnesi koleksiyonu bir özelliğe sahip değildir. Şehir nesnelerin bir listesini varsa ve tüm müşteriler, her şehirde bulmak istediğiniz bulmak için bir birleştirme işlemi'ni kullanabilirsiniz.  
  
 LINQ framework içinde sağlanan birleşim yöntemleri <xref:System.Linq.Enumerable.Join%2A> ve <xref:System.Linq.Enumerable.GroupJoin%2A>. Bu yöntemler equijoins ya da bunların anahtarların eşitlik bakımından göre iki veri kaynağı ile eşleşen birleştirmeler gerçekleştirin. (Transact-SQL destekler karşılaştırması için örneğin 'küçüktür' işleci 'equals' dışındaki operatörlere katılın.) İlişkisel veritabanı koşullarında <xref:System.Linq.Enumerable.Join%2A> uygulayan bir iç birleştirme, birleşim türü içinde yalnızca diğer veri kümesinde bir eşleşmeye sahip nesneler döndürülür. <xref:System.Linq.Enumerable.GroupJoin%2A> Yöntemi eşdeğeri yoktur doğrudan ilişkisel veritabanı bağlamında, ancak İç birleşimler sol dış birleştirmeler ve bir üst kümesi uygular. Diğer veri kaynağında ilişkili hiçbir öğe olsa bile bir sol dış birleşim ilk (soldaki) veri kaynağının her öğe döndüren bir birleştirme ' dir.  
  
 Aşağıdaki çizimde, iki ve öğeleri bir iç birleştirme veya bir sol dış birleşim dahil edilen bu kümeleri içinde kavramsal bir görünümü gösterir.  
  
 ![İç gösteren iki örtüşen daireler&#47;dış. ](../../../../csharp/programming-guide/concepts/linq/media/joincircles.png "JoinCircles")  
  
## <a name="methods"></a>Yöntemler  
  
|Yöntem adı|Açıklama|C# sorgu ifade sözdizimi|Daha fazla bilgi|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Birleştirme|Anahtar Seçici işlevlerine göre iki diziyi birleştirir ve değer çiftlerini ayıklar.|`join … in … on … equals …`|<xref:System.Linq.Enumerable.Join%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Join%2A?displayProperty=nameWithType>|  
|GroupJoin|İki sıranın anahtar Seçici işlevleri ve grupları her öğe için sonuçlar temelinde birleştirir.|`join … in … on … equals … into …`|<xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Linq>
- [Standart sorgu işleçlerine genel bakış (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Anonim Tipler](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
- [Birleşimler ve Çapraz Ürün Sorguları Düzenleme](../../../../framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)
- [join yan tümcesi](../../../../csharp/language-reference/keywords/join-clause.md)
- [Nasıl yapılır: Bileşik anahtarlar kullanarak birleştirme](../../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md)
- [Nasıl yapılır: Dosyalardan içerik (LINQ) katılın (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md)
- [Nasıl yapılır: Join tümcesinin sonuçlarını sıralama](../../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)
- [Nasıl yapılır: Özel birleştirme işlemleri gerçekleştirme](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md)
- [Nasıl yapılır: Gruplandırılmış birleştirmeler gerçekleştirme](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md)
- [Nasıl yapılır: İç birleştirmeler gerçekleştirme](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md)
- [Nasıl yapılır: Sol dış birleştirmeler gerçekleştirme](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md)
- [Nasıl yapılır: (LINQ) birden fazla kaynaktan nesne koleksiyonları doldurma (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)
