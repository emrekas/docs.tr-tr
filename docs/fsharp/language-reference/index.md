---
title: F# Dili Başvurusu
description: Bulma F# dili belirteçleri, kavramları, türleri, ifadeler ve derleyici tarafından desteklenen yapı konular bu başvuruyu dil özellik bilgileri.
ms.date: 05/16/2016
ms.openlocfilehash: b70264b44b0820993cd77cb6c4f95a1547783174
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57846642"
---
# <a name="f-language-reference"></a>F# Dili Başvurusu

Bu bölüm bir başvurudur F# dil, .NET hedefleyen bir çoklu paradigma programlama dili. F# Dil işlev, nesne yönelimli ve buyurgan programlama modellerini destekler.

## <a name="f-tokens"></a>F# Tokens

Tablolarda anahtar sözcükler, simgeler ve belirteçleri olarak kullanılan sabit değerleri sağlayan başvuru konuları aşağıdaki tabloda gösterilmektedir F#.

|Başlık|Açıklama|
|-----|-----------|
|[Klavye Başvurusu](keyword-reference.md)|Tüm hakkında daha fazla bilgi için bağlantılar içeren F# dil anahtar sözcükleri.|
|[Simge ve İşleç Başvurusu](symbol-and-operator-reference/index.md)|Simgeler ve işleçler kullanılan bir tablo içeriyor F# dili.|
|[Değişmez Değerler](literals.md)|Değişmez değerler için söz dizimini açıklar F# ve tür bilgilerini belirtmek nasıl F# değişmez.|

## <a name="f-language-concepts"></a>F#Dil kavramları

Dil kavramları açıklayan kullanılabilir başvuru konuları aşağıdaki tabloda gösterilmektedir.

