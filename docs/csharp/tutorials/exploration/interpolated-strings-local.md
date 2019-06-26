---
title: Dize ilişkilendirme - C# Öğreticisi
description: Bu öğreticide nasıl kullanılacağını gösterir C# biçimlendirilmiş bir ifade eklemek için dize ilişkilendirme özelliğinden daha büyük bir dizedeki sonuçlanır.
author: rpetrusha
ms.author: ronpet
ms.date: 10/23/2018
ms.openlocfilehash: a39ed5b320f16004f4ddcb35a7fcee5869b97137
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2019
ms.locfileid: "67397814"
---
# <a name="use-string-interpolation-to-construct-formatted-strings"></a><span data-ttu-id="70259-103">Dize ilişkilendirme, biçimlendirilmiş dizeler oluşturmak için kullanın</span><span class="sxs-lookup"><span data-stu-id="70259-103">Use string interpolation to construct formatted strings</span></span>

<span data-ttu-id="70259-104">Bu öğreticide nasıl kullanacağınızı öğretir C# [dize ilişkilendirme](../../language-reference/tokens/interpolated.md) değerleri bir tek bir sonuç dizesine eklemek için.</span><span class="sxs-lookup"><span data-stu-id="70259-104">This tutorial teaches you how to use C# [string interpolation](../../language-reference/tokens/interpolated.md) to insert values into a single result string.</span></span> <span data-ttu-id="70259-105">C# kodu yazacak ve derleyerek ve çalıştırarak bunu sonuçlarını göreceksiniz.</span><span class="sxs-lookup"><span data-stu-id="70259-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="70259-106">Öğretici, bir dizi değer bir dize olarak eklemek ve bu değerleri farklı yollarla biçimlendiren işlemini gösteren ders içerir.</span><span class="sxs-lookup"><span data-stu-id="70259-106">The tutorial contains a series of lessons that show you how to insert values into a string and format those values in different ways.</span></span>

