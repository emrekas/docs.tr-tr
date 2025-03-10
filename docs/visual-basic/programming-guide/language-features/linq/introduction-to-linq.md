---
title: Visual Basic'de LINQ'e Giriş
ms.date: 08/28/2018
helpviewer_keywords:
- queries [LINQ in Visual Basic], about LINQ in Visual Basic queries
- query execution [LINQ in Visual Basic]
- range variables [Visual Basic]
- LINQ [Visual Basic]
- LINQ [Visual Basic], about LINQ in Visual Basic
- query expressions [LINQ in Visual Basic]
- LINQ
- deferred execution
- iteration variables [Visual Basic]
ms.assetid: 3047d86e-0d49-40e2-928b-dc02e46c7984
ms.openlocfilehash: c9a8149ecf4f2a1c76ba00b0f80bc703114e11ca
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69660780"
---
# <a name="introduction-to-linq-in-visual-basic"></a>Visual Basic'de LINQ'e Giriş
Dil ile tümleşik sorgu (LINQ) Visual Basic 'e sorgu özellikleri ekler ve tüm veri türleriyle çalışırken basit ve güçlü yetenekler sağlar. İşlenecek bir veritabanına sorgu göndermek veya arama yaptığınız her veri türü için farklı sorgu söz dizimiyle çalışmak yerine, LINQ sorguları Visual Basic dilinin bir parçası olarak tanıtır. Veri türünden bağımsız olarak Birleşik bir sözdizimi kullanır.  
  
 LINQ, SQL Server veritabanından, XML, bellek içi dizilerden ve koleksiyonlardan, ADO.NET veri kümelerinde veya LINQ destekleyen başka herhangi bir uzak ya da yerel veri kaynağından veri sorgulamanızı sağlar. Tüm bunu ortak Visual Basic dil öğeleriyle yapabilirsiniz. Sorgularınızı Visual Basic dilde yazıldığı için, sorgu sonuçlarınız kesin türü belirtilmiş nesneler olarak döndürülür. Bu nesneler IntelliSense 'i destekler, bu da çalışma zamanı yerine, derleme zamanında daha hızlı kod yazmanızı ve sorgularınızdaki hataları yakalamanıza olanak sağlar. LINQ sorguları, sonuçları iyileştirmek için ek sorguların kaynağı olarak kullanılabilir. Kullanıcıların sorgu sonuçlarınızı kolayca görüntülemesi ve değiştirebilmeleri için denetimlere de bağlanabilir.  
  
 Örneğin, aşağıdaki kod örneğinde, bir koleksiyondaki müşterilerin listesini döndüren ve konumlarına göre gruplayan bir LINQ sorgusu gösterilmektedir.  
  
 [!code-vb[VbVbalrIntroToLINQ#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#1)]  
  
## <a name="running-the-examples"></a>Örnekleri çalıştırma  
 Giriş bölümündeki örnekleri ve [LINQ sorgu bölümünün yapısını](#structure-of-a-linq-query) çalıştırmak için, müşteri ve siparişlerin listesini döndüren aşağıdaki kodu ekleyin.  
  
 [!code-vb[VbVbalrIntroToLINQ#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#31)]  
  
## <a name="linq-providers"></a>LINQ sağlayıcıları  
 Bir *LINQ sağlayıcısı* Visual Basic LINQ sorgularınızı sorgulanan veri kaynağına eşler. Bir LINQ sorgusu yazdığınızda, sağlayıcı bu sorguyu alır ve veri kaynağının yürütebilecek komutlara dönüştürür. Sağlayıcı ayrıca verileri kaynaktan sorgu sonucu oluşturan nesnelere dönüştürür. Son olarak, veri kaynağına güncelleştirme gönderdiğinizde nesneleri verilere dönüştürür.  
  
 Visual Basic aşağıdaki LINQ sağlayıcılarını içerir.  
  
|Sağlayıcı|Açıklama|  
|---|---|  
|Nesnelere LINQ|LINQ to Objects sağlayıcı, bellek içi koleksiyonları ve dizileri sorgulamanızı sağlar. Bir nesne <xref:System.Collections.IEnumerable> ya <xref:System.Collections.Generic.IEnumerable%601> da arabirimini destekliyorsa, LINQ to Objects sağlayıcı sorgulamanızı sağlar.<br /><br /> Tüm Visual Basic projeleri için varsayılan olarak içeri aktarılan <xref:System.Linq> ad alanını içeri aktararak LINQ to Objects sağlayıcıyı etkinleştirebilirsiniz.<br /><br /> LINQ to Objects sağlayıcısı hakkında daha fazla bilgi için bkz. [LINQ to Objects](../../concepts/linq/linq-to-objects.md).|  
|LINQ - SQL|LINQ to SQL sağlayıcı, verileri bir SQL Server veritabanında sorgulamanıza ve değiştirmenize olanak sağlar. Bu, bir uygulamanın nesne modelini bir veritabanındaki tablolar ve nesneler için eşlemeyi kolaylaştırır.<br /><br /> Visual Basic, Nesne İlişkisel Tasarımcısı (O/R Tasarımcısı) dahil LINQ to SQL birlikte çalışmayı kolaylaştırır. Bu tasarımcı, bir veritabanındaki nesnelerle eşleşen bir uygulamada nesne modeli oluşturmak için kullanılır. O/R Tasarımcısı Ayrıca, saklı yordamları ve işlevleri <xref:System.Data.Linq.DataContext> , veritabanı ile iletişimi yöneten ve iyimser eşzamanlılık denetimleri için durum depolayan nesne ile eşlemek için de işlevsellik sağlar.<br /><br /> LINQ to SQL sağlayıcısı hakkında daha fazla bilgi için bkz. [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md). Nesne İlişkisel Tasarımcısı hakkında daha fazla bilgi için bkz. [Visual Studio 'da LINQ to SQL araçları](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).|  
|LINQ - XML|LINQ to XML sağlayıcı, XML 'yi sorgulamanıza ve değiştirmenize olanak sağlar. Bellek içi XML 'yi değiştirebilir veya XML dosyasından XML yükleyebilir ve bir dosyaya kaydedebilirsiniz.<br /><br /> Ayrıca, LINQ to XML sağlayıcı, doğrudan Visual Basic kodunuzda XML yazmanızı sağlayan XML sabit değerleri ve XML eksen özelliklerini etkinleştirir. Daha fazla bilgi için bkz. [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).|  
|LINQ - DataSet|LINQ to DataSet sağlayıcı, bir ADO.NET veri kümesindeki verileri sorgulamanıza ve güncelleştirmenize olanak sağlar. Veri kümenizdeki verileri sorgulama, toplama ve güncelleştirme özelliklerini basitleştirmek ve genişletmek için veri kümelerini kullanan uygulamalara LINQ 'ın gücünü ekleyebilirsiniz.<br /><br /> Daha fazla bilgi için [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).|  
  
## <a name="structure-of-a-linq-query"></a>LINQ sorgusunun yapısı  
 Genellikle *sorgu ifadesi*olarak ANıLAN bir LINQ sorgusu, sorgu için veri kaynaklarını ve yineleme değişkenlerini tanımlayan bir sorgu yan tümceleri birleşimini içerir. Sorgu ifadesi Ayrıca sıralama, filtreleme, gruplama ve katılma veya kaynak verilere uygulanacak hesaplamalar için yönergeleri de içerebilir. Sorgu ifadesi söz dizimi SQL; sözdizimine benzer Bu nedenle, bilinen sözdiziminin büyük bir bölümünü bulabilirsiniz.  
  
 Sorgu ifadesi bir `From` yan tümcesiyle başlar. Bu yan tümce, bir sorgunun kaynak verilerini ve kaynak verilerin her öğesine tek tek başvurmak için kullanılan değişkenleri tanımlar. Bu değişkenler, *Aralık değişkenleri* veya *yineleme değişkenleri*olarak adlandırılır. Yan tümcesi, WHERE `From` yan tümcesinin isteğe bağlı olduğu `Aggregate` sorgular dışında bir sorgu için gereklidir. `From` Sorgunun kapsamı ve kaynağı `From` veya `Aggregate` yan tümcelerinde tanımlandıktan sonra sorgu yan tümcelerinin herhangi bir birleşimini dahil edebilirsiniz ve sorguyu daraltın. Sorgu yan tümceleri hakkında daha fazla bilgi için bu konunun ilerleyen kısımlarında Visual Basic LINQ sorgu Işleçleri ' ne bakın. Örneğin, aşağıdaki sorgu müşteri verilerinin bir kaynak koleksiyonunu `customers` değişken olarak ve adlı `cust`bir yineleme değişkenini tanımlar.  
  
 [!code-vb[VbVbalrIntroToLINQ#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#2)]  
  
 Bu örnek kendi kendine geçerli bir sorgudur; Ancak, sonucu iyileştirmek için daha fazla sorgu yan tümcesi eklediğinizde sorgu daha güçlü hale gelir. Örneğin, sonucu bir veya daha fazla `Where` değere göre filtrelemek için bir yan tümce ekleyebilirsiniz. Sorgu ifadeleri tek satırlık bir koddur; sorgu sonuna yalnızca ek sorgu yan tümceleri ekleyebilirsiniz. Alt çizgi (\_) satır devamlılığı karakterini kullanarak okunabilirliği geliştirmek için birden çok satırlık metin üzerinde bir sorgu kesebilirsiniz. Aşağıdaki kod örneğinde bir `Where` yan tümce içeren bir sorgu örneği gösterilmektedir.  
  
 [!code-vb[VbVbalrIntroToLINQ#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#3)]  
  
 Başka bir güçlü sorgu yan tümcesi `Select` , veri kaynağından yalnızca seçili alanları döndürmenizi sağlayan yan tümcelerdir. LINQ sorguları, kesin olarak belirlenmiş nesneler için sıralanabilir koleksiyonlar döndürüyor. Bir sorgu, anonim türlerin veya adlandırılmış türlerin bir koleksiyonunu döndürebilir. `Select` Yan tümcesini kullanarak veri kaynağından yalnızca tek bir alan döndürebilirsiniz. Bunu yaptığınızda, döndürülen koleksiyonun türü bu tek alanın türüdür. Ayrıca, `Select` yan tümcesini kullanarak veri kaynağından birden çok alan döndürebilirsiniz. Bunu yaptığınızda, döndürülen koleksiyonun türü yeni bir anonim türdür. Sorgu tarafından döndürülen alanları belirtilen adlandırılmış türdeki alanlara de eşleştirebilirsiniz. Aşağıdaki kod örneği, veri kaynağından seçilen alanlardan verilerle doldurulmuş üyelere sahip anonim türlerin koleksiyonunu döndüren bir sorgu ifadesini gösterir.  
  
 [!code-vb[VbVbalrIntroToLINQ#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#4)]  
  
 LINQ sorguları, birden fazla veri kaynağını birleştirmek ve tek bir sonuç döndürmek için de kullanılabilir. Bu, bir veya daha fazla `From` yan tümce veya `Join` ya `Group Join` da sorgu yan tümceleri kullanılarak gerçekleştirilebilir. Aşağıdaki kod örneği, müşteri ve sipariş verilerini birleştiren ve müşteri ve sipariş verilerini içeren anonim türlerin koleksiyonunu döndüren bir sorgu ifadesini gösterir.  
  
 [!code-vb[VbVbalrIntroToLINQ#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#5)]  
  
 Bir müşteri nesneleri koleksiyonu `Group Join` içeren hiyerarşik bir sorgu sonucu oluşturmak için yan tümcesini kullanabilirsiniz. Her müşteri nesnesi ilgili müşterinin tüm siparişlerinin koleksiyonunu içeren bir özelliğe sahiptir. Aşağıdaki kod örneği, müşteri ve sipariş verilerini hiyerarşik sonuç olarak birleştiren ve anonim türlerin koleksiyonunu döndüren bir sorgu ifadesini gösterir. Sorgu, müşteri için sipariş verilerinin bir koleksiyonunu `CustomerOrders` içeren bir özellik içeren bir tür döndürür. Ayrıca, bu müşterinin `OrderTotal` tüm siparişlerinin toplam toplamlarını içeren bir özellik içerir. (Bu sorgu bir LEFT OUTER JOIN ile eşdeğerdir.)  
  
 [!code-vb[VbVbalrIntroToLINQ#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#6)]  
  
 Güçlü sorgu ifadeleri oluşturmak için kullanabileceğiniz birkaç ek LINQ sorgu işleci vardır. Bu konunun sonraki bölümünde, bir sorgu ifadesine dahil etmek için kullanabileceğiniz çeşitli sorgu tümceleri ele alınmaktadır. Visual Basic sorgu yan tümceleri hakkında ayrıntılar için bkz. [sorgular](../../../../visual-basic/language-reference/queries/index.md).  
  
## <a name="visual-basic-linq-query-operators"></a>Visual Basic LINQ sorgu işleçleri  

<xref:System.Linq> Ad alanındaki sınıflar ve LINQ sorgularını destekleyen diğer ad alanları, uygulamanızın gereksinimlerine göre sorguları oluşturmak ve iyileştirmek için çağırabileceğiniz yöntemleri içerir. Visual Basic aşağıdaki ortak sorgu yan tümceleri için anahtar sözcükler içerir. Visual Basic sorgu yan tümceleri hakkında ayrıntılar için bkz. [sorgular](../../../language-reference/queries/index.md).

### <a name="from-clause"></a>From yan tümcesi

Bir sorgu başlatmak için bir `Aggregate` [ `From` yan tümce](../../../../visual-basic/language-reference/queries/from-clause.md) veya yan tümce gereklidir. Bir `From` yan tümce, bir sorgu için bir kaynak koleksiyonu ve bir yineleme değişkeni belirtir. Örneğin:

 [!code-vb[VbVbalrIntroToLINQ#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#7)]

### <a name="select-clause"></a>Select tümcesi

İsteğe bağlı. [ Bir`Select` yan tümce](../../../../visual-basic/language-reference/queries/select-clause.md) bir sorgu için yineleme değişkenleri kümesi bildirir. Örneğin:

 [!code-vb[VbVbalrIntroToLINQ#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#8)]

Bir `Select` yan tümce belirtilmemişse, sorgunun yineleme değişkenleri `From` veya `Aggregate` yan tümcesi tarafından belirtilen yineleme değişkenlerinden oluşur.

### <a name="where-clause"></a>Where yan tümcesi

İsteğe bağlı. [ Bir`Where` yan tümce](../../../../visual-basic/language-reference/queries/where-clause.md) bir sorgu için filtreleme koşulunu belirtir. Örneğin:

 [!code-vb[VbVbalrIntroToLINQ#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#9)]

### <a name="order-by-clause"></a>Order by tümcesi]

| Seçim. [ Bir`Order By` yan tümce](../../../../visual-basic/language-reference/queries/order-by-clause.md) bir sorgudaki sütunlar için sıralama düzenini belirtir. Örneğin:

 [!code-vb[VbVbalrIntroToLINQ#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#10)]

### <a name="join-clause"></a>Join tümcesi

İsteğe bağlı. Yan tümce iki koleksiyonu tek bir koleksiyon halinde birleştirir. [ `Join` ](../../../../visual-basic/language-reference/queries/join-clause.md) Örneğin:

 [!code-vb[VbVbalrIntroToLINQ#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#11)]

### <a name="group-by-clause"></a>Group By tümcesi

İsteğe bağlı. [ Bir`Group By` yan tümce](../../../../visual-basic/language-reference/queries/group-by-clause.md) bir sorgu sonucunun öğelerini gruplandırır. Her gruba toplama işlevleri uygulamak için kullanılabilir. Örneğin:

 [!code-vb[VbVbalrIntroToLINQ#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#12)]

### <a name="group-join-clause"></a>Group Join tümcesi

İsteğe bağlı. Yan tümce iki koleksiyonu tek bir hiyerarşik koleksiyonda birleştirir. [ `Group Join` ](../../../../visual-basic/language-reference/queries/group-join-clause.md) Örneğin:

 [!code-vb[VbVbalrIntroToLINQ#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#13)]

### <a name="aggregate-clause"></a>Aggregate tümcesi

Bir sorgu başlatmak için bir `From` [ `Aggregate` yan tümce](../../../../visual-basic/language-reference/queries/aggregate-clause.md) veya yan tümce gereklidir. `Aggregate` Yan tümce bir koleksiyona bir veya daha fazla toplama işlevi uygular. Örneğin, aşağıdaki örnekte olduğu gibi, `Aggregate` bir sorgu tarafından döndürülen tüm öğelerin toplamını hesaplamak için yan tümcesini kullanabilirsiniz.

 [!code-vb[VbVbalrIntroToLINQ#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#14)]

Bir sorguyu değiştirmek için `Aggregate` yan tümcesini de kullanabilirsiniz. Örneğin, `Aggregate` yan tümcesini kullanarak ilgili sorgu koleksiyonunda bir hesaplama yapabilirsiniz. Örneğin:

 [!code-vb[VbVbalrIntroToLINQ#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#15)]

### <a name="let-clause"></a>Let tümcesi

İsteğe bağlı. [ Bir`Let` yan tümce](../../../../visual-basic/language-reference/queries/let-clause.md) bir değeri hesaplar ve bunu sorgudaki yeni bir değişkene atar. Örneğin:

 [!code-vb[VbVbalrIntroToLINQ#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#16)]

### <a name="distinct-clause"></a>Distinct tümcesi

İsteğe bağlı. Bir `Distinct` yan tümce, sorgu sonuçlarında yinelenen değerleri ortadan kaldırmak için geçerli yineleme değişkeninin değerlerini kısıtlar. Örneğin:

 [!code-vb[VbVbalrIntroToLINQ#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#17)]

### <a name="skip-clause"></a>Skip tümcesi

İsteğe bağlı. Yan tümce, koleksiyonda belirtilen sayıda öğeyi atlar ve kalan öğeleri döndürür. [ `Skip` ](../../../../visual-basic/language-reference/queries/skip-clause.md) Örneğin:

 [!code-vb[VbVbalrIntroToLINQ#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#18)]

### <a name="skip-while-clause"></a>Skip While tümcesi

İsteğe bağlı. `true` [ Bir`Skip While` yan tümce](../../../../visual-basic/language-reference/queries/skip-while-clause.md) , belirtilen koşul olduğu sürece bir koleksiyondaki öğeleri atlar ve kalan öğeleri döndürür. Örneğin:

 [!code-vb[VbVbalrIntroToLINQ#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#19)]

### <a name="take-clause"></a>Take tümcesi

İsteğe bağlı. [ Bir`Take` yan tümce](../../../../visual-basic/language-reference/queries/take-clause.md) , bir koleksiyonun başından itibaren belirtilen sayıda bitişik öğeyi döndürür. Örneğin:

 [!code-vb[VbVbalrIntroToLINQ#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#20)]

### <a name="take-while-clause"></a>Take While tümcesi

İsteğe bağlı. `true` [ Bir`Take While` yan tümce](../../../../visual-basic/language-reference/queries/take-while-clause.md) , belirtilen koşul olduğu ve kalan öğeleri atlayan sürece bir koleksiyondaki öğeleri içerir. Örneğin:

 [!code-vb[VbVbalrIntroToLINQ#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#21)]
  
## <a name="use-additional-linq-query-features"></a>Ek LINQ sorgu özellikleri kullan  
  
LINQ tarafından sunulan sıralanabilir ve sorgulanabilir türlerin üyelerini çağırarak ek LINQ sorgu özellikleri kullanabilirsiniz. Sorgu ifadesinin sonucu üzerinde belirli bir sorgu işlecini çağırarak bu ek özellikleri kullanabilirsiniz. Örneğin, aşağıdaki örnek, iki sorgunun sonuçlarını <xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType> tek bir sorgu sonucuyla birleştirmek için yöntemini kullanır. Sorgu sonucunu genel <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> liste olarak döndürmek için yöntemini kullanır.
  
 [!code-vb[VbVbalrIntroToLINQ#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#22)]  
  
 Ek LINQ özellikleri hakkında ayrıntılı bilgi için bkz. [Standart sorgu Işleçlerine genel bakış](../../concepts/linq/standard-query-operators-overview.md).  
  
## <a name="connect-to-a-database-by-using-linq-to-sql"></a>LINQ to SQL kullanarak bir veritabanına bağlanma  
 Visual Basic, LINQ to SQL bir dosya kullanarak erişmek istediğiniz tablolar, görünümler ve saklı yordamlar gibi SQL Server veritabanı nesnelerini belirlersiniz. Bir LINQ to SQL dosyası. dbml uzantısına sahiptir.  
  
 SQL Server veritabanına geçerli bir bağlantınız olduğunda projenize **LINQ to SQL sınıfları** öğe şablonu ekleyebilirsiniz. Bu işlem Nesne İlişkisel Tasarımcısı (O/R Designer) ' u görüntüler. O/R Tasarımcısı, kodunuzda erişmek istediğiniz öğeleri tasarımcı yüzeyine **Sunucu Gezgini**/**veritabanı Gezgini** sürüklemenize olanak sağlar. LINQ to SQL dosyası projenize bir <xref:System.Data.Linq.DataContext> nesne ekler. Bu nesne, erişmek istediğiniz tablo ve görünümlere yönelik özellikler ve koleksiyonlar ve çağırmak istediğiniz saklı yordamlar için yöntemler içerir. Değişikliklerinizi LINQ to SQL (. dbml) dosyasına kaydettikten sonra, O nesnelere O nesneleri, O/R Tasarımcısı tarafından tanımlanan <xref:System.Data.Linq.DataContext> nesneye başvurarak, kodunuzda erişebilirsiniz. Projenizin <xref:System.Data.Linq.DataContext> nesnesi, LINQ to SQL dosyanızın adına göre adlandırılır. Örneğin, Northwind. dbml adlı bir LINQ to SQL dosyası adlı <xref:System.Data.Linq.DataContext> `NorthwindDataContext`bir nesne oluşturur.  
  
 Adım adım yönergelere sahip örnekler için bkz [. nasıl yapılır: Bir veritabanını](how-to-query-a-database-by-using-linq.md) sorgulama ve [nasıl yapılır: Saklı yordam](how-to-call-a-stored-procedure-by-using-linq.md)çağrısı yapın.  
  
## <a name="visual-basic-features-that-support-linq"></a>LINQ 'i destekleyen Visual Basic özellikleri  
 Visual Basic, LINQ Simple kullanımını yapan ve LINQ sorguları gerçekleştirmek için yazmanız gereken kod miktarını azaltan diğer önemli özellikleri içerir. Bunlar aşağıdakileri içerir:  
  
- Bir sorgu sonucuna dayalı yeni bir tür oluşturmanıza olanak sağlayan **anonim türler**.  
  
- Türü belirtmeyi ertelemenizi sağlayan ve derleyicinin türü sorgu sonucuna göre çıkarmasına izin veren **örtük olarak yazılan değişkenler**.  
  
- **Uzantı yöntemleri**, türün kendisini değiştirmeden kendi yöntemleriniz ile var olan bir türü genişletmenizi sağlar.  
  
 Ayrıntılar için bkz. [LINQ 'ı destekleyen Visual Basic Özellikler](../../concepts/linq/features-that-support-linq.md).  
  
## <a name="deferred-and-immediate-query-execution"></a>Ertelenmiş ve acil sorgu yürütme

 Sorgu yürütme, sorgu oluşturmaktan farklıdır. Bir sorgu oluşturulduktan sonra, yürütülmesi ayrı bir mekanizma tarafından tetiklenir. Sorgu, tanımlanır (*anında yürütme*), veya tanım depolanabilir ve sorgu daha sonra yürütülebilir (*ertelenmiş yürütme*).  
  
 Varsayılan olarak, bir sorgu oluşturduğunuzda sorgu hemen yürütülmez. Bunun yerine sorgu tanımı, sorgu sonucuna başvurmak için kullanılan değişkende depolanır. Sorgu sonuç değişkenine bir `For…Next` döngüde olduğu gibi, daha sonra kod içinde erişildiğinde sorgu yürütülür. Bu işlem *ertelenmiş yürütme*olarak adlandırılır.  
  
 Sorgular, tanımlandıklarında da çalıştırılabilir, bu da *anında yürütme*olarak adlandırılır. Sorgu sonucunun tek tek öğelerine erişmesi gereken bir yöntemi uygulayarak hemen yürütmeyi tetikleyebilirsiniz. Bu,,,, veya `Count` `Average` `Min` `Sum` gibi`Max`bir toplama işlevinin dahil edilmesi sonucu olabilir. Toplama işlevleri hakkında daha fazla bilgi için bkz. [Aggregate yan tümcesi](../../../language-reference/queries/aggregate-clause.md).  
  
 `ToList` Ya`ToArray` da yöntemlerinin kullanılması, hemen yürütmeye zorlar. Bu, sorguyu hemen çalıştırmak ve sonuçları önbelleğe almak istediğinizde yararlı olabilir. Bu yöntemler hakkında daha fazla bilgi için bkz. [veri türlerini dönüştürme](../../concepts/linq/converting-data-types.md).  
  
 Sorgu yürütme hakkında daha fazla bilgi için, bkz. [Ilk LINQ sorgunuzu yazma](../../concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="xml-in-visual-basic"></a>Visual Basic'de XML  
 Visual Basic ' deki XML özellikleri, kodunuzda XML oluşturma, erişme, sorgulama ve değişiklik yapma olanağı sağlayan XML değişmez değerleri ve XML eksen özelliklerini içerir. XML değişmez değerleri doğrudan kodunuzda XML yazmanızı sağlar. Visual Basic Derleyicisi, XML 'yi birinci sınıf veri nesnesi olarak değerlendirir.  
  
 Aşağıdaki kod örneği, bir XML öğesinin nasıl oluşturulduğunu, alt öğelerine ve özniteliklerine erişmeyi ve LINQ kullanarak öğenin içeriğini sorgulamayı gösterir.  
  
 [!code-vb[VbXmlSamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples3.vb#8)]  
  
 Daha fazla bilgi için bkz. [XML](../xml/index.md).  
  
## <a name="related-resources"></a>İlgili kaynaklar  
  
|Konu|Açıklama|  
|---|---|  
|[XML](../../language-features/xml/index.md)|Visual Basic ' deki ve Visual Basic kodunuzda birinci sınıf veri nesneleri olarak XML bulundurmasını sağlayan XML özelliklerini açıklar.|  
|[Sorgular](../../../language-reference/queries/index.md)|Visual Basic ' de kullanılabilen sorgu yan tümceleri hakkında başvuru bilgileri sağlar.|  
|[LINQ (dil ile tümleşik sorgu)](../../concepts/linq/index.md)|Genel bilgileri, programlama kılavuzunu ve LINQ için örnekleri içerir.|  
|[LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)|Genel bilgileri, programlama kılavuzunu ve LINQ to SQL yönelik örnekleri içerir.|  
|[LINQ to Objects](../../concepts/linq/linq-to-objects.md)|Genel bilgileri, programlama kılavuzunu ve LINQ to Objects yönelik örnekleri içerir.|  
|[LINQ to ADO.NET (Portal Sayfası)](../../concepts/linq/linq-to-adonet-portal-page.md)|Genel bilgiler, Programlama Kılavuzu ve LINQ to ADO.NET için örneklere bağlantılar içerir.|  
|[LINQ to XML](../../concepts/linq/linq-to-xml.md)|Genel bilgileri, programlama kılavuzunu ve LINQ to XML yönelik örnekleri içerir.|  
  
## <a name="how-to-and-walkthrough-topics"></a>Nasıl yapılır ve İzlenecek yol konuları
 [Nasıl yapılır: Veritabanını sorgulama](how-to-query-a-database-by-using-linq.md)  
  
 [Nasıl yapılır: Saklı yordam çağırma](how-to-call-a-stored-procedure-by-using-linq.md)  
  
 [Nasıl yapılır: Veritabanındaki verileri değiştirme](how-to-modify-data-in-a-database-by-using-linq.md)  
  
 [Nasıl yapılır: Birleştirme ile verileri birleştirme](how-to-combine-data-with-linq-by-using-joins.md)  
  
 [Nasıl yapılır: Sorgu sonuçlarını Sırala](how-to-sort-query-results-by-using-linq.md)  
  
 [Nasıl yapılır: Sorgu sonuçlarını filtrele](how-to-filter-query-results-by-using-linq.md)  
  
 [Nasıl yapılır: Count, Sum veya Average Data](how-to-count-sum-or-average-data-by-using-linq.md)  
  
 [Nasıl yapılır: Bir sorgu sonucunda en küçük veya en büyük değeri bulma](how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)  
  
 [Nasıl yapılır: Güncelleştirme, ekleme ve silme işlemleri gerçekleştirmek için saklı yordamlar atama (O/R Tasarımcısı)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
  
## <a name="featured-book-chapters"></a>Öne çıkan kitap bölümleri  
 [Bölüm 17: LINQ](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652502(v=orm.10)) [programlama Visual Basic 2008](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652504(v=orm.10))  
  
## <a name="see-also"></a>Ayrıca bkz.

- [LINQ (dil ile tümleşik sorgu)](../../concepts/linq/index.md)
- [Visual Basic LINQ to XML genel bakış](../../language-features/xml/overview-of-linq-to-xml.md)
- [LINQ to DataSet Genel Bakış](../../../../framework/data/adonet/linq-to-dataset-overview.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Visual Studio'daki LINQ to SQL Araçları](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)
- [DataContext Metotları (O/R Tasarımcısı)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