|Başlık|Açıklama|
|-----|-----------|
|[İşlevler](functions/index.md)|Tüm programlama dillerinde program yürütmenin temel birimi işlevlerdir. Diğer dillerde olduğu gibi bir F# işlevi bir ada sahip, parametreleri ve sınav zamanı bağımsız değişkenleri olabilir ve bir gövdeye sahip. F#Ayrıca ifadelerde örtülü bir tanım kısmi yoluyla işlevlerin yeni işlevleri ve curried işlevleri oluşturmak üzere işlevlerin oluşturulması adlandırılmamış işlevleri'ni kullanarak değerleri olarak işlevler değerlendirmesini gibi fonksiyonel programlama yapılarını destekler işlev bağımsız değişkenleri uygulama.|
|[F# Türleri](fsharp-types.md)|Kullanılan türleri açıklayan F# ve nasıl F# türleri adlı ve açıklanmıştır.|
|[Tür Çıkarımı](type-inference.md)|Açıklayan nasıl F# derleyici değerleri, değişkenleri, parametreler ve dönüş değerleri türlerini algılar.|
|[Otomatik Genelleştirme](generics/automatic-generalization.md)|Genel yapılardan açıklar F#.|
|[Devralma](inheritance.md)|Nesne yönelimli programlama subtyping ya da "olan bir" ilişkileri modellemek için kullanılan bir devralma açıklar.|
|[Üyeler](members/index.md)|Üyelerini açıklar F# nesne türleri.|
|[Parametreler ve Bağımsız Değişkenler](Parameters-and-Arguments.md)|Parametreleri tanımlama ve bağımsız değişkenleri işlevleri, yöntemlere ve özelliklere geçirme için dil desteğini açıklar. Bu başvuruya göre geçirme hakkında bilgi içerir.|
|[İşleç Aşırı Yüklemesi](operator-overloading.md)|Aritmetik işleçler bir sınıf ya da kayıt türü ve genel düzeyde aşırı açıklar.|
|[Tür Değiştirme ve Dönüştürmeler](casting-and-conversions.md)|Tür dönüştürmelerinde desteğini açıklar F#.|
|[Erişim Denetimi](access-control.md)|Erişim denetimi açıklanmaktadır F#. Erişim denetimi, hangi istemcilerin vb. türleri, yöntemleri, İşlevler gibi belirli program öğelerini kullanabilir bildirme anlamına gelir.|
|[Desen Eşleştirme](pattern-matching.md)|Tamamında kullanılan giriş verileri dönüştürmeye ilişkin kurallardır desenleri açıklar F# bir desen ile karşılaştırma verileri ayıklamak için dil, verileri bileşenlerine ayırmak veya çeşitli şekillerde verilerden bilgi ayıklamak.|
|[Etkin Desenler](active-patterns.md)|Etkin desenler açıklanmaktadır. Etkin desenler, giriş verileri alt bölümlere adlandırılmış bölümler tanımlamanıza olanak sağlar. Etkin desenler, her bölüm için özelleştirilmiş bir şekilde veri ayırmak için kullanabilirsiniz.|
|[Onaylamalar](assertions.md)|Açıklar `assert` bir ifade test etmek için kullanabileceğiniz bir hata ayıklama özelliği olan ifade. Hata ayıklama modunda başarısızlık durumunda, bir sistem hatası iletişim kutusu bir onay oluşturur.|
|[Özel Durum İşleme](exception-handling/index.md)|Özel durum işleme desteği hakkında bilgi içeren F# dili.|
|[Öznitelikleri](attributes.md)|Bir programlama yapısı için uygulanacak meta verilerini etkinleştir öznitelikleri açıklanmaktadır.|
|[Kaynak Yönetimi: `use` Anahtar Sözcüğü](resource-management-the-use-keyword.md)|Anahtar sözcükler açıklar `use` ve `using`, hangi denetleyebilir başlatma ve kaynakların sürüm|
|[Ad alanları](namespaces.md)|Ad alanı desteği açıklanmaktadır F#. Bir ad alanı program öğeleri gruplandırması için bir ad eklemek sağlayarak, ilgili işlevleri alanlarına kod düzenlemenize olanak tanır.|
|[Modüller](modules.md)|Modüller açıklar. Bir F# modülüdür gruplandırması F# , değerleri, türleri ve işlev değerleri olarak gibi kod bir F# program. Kod modüllerinde gruplandırma ilgili kod bir arada tutmaya yardımcı olur ve programınızdaki ad çakışmalarını önlemek yardımcı olur.|
|[Önemli Bildirimler: `open` Anahtar Sözcüğü](import-declarations-the-open-keyword.md)|Açıklayan nasıl `open` çalışır. İçeri aktarma bildirimi, modül veya öğeleri bir tam adı kullanmadan başvuru ad alanı belirtir.|
|[İmzalar](signatures.md)|İmzalar ve imza dosyalarını açıklar. Bir imza dosyası bir dizi ortak imzalarını hakkında bilgi içeren F# türleri, ad alanları ve modüller gibi öğelerin program. Bu program öğelerini erişilebilirliğini belirtmek için kullanılabilir.|
|[XML Belgeleri](xml-documentation.md)|Belge dosyaları için XML belge açıklamaları, olarak da bilinen üç eğik çizgi açıklamalarını oluşturma desteğini açıklar. Kod açıklamaları belgelerinden üretebilir F# diğer .NET dilleri olduğu gibi.|
|[Ayrıntılı Söz Dizimi](verbose-syntax.md)|Sözdizimi açıklar F# basit söz dizimi etkinleştirilmediğinde oluşturur. Ayrıntılı sözdizimi tarafından belirtilen `#light "off"` kod dosyasının üst yönergesi.|

## <a name="f-types"></a>F# Türleri

Aşağıdaki tablo tarafından desteklenen türleri açıklayan başvuru konuları kullanılabilir gösterir F# dili.

|Başlık|Açıklama|
|-----|-----------|
|[Değerleri](values/index.md)|Belirli bir türüne sahip sabit miktarlarının değerleri açıklar; değerleri tamsayı veya kayan nokta numaralarını, karakter veya metin, listeler, dizileri, diziler, diziler, ayrılmış birleşimler, kayıtları, sınıf türleri veya işlev değerleri olabilir.|
|[Temel Türler](basic-types.md)|Kullanılan temel temel türleri açıklayan F# dili. Ayrıca karşılık gelen .NET türleri ve minimum ve maksimum değerler her türü için sağlar.|
|[Birim Türü](unit-type.md)|Açıklar `unit` belirli bir değer; devamsızlık gösteren bir tür olan türü `unit` türüne sahip başka bir değer yok veya gerekli olduğunda, bir yer tutucu olarak görev yapar yalnızca tek bir değer.|
|[Dizeler](strings.md)|Dizelerde açıklar F#. `string` Türü sabit metin, Unicode karakter dizisi olarak temsil eder. `string` için bir diğer addır `System.String` .NET Framework'teki.|
|[Demetler](tuples.md)|Gruplandırmaları adlandırılmamış ancak sıralı değerleri muhtemelen farklı türde diziler açıklar.|
|[F# Koleksiyon Türleri](fsharp-collection-types.md)|Genel bir bakış F# diziler, listeler, dizileri (seq), haritalar ve kümeler için türleri dahil olmak üzere, işlev koleksiyon türleri.|
|[Listeler](lists.md)|Listelerini açıklar. Bir listede F# öğeleri sıralı, sabit bir dizi tümü aynı türde.|
|[Seçenekler](options.md)|Seçenek türü açıklar. Bir seçenek F# bir değer olabilir veya olmayabilir kullanılır. Bir temel türü seçeneği vardır ve bu türde bir değer ya da tutabilir veya bir değer olmayabilir.|
|[Diziler](sequences.md)|Dizileri açıklar. Mantıksal bir dizi öğelerinin bir dizisidir tümü tek. Gösterim literal öğesi sayısını gösteren daha küçük olabilir bireysel sırası öğeleri yalnızca gerekli olursa, hesaplanır.|
|[Diziler](arrays.md)|Dizileri açıklar. Sabit boyutlu, sıfır tabanlı, kesilebilir dizileri ardışık veri öğelerinin tümü aynı türde dizilerdir.|
|[Kayıtlar](records.md)|Kayıtları açıklar. Kayıtları basit toplamalarla üyeleri ile isteğe bağlı olarak adlandırılan değerleri temsil eder.|
|[Ayrılmış Birleşimler](discriminated-unions.md)|Ayrılmış birleşimler, çeşitli adlandırılmış durumlarda, farklı olması olası değerlerini ve türlerini her biri olabilen değerleri için destek sağlayan açıklar.|
|[Sabit Listeleri](enumerations.md)|Numaralandırmaları açıklar tanımlı bir dizi türleri değerleri olarak adlandırılır. Kod daha okunabilir ve sürdürülebilir hale getirmek için değişmez değerler yerine bunları kullanabilirsiniz.|
|[Başvuru Hücreleri](reference-cells.md)|Başvuru semantiğiyle değişebilir değişkenleri oluşturmanıza olanak sağlayan depolama yerleridir başvuru hücreleri açıklar.|
|[Tür Kısaltmaları](type-abbreviations.md)|Türleri için alternatif adlar olan tür kısaltmaları açıklar.|
|[Sınıflar](classes.md)|Özellikleri, yöntemleri ve olayları olabilir nesneleri temsil eden türler sınıflarını açıklar.|
|[Yapılar](structures.md)|Az miktarda veri ve basit davranışı sahip türleri bir sınıf daha verimli olabilir compact nesne türleri yapıları açıklar.|
|[Arabirimler](interfaces.md)|Diğer sınıfları uygulayan ilgili üyeleri kümesini belirten ve arabirimler açıklanmaktadır.|
|[Soyut Sınıflar](abstract-classes.md)|Uygulanmayanları, bazı veya tüm üyeleri bırakın ve böylece uygulamaları türetilmiş sınıflar tarafından sağlanması sınıflarının soyut sınıfları açıklar.|
|[Tür Uzantıları](type-extensions.md)|Bir önceden tanımlanmış nesne türü için yeni üyeler eklemenize olanak sağlayan tür uzantıları açıklar.|
|[Esnek Türler](flexible-types.md)|Esnek türler açıklanmaktadır. Bir esnek tür ek açıklamasına parametre, değişken veya değer türü ile uyumlu bir türe sahip bir göstergesi, uyumluluk sınıfları arabirimler ve nesne yönelimli bir hiyerarşideki konuma göre belirlendiği belirtilmiştir.|
|[Temsilciler](delegates.md)|Bir nesne olarak bir işlev çağrısını temsil eden temsilciler açıklar.|
|[Ölçü Birimleri](units-of-measure.md)|Ölçü birimleri açıklar. Kayan nokta değerleri olarak F# genellikle uzunluğu, toplu, yığın ve benzeri belirtmek için kullanılan ölçü birimlerini ilişkili.|
|[Tür Sağlayıcıları](../tutorials/type-providers/index.md)|Açıklayan tür sağlar ve yerleşik tür sağlayıcılarını kullanarak veritabanları ve web hizmetleri için izlenecek yollar için bağlantılar sağlar.|

## <a name="f-expressions"></a>F# Expressions

Aşağıdaki tabloda açıklayan konulara F# ifadeler.

|Başlık|Açıklama|
|-----|-----------|
|[Koşullu ifadeler: `if...then...else`](conditional-expressions-if-then-else.md)|Açıklar `if...then...else` kodunun farklı dallara çalışan ve ayrıca verilen Boole ifadesi bağlı olarak farklı bir değer olarak değerlendirilen ifade.|
|[Eşleşme İfadeleri](match-expressions.md)|Açıklar `match` karşılaştırma ifade desenleri temel alan dallanma denetim sağlayan bir ifade.|
|[Döngüler: `for...to` İfade](loops-for-to-expression.md)|Açıklar `for...to` bir döngüde bir dizi bir döngü değişkeninin değerleri üzerinden yineleme yapmak için kullanılan ifade.|
|[Döngüler: `for...in` İfade](loops-for-in-expression.md)|Açıklar `for...in` ifadesi, bir aralık ifadesi, sıra, list, dizi gibi bir sıralanabilir koleksiyonun içindeki bir desenle eşleşmeleri üzerinden yineleme yapmak için kullanılan uvozuje konstruktor veya numaralandırma destekleyen diğer yapı.|
|[Döngüler: `while...do` İfade](loops-while-do-expression.md)|Açıklar `while...do` belirtilen test koşulu true olduğu sürece, yinelemeli yürütme (döngü) gerçekleştirmek için kullanılan ifade.|
|[Nesne İfadeleri](object-expressions.md)|Bir mevcut temel tür, arabirimi veya arabirim kümesine göre bir dinamik olarak oluşturulmuş, anonim bir nesne türünün yeni örneğini oluşturma ifadeler nesne ifadeleri açıklar.|
|[Gecikmeli İfadeler](lazy-expressions.md)|Hemen değerlendirilmeyen, ancak bunun yerine sonucu gerçekten gerekli olduğunda değerlendirilir hesaplamalar olan yavaş ifadeler açıklanmaktadır.|
|[Hesaplama İfadeleri](computation-expressions.md)|Hesaplama ifadeleri açıklar F#, sıralı hesaplamalar yazmak için kullanışlı bir söz dizimi sağlayan ve birleşik kullanarak denetim akışı yapılarını ve bağlar. İçin kullanışlı bir söz dizimi sağlamak için kullanılabilir *monadları*, veri, Denetim ve yan etkileri işlevsel programlarda yönetmek için kullanılan bir işlevsel programlama özelliği. Hesaplama ifadesi, zaman uyumsuz iş akışı bir tür, zaman uyumsuz ve paralel hesaplamaları için destek sağlar. Daha fazla bilgi için [zaman uyumsuz iş akışları](asynchronous-workflows.md).|
|[Zaman Uyumsuz İş Akışları](asynchronous-workflows.md)|Zaman uyumsuz iş akışları, zaman uyumsuz kod çok yakın şekilde, bir şekilde doğal olarak zaman uyumlu bir kod yazmak istediğiniz yazmanızı sağlayan bir dil özelliğini açıklar.|
|[Kod Alıntıları](code-quotations.md)|Kod tırnak işaretleri, oluşturmak ve bunlarla çalışmak sağlayan bir dil özelliği açıklar F# ifadeleri programlı bir şekilde kod.|
|[Sorgu İfadeleri](query-expressions.md)|Sorgu ifadeleri, LINQ için uygulayan bir dil özelliği açıklar F# ve bir veri kaynağı veya bir sıralanabilir koleksiyonun karşı sorgular yazmaya olanak tanır.|

## <a name="compiler-supported-constructs"></a>Derleyici tarafından desteklenen yapılar

Aşağıdaki tabloda, derleyici tarafından desteklenen özel yapıları açıklayan konulara listeler.

|Konu|Açıklama|
|-----|-----------|
|[Derleyici Seçenekleri](compiler-options.md)|Komut satırı seçeneklerini açıklar F# derleyici.|
|[Derleyici Yönergeleri](compiler-directives.md)|İşlemci yönergeleri ve derleyici yönergeleri açıklar.|
|[Kaynak Satırı, Dosya ve Yol Tanımlayıcıları](source-line-file-path-identifiers.md)|Tanımlayıcılar açıklanmaktadır `__LINE__`, `__SOURCE_DIRECTORY__` ve `__SOURCE_FILE__`, kodunuzda kaynak satırı numarasını, dizin ve dosya adına erişmenize olanak tanıyan yerleşik değerleri şunlardır.|

## <a name="see-also"></a>Ayrıca bkz.

- [Visual F#](../index.md)
