---
title: C# dilinde koleksiyonlar üzerinden yineleme yapma
ms.date: 08/14/2018
ms.assetid: c93f6dd4-e72a-4a06-be1c-a98b3255b734
ms.openlocfilehash: 2b0e1d509cf80e13d2cee3cf0ddf2021d6c84c5b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61668503"
---
# <a name="iterators-c"></a><span data-ttu-id="d3da2-102">Yineleyiciler (C#)</span><span class="sxs-lookup"><span data-stu-id="d3da2-102">Iterators (C#)</span></span>

<span data-ttu-id="d3da2-103">Bir *yineleyici* koleksiyonlarına listeler ve diziler gibi adım için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="d3da2-103">An *iterator* can be used to step through collections such as lists and arrays.</span></span>

<span data-ttu-id="d3da2-104">Yineleyici yöntemini veya `get` erişimci bir koleksiyon üzerinde özel yineleme gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="d3da2-104">An iterator method or `get` accessor performs a custom iteration over a collection.</span></span> <span data-ttu-id="d3da2-105">Yineleyici yöntemini kullanır [yield return](../../../csharp/language-reference/keywords/yield.md) her öğeyi bir defada döndürmek için deyimi.</span><span class="sxs-lookup"><span data-stu-id="d3da2-105">An iterator method uses the [yield return](../../../csharp/language-reference/keywords/yield.md) statement to return each element one at a time.</span></span> <span data-ttu-id="d3da2-106">Olduğunda bir `yield return` deyimine ulaşıldığında, kodun geçerli konumu anımsanacak.</span><span class="sxs-lookup"><span data-stu-id="d3da2-106">When a `yield return` statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="d3da2-107">Yürütme, yineleyici işlevinin bir sonraki zamana o konumdan başlatılır.</span><span class="sxs-lookup"><span data-stu-id="d3da2-107">Execution is restarted from that location the next time the iterator function is called.</span></span>

