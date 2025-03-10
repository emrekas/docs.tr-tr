---
title: Koleksiyonlar (C#)
ms.date: 07/20/2015
ms.assetid: 317d7dc3-8587-4873-8b3e-556f86497939
ms.openlocfilehash: 712ae4c9b4cf577ab728e4b78582445070e08049
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69595287"
---
# <a name="collections-c"></a>Koleksiyonlar (C#)

Birçok uygulama için ilgili nesne grupları oluşturmak ve yönetmek istersiniz. Nesneleri gruplandırmanın iki yolu vardır: nesne dizileri oluşturarak ve nesne koleksiyonları oluşturarak.

Diziler, kesin olarak belirlenmiş sabit sayıda nesne oluşturmak ve bunlarla çalışmak için en yararlı seçenektir. Diziler hakkında daha fazla bilgi için bkz. [diziler](../arrays/index.md).

Koleksiyonlar, nesne gruplarıyla çalışmak için daha esnek bir yol sağlar. Dizilerden farklı olarak, çalıştığınız nesne grubu, uygulama değişikliğinin ihtiyaçlarına göre dinamik olarak büyüyebilir ve küçülebilir. Bazı koleksiyonlar için, anahtarı kullanarak nesneyi hızlı bir şekilde alabilmeniz için koleksiyona yerleştirdiğiniz herhangi bir nesneye bir anahtar atayabilirsiniz.

Koleksiyon bir sınıftır, bu nedenle bu koleksiyona öğe ekleyebilmeniz için önce sınıfın bir örneğini bildirmeniz gerekir.

Koleksiyonunuz yalnızca bir veri türünün öğelerini içeriyorsa, <xref:System.Collections.Generic?displayProperty=nameWithType> ad alanındaki sınıflardan birini kullanabilirsiniz. Genel bir koleksiyon, tür güvenliğini, başka bir veri türü eklenememesi için uygular. Genel koleksiyondan bir öğe aldığınızda, veri türünü belirlememek veya dönüştürmek zorunda değilsiniz.

> [!NOTE]
> Bu konudaki örnekler için `System.Collections.Generic` ve `System.Linq` ad alanları için [using](../../language-reference/keywords/using-directive.md) yönergelerini içerir.

 **Bu konudaki**

- [Basit bir koleksiyon kullanma](#BKMK_SimpleCollection)

- [Koleksiyon türleri](#BKMK_KindsOfCollections)

  - [System. Collections. Generic sınıfları](#BKMK_Generic)

  - [System. Collections. eşzamanlı sınıflar](#BKMK_Concurrent)

  - [System. Collections sınıfları](#BKMK_Collections)

- [Anahtar/değer çiftleri koleksiyonu uygulama](#BKMK_KeyValuePairs)

- [Koleksiyona erişmek için LINQ kullanma](#BKMK_LINQ)

- [Bir koleksiyonu sıralama](#BKMK_Sorting)

- [Özel bir koleksiyon tanımlama](#BKMK_CustomCollection)

- [Yineleyiciler](#BKMK_Iterators)

<a name="BKMK_SimpleCollection"></a>

## <a name="using-a-simple-collection"></a>Basit bir koleksiyon kullanma

Bu bölümdeki örneklerde, türü kesin belirlenmiş bir <xref:System.Collections.Generic.List%601> nesne listesiyle çalışmanıza olanak sağlayan genel sınıfı kullanılır.

Aşağıdaki örnek, bir dizi dizenin bir listesini oluşturur ve sonra, bir [foreach](../../language-reference/keywords/foreach-in.md) ifadesi kullanarak dizeler arasında yinelenir.

```csharp
// Create a list of strings.
var salmons = new List<string>();
salmons.Add("chinook");
salmons.Add("coho");
salmons.Add("pink");
salmons.Add("sockeye");

// Iterate through the list.
foreach (var salmon in salmons)
{
    Console.Write(salmon + " ");
}
// Output: chinook coho pink sockeye
```

Bir koleksiyonun içeriği önceden biliniyorsa, koleksiyonu başlatmak için bir *koleksiyon başlatıcısı* kullanabilirsiniz. Daha fazla bilgi için bkz. [nesne ve koleksiyon başlatıcıları](../classes-and-structs/object-and-collection-initializers.md).

Aşağıdaki örnek, koleksiyona öğe eklemek için bir koleksiyon başlatıcısı kullanılması dışında, önceki örnekle aynıdır.

```csharp
// Create a list of strings by using a
// collection initializer.
var salmons = new List<string> { "chinook", "coho", "pink", "sockeye" };

// Iterate through the list.
foreach (var salmon in salmons)
{
    Console.Write(salmon + " ");
}
// Output: chinook coho pink sockeye
```

Bir koleksiyon aracılığıyla yinelemek için bir [for](../../language-reference/keywords/for.md) ifadesinin yerine `foreach` bir for ifadesini kullanabilirsiniz. Bunu, koleksiyon öğelerine dizin konumuna erişerek gerçekleştirirsiniz. Öğelerin dizini 0 ' dan başlar ve öğe sayısı eksi 1 ' den sona erer.

Aşağıdaki örnek `for` `foreach`yerine kullanarak bir koleksiyonun öğeleri boyunca yinelenir.

```csharp
// Create a list of strings by using a
// collection initializer.
var salmons = new List<string> { "chinook", "coho", "pink", "sockeye" };

for (var index = 0; index < salmons.Count; index++)
{
    Console.Write(salmons[index] + " ");
}
// Output: chinook coho pink sockeye
```

Aşağıdaki örnek, kaldırılacak nesneyi belirterek koleksiyondan bir öğeyi kaldırır.

```csharp
// Create a list of strings by using a
// collection initializer.
var salmons = new List<string> { "chinook", "coho", "pink", "sockeye" };

// Remove an element from the list by specifying
// the object.
salmons.Remove("coho");

// Iterate through the list.
foreach (var salmon in salmons)
{
    Console.Write(salmon + " ");
}
// Output: chinook pink sockeye
```

Aşağıdaki örnek, genel bir listeden öğeleri kaldırır. Bir `foreach` ifade yerine, azalan düzende yinelenen bir [for](../../language-reference/keywords/for.md) deyimleri kullanılır. Bunun nedeni, <xref:System.Collections.Generic.List%601.RemoveAt%2A> yöntemin kaldırılan bir öğeden sonra öğelerin daha düşük bir dizin değerine sahip olmasına neden olur.

```csharp
var numbers = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };

// Remove odd numbers.
for (var index = numbers.Count - 1; index >= 0; index--)
{
    if (numbers[index] % 2 == 1)
    {
        // Remove the element by specifying
        // the zero-based index in the list.
        numbers.RemoveAt(index);
    }
}

// Iterate through the list.
// A lambda expression is placed in the ForEach method
// of the List(T) object.
numbers.ForEach(
    number => Console.Write(number + " "));
// Output: 0 2 4 6 8
```

İçindeki <xref:System.Collections.Generic.List%601>öğe türleri için kendi sınıfınızı de tanımlayabilirsiniz. Aşağıdaki örnekte `Galaxy` , <xref:System.Collections.Generic.List%601> tarafından kullanılan sınıfı kodda tanımlanmıştır.

```csharp
private static void IterateThroughList()
{
    var theGalaxies = new List<Galaxy>
        {
            new Galaxy() { Name="Tadpole", MegaLightYears=400},
            new Galaxy() { Name="Pinwheel", MegaLightYears=25},
            new Galaxy() { Name="Milky Way", MegaLightYears=0},
            new Galaxy() { Name="Andromeda", MegaLightYears=3}
        };

    foreach (Galaxy theGalaxy in theGalaxies)
    {
        Console.WriteLine(theGalaxy.Name + "  " + theGalaxy.MegaLightYears);
    }

    // Output:
    //  Tadpole  400
    //  Pinwheel  25
    //  Milky Way  0
    //  Andromeda  3
}

public class Galaxy
{
    public string Name { get; set; }
    public int MegaLightYears { get; set; }
}
```

<a name="BKMK_KindsOfCollections"></a>

## <a name="kinds-of-collections"></a>Koleksiyon türleri

Birçok ortak koleksiyon .NET Framework tarafından sağlanır. Her koleksiyon türü belirli bir amaç için tasarlanmıştır.

Ortak koleksiyon sınıflarından bazıları bu bölümde açıklanmıştır:

- <xref:System.Collections.Generic> sınıflar

- <xref:System.Collections.Concurrent> sınıflar

- <xref:System.Collections> sınıflar

<a name="BKMK_Generic"></a>

### <a name="systemcollectionsgeneric-classes"></a>System. Collections. Generic sınıfları

<xref:System.Collections.Generic> Ad alanındaki sınıflardan birini kullanarak genel bir koleksiyon oluşturabilirsiniz. Genel bir koleksiyon, koleksiyondaki her öğe aynı veri türüne sahip olduğunda faydalıdır. Genel bir koleksiyon, yalnızca istenen veri türünün eklenmesine izin vererek güçlü yazma uygular.

Aşağıdaki tabloda, <xref:System.Collections.Generic?displayProperty=nameWithType> ad alanının sık kullanılan sınıflarının bazıları listelenmektedir:

|örneği|Açıklama|
|---|---|
|<xref:System.Collections.Generic.Dictionary%602>|Anahtara göre düzenlenen anahtar/değer çiftleri koleksiyonunu temsil eder.|
|<xref:System.Collections.Generic.List%601>|Dizin tarafından erişilebilen nesnelerin listesini temsil eder. Listeleri aramak, sıralamak ve değiştirmek için yöntemler sağlar.|
|<xref:System.Collections.Generic.Queue%601>|Nesnelerin ilk, ilk çıkar (FıFO) koleksiyonunu temsil eder.|
|<xref:System.Collections.Generic.SortedList%602>|İlişkili <xref:System.Collections.Generic.IComparer%601> uygulamaya göre anahtara göre sıralanan anahtar/değer çiftleri koleksiyonunu temsil eder.|
|<xref:System.Collections.Generic.Stack%601>|Nesnelerin son, ilk çıkar (LıFO) koleksiyonunu temsil eder.|

Daha fazla bilgi için bkz. [yaygın olarak kullanılan koleksiyon türleri](../../../standard/collections/commonly-used-collection-types.md), [koleksiyon sınıfı seçme](../../../standard/collections/selecting-a-collection-class.md)ve <xref:System.Collections.Generic>.

<a name="BKMK_Concurrent"></a>

### <a name="systemcollectionsconcurrent-classes"></a>System. Collections. eşzamanlı sınıflar

.NET Framework 4 veya daha yeni bir sürümde, <xref:System.Collections.Concurrent> ad alanındaki koleksiyonlar, koleksiyon öğelerine birden çok iş parçacığından erişmek için verimli iş parçacığı güvenli işlemleri sağlar.

Birden çok iş parçacığının <xref:System.Collections.Concurrent> koleksiyona aynı anda eriştiği her seferinde <xref:System.Collections.Generic?displayProperty=nameWithType> ve <xref:System.Collections?displayProperty=nameWithType> ad alanındaki ilgili türler yerine ad alanındaki sınıflar kullanılmalıdır. Daha fazla bilgi için bkz. [Iş parçacığı güvenli koleksiyonlar](../../../standard/collections/thread-safe/index.md) ve <xref:System.Collections.Concurrent>.

<xref:System.Collections.Concurrent> Ad alanına dahil edilen bazı sınıflar, <xref:System.Collections.Concurrent.BlockingCollection%601> <xref:System.Collections.Concurrent.ConcurrentDictionary%602> <xref:System.Collections.Concurrent.ConcurrentQueue%601>, ve <xref:System.Collections.Concurrent.ConcurrentStack%601>' dir.

<a name="BKMK_Collections"></a>

### <a name="systemcollections-classes"></a>System. Collections sınıfları

<xref:System.Collections?displayProperty=nameWithType> Ad alanındaki sınıflar öğeleri özel olarak yazılmış nesneler olarak depolamaz, ancak türünden `Object`nesneler olarak depolamaz.

Mümkün olduğunda, ad alanındaki eski türler <xref:System.Collections.Generic?displayProperty=nameWithType> `System.Collections` yerine ad alanı <xref:System.Collections.Concurrent> veya ad alanı içinde genel koleksiyonları kullanmanız gerekir.

Aşağıdaki tabloda, `System.Collections` ad alanında sık kullanılan sınıfların bazıları listelenmektedir:

|örneği|Açıklama|
|---|---|
|<xref:System.Collections.ArrayList>|Boyutu dinamik olarak gerektiği şekilde arttığı bir nesne dizisini temsil eder.|
|<xref:System.Collections.Hashtable>|Anahtarın karma koduna göre düzenlenmiş anahtar/değer çiftleri koleksiyonunu temsil eder.|
|<xref:System.Collections.Queue>|Nesnelerin ilk, ilk çıkar (FıFO) koleksiyonunu temsil eder.|
|<xref:System.Collections.Stack>|Nesnelerin son, ilk çıkar (LıFO) koleksiyonunu temsil eder.|

<xref:System.Collections.Specialized> Ad alanı, yalnızca dize toplamaları ve bağlantılı liste ve karma sözlük gibi özelleştirilmiş ve kesin tür belirtilmiş koleksiyon sınıfları sağlar.

<a name="BKMK_KeyValuePairs"></a>

## <a name="implementing-a-collection-of-keyvalue-pairs"></a>Anahtar/değer çiftleri koleksiyonu uygulama

Genel <xref:System.Collections.Generic.Dictionary%602> koleksiyon, her bir öğenin anahtarını kullanarak bir koleksiyondaki öğelere erişmenizi sağlar. Sözlüğe eklenen her ekleme bir değerden ve ilişkili anahtarından oluşur. `Dictionary` Sınıfı bir karma tablo olarak uygulandığından, anahtarını kullanarak bir değerin alınması hızlıdır.

Aşağıdaki örnek bir `Dictionary` koleksiyon oluşturur ve bir `foreach` ifade kullanarak sözlükten yinelenir.

```csharp
private static void IterateThruDictionary()
{
    Dictionary<string, Element> elements = BuildDictionary();

    foreach (KeyValuePair<string, Element> kvp in elements)
    {
        Element theElement = kvp.Value;

        Console.WriteLine("key: " + kvp.Key);
        Console.WriteLine("values: " + theElement.Symbol + " " +
            theElement.Name + " " + theElement.AtomicNumber);
    }
}

private static Dictionary<string, Element> BuildDictionary()
{
    var elements = new Dictionary<string, Element>();

    AddToDictionary(elements, "K", "Potassium", 19);
    AddToDictionary(elements, "Ca", "Calcium", 20);
    AddToDictionary(elements, "Sc", "Scandium", 21);
    AddToDictionary(elements, "Ti", "Titanium", 22);

    return elements;
}

private static void AddToDictionary(Dictionary<string, Element> elements,
    string symbol, string name, int atomicNumber)
{
    Element theElement = new Element();

    theElement.Symbol = symbol;
    theElement.Name = name;
    theElement.AtomicNumber = atomicNumber;

    elements.Add(key: theElement.Symbol, value: theElement);
}

public class Element
{
    public string Symbol { get; set; }
    public string Name { get; set; }
    public int AtomicNumber { get; set; }
}
```

Koleksiyonu oluşturmak için bir koleksiyon başlatıcısı kullanmak yerine, `AddToDictionary` veyöntemleriniaşağıdakiyöntemledeğiştirebilirsiniz.`BuildDictionary` `Dictionary`

```csharp
private static Dictionary<string, Element> BuildDictionary2()
{
    return new Dictionary<string, Element>
    {
        {"K",
            new Element() { Symbol="K", Name="Potassium", AtomicNumber=19}},
        {"Ca",
            new Element() { Symbol="Ca", Name="Calcium", AtomicNumber=20}},
        {"Sc",
            new Element() { Symbol="Sc", Name="Scandium", AtomicNumber=21}},
        {"Ti",
            new Element() { Symbol="Ti", Name="Titanium", AtomicNumber=22}}
    };
}
```

Aşağıdaki örnek, bir öğeyi <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A> anahtara göre hızlı <xref:System.Collections.Generic.Dictionary%602.Item%2A> bir şekilde `Dictionary` bulmak için yöntemini ve özelliğini kullanır. Özelliği, `elements`içindeöğesini C#kullanarak koleksiyondaki bir öğeye erişmenizi sağlar. `Item` `elements[symbol]`

```csharp
private static void FindInDictionary(string symbol)
{
    Dictionary<string, Element> elements = BuildDictionary();

    if (elements.ContainsKey(symbol) == false)
    {
        Console.WriteLine(symbol + " not found");
    }
    else
    {
        Element theElement = elements[symbol];
        Console.WriteLine("found: " + theElement.Name);
    }
}
```

Aşağıdaki örnek bunun yerine, bir <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> öğeyi anahtara göre hızlı bir şekilde bulmak için yöntemini kullanır.

```csharp
private static void FindInDictionary2(string symbol)
{
    Dictionary<string, Element> elements = BuildDictionary();

    Element theElement = null;
    if (elements.TryGetValue(symbol, out theElement) == false)
        Console.WriteLine(symbol + " not found");
    else
        Console.WriteLine("found: " + theElement.Name);
}
```

<a name="BKMK_LINQ"></a>

## <a name="using-linq-to-access-a-collection"></a>Koleksiyona erişmek için LINQ kullanma

LINQ (dil ile tümleşik sorgu), koleksiyonlara erişmek için kullanılabilir. LINQ sorguları filtreleme, sıralama ve gruplama özellikleri sağlar. Daha fazla bilgi için bkz. [ C#LINQ ile çalışmaya ](./linq/getting-started-with-linq.md)başlama.

Aşağıdaki örnek, genel `List`olarak bir LINQ sorgusu çalıştırır. LINQ sorgusu, sonuçları içeren farklı bir koleksiyon döndürür.

```csharp
private static void ShowLINQ()
{
    List<Element> elements = BuildList();

    // LINQ Query.
    var subset = from theElement in elements
                 where theElement.AtomicNumber < 22
                 orderby theElement.Name
                 select theElement;

    foreach (Element theElement in subset)
    {
        Console.WriteLine(theElement.Name + " " + theElement.AtomicNumber);
    }

    // Output:
    //  Calcium 20
    //  Potassium 19
    //  Scandium 21
}

private static List<Element> BuildList()
{
    return new List<Element>
    {
        { new Element() { Symbol="K", Name="Potassium", AtomicNumber=19}},
        { new Element() { Symbol="Ca", Name="Calcium", AtomicNumber=20}},
        { new Element() { Symbol="Sc", Name="Scandium", AtomicNumber=21}},
        { new Element() { Symbol="Ti", Name="Titanium", AtomicNumber=22}}
    };
}

public class Element
{
    public string Symbol { get; set; }
    public string Name { get; set; }
    public int AtomicNumber { get; set; }
}
```

<a name="BKMK_Sorting"></a>

## <a name="sorting-a-collection"></a>Bir koleksiyonu sıralama

Aşağıdaki örnek bir koleksiyonu sıralamak için bir yordam gösterir. Örnek, `Car` <xref:System.Collections.Generic.List%601>içinde depolanan sınıfının örneklerini sıralar. Sınıfı, <xref:System.IComparable%601.CompareTo%2A> yönteminin uygulanması <xref:System.IComparable%601> için arabirimini uygular. `Car`

Yöntemine yapılan her çağrı <xref:System.IComparable%601.CompareTo%2A> , sıralama için kullanılan tek bir karşılaştırma yapar. `CompareTo` Yöntemdeki Kullanıcı tarafından yazılan kod, geçerli nesnenin her bir karşılaştırması için başka bir nesneyle ilgili bir değer döndürür. Geçerli nesne diğer nesneden daha küçükse döndürülen değer sıfırdan küçük, geçerli nesne diğer nesneden büyükse sıfırdan büyük ve eşitse sıfır. Bu, büyük, küçüktür ve eşittir ölçütlerine göre kod içinde tanımlamanızı sağlar.

`ListCars` Yönteminde`cars.Sort()` , ifade listeyi sıralar. <xref:System.Collections.Generic.List%601.Sort%2A> `CompareTo` Öğesininyöntemine`Car` yapılan bu çağrı, yönteminin içindeki `List`nesneler için otomatik olarak çağrılmasına neden olur. <xref:System.Collections.Generic.List%601>

```csharp
private static void ListCars()
{
    var cars = new List<Car>
    {
        { new Car() { Name = "car1", Color = "blue", Speed = 20}},
        { new Car() { Name = "car2", Color = "red", Speed = 50}},
        { new Car() { Name = "car3", Color = "green", Speed = 10}},
        { new Car() { Name = "car4", Color = "blue", Speed = 50}},
        { new Car() { Name = "car5", Color = "blue", Speed = 30}},
        { new Car() { Name = "car6", Color = "red", Speed = 60}},
        { new Car() { Name = "car7", Color = "green", Speed = 50}}
    };

    // Sort the cars by color alphabetically, and then by speed
    // in descending order.
    cars.Sort();

    // View all of the cars.
    foreach (Car thisCar in cars)
    {
        Console.Write(thisCar.Color.PadRight(5) + " ");
        Console.Write(thisCar.Speed.ToString() + " ");
        Console.Write(thisCar.Name);
        Console.WriteLine();
    }

    // Output:
    //  blue  50 car4
    //  blue  30 car5
    //  blue  20 car1
    //  green 50 car7
    //  green 10 car3
    //  red   60 car6
    //  red   50 car2
}

public class Car : IComparable<Car>
{
    public string Name { get; set; }
    public int Speed { get; set; }
    public string Color { get; set; }

    public int CompareTo(Car other)
    {
        // A call to this method makes a single comparison that is
        // used for sorting.

        // Determine the relative order of the objects being compared.
        // Sort by color alphabetically, and then by speed in
        // descending order.

        // Compare the colors.
        int compare;
        compare = String.Compare(this.Color, other.Color, true);

        // If the colors are the same, compare the speeds.
        if (compare == 0)
        {
            compare = this.Speed.CompareTo(other.Speed);

            // Use descending order for speed.
            compare = -compare;
        }

        return compare;
    }
}
```

<a name="BKMK_CustomCollection"></a>

## <a name="defining-a-custom-collection"></a>Özel bir koleksiyon tanımlama

<xref:System.Collections.Generic.IEnumerable%601> Veya<xref:System.Collections.IEnumerable> arabirimini uygulayarak bir koleksiyon tanımlayabilirsiniz.

Özel bir koleksiyon tanımlamanızı mümkün olsa da, bu konunun önceki kısımlarında yer alan [koleksiyonlar türlerinde](#BKMK_KindsOfCollections) açıklanan .NET Framework dahil edilen koleksiyonları kullanmak genellikle daha iyidir.

Aşağıdaki örnek adlı `AllColors`özel bir koleksiyon sınıfını tanımlar. Bu sınıf, <xref:System.Collections.IEnumerable.GetEnumerator%2A> yönteminin <xref:System.Collections.IEnumerable> uygulanması için arabirimini uygular.

Yöntemi `GetEnumerator` , `ColorEnumerator` sınıfının bir örneğini döndürür. `ColorEnumerator`<xref:System.Collections.IEnumerator.Current%2A>özelliği, yöntemive<xref:System.Collections.IEnumerator.Reset%2A> yönteminin uygulanması için arabiriminiuygular.<xref:System.Collections.IEnumerator> <xref:System.Collections.IEnumerator.MoveNext%2A>

```csharp
private static void ListColors()
{
    var colors = new AllColors();

    foreach (Color theColor in colors)
    {
        Console.Write(theColor.Name + " ");
    }
    Console.WriteLine();
    // Output: red blue green
}

// Collection class.
public class AllColors : System.Collections.IEnumerable
{
    Color[] _colors =
    {
        new Color() { Name = "red" },
        new Color() { Name = "blue" },
        new Color() { Name = "green" }
    };

    public System.Collections.IEnumerator GetEnumerator()
    {
        return new ColorEnumerator(_colors);

        // Instead of creating a custom enumerator, you could
        // use the GetEnumerator of the array.
        //return _colors.GetEnumerator();
    }

    // Custom enumerator.
    private class ColorEnumerator : System.Collections.IEnumerator
    {
        private Color[] _colors;
        private int _position = -1;

        public ColorEnumerator(Color[] colors)
        {
            _colors = colors;
        }

        object System.Collections.IEnumerator.Current
        {
            get
            {
                return _colors[_position];
            }
        }

        bool System.Collections.IEnumerator.MoveNext()
        {
            _position++;
            return (_position < _colors.Length);
        }

        void System.Collections.IEnumerator.Reset()
        {
            _position = -1;
        }
    }
}

// Element class.
public class Color
{
    public string Name { get; set; }
}
```

<a name="BKMK_Iterators"></a>

## <a name="iterators"></a>Yineleyiciler

Bir *Yineleyici* , bir koleksiyon üzerinde özel bir yineleme gerçekleştirmek için kullanılır. Yineleyici bir yöntem veya `get` erişimci olabilir. Bir yineleyici, tek seferde koleksiyonun her bir öğesini döndürmek için bir [yield return](../../language-reference/keywords/yield.md) ifadesini kullanır.

Bir [foreach](../../language-reference/keywords/foreach-in.md) ifadesi kullanarak bir yineleyici çağırın. `foreach` Döngünün her yinelemesi yineleyiciyi çağırır. Yineleyiciden bir `yield return` ifadeye ulaşıldığında, bir ifade döndürülür ve koddaki geçerli konum korunur. Bu konumdan, yineleyici bir sonraki sefer çağrıldığında yürütme yeniden başlatılır.

Daha fazla bilgi için bkz. [yineleyicilerC#()](./iterators.md).

Aşağıdaki örnek bir yineleyici yöntemi kullanır. Yineleyici yöntemi `yield return` için bir [for](../../language-reference/keywords/for.md) döngüsü içinde olan bir ifade vardır. Yönteminde, `foreach` ifade gövdesinin her yinelemesi, bir sonraki `yield return` ifadeye devam eden Yineleyici yöntemine bir çağrı oluşturur. `ListEvenNumbers`

```csharp
private static void ListEvenNumbers()
{
    foreach (int number in EvenSequence(5, 18))
    {
        Console.Write(number.ToString() + " ");
    }
    Console.WriteLine();
    // Output: 6 8 10 12 14 16 18
}

private static IEnumerable<int> EvenSequence(
    int firstNumber, int lastNumber)
{
    // Yield even numbers in the range.
    for (var number = firstNumber; number <= lastNumber; number++)
    {
        if (number % 2 == 0)
        {
            yield return number;
        }
    }
}
```

## <a name="see-also"></a>Ayrıca bkz.

- [Nesne ve Koleksiyon Başlatıcıları](../classes-and-structs/object-and-collection-initializers.md)
- [Programlama kavramları (C#)](./index.md)
- [Option Strict Deyimi](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [LINQ to Objects (C#)](./linq/linq-to-objects.md)
- [Paralel LINQ (PLINQ)](../../../standard/parallel-programming/parallel-linq-plinq.md)
- [Koleksiyonlar ve Veri Yapıları](../../../standard/collections/index.md)
- [Koleksiyon Sınıfı Seçme](../../../standard/collections/selecting-a-collection-class.md)
- [Koleksiyonlardaki Karşılaştırmalar ve Sıralamalar](../../../standard/collections/comparisons-and-sorts-within-collections.md)
- [Genel Koleksiyonlar Ne Zaman Kullanılır?](../../../standard/collections/when-to-use-generic-collections.md)
