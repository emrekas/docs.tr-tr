---
title: Koleksiyonlarla çalışma- C# öğreticiye giriş
description: Bu C# öğreticide liste koleksiyonunu inceleyerek öğrenin.
ms.date: 10/13/2017
ms.custom: mvc
ms.openlocfilehash: 160e34ddb529a8515a08d6aab838ba107936c616
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587263"
---
# <a name="learn-to-manage-data-collections-using-the-generic-list-type"></a>Genel liste türünü kullanarak veri koleksiyonlarını yönetmeyi öğrenin

Bu giriş öğreticisi, C# dile ve <xref:System.Collections.Generic.List%601> sınıfın temel bilgilerine bir giriş sağlar.

Bu öğreticide, geliştirme için kullanabileceğiniz bir makineniz olması beklenir. [10 dakika Içinde başlayan](https://www.microsoft.com/net/core) .net konusunun yerel geliştirme ortamınızı Mac, PC veya Linux üzerinde ayarlamaya yönelik yönergeler vardır. Kullanacağınız komutlara hızlı bir genel bakış, daha fazla ayrıntı bağlantılarıyla birlikte [geliştirme araçları hakkında bilgi sahibi](local-environment.md)olmak için kullanılır.

## <a name="a-basic-list-example"></a>Temel liste örneği

**List-öğreticisi**adlı bir dizin oluşturun. Geçerli dizini oluşturun ve çalıştırın `dotnet new console`.

En sevdiğiniz düzenleyicide **program.cs** açın ve mevcut kodu aşağıdaki kodla değiştirin:

```csharp
using System;
using System.Collections.Generic;

namespace list_tutorial
{
    class Program
    {
        static void Main(string[] args)
        {
            var names = new List<string> { "<name>", "Ana", "Felipe" };
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

Adınızla `<name>` değiştirin. **Program.cs**Kaydet. Denemek `dotnet run` için konsol pencerenizi yazın.

Yalnızca bir dize listesi oluşturdunuz, bu listeye üç ad ekledik ve adları tüm büyük harfler içinde yazdırdınız. Önceki öğreticilerde, listede döngü gerçekleştirmek için öğrenmiş olduğunuz kavramları kullanıyorsunuz.

Adları görüntülenecek kod, [dize ilişkilendirme](../../language-reference/tokens/interpolated.md) özelliğini kullanır.  Bir `string` karakterden`$` önce karakterinden sonra, dize bildirimine C# kod ekleyebilirsiniz. Gerçek dize, bu C# kodun oluşturduğu değerle değiştirir. Bu örnekte, <xref:System.String.ToUpper%2A> yöntemini çağırdığı için `{name.ToUpper()}` , her bir adla ' ı, büyük harflere dönüştürülecek şekilde değiştirir.

Araştırma devam edelim.

## <a name="modify-list-contents"></a>Liste içeriğini değiştirme

Oluşturduğunuz koleksiyon <xref:System.Collections.Generic.List%601> türünü kullanır. Bu tür öğe dizilerini depolar. Açılı ayraçlar arasındaki öğelerin türünü belirtirsiniz.

Bu <xref:System.Collections.Generic.List%601> türün önemli bir yönü büyümenin veya küçülebileceği, öğe eklemenize veya kaldırmanıza imkan sağlar. Yöntemdeki`Main` kapatmadan `}` önce bu kodu ekleyin:

```csharp
Console.WriteLine();
names.Add("Maria");
names.Add("Bill");
names.Remove("Ana");
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

Listenin sonuna iki ad daha eklediniz. Ayrıca bir tane de kaldırmış olursunuz. Dosyayı kaydedin ve denemek için yazın `dotnet run` .

, <xref:System.Collections.Generic.List%601> Tek tek öğeleri **dizine** göre de başvurmanızı sağlar. Dizini, liste adını izleyen `[` ve `]` belirteçleri arasına yerleştirebilirsiniz. C#ilk dizin için 0 kullanır. Bu kodu, yeni eklediğiniz kodun hemen altına ekleyin ve deneyin:

```csharp
Console.WriteLine($"My name is {names[0]}");
Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");
```

Liste sonunun ötesinde bir dizine erişemezsiniz. Dizinlerin 0 ' dan başlayıp, en büyük geçerli dizinin listedeki öğe sayısından bir daha az olması gerektiğini unutmayın. Listenin <xref:System.Collections.Generic.List%601.Count%2A> özelliğini ne kadar süreyle kullandığını kontrol edebilirsiniz. Main yönteminin sonuna aşağıdaki kodu ekleyin:

```csharp
Console.WriteLine($"The list has {names.Count} people in it");
 ```

Dosyayı kaydedin ve sonuçları görmek için `dotnet run` yeniden yazın.

## <a name="search-and-sort-lists"></a>Arama ve sıralama listeleri