<span data-ttu-id="70259-107">Bu öğreticide, geliştirme için kullanabileceğiniz bir makine olmasını bekliyor.</span><span class="sxs-lookup"><span data-stu-id="70259-107">This tutorial expects that you have a machine you can use for development.</span></span> <span data-ttu-id="70259-108">.NET konu [10 dakika içinde kullanmaya başla](https://www.microsoft.com/net/core) Mac, PC veya Linux üzerinde yerel geliştirme ortamınızı ayarlamaya yönelik yönergeler içerir.</span><span class="sxs-lookup"><span data-stu-id="70259-108">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="70259-109">Ayrıca tamamlayabilirsiniz [etkileşimli sürüm](interpolated-strings.yml) tarayıcınızda Bu öğreticinin.</span><span class="sxs-lookup"><span data-stu-id="70259-109">You also can complete the [interactive version](interpolated-strings.yml) of this tutorial in your browser.</span></span>

## <a name="create-an-interpolated-string"></a><span data-ttu-id="70259-110">İlişkilendirilmiş dize oluşturma</span><span class="sxs-lookup"><span data-stu-id="70259-110">Create an interpolated string</span></span>

<span data-ttu-id="70259-111">Adlı bir dizin oluşturmak **ilişkilendirilmiş**.</span><span class="sxs-lookup"><span data-stu-id="70259-111">Create a directory named **interpolated**.</span></span> <span data-ttu-id="70259-112">Geçerli dizin olun ve konsol penceresinden aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="70259-112">Make it the current directory and run the following command from a console window:</span></span>

```console
dotnet new console
```

<span data-ttu-id="70259-113">Bu komut geçerli dizinde yeni bir .NET Core konsol uygulaması oluşturur.</span><span class="sxs-lookup"><span data-stu-id="70259-113">This command creates a new .NET Core console application in the current directory.</span></span>

<span data-ttu-id="70259-114">Açık **Program.cs** satırı değiştirin ve tercih ettiğiniz düzenleyiciyi `Console.WriteLine("Hello World!");` aşağıdaki kodla değiştirin burada `<name>` adınızla:</span><span class="sxs-lookup"><span data-stu-id="70259-114">Open **Program.cs** in your favorite editor, and replace the line `Console.WriteLine("Hello World!");` with the following code, where you replace `<name>` with your name:</span></span>

```csharp
var name = "<name>";
Console.WriteLine($"Hello, {name}. It's a pleasure to meet you!");
```

<span data-ttu-id="70259-115">Bu kod yazarak deneme `dotnet run` konsol pencerenizde.</span><span class="sxs-lookup"><span data-stu-id="70259-115">Try this code by typing `dotnet run` in your console window.</span></span> <span data-ttu-id="70259-116">Programı çalıştırdığınızda karşılamada adınızı içeren tek bir dize görüntüler.</span><span class="sxs-lookup"><span data-stu-id="70259-116">When you run the program, it displays a single string that includes your name in the greeting.</span></span> <span data-ttu-id="70259-117">İçinde yer alan dize <xref:System.Console.WriteLine%2A> yöntem çağrısında bir *ilişkilendirilmiş dize ifadesi*.</span><span class="sxs-lookup"><span data-stu-id="70259-117">The string included in the <xref:System.Console.WriteLine%2A> method call is an *interpolated string expression*.</span></span> <span data-ttu-id="70259-118">Tek bir dize olanak sağlayan bir şablon türüdür (adlı *sonuç dizesi*), gömülü kod içeren bir dizeden.</span><span class="sxs-lookup"><span data-stu-id="70259-118">It's a kind of template that lets you construct a single string (called the *result string*) from a string that includes embedded code.</span></span> <span data-ttu-id="70259-119">İlişkilendirilmiş dizeler özellikle bir dize veya dizeleri birleştirirken (bir araya getirme) değerlerini eklemek için yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="70259-119">Interpolated strings are particularly useful for inserting values into a string or concatenating (joining together) strings.</span></span>

<span data-ttu-id="70259-120">Bu basit örnek her ilişkilendirilmiş dizenin sahip olması gereken iki öğeyi içerir:</span><span class="sxs-lookup"><span data-stu-id="70259-120">This simple example contains the two elements that every interpolated string must have:</span></span>

- <span data-ttu-id="70259-121">İle başlayan bir dize sabit değeri `$` açma tırnak işareti karakterinden önce karakter karakter.</span><span class="sxs-lookup"><span data-stu-id="70259-121">A string literal that begins with the `$` character before its opening quotation mark character.</span></span> <span data-ttu-id="70259-122">Arasında boşluk olamaz `$` sembol ve tırnak işareti karakteri.</span><span class="sxs-lookup"><span data-stu-id="70259-122">There can't be any spaces between the `$` symbol and the quotation mark character.</span></span> <span data-ttu-id="70259-123">(Görmek istiyorsanız, ne olacağını yaptığınızda, sonra boşluk Ekle `$` karakter, dosyayı kaydedin ve yazarak programı yeniden çalıştırın `dotnet run` konsol penceresinde.</span><span class="sxs-lookup"><span data-stu-id="70259-123">(If you'd like to see what happens if you include one, insert a space after the `$` character, save the file, and run the program again by typing `dotnet run` in the console window.</span></span> <span data-ttu-id="70259-124">C# Derleyici bir hata iletisi görüntüler "hatası CS1056: Beklenmeyen karakter '$' ".)</span><span class="sxs-lookup"><span data-stu-id="70259-124">The C# compiler displays an error message, "error CS1056: Unexpected character '$'".)</span></span>

- <span data-ttu-id="70259-125">Bir veya daha fazla *ilişkilendirme ifadeleri*.</span><span class="sxs-lookup"><span data-stu-id="70259-125">One or more *interpolation expressions*.</span></span> <span data-ttu-id="70259-126">Bir ilişkilendirme ifade bir açma ve kapatma ayracı gösterilir (`{` ve `}`).</span><span class="sxs-lookup"><span data-stu-id="70259-126">An interpolation expression is indicated by an opening and closing brace (`{` and `}`).</span></span> <span data-ttu-id="70259-127">Bir değer döndüren bir C# ifadesini ekleyebilirsiniz (dahil olmak üzere `null`) küme ayraçları içinde.</span><span class="sxs-lookup"><span data-stu-id="70259-127">You can put any C# expression that returns a value (including `null`) inside the braces.</span></span>

<span data-ttu-id="70259-128">Diğer veri türlerinden bazılarıyla birkaç daha fazla dize ilişkilendirme örneği deneyelim.</span><span class="sxs-lookup"><span data-stu-id="70259-128">Let's try a few more string interpolation examples with some other data types.</span></span>

## <a name="include-different-data-types"></a><span data-ttu-id="70259-129">Farklı veri türleri ekleme</span><span class="sxs-lookup"><span data-stu-id="70259-129">Include different data types</span></span>

<span data-ttu-id="70259-130">Önceki bölümde, bir dizenin içine eklemek için dize ilişkilendirme kullanılır.</span><span class="sxs-lookup"><span data-stu-id="70259-130">In the previous section, you used string interpolation to insert one string inside of another.</span></span> <span data-ttu-id="70259-131">Bir ilişkilendirme ifadenin sonucu herhangi bir veri türünde ancak olabilir.</span><span class="sxs-lookup"><span data-stu-id="70259-131">The result of an interpolation expression can be of any data type, though.</span></span> <span data-ttu-id="70259-132">Şimdi bir aradeğerlendirme dizesinde değerleri çeşitli veri türlerini içerir.</span><span class="sxs-lookup"><span data-stu-id="70259-132">Let's include values of various data types in an interpolated string.</span></span>

<span data-ttu-id="70259-133">Aşağıdaki örnekte, ilk tanımlarız bir [sınıfı](../../programming-guide/classes-and-structs/classes.md) veri türü `Vegetable` olan bir `Name` [özelliği](../../properties.md) ve `ToString` [yöntemi](../../methods.md), hangi [geçersiz kılmalar](../../language-reference/keywords/override.md) davranışını <xref:System.Object.ToString?displayProperty=nameWithType> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="70259-133">In the following example, we first define a [class](../../programming-guide/classes-and-structs/classes.md) data type `Vegetable` that has a `Name` [property](../../properties.md) and a `ToString` [method](../../methods.md), which [overrides](../../language-reference/keywords/override.md) the behavior of the <xref:System.Object.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="70259-134">[ `public` Erişim değiştiricisi](../../language-reference/keywords/public.md) bu yöntem herhangi bir istemci kod, dize gösterimini almaya kullanılabilmesini bir `Vegetable` örneği.</span><span class="sxs-lookup"><span data-stu-id="70259-134">The [`public` access modifier](../../language-reference/keywords/public.md) makes that method available to any client code to get the string representation of a `Vegetable` instance.</span></span> <span data-ttu-id="70259-135">Örnekte `Vegetable.ToString` yöntemi değerini döndürür `Name` sırasında başlatılır özelliği `Vegetable` [Oluşturucusu](../../programming-guide/classes-and-structs/constructors.md):</span><span class="sxs-lookup"><span data-stu-id="70259-135">In the example the `Vegetable.ToString` method returns the value of the `Name` property that is initialized at the `Vegetable` [constructor](../../programming-guide/classes-and-structs/constructors.md):</span></span>

```csharp
public Vegetable(string name) => Name = name;
```

<span data-ttu-id="70259-136">Biz bir örneğini oluşturup `Vegetable` adlı sınıfı `item` kullanarak [ `new` işleci](../../language-reference/operators/new-operator.md) oluşturucusu için bir ad sağlayarak `Vegetable`:</span><span class="sxs-lookup"><span data-stu-id="70259-136">Then we create an instance of the `Vegetable` class named `item` by using the [`new` operator](../../language-reference/operators/new-operator.md) and providing a name for the constructor `Vegetable`:</span></span>

```csharp
var item = new Vegetable("eggplant");
```

<span data-ttu-id="70259-137">Son olarak, ekliyoruz `item` değişken de içeren ilişkilendirilmiş dize halinde bir <xref:System.DateTime> değeri bir <xref:System.Decimal> değeri ve bir `Unit` [numaralandırması](../../programming-guide/enumeration-types.md) değeri.</span><span class="sxs-lookup"><span data-stu-id="70259-137">Finally, we include the `item` variable into an interpolated string that also contains a <xref:System.DateTime> value, a <xref:System.Decimal> value, and a `Unit` [enumeration](../../programming-guide/enumeration-types.md) value.</span></span> <span data-ttu-id="70259-138">Tüm Düzenleyici C# kodu aşağıdaki kodla değiştirin ve ardından `dotnet run` komutu çalıştırmak için:</span><span class="sxs-lookup"><span data-stu-id="70259-138">Replace all of the C# code in your editor with the following code, and then use the `dotnet run` command to run it:</span></span>

```csharp
using System;

public class Vegetable
{
   public Vegetable(string name) => Name = name;
   
   public string Name { get; }
   
   public override string ToString() => Name;
}

public class Program
{
   public enum Unit { item, kilogram, gram, dozen };

   public static void Main()
   {
      var item = new Vegetable("eggplant");
      var date = DateTime.Now;
      var price = 1.99m;
      var unit = Unit.item;
      Console.WriteLine($"On {date}, the price of {item} was {price} per {unit}.");
   }
}
```

<span data-ttu-id="70259-139">Unutmayın ilişkilendirme ifade `item` aradeğerlendirme dizesinde çözümleniyor sonuç dizesindeki "eggplant" metni.</span><span class="sxs-lookup"><span data-stu-id="70259-139">Note that the interpolation expression `item` in the interpolated string resolves to the text "eggplant" in the result string.</span></span> <span data-ttu-id="70259-140">Deyim sonucu türü dize olmadığı durumlarda, sonuç şu şekilde bir dizeye çözümlenir çünkü:</span><span class="sxs-lookup"><span data-stu-id="70259-140">That's because, when the type of the expression result is not a string, the result is resolved to a string in the following way:</span></span>

- <span data-ttu-id="70259-141">İlişkilendirme ifade değerlendirilirse `null`, boş bir dize ("", veya <xref:System.String.Empty?displayProperty=nameWithType>) kullanılır.</span><span class="sxs-lookup"><span data-stu-id="70259-141">If the interpolation expression evaluates to `null`, an empty string ("", or <xref:System.String.Empty?displayProperty=nameWithType>) is used.</span></span>

- <span data-ttu-id="70259-142">İlişkilendirme ifade değerlendirme değil, `null`, genellikle `ToString` sonuç türü yöntemi çağrılır.</span><span class="sxs-lookup"><span data-stu-id="70259-142">If the interpolation expression doesn't evaluate to `null`, typically the `ToString` method of the result type is called.</span></span> <span data-ttu-id="70259-143">Bu uygulamasını güncelleştirerek test `Vegetable.ToString` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="70259-143">You can test this by updating the implementation of the `Vegetable.ToString` method.</span></span> <span data-ttu-id="70259-144">Bile uygulanması gerekmeyebilir `ToString` her türü bu yöntemin bazı uygulama olduğundan yöntemi.</span><span class="sxs-lookup"><span data-stu-id="70259-144">You might not even need to implement the `ToString` method since every type has some implementation of this method.</span></span> <span data-ttu-id="70259-145">Bunu test etmek için tanımı için açıklama `Vegetable.ToString` örnekte yöntemi (Bunu yapmak için bir açıklama simgesini yerleştirmek `//`, önündeki).</span><span class="sxs-lookup"><span data-stu-id="70259-145">To test this, comment out the definition of the `Vegetable.ToString` method in the example (to do that, put a comment symbol, `//`, in front of it).</span></span> <span data-ttu-id="70259-146">Çıkışta "eggplant" dizesi, varsayılan davranış, tam olarak nitelenmiş tür adıyla ("Vegetable" Bu örnekte), değiştirilir, <xref:System.Object.ToString?displayProperty=nameWithType> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="70259-146">In the output, the string "eggplant" is replaced by the fully qualified type name ("Vegetable" in this example), which is the default behavior of the <xref:System.Object.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="70259-147">Varsayılan davranışını `ToString` yöntemi için bir sabit listesi değeri, değerin dize gösterimi döndürmektir.</span><span class="sxs-lookup"><span data-stu-id="70259-147">The default behavior of the `ToString` method for an enumeration value is to return the string representation of the value.</span></span>

<span data-ttu-id="70259-148">Bu örnek çıktıda, (eggplant fiyatı, her saniye değişmez) kesin tarih ve Fiyat değerini para birimi göstermez.</span><span class="sxs-lookup"><span data-stu-id="70259-148">In the output from this example, the date is too precise (the price of eggplant doesn't change every second), and the price value doesn't indicate a unit of currency.</span></span> <span data-ttu-id="70259-149">Sonraki bölümde, ifade sonuçları dize temsillerini biçimini denetleyerek bu sorunları gidermek nasıl öğreneceksiniz.</span><span class="sxs-lookup"><span data-stu-id="70259-149">In the next section, you'll learn how to fix those issues by controlling the format of string representations of the expression results.</span></span>

## <a name="control-the-formatting-of-interpolation-expressions"></a><span data-ttu-id="70259-150">İlişkilendirme ifadelerin biçimlendirmesini denetleme</span><span class="sxs-lookup"><span data-stu-id="70259-150">Control the formatting of interpolation expressions</span></span>

<span data-ttu-id="70259-151">Önceki bölümde, sonuç dizesine yetersiz şekilde biçimlendirilmiş iki dize eklenmişti.</span><span class="sxs-lookup"><span data-stu-id="70259-151">In the previous section, two poorly formatted strings were inserted into the result string.</span></span> <span data-ttu-id="70259-152">Bir tarih yalnızca uygun bir tarih ve saat değeri oluştu.</span><span class="sxs-lookup"><span data-stu-id="70259-152">One was a date and time value for which only the date was appropriate.</span></span> <span data-ttu-id="70259-153">İkinci para biriminin göstermek istemediğiniz bir fiyattı.</span><span class="sxs-lookup"><span data-stu-id="70259-153">The second was a price that didn't indicate its unit of currency.</span></span> <span data-ttu-id="70259-154">Her iki sorun da kolayca giderilebilir.</span><span class="sxs-lookup"><span data-stu-id="70259-154">Both issues are easy to address.</span></span> <span data-ttu-id="70259-155">Dize ilişkilendirme belirtmenize olanak tanır *biçim dizeleri* belirli türlerin biçimlendirmesini denetleyen.</span><span class="sxs-lookup"><span data-stu-id="70259-155">String interpolation lets you specify *format strings* that control the formatting of particular types.</span></span> <span data-ttu-id="70259-156">Çağrısını değiştirin `Console.WriteLine` aşağıdaki satırda gösterildiği gibi tarih ve fiyat ifadeler için biçim dizeleri dahil etmek için önceki örnekte:</span><span class="sxs-lookup"><span data-stu-id="70259-156">Modify the call to `Console.WriteLine` from the previous example to include the format strings for the date and price expressions as shown in the following line:</span></span>

```csharp
Console.WriteLine($"On {date:d}, the price of {item} was {price:C2} per {unit}.");
```

<span data-ttu-id="70259-157">İki nokta ile ilişkilendirme ifade izleyerek bir biçim dizesi belirtin (":") ve biçim dizesi.</span><span class="sxs-lookup"><span data-stu-id="70259-157">You specify a format string by following the interpolation expression with a colon (":") and the format string.</span></span> <span data-ttu-id="70259-158">"d" bir [standart tarih ve saat biçim dizesi](../../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier) temsil eden kısa tarih biçimi.</span><span class="sxs-lookup"><span data-stu-id="70259-158">"d" is a [standard date and time format string](../../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier) that represents the short date format.</span></span> <span data-ttu-id="70259-159">"C2" olan bir [standart sayısal biçim dizesi](../../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier) , bir sayı olarak iki basamakla para birimi değeri ondalık ayırıcıdan sonra temsil eder.</span><span class="sxs-lookup"><span data-stu-id="70259-159">"C2" is a  [standard numeric format string](../../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier) that represents a number as a currency value with two digits after the decimal point.</span></span>

<span data-ttu-id="70259-160">.NET kitaplıklarına türlerinde bir dizi önceden tanımlanmış bir dizi biçim dizesini destekler.</span><span class="sxs-lookup"><span data-stu-id="70259-160">A number of types in the .NET libraries support a predefined set of format strings.</span></span> <span data-ttu-id="70259-161">Bunlar, tüm sayısal türlerin ve tarih ve saat türleri içerir.</span><span class="sxs-lookup"><span data-stu-id="70259-161">These include all the numeric types and the date and time types.</span></span> <span data-ttu-id="70259-162">Biçim dizelerini destekleyen türler tam bir listesi için bkz. [biçim dizeleri ve .NET sınıfı kitaplık türleri](../../../standard/base-types/formatting-types.md#stringRef) içinde [NET'teki biçimlendirme türleri](../../../standard/base-types/formatting-types.md) makalesi.</span><span class="sxs-lookup"><span data-stu-id="70259-162">For a complete list of types that support format strings, see [Format Strings and .NET Class Library Types](../../../standard/base-types/formatting-types.md#stringRef) in the [Formatting Types in .NET](../../../standard/base-types/formatting-types.md) article.</span></span>

<span data-ttu-id="70259-163">Metin düzenleyici ve tarih ve saat ile sayısal biçimlendirme değişikliklerin nasıl etkilediğini görmek için programı yeniden çalıştırın ve değişiklik yaptığınızda her zaman'daki biçim dizelerini değiştirmeyi deneyin.</span><span class="sxs-lookup"><span data-stu-id="70259-163">Try modifying the format strings in your text editor and, each time you make a change, rerun the program to see how the changes affect the formatting of the date and time and the numeric value.</span></span> <span data-ttu-id="70259-164">"D" değiştirmek `{date:d}` "(kısa saat biçimini görüntülemek için) t", "(yıl ve ay görüntülemek için) y" ve "yyyy" (yılı dört basamaklı bir sayı görüntülemek için).</span><span class="sxs-lookup"><span data-stu-id="70259-164">Change the "d" in `{date:d}` to "t" (to display the short time format), "y" (to display the year and month), and "yyyy" (to display the year as a four-digit number).</span></span> <span data-ttu-id="70259-165">"C2" değiştirmek `{price:C2}` (üstel gösterim için için) "e" ve "F3" (için ondalık ayırıcıdan sonra üç basamak içeren sayısal bir değer).</span><span class="sxs-lookup"><span data-stu-id="70259-165">Change the "C2" in `{price:C2}` to "e" (for exponential notation) and "F3" (for a numeric value with three digits after the decimal point).</span></span>

<span data-ttu-id="70259-166">Biçimlendirmenin yanı sıra alan genişliğini ve sonuç dizesine eklenir biçimlendirilmiş dizeler hizalamasını da denetleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="70259-166">In addition to controlling formatting, you can also control the field width and alignment of the formatted strings that are included in the result string.</span></span> <span data-ttu-id="70259-167">Sonraki bölümde, bunun nasıl yapılacağını öğreneceksiniz.</span><span class="sxs-lookup"><span data-stu-id="70259-167">In the next section, you'll learn how to do this.</span></span>

## <a name="control-the-field-width-and-alignment-of-interpolation-expressions"></a><span data-ttu-id="70259-168">Alan genişliğini ve hizalamasını ilişkilendirme ifadeleri denetleme</span><span class="sxs-lookup"><span data-stu-id="70259-168">Control the field width and alignment of interpolation expressions</span></span>

<span data-ttu-id="70259-169">Bir ilişkilendirme ifadenin sonucu dize olarak biçimlendirildiğinde normalde, bu dize bir sonuç dizesinde baştaki veya sondaki boşluk olmadan dahil edilir.</span><span class="sxs-lookup"><span data-stu-id="70259-169">Ordinarily, when the result of an interpolation expression is formatted to string, that string is included in a result string without leading or trailing spaces.</span></span> <span data-ttu-id="70259-170">Özellikle bir veri kümesiyle bir alan genişliğini denetleyebilir çalışırken ve metin hizalamasını daha okunabilir bir çıktı oluşturmak için yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="70259-170">Particularly when you work with a set of data, being able to control a field width and text alignment helps to produce a more readable output.</span></span> <span data-ttu-id="70259-171">Ardından, metin düzenleyici tüm kodu aşağıdaki kodla değiştirin. Bu görmek için şunu yazın `dotnet run` programı çalıştırmak için:</span><span class="sxs-lookup"><span data-stu-id="70259-171">To see this, replace all the code in your text editor with the following code, then type `dotnet run` to execute the program:</span></span>

```csharp
using System;
using System.Collections.Generic;

public class Example
{
   public static void Main()
   {
      var titles = new Dictionary<string, string>()
      {
          ["Doyle, Arthur Conan"] = "Hound of the Baskervilles, The",
          ["London, Jack"] = "Call of the Wild, The",
          ["Shakespeare, William"] = "Tempest, The"
      };

      Console.WriteLine("Author and Title List");
      Console.WriteLine();
      Console.WriteLine($"|{"Author",-25}|{"Title",30}|");
      foreach (var title in titles)
         Console.WriteLine($"|{title.Key,-25}|{title.Value,30}|");
   }
}
```

<span data-ttu-id="70259-172">Yazarlar adları sola hizalanmış ve bunlar yazdı başlıkları sağa hizalanır.</span><span class="sxs-lookup"><span data-stu-id="70259-172">The names of authors are left-aligned, and the titles they wrote are right-aligned.</span></span> <span data-ttu-id="70259-173">Virgül ekleyerek hizalamayı belirtin (",") sonra bir ilişkilendirme ifade ve belirleme *minimum* alan genişliği.</span><span class="sxs-lookup"><span data-stu-id="70259-173">You specify the alignment by adding a comma (",") after an interpolation expression and designating the *minimum* field width.</span></span> <span data-ttu-id="70259-174">Belirtilen değer pozitif bir sayıysa alan sağa hizalanır.</span><span class="sxs-lookup"><span data-stu-id="70259-174">If the specified value is a positive number, the field is right-aligned.</span></span> <span data-ttu-id="70259-175">Negatif bir sayı ise, alan sola hizalanır.</span><span class="sxs-lookup"><span data-stu-id="70259-175">If it is a negative number, the field is left-aligned.</span></span>

<span data-ttu-id="70259-176">Negatif işaretlerini kaldırmayı deneyip `{"Author",-25}` ve `{title.Key,-25}` kodu ve şu kod gibi örneği tekrar çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="70259-176">Try removing the negative signs from the `{"Author",-25}` and `{title.Key,-25}` code and run the example again, as the following code does:</span></span>

```csharp
Console.WriteLine($"|{"Author",25}|{"Title",30}|");
foreach (var title in titles)
   Console.WriteLine($"|{title.Key,25}|{title.Value,30}|");
```

<span data-ttu-id="70259-177">Bu kez, yazar bilgileri sağa hizalanır.</span><span class="sxs-lookup"><span data-stu-id="70259-177">This time, the author information is right-aligned.</span></span>

<span data-ttu-id="70259-178">Hizalama tanımlayıcısı ve bir biçim dizesi tek ilişkilendirme ifadesi için birleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="70259-178">You can combine an alignment specifier and a format string for a single interpolation expression.</span></span> <span data-ttu-id="70259-179">Bunu yapmak için ardından iki nokta işareti ve biçim dizesi hizalama ilk olarak belirtin.</span><span class="sxs-lookup"><span data-stu-id="70259-179">To do that, specify the alignment first, followed by a colon and the format string.</span></span> <span data-ttu-id="70259-180">Tüm kod içinde değiştirmek `Main` ile biçimlendirilmiş üç dizeyi görüntüleyen yöntemini aşağıdaki kodla alan genişlikleri tanımlı.</span><span class="sxs-lookup"><span data-stu-id="70259-180">Replace all of the code inside the `Main` method with the following code, which displays three formatted strings with defined field widths.</span></span> <span data-ttu-id="70259-181">Ardından girerek programı çalıştırın `dotnet run` komutu.</span><span class="sxs-lookup"><span data-stu-id="70259-181">Then run the program by entering the `dotnet run` command.</span></span>

```csharp
Console.WriteLine($"[{DateTime.Now,-20:d}] Hour [{DateTime.Now,-10:HH}] [{1063.342,15:N2}] feet");
```

<span data-ttu-id="70259-182">Çıktı aşağıdakine benzer olacaktır:</span><span class="sxs-lookup"><span data-stu-id="70259-182">The output looks something like the following:</span></span>

```console
[04/14/2018          ] Hour [16        ] [       1,063.34] feet
```

<span data-ttu-id="70259-183">Dize ilişkilendirme öğreticisini tamamladınız.</span><span class="sxs-lookup"><span data-stu-id="70259-183">You've completed the string interpolation tutorial.</span></span>

<span data-ttu-id="70259-184">Daha fazla bilgi için [dize ilişkilendirme](../../language-reference/tokens/interpolated.md) konu ve [dize ilişkilendirme C#](../../tutorials/string-interpolation.md) öğretici.</span><span class="sxs-lookup"><span data-stu-id="70259-184">For more information, see the [String interpolation](../../language-reference/tokens/interpolated.md) topic and the [String interpolation in C#](../../tutorials/string-interpolation.md) tutorial.</span></span>
