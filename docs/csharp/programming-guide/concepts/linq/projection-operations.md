---
title: Projeksiyon Işlemleri (C#)
ms.date: 07/20/2015
ms.assetid: 98df573a-aad9-4b8c-9a71-844be2c4fb41
ms.openlocfilehash: 4b34f3e578e746d75bdad7baaf731d743830713c
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69591566"
---
# <a name="projection-operations-c"></a>Projeksiyon Işlemleri (C#)
Projeksiyon, bir nesneyi genellikle daha sonra kullanılacak olan özelliklerden oluşan yeni bir forma dönüştürme işlemine başvurur. Projeksiyonu kullanarak her nesneden oluşturulan yeni bir tür oluşturabilirsiniz. Bir özelliği proje üzerinde bir matematik işlevi de gerçekleştirebilirsiniz. Özgün nesneyi değiştirmeden de proje oluşturabilirsiniz.  
  
 Yansıtmayı gerçekleştiren standart sorgu işleci yöntemleri aşağıdaki bölümde listelenmiştir.  
  
## <a name="methods"></a>Yöntemler  
  
|Yöntem adı|Açıklama|C#Sorgu Ifadesi söz dizimi|Daha fazla bilgi|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Seçim|Bir dönüşüm işlevine dayalı projeler değerleri.|`select`|<xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType>|  
|SelectMany|Bir dönüşüm işlevine dayalı ve sonra bunları tek bir sırayla düzleştirir.|Birden çok `from` yan tümce kullanma|<xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SelectMany%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Sorgu Ifadesi söz dizimi örnekleri  
  
### <a name="select"></a>Seçim  
 Aşağıdaki örnek, `select` bir dize listesindeki her bir dizeden ilk harfi proje için yan tümcesini kullanır.  
  
```csharp  
List<string> words = new List<string>() { "an", "apple", "a", "day" };  
  
var query = from word in words  
            select word.Substring(0, 1);  
  
foreach (string s in query)  
    Console.WriteLine(s);  
  
/* This code produces the following output:  
  
    a  
    a  
    a  
    d  
*/  
```  
  
### <a name="selectmany"></a>SelectMany  
 Aşağıdaki örnek, her bir `from` sözcüğü bir dize listesindeki her bir dizeden proje için birden çok yan tümce kullanır.  
  
```csharp  
List<string> phrases = new List<string>() { "an apple a day", "the quick brown fox" };  
  
var query = from phrase in phrases  
            from word in phrase.Split(' ')  
            select word;  
  
foreach (string s in query)  
    Console.WriteLine(s);  
  
/* This code produces the following output:  
  
    an  
    apple  
    a  
    day  
    the  
    quick  
    brown  
    fox  
*/  
```  
  
## <a name="select-versus-selectmany"></a>Select SelectMany  
 Her ikisinin de `Select()` `SelectMany()` işi, kaynak değerlerinden bir sonuç değeri (veya değerler) üretmeniz. `Select()`Her kaynak değer için bir sonuç değeri üretir. Bu nedenle, genel sonuç, kaynak koleksiyonuyla aynı sayıda öğeye sahip olan bir koleksiyondur. Buna karşılık, `SelectMany()` her kaynak değerden birleştirilmiş alt koleksiyonlar içeren tek bir genel sonuç üretir. Bağımsız değişken `SelectMany()` olarak geçirilen dönüştürme işlevinin her kaynak değer için sıralanabilir bir değer dizisi döndürmesi gerekir. Bu sıralanabilir sıralar daha sonra bir büyük `SelectMany()` sıra oluşturmak için ile birleştirilir.  
  
 Aşağıdaki iki çizimde, bu iki yöntemin eylemleri arasındaki kavramsal fark gösterilmektedir. Her durumda, seçici (dönüşüm) işlevinin her kaynak değerden çiçekler dizisini seçtiği varsayılır.  
  
 Bu çizimde, kaynak `Select()` koleksiyonuyla aynı sayıda öğeye sahip bir koleksiyonun nasıl döndürdüğü gösterilmektedir.  
  
 ![Seçme eylemini gösteren grafik&#40;&#41;](./media/projection-operations/select-action-graphic.png)  
  
 Bu çizimde, dizi `SelectMany()` dizilerinin her bir ara dizideki her bir değeri içeren bir son sonuç değerine nasıl sıralanacağı gösterilmektedir.  
  
 ![SelectMany&#40;&#41;eylemini gösteren grafik.](./media/projection-operations/select-many-action-graphic.png )  
  
### <a name="code-example"></a>Kod Örneği  
 Aşağıdaki örnek, `Select()` ve `SelectMany()`davranışlarını karşılaştırır. Kod, kaynak koleksiyondaki her bir çiçek adı listesinden ilk iki öğeyi alarak çiçekler ' ın bir "Buquet" oluşturur. Bu örnekte, Transform işlevinin <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> kullandığı "tek değer" değeri bir değer koleksiyonudur. Bu, her bir `foreach` alt dizideki her bir dizeyi numaralandırmak için ek döngü gerektirir.  
  
```csharp  
class Bouquet  
{  
    public List<string> Flowers { get; set; }  
}  
  
static void SelectVsSelectMany()  
{  
    List<Bouquet> bouquets = new List<Bouquet>() {  
        new Bouquet { Flowers = new List<string> { "sunflower", "daisy", "daffodil", "larkspur" }},  
        new Bouquet{ Flowers = new List<string> { "tulip", "rose", "orchid" }},  
        new Bouquet{ Flowers = new List<string> { "gladiolis", "lily", "snapdragon", "aster", "protea" }},  
        new Bouquet{ Flowers = new List<string> { "larkspur", "lilac", "iris", "dahlia" }}  
    };  
  
    // *********** Select ***********              
    IEnumerable<List<string>> query1 = bouquets.Select(bq => bq.Flowers);  
  
    // ********* SelectMany *********  
    IEnumerable<string> query2 = bouquets.SelectMany(bq => bq.Flowers);  
  
    Console.WriteLine("Results by using Select():");  
    // Note the extra foreach loop here.  
    foreach (IEnumerable<String> collection in query1)  
        foreach (string item in collection)  
            Console.WriteLine(item);  
  
    Console.WriteLine("\nResults by using SelectMany():");  
    foreach (string item in query2)  
        Console.WriteLine(item);  
  
    /* This code produces the following output:  
  
       Results by using Select():  
        sunflower  
        daisy  
        daffodil  
        larkspur  
        tulip  
        rose  
        orchid  
        gladiolis  
        lily  
        snapdragon  
        aster  
        protea  
        larkspur  
        lilac  
        iris  
        dahlia  
  
       Results by using SelectMany():  
        sunflower  
        daisy  
        daffodil  
        larkspur  
        tulip  
        rose  
        orchid  
        gladiolis  
        lily  
        snapdragon  
        aster  
        protea  
        larkspur  
        lilac  
        iris  
        dahlia  
    */  
  
}  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Linq>
- [Standart sorgu Işleçlerine genelC#bakış ()](./standard-query-operators-overview.md)
- [select yan tümcesi](../../../language-reference/keywords/select-clause.md)
- [Nasıl yapılır: Birden çok kaynaktan nesne koleksiyonları doldurma (LINQ) (C#)](./how-to-populate-object-collections-from-multiple-sources-linq.md)
- [Nasıl yapılır: Grupları (LINQ) kullanarak bir dosyayı çok sayıda dosyaya bölme (LINQC#) ()](./how-to-split-a-file-into-many-files-by-using-groups-linq.md)