Örneklerimizde görece küçük listeler kullanılıyor, ancak uygulamalarınız genellikle binlerce numaralandırma olan çok sayıda öğesi olan listeler oluşturabilir. Bu daha büyük koleksiyonlardaki öğeleri bulmak için listede farklı öğeler için arama yapmanız gerekir. <xref:System.Collections.Generic.List%601.IndexOf%2A> Yöntemi bir öğe arar ve öğenin dizinini döndürür. Bu kodu `Main` yönteminizin en altına ekleyin:

```csharp
var index = names.IndexOf("Felipe");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
}
else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");
}

index = names.IndexOf("Not Found");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
}
else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");

}
```

Listenizdeki öğeler de sıralanmış olabilir. <xref:System.Collections.Generic.List%601.Sort%2A> Yöntemi, listedeki tüm öğeleri normal sıralarına göre sıralar (dizeler söz konusu olduğunda alfabetik olarak). Bu kodu `Main` yönteminizin en altına ekleyin:

```csharp
names.Sort();
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

Bu en son sürümü denemek `dotnet run` için dosyayı kaydedin ve yazın.

Sonraki bölüme başlamadan önce geçerli kodu ayrı bir yönteme taşıyalim. Bu, yeni bir örnekle çalışmaya başlamasını kolaylaştırır. Yönteminizi olarak `WorkingWithStrings` yeniden adlandırın ve çağıran `Main` `WorkingWithStrings`yeni bir yöntem yazın. `Main` İşiniz bittiğinde kodunuzun şöyle görünmesi gerekir:

```csharp
using System;
using System.Collections.Generic;

namespace list_tutorial
{
    class Program
    {
        static void Main(string[] args)
        {
            WorkingWithStrings();
        }

        public static void WorkingWithStrings()
        {
            var names = new List<string> { "<name>", "Ana", "Felipe" };
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }

            Console.WriteLine();
            names.Add("Maria");
            names.Add("Bill");
            names.Remove("Ana");
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }

            Console.WriteLine($"My name is {names[0]}");
            Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");

            Console.WriteLine($"The list has {names.Count} people in it");

            var index = names.IndexOf("Felipe");
            Console.WriteLine($"The name {names[index]} is at index {index}");

            var notFound = names.IndexOf("Not Found");
            Console.WriteLine($"When an item is not found, IndexOf returns {notFound}");

            names.Sort();
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

## <a name="lists-of-other-types"></a>Diğer türlerin listeleri

Şu ana kadar listelerdeki `string` türü kullanıyorsunuz. Farklı bir tür kullanalım. <xref:System.Collections.Generic.List%601> Bir sayı kümesi oluşturalım.

Aşağıdakileri yeni `Main` yönteminizin altına ekleyin:

```csharp
var fibonacciNumbers = new List<int> {1, 1};
```

Bu, tamsayıların bir listesini oluşturur ve ilk iki tamsayının değerini 1 değerine ayarlar. Bunlar bir *Fibonaccı sırasının*ilk iki değeri, bir dizi sayı. Her bir sonraki Fibonaccı numarası, önceki iki sayının toplamı alınarak bulunur. Şu kodu ekleyin:

```csharp
var previous = fibonacciNumbers[fibonacciNumbers.Count - 1];
var previous2 = fibonacciNumbers[fibonacciNumbers.Count - 2];

fibonacciNumbers.Add(previous + previous2);

foreach (var item in fibonacciNumbers)
    Console.WriteLine(item);
```

Sonuçları görmek için dosyayı kaydedin `dotnet run` ve yazın.

> [!TIP]
> Yalnızca bu bölüme odaklanmak için, çağıran `WorkingWithStrings();`kodu açıklama olarak ayarlayabilirsiniz. Çağrının önüne şu `/` şekilde iki karakter koymanız yeterlidir:. `// WorkingWithStrings();`

## <a name="challenge"></a>Sına

Bu ve önceki derslerden bazılarını bir araya getirebilirsiniz. Fibonaccı numaralarına en fazla ne kadar derlediğiniz hakkında ' yı genişletin. Dizideki ilk 20 sayıyı oluşturmak için kodu yazmayı deneyin. (İpucu olarak, 20 fibonaccı numarası 6765 ' dir.)

## <a name="complete-challenge"></a>Sınama Tamam

[GitHub 'daki tamamlanmış örnek koda bakarak](https://github.com/dotnet/samples/tree/master/csharp/list-quickstart/Program.cs#L13-L23)örnek bir çözüm görebilirsiniz.

Döngünün her tekrarında, listedeki son iki tamsayının yerine getiriyorsunuz ve bu değeri listeye ekliyor olursunuz. Döngü, listeye 20 öğe ekleyinceye kadar yinelenir.

Tebrikler, liste öğreticisini tamamladınız. Kendi geliştirme ortamınızda [sınıflarla tanışın](introduction-to-classes.md) öğreticisine devam edebilirsiniz.

`List` [Koleksiyonlar](../../../standard/collections/index.md)hakkında [.net Kılavuzu](../../../standard/index.md) konusundaki türle çalışma hakkında daha fazla bilgi edinebilirsiniz. Diğer birçok koleksiyon türünü de öğreneceksiniz.