<span data-ttu-id="d3da2-108">Kullanarak bir yineleyici istemci kodundan kullanmak bir [foreach](../../../csharp/language-reference/keywords/foreach-in.md) deyimini veya LINQ sorgusu kullanarak.</span><span class="sxs-lookup"><span data-stu-id="d3da2-108">You consume an iterator from client code by using a [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement or by using a LINQ query.</span></span>

<span data-ttu-id="d3da2-109">Aşağıdaki örnekte, ilk yinelemeyi `foreach` döngüye neden oluyor, devam etmek yürütme `SomeNumbers` yineleyici yöntemin ilk kadar `yield return` deyimine ulaşıldığında.</span><span class="sxs-lookup"><span data-stu-id="d3da2-109">In the following example, the first iteration of the `foreach` loop causes execution to proceed in the `SomeNumbers` iterator method until the first `yield return` statement is reached.</span></span> <span data-ttu-id="d3da2-110">Bu yineleme 3 değerini döndürür ve yineleyici yöntem geçerli konumu korunur.</span><span class="sxs-lookup"><span data-stu-id="d3da2-110">This iteration returns a value of 3, and the current location in the iterator method is retained.</span></span> <span data-ttu-id="d3da2-111">Döngüsünün sonraki yinelemesinde, yineleyici yöntemin yürütülmesine kadar devam eder, ulaştığında yeniden kaldığı bir `yield return` deyimi.</span><span class="sxs-lookup"><span data-stu-id="d3da2-111">On the next iteration of the loop, execution in the iterator method continues from where it left off, again stopping when it reaches a `yield return` statement.</span></span> <span data-ttu-id="d3da2-112">Bu yineleme 5 değerini döndürür ve yineleyici yöntem geçerli konumu tekrar korunur.</span><span class="sxs-lookup"><span data-stu-id="d3da2-112">This iteration returns a value of 5, and the current location in the iterator method is again retained.</span></span> <span data-ttu-id="d3da2-113">Yineleyici yöntemin sonuna ulaşıldığında döngüsünü tamamlar.</span><span class="sxs-lookup"><span data-stu-id="d3da2-113">The loop completes when the end of the iterator method is reached.</span></span>

```csharp
static void Main()
{
    foreach (int number in SomeNumbers())
    {
        Console.Write(number.ToString() + " ");
    }
    // Output: 3 5 8
    Console.ReadKey();
}

public static System.Collections.IEnumerable SomeNumbers()
{
    yield return 3;
    yield return 5;
    yield return 8;
}
```

<span data-ttu-id="d3da2-114">Bir yineleyici yöntemin dönüş türü veya `get` erişimcisi olabilir <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, veya <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="d3da2-114">The return type of an iterator method or `get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

<span data-ttu-id="d3da2-115">Kullanabileceğiniz bir `yield break` yinelemeyi sonlandırmak için deyimi.</span><span class="sxs-lookup"><span data-stu-id="d3da2-115">You can use a `yield break` statement to end the iteration.</span></span>

> [!NOTE]
> <span data-ttu-id="d3da2-116">Bu konuda, basit bir yineleyici örnek hariç tüm örnekler için dahil [kullanarak](../../../csharp/language-reference/keywords/using-directive.md) yönergeleri `System.Collections` ve `System.Collections.Generic` ad alanları.</span><span class="sxs-lookup"><span data-stu-id="d3da2-116">For all examples in this topic except the Simple Iterator example, include [using](../../../csharp/language-reference/keywords/using-directive.md) directives for the `System.Collections` and `System.Collections.Generic` namespaces.</span></span>

## <a name="simple-iterator"></a><span data-ttu-id="d3da2-117">Basit bir yineleyici</span><span class="sxs-lookup"><span data-stu-id="d3da2-117">Simple Iterator</span></span>

<span data-ttu-id="d3da2-118">Aşağıdaki örnek, tek bir sahip `yield return` içindeki bir [için](../../../csharp/language-reference/keywords/for.md) döngü.</span><span class="sxs-lookup"><span data-stu-id="d3da2-118">The following example has a single `yield return` statement that is inside a [for](../../../csharp/language-reference/keywords/for.md) loop.</span></span> <span data-ttu-id="d3da2-119">İçinde `Main`, her bir yinelemesini `foreach` diğerine geçer yineleyici işlevine bir çağrı oluşturur ve deyim gövdesi `yield return` deyimi.</span><span class="sxs-lookup"><span data-stu-id="d3da2-119">In `Main`, each iteration of the `foreach` statement body creates a call to the iterator function, which proceeds to the next `yield return` statement.</span></span>

```csharp
static void Main()
{
    foreach (int number in EvenSequence(5, 18))
    {
        Console.Write(number.ToString() + " ");
    }
    // Output: 6 8 10 12 14 16 18
    Console.ReadKey();
}

public static System.Collections.Generic.IEnumerable<int>
    EvenSequence(int firstNumber, int lastNumber)
{
    // Yield even numbers in the range.
    for (int number = firstNumber; number <= lastNumber; number++)
    {
        if (number % 2 == 0)
        {
            yield return number;
        }
    }
}
```

## <a name="creating-a-collection-class"></a><span data-ttu-id="d3da2-120">Koleksiyon sınıfı oluşturma</span><span class="sxs-lookup"><span data-stu-id="d3da2-120">Creating a Collection Class</span></span>

<span data-ttu-id="d3da2-121">Aşağıdaki örnekte, `DaysOfTheWeek` sınıfının Implements <xref:System.Collections.IEnumerable> gerektiren arabirimi bir <xref:System.Collections.IEnumerable.GetEnumerator%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="d3da2-121">In the following example, the `DaysOfTheWeek` class implements the <xref:System.Collections.IEnumerable> interface, which requires a <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="d3da2-122">Derleyici örtük olarak çağırır `GetEnumerator` döndüren yöntemi bir <xref:System.Collections.IEnumerator>.</span><span class="sxs-lookup"><span data-stu-id="d3da2-122">The compiler implicitly calls the `GetEnumerator` method, which returns an <xref:System.Collections.IEnumerator>.</span></span>

<span data-ttu-id="d3da2-123">`GetEnumerator` Yöntemi döndürür her dize bir kerede kullanarak `yield return` deyimi.</span><span class="sxs-lookup"><span data-stu-id="d3da2-123">The `GetEnumerator` method returns each string one at a time by using the `yield return` statement.</span></span>

```csharp
static void Main()
{
    DaysOfTheWeek days = new DaysOfTheWeek();

    foreach (string day in days)
    {
        Console.Write(day + " ");
    }
    // Output: Sun Mon Tue Wed Thu Fri Sat
    Console.ReadKey();
}

public class DaysOfTheWeek : IEnumerable
{
    private string[] days = { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" };

    public IEnumerator GetEnumerator()
    {
        for (int index = 0; index < days.Length; index++)
        {
            // Yield each day of the week.
            yield return days[index];
        }
    }
}
```

<span data-ttu-id="d3da2-124">Aşağıdaki örnek, oluşturur bir `Zoo` hayvanlar koleksiyonunu içeren sınıf.</span><span class="sxs-lookup"><span data-stu-id="d3da2-124">The following example creates a `Zoo` class that contains a collection of animals.</span></span>

<span data-ttu-id="d3da2-125">`foreach` Sınıfı örneğini ifade deyimi (`theZoo`) örtük olarak çağırır `GetEnumerator` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="d3da2-125">The `foreach` statement that refers to the class instance (`theZoo`) implicitly calls the `GetEnumerator` method.</span></span> <span data-ttu-id="d3da2-126">`foreach` Başvurmak ifadeleri `Birds` ve `Mammals` özellikleri kullanım `AnimalsForType` yineleyici yöntemin adı.</span><span class="sxs-lookup"><span data-stu-id="d3da2-126">The `foreach` statements that refer to the `Birds` and `Mammals` properties use the `AnimalsForType` named iterator method.</span></span>

```csharp
static void Main()
{
    Zoo theZoo = new Zoo();

    theZoo.AddMammal("Whale");
    theZoo.AddMammal("Rhinoceros");
    theZoo.AddBird("Penguin");
    theZoo.AddBird("Warbler");

    foreach (string name in theZoo)
    {
        Console.Write(name + " ");
    }
    Console.WriteLine();
    // Output: Whale Rhinoceros Penguin Warbler

    foreach (string name in theZoo.Birds)
    {
        Console.Write(name + " ");
    }
    Console.WriteLine();
    // Output: Penguin Warbler

    foreach (string name in theZoo.Mammals)
    {
        Console.Write(name + " ");
    }
    Console.WriteLine();
    // Output: Whale Rhinoceros

    Console.ReadKey();
}

public class Zoo : IEnumerable
{
    // Private members.
    private List<Animal> animals = new List<Animal>();

    // Public methods.
    public void AddMammal(string name)
    {
        animals.Add(new Animal { Name = name, Type = Animal.TypeEnum.Mammal });
    }

    public void AddBird(string name)
    {
        animals.Add(new Animal { Name = name, Type = Animal.TypeEnum.Bird });
    }

    public IEnumerator GetEnumerator()
    {
        foreach (Animal theAnimal in animals)
        {
            yield return theAnimal.Name;
        }
    }

    // Public members.
    public IEnumerable Mammals
    {
        get { return AnimalsForType(Animal.TypeEnum.Mammal); }
    }

    public IEnumerable Birds
    {
        get { return AnimalsForType(Animal.TypeEnum.Bird); }
    }

    // Private methods.
    private IEnumerable AnimalsForType(Animal.TypeEnum type)
    {
        foreach (Animal theAnimal in animals)
        {
            if (theAnimal.Type == type)
            {
                yield return theAnimal.Name;
            }
        }
    }

    // Private class.
    private class Animal
    {
        public enum TypeEnum { Bird, Mammal }

        public string Name { get; set; }
        public TypeEnum Type { get; set; }
    }
}
```

## <a name="using-iterators-with-a-generic-list"></a><span data-ttu-id="d3da2-127">Yineleyiciler genel listeyle kullanma</span><span class="sxs-lookup"><span data-stu-id="d3da2-127">Using Iterators with a Generic List</span></span>

<span data-ttu-id="d3da2-128">Aşağıdaki örnekte, <xref:System.Collections.Generic.Stack%601> genel bir sınıf uygulayan <xref:System.Collections.Generic.IEnumerable%601> genel arabirim.</span><span class="sxs-lookup"><span data-stu-id="d3da2-128">In the following example, the <xref:System.Collections.Generic.Stack%601> generic class implements the <xref:System.Collections.Generic.IEnumerable%601> generic interface.</span></span> <span data-ttu-id="d3da2-129"><xref:System.Collections.Generic.Stack%601.Push%2A> Yöntemi, bir dizi türüne değerleri atar `T`.</span><span class="sxs-lookup"><span data-stu-id="d3da2-129">The <xref:System.Collections.Generic.Stack%601.Push%2A> method assigns values to an array of type `T`.</span></span> <span data-ttu-id="d3da2-130"><xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> Yöntemi kullanarak dizi değerlerini döndürür `yield return` deyimi.</span><span class="sxs-lookup"><span data-stu-id="d3da2-130">The <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method returns the array values by using the `yield return` statement.</span></span>

<span data-ttu-id="d3da2-131">Genel yanı sıra <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> yöntem, genel olmayan <xref:System.Collections.IEnumerable.GetEnumerator%2A> yöntemi de uygulanmalı.</span><span class="sxs-lookup"><span data-stu-id="d3da2-131">In addition to the generic <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method, the non-generic <xref:System.Collections.IEnumerable.GetEnumerator%2A> method must also be implemented.</span></span> <span data-ttu-id="d3da2-132">Bunun nedeni, <xref:System.Collections.Generic.IEnumerable%601> devraldığı <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="d3da2-132">This is because <xref:System.Collections.Generic.IEnumerable%601> inherits from <xref:System.Collections.IEnumerable>.</span></span> <span data-ttu-id="d3da2-133">Genel olmayan uygulama için genel uygulamasını erteler.</span><span class="sxs-lookup"><span data-stu-id="d3da2-133">The non-generic implementation defers to the generic implementation.</span></span>

<span data-ttu-id="d3da2-134">Örneğin, verilerin aynı koleksiyon aracılığıyla yineleme çeşitli yöntemler desteklemek için adlandırılmış yineleyiciler kullanır.</span><span class="sxs-lookup"><span data-stu-id="d3da2-134">The example uses named iterators to support various ways of iterating through the same collection of data.</span></span> <span data-ttu-id="d3da2-135">Bunlar yineleyiciler adlı `TopToBottom` ve `BottomToTop` özellikleri ve `TopN` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="d3da2-135">These named iterators are the `TopToBottom` and `BottomToTop` properties, and the `TopN` method.</span></span>

<span data-ttu-id="d3da2-136">`BottomToTop` Özelliği kullanan bir yineleyici içinde bir `get` erişimcisi.</span><span class="sxs-lookup"><span data-stu-id="d3da2-136">The `BottomToTop` property uses an iterator in a `get` accessor.</span></span>

```csharp
static void Main()
{
    Stack<int> theStack = new Stack<int>();

    //  Add items to the stack.
    for (int number = 0; number <= 9; number++)
    {
        theStack.Push(number);
    }

    // Retrieve items from the stack.
    // foreach is allowed because theStack implements IEnumerable<int>.
    foreach (int number in theStack)
    {
        Console.Write("{0} ", number);
    }
    Console.WriteLine();
    // Output: 9 8 7 6 5 4 3 2 1 0

    // foreach is allowed, because theStack.TopToBottom returns IEnumerable(Of Integer).
    foreach (int number in theStack.TopToBottom)
    {
        Console.Write("{0} ", number);
    }
    Console.WriteLine();
    // Output: 9 8 7 6 5 4 3 2 1 0

    foreach (int number in theStack.BottomToTop)
    {
        Console.Write("{0} ", number);
    }
    Console.WriteLine();
    // Output: 0 1 2 3 4 5 6 7 8 9

    foreach (int number in theStack.TopN(7))
    {
        Console.Write("{0} ", number);
    }
    Console.WriteLine();
    // Output: 9 8 7 6 5 4 3

    Console.ReadKey();
}

public class Stack<T> : IEnumerable<T>
{
    private T[] values = new T[100];
    private int top = 0;

    public void Push(T t)
    {
        values[top] = t;
        top++;
    }
    public T Pop()
    {
        top--;
        return values[top];
    }

    // This method implements the GetEnumerator method. It allows
    // an instance of the class to be used in a foreach statement.
    public IEnumerator<T> GetEnumerator()
    {
        for (int index = top - 1; index >= 0; index--)
        {
            yield return values[index];
        }
    }

    IEnumerator IEnumerable.GetEnumerator()
    {
        return GetEnumerator();
    }

    public IEnumerable<T> TopToBottom
    {
        get { return this; }
    }

    public IEnumerable<T> BottomToTop
    {
        get
        {
            for (int index = 0; index <= top - 1; index++)
            {
                yield return values[index];
            }
        }
    }

    public IEnumerable<T> TopN(int itemsFromTop)
    {
        // Return less than itemsFromTop if necessary.
        int startIndex = itemsFromTop >= top ? 0 : top - itemsFromTop;

        for (int index = top - 1; index >= startIndex; index--)
        {
            yield return values[index];
        }
    }

}
```

## <a name="syntax-information"></a><span data-ttu-id="d3da2-137">Söz dizimi bilgileri</span><span class="sxs-lookup"><span data-stu-id="d3da2-137">Syntax Information</span></span>

<span data-ttu-id="d3da2-138">Yineleyici yöntem olarak oluşabilir veya `get` erişimcisi.</span><span class="sxs-lookup"><span data-stu-id="d3da2-138">An iterator can occur as a method or `get` accessor.</span></span> <span data-ttu-id="d3da2-139">Bir yineleyiciyi bir olay, örnek oluşturucusu, statik oluşturucu veya statik Sonlandırıcı oluşamaz.</span><span class="sxs-lookup"><span data-stu-id="d3da2-139">An iterator cannot occur in an event, instance constructor, static constructor, or static finalizer.</span></span>

<span data-ttu-id="d3da2-140">Örtük bir dönüştürme ifadesi türden bulunmalıdır `yield return` IEnumerable tür bağımsız değişkeni ifadesine\<T > döndürülen yineleyici tarafından.</span><span class="sxs-lookup"><span data-stu-id="d3da2-140">An implicit conversion must exist from the expression type in the `yield return` statement to the type argument for the IEnumerable\<T> returned by the iterator.</span></span>

<span data-ttu-id="d3da2-141">C# ' ta bir yineleyici yöntemini içeremez `in`, `ref`, veya `out` parametreleri.</span><span class="sxs-lookup"><span data-stu-id="d3da2-141">In C#, an iterator method cannot have any `in`, `ref`, or `out` parameters.</span></span>

<span data-ttu-id="d3da2-142">C# ' ta, "yield" ayrılmış bir sözcük değildir ve yalnızca önce kullanıldığında özel anlamı bir `return` veya `break` anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="d3da2-142">In C#, "yield" is not a reserved word and has special meaning only when it is used before a `return` or `break` keyword.</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="d3da2-143">Teknik Uygulama</span><span class="sxs-lookup"><span data-stu-id="d3da2-143">Technical Implementation</span></span>

<span data-ttu-id="d3da2-144">Bir yöntem olarak bir yineleyici yazma olsa da, derleyici, iç içe geçmiş bir sınıf içinde başka bir deyişle, aslında bir Durum makinesi çevirir.</span><span class="sxs-lookup"><span data-stu-id="d3da2-144">Although you write an iterator as a method, the compiler translates it into a nested class that is, in effect, a state machine.</span></span> <span data-ttu-id="d3da2-145">Bu sınıf olarak uzun yineleyici konumunu izler `foreach` istemci kodu döngüde devam eder.</span><span class="sxs-lookup"><span data-stu-id="d3da2-145">This class keeps track of the position of the iterator as long the `foreach` loop in the client code continues.</span></span>

<span data-ttu-id="d3da2-146">Derleyicinin ne yaptığını görmek için bir yineleyici yöntem için oluşturulan Microsoft Ara dil kodunu görüntülemek için Ildasm.exe Aracı'nı kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d3da2-146">To see what the compiler does, you can use the Ildasm.exe tool to view the Microsoft intermediate language code that's generated for an iterator method.</span></span>

<span data-ttu-id="d3da2-147">İçin bir yineleyici oluşturduğunuzda bir [sınıfı](../../../csharp/language-reference/keywords/class.md) veya [yapı](../../../csharp/language-reference/keywords/struct.md), tam uygulamanız gerekmez <xref:System.Collections.IEnumerator> arabirimi.</span><span class="sxs-lookup"><span data-stu-id="d3da2-147">When you create an iterator for a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md), you don't have to implement the whole <xref:System.Collections.IEnumerator> interface.</span></span> <span data-ttu-id="d3da2-148">Derleyici yineleyici algıladığında otomatik olarak oluşturduğu `Current`, `MoveNext`, ve `Dispose` yöntemlerinin <xref:System.Collections.IEnumerator> veya <xref:System.Collections.Generic.IEnumerator%601> arabirimi.</span><span class="sxs-lookup"><span data-stu-id="d3da2-148">When the compiler detects the iterator, it automatically generates the `Current`, `MoveNext`, and `Dispose` methods of the <xref:System.Collections.IEnumerator> or <xref:System.Collections.Generic.IEnumerator%601> interface.</span></span>

<span data-ttu-id="d3da2-149">Her yinelemede üzerinde `foreach` döngü (veya doğrudan arama `IEnumerator.MoveNext`), İleri yineleyici kod gövdesi önceki sonra sürdürür `yield return` deyimi.</span><span class="sxs-lookup"><span data-stu-id="d3da2-149">On each successive iteration of the `foreach` loop (or the direct call to `IEnumerator.MoveNext`), the next iterator code body resumes after the previous `yield return` statement.</span></span> <span data-ttu-id="d3da2-150">Daha sonra bir sonraki sürdürür `yield return` yineleyici gövdenin sonuna ulaşılana kadar bir deyimi veya kadar bir `yield break` deyimi karşılaştı.</span><span class="sxs-lookup"><span data-stu-id="d3da2-150">It then continues to the next `yield return` statement until the end of the iterator body is reached, or until a `yield break` statement is encountered.</span></span>

<span data-ttu-id="d3da2-151">Yineleyicileri desteklemez <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=nameWithType> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="d3da2-151">Iterators don't support the <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="d3da2-152">Başlangıçtan itibaren yinelemek için yeni bir yineleyici edinmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="d3da2-152">To reiterate from the start, you must obtain a new iterator.</span></span> <span data-ttu-id="d3da2-153">Çağırma <xref:System.Collections.IEnumerator.Reset%2A> üzerinde bir yineleyici yöntem tarafından döndürülen yineleyici oluşturur bir <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="d3da2-153">Calling <xref:System.Collections.IEnumerator.Reset%2A> on the iterator returned by an iterator method throws a <xref:System.NotSupportedException>.</span></span>

<span data-ttu-id="d3da2-154">Ek bilgi için bkz: [C# dil belirtimi](~/_csharplang/spec/classes.md#iterators).</span><span class="sxs-lookup"><span data-stu-id="d3da2-154">For additional information, see the [C# Language Specification](~/_csharplang/spec/classes.md#iterators).</span></span>

## <a name="use-of-iterators"></a><span data-ttu-id="d3da2-155">Yineleyicilerin kullanın</span><span class="sxs-lookup"><span data-stu-id="d3da2-155">Use of Iterators</span></span>

<span data-ttu-id="d3da2-156">Yineleyiciler basitliğinin korumak etkinleştirme bir `foreach` döngü listesi sırası doldurmak için karmaşık kodlar kullanmanız gerektiğinde.</span><span class="sxs-lookup"><span data-stu-id="d3da2-156">Iterators enable you to maintain the simplicity of a `foreach` loop when you need to use complex code to populate a list sequence.</span></span> <span data-ttu-id="d3da2-157">Aşağıdakileri yapmak istediğinizde bu yararlı olabilir:</span><span class="sxs-lookup"><span data-stu-id="d3da2-157">This can be useful when you want to do the following:</span></span>

- <span data-ttu-id="d3da2-158">Liste sonra ilk dağıtmayın `foreach` döngü yinelemesi.</span><span class="sxs-lookup"><span data-stu-id="d3da2-158">Modify the list sequence after the first `foreach` loop iteration.</span></span>

- <span data-ttu-id="d3da2-159">Büyük bir liste ilk yinelemeyi önce tam olarak yüklenmesini önlemek bir `foreach` döngü.</span><span class="sxs-lookup"><span data-stu-id="d3da2-159">Avoid fully loading a large list before the first iteration of a `foreach` loop.</span></span> <span data-ttu-id="d3da2-160">Tablo satırları toplu yükleme için disk belleğine alınan fetch buna bir örnektir.</span><span class="sxs-lookup"><span data-stu-id="d3da2-160">An example is a paged fetch to load a batch of table rows.</span></span> <span data-ttu-id="d3da2-161">Başka bir örnek <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> yineleyiciler .NET Framework içindeki uygulayan yöntemi.</span><span class="sxs-lookup"><span data-stu-id="d3da2-161">Another example is the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> method, which implements iterators within the .NET Framework.</span></span>

- <span data-ttu-id="d3da2-162">Yineleyici listesinde oluşturmaya kapsüller.</span><span class="sxs-lookup"><span data-stu-id="d3da2-162">Encapsulate building the list in the iterator.</span></span> <span data-ttu-id="d3da2-163">Yineleyici yöntem içinde listesi oluşturmak ve ardından her bir döngü sonucu verecek.</span><span class="sxs-lookup"><span data-stu-id="d3da2-163">In the iterator method, you can build the list and then yield each result in a loop.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3da2-164">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d3da2-164">See also</span></span>

- <xref:System.Collections.Generic>
- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="d3da2-165">foreach, in</span><span class="sxs-lookup"><span data-stu-id="d3da2-165">foreach, in</span></span>](../../../csharp/language-reference/keywords/foreach-in.md)
- [<span data-ttu-id="d3da2-166">yield</span><span class="sxs-lookup"><span data-stu-id="d3da2-166">yield</span></span>](../../../csharp/language-reference/keywords/yield.md)
- [<span data-ttu-id="d3da2-167">Dizilerle foreach kullanma</span><span class="sxs-lookup"><span data-stu-id="d3da2-167">Using foreach with Arrays</span></span>](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="d3da2-168">Genel Türler</span><span class="sxs-lookup"><span data-stu-id="d3da2-168">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)