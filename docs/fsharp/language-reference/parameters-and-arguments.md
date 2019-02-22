---
title: Parametreler ve Bağımsız Değişkenler
description: Hakkında bilgi edinin F# parametreleri tanımlama ve İşlevler, yöntemler ve özellikler için bağımsız değişkenler geçirme için dil desteği.
ms.date: 05/16/2016
ms.openlocfilehash: 65e3b4f8ffb03e81104c963c5e2da7aba2e2b220
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56583504"
---
# <a name="parameters-and-arguments"></a><span data-ttu-id="2ee3b-103">Parametreler ve Bağımsız Değişkenler</span><span class="sxs-lookup"><span data-stu-id="2ee3b-103">Parameters and Arguments</span></span>

<span data-ttu-id="2ee3b-104">Bu konuda tanımlayan parametreler ve bağımsız değişkenleri işlevleri, yöntemlere ve özelliklere geçirme için dil desteği açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-104">This topic describes language support for defining parameters and passing arguments to functions, methods, and properties.</span></span> <span data-ttu-id="2ee3b-105">Başvuruya göre nasıl ve tanımlayın ve değişken sayıda bağımsız değişken alabilir yöntemleri kullanma hakkında bilgiler içerir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-105">It includes information about how to pass by reference, and how to define and use methods that can take a variable number of arguments.</span></span>

## <a name="parameters-and-arguments"></a><span data-ttu-id="2ee3b-106">Parametreler ve Bağımsız Değişkenler</span><span class="sxs-lookup"><span data-stu-id="2ee3b-106">Parameters and Arguments</span></span>

<span data-ttu-id="2ee3b-107">Terim *parametre* sağlanacak beklenen değerleri adlarını tanımlamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-107">The term *parameter* is used to describe the names for values that are expected to be supplied.</span></span> <span data-ttu-id="2ee3b-108">Terim *bağımsız değişken* her parametre için sağlanan değerler için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-108">The term *argument* is used for the values provided for each parameter.</span></span>

<span data-ttu-id="2ee3b-109">Parametreleri, tanımlama grubu ya da curried form veya ikisinin birleşimi belirtilebilir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-109">Parameters can be specified in tuple or curried form, or in some combination of the two.</span></span> <span data-ttu-id="2ee3b-110">Bir açık parametre adını kullanarak, bağımsız değişkenler geçirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-110">You can pass arguments by using an explicit parameter name.</span></span> <span data-ttu-id="2ee3b-111">Yöntemlerin parametreleri isteğe bağlı olarak belirtilebilir ve bir varsayılan değer verilir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-111">Parameters of methods can be specified as optional and given a default value.</span></span>

## <a name="parameter-patterns"></a><span data-ttu-id="2ee3b-112">Parametre desenleri</span><span class="sxs-lookup"><span data-stu-id="2ee3b-112">Parameter Patterns</span></span>

<span data-ttu-id="2ee3b-113">İşlevlere ve metotlara için sağlanan parametreler, genel olarak, boşluklarla ayırarak desenleri alır.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-113">Parameters supplied to functions and methods are, in general, patterns separated by spaces.</span></span> <span data-ttu-id="2ee3b-114">İlkesi, herhangi bir kalıpla açıklanan, yani [eşleşme ifadeleri](match-expressions.md) bir işlevi veya üye için parametre listesinde kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-114">This means that, in principle, any of the patterns described in [Match Expressions](match-expressions.md) can be used in a parameter list for a function or member.</span></span>

<span data-ttu-id="2ee3b-115">Yöntemler, genellikle bağımsız değişkenleri geçirme demet biçimini kullanın.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-115">Methods usually use the tuple form of passing arguments.</span></span> <span data-ttu-id="2ee3b-116">Kayıt formu .NET yöntemleri bağımsız değişkenler geçirilir şekilde eşleştiği için bu diğer .NET dilleri perspektifinden NET bir sonuç elde edilir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-116">This achieves a clearer result from the perspective of other .NET languages because the tuple form matches the way arguments are passed in .NET methods.</span></span>

<span data-ttu-id="2ee3b-117">Formun curried işlevleri kullanılarak oluşturulan ile en sık kullanılan `let` bağlar.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-117">The curried form is most often used with functions created by using `let` bindings.</span></span>

<span data-ttu-id="2ee3b-118">Aşağıdaki sözde kod tanımlama grubu ve curried bağımsız örneklerini gösterir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-118">The following pseudocode shows examples of tuple and curried arguments.</span></span>

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

<span data-ttu-id="2ee3b-119">Birleşik forms bazı bağımsız değişkenler de tanımlama gruplarına ve bazı değil mümkündür.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-119">Combined forms are possible when some arguments are in tuples and some are not.</span></span>

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

<span data-ttu-id="2ee3b-120">Diğer desenler içinde parametre listeleri de kullanılabilir, ancak parametre düzeni tüm olası girişleri eşleşmiyorsa olabilir bir tam eşleşme çalışma zamanında.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-120">Other patterns can also be used in parameter lists, but if the parameter pattern does not match all possible inputs, there might be an incomplete match at run time.</span></span> <span data-ttu-id="2ee3b-121">Özel durum `MatchFailureException` bir bağımsız değişkenin değeri parametre listesinde belirtilen desenleri eşleşmediğinde oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-121">The exception `MatchFailureException` is generated when the value of an argument does not match the patterns specified in the parameter list.</span></span> <span data-ttu-id="2ee3b-122">Parametre düzeni için eksik eşleşmeler izin veriyorsa, derleyici bir uyarı verir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-122">The compiler issues a warning when a parameter pattern allows for incomplete matches.</span></span> <span data-ttu-id="2ee3b-123">Diğer düzen en az bir parametre listeleri için yaygın olarak kullanışlıdır ve joker karakter deseni.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-123">At least one other pattern is commonly useful for parameter lists, and that is the wildcard pattern.</span></span> <span data-ttu-id="2ee3b-124">Yalnızca sağlanan herhangi bir bağımsız değişken yok saymak istediğinizde bir parametre listesinde joker karakter deseni kullanın.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-124">You use the wildcard pattern in a parameter list when you simply want to ignore any arguments that are supplied.</span></span> <span data-ttu-id="2ee3b-125">Aşağıdaki kodu bir bağımsız değişken listesinde joker karakter deseni kullanımını gösterir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-125">The following code illustrates the use of the wildcard pattern in an argument list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

<span data-ttu-id="2ee3b-126">Aşağıdaki kodda gösterildiği gibi bir dize dizisi olarak normal olarak sağlanan komut satırı bağımsız değişkenleri ilginizi olmadığında yararlı geçirilen bağımsız değişkenlerdeki ihtiyacınız olduğunda, bir programa ana girdi noktası olduğu gibi joker karakter deseni olabilir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-126">The wildcard pattern can be useful whenever you do not need the arguments passed in, such as in the main entry point to a program, when you are not interested in the command-line arguments that are normally supplied as a string array, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

<span data-ttu-id="2ee3b-127">Bağımsız değişkenler bazen kullanılan diğer desenler `as` deseni ve ayrılmış birleşimler ve Etkin desenler ilişkili tanımlayıcı desenler.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-127">Other patterns that are sometimes used in arguments are the `as` pattern, and identifier patterns associated with discriminated unions and active patterns.</span></span> <span data-ttu-id="2ee3b-128">Tek örneği ayrılmış birleşim deseni şu şekilde kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-128">You can use the single-case discriminated union pattern as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

<span data-ttu-id="2ee3b-129">Çıktı aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="2ee3b-129">The output is as follows.</span></span>

```
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

<span data-ttu-id="2ee3b-130">Etkin desenler, bağımsız değişken aşağıdaki örnekte olduğu gibi istediğiniz bir biçime dönüştürme, parametre olarak, örneğin, yararlı olabilir:</span><span class="sxs-lookup"><span data-stu-id="2ee3b-130">Active patterns can be useful as parameters, for example, when transforming an argument into a desired format, as in the following example:</span></span>

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

<span data-ttu-id="2ee3b-131">Kullanabileceğiniz `as` kod aşağıdaki satırda gösterildiği gibi yerel bir değer olarak, eşleşen bir değeri depolamak için desen.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-131">You can use the `as` pattern to store a matched value as a local value, as is shown in the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

<span data-ttu-id="2ee3b-132">Nadiren kullanılan başka bir desendir son bağımsız değişken, işlev gövdesi olarak sağlayarak adlandırılmamış ayrıldığında bir işlev, bir lambda ifadesi hemen örtük bağımsız değişken bir desen eşleştirmesi gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-132">Another pattern that is used occasionally is a function that leaves the last argument unnamed by providing, as the body of the function, a lambda expression that immediately performs a pattern match on the implicit argument.</span></span> <span data-ttu-id="2ee3b-133">Buna örnek olarak aşağıdaki kod satırını ' dir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-133">An example of this is the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

<span data-ttu-id="2ee3b-134">Bu kod, genel bir liste alan ve döndüren bir işlev tanımlar `true` liste boşsa ve `false` Aksi takdirde.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-134">This code defines a function that takes a generic list and returns `true` if the list is empty, and `false` otherwise.</span></span> <span data-ttu-id="2ee3b-135">Bu tür teknikler kullanımını kod okumak daha zor hale getirebilir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-135">The use of such techniques can make code more difficult to read.</span></span>

<span data-ttu-id="2ee3b-136">Bazen, eksik eşleşmeler içeren desenleri kullanışlıdır, programınızdaki listeleri yalnızca üç öğe olduğunu biliyorsanız, örneğin, bir desen aşağıdaki gibi bir parametre listesinde kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-136">Occasionally, patterns that involve incomplete matches are useful, for example, if you know that the lists in your program have only three elements, you might use a pattern like the following in a parameter list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

<span data-ttu-id="2ee3b-137">Tam eşleşme sahip desenleri kullanımını en iyi hızlı prototip oluşturma ve geçici diğer kullanımlar için ayrılmıştır.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-137">The use of patterns that have incomplete matches is best reserved for quick prototyping and other temporary uses.</span></span> <span data-ttu-id="2ee3b-138">Derleyici bu tür kod için bir uyarı verir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-138">The compiler will issue a warning for such code.</span></span> <span data-ttu-id="2ee3b-139">Desenler, tüm olası girişleri genel durumunun kapsamamaktadır ve bileşen API'leri için uygun değildir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-139">Such patterns cannot cover the general case of all possible inputs and therefore are not suitable for component APIs.</span></span>

## <a name="named-arguments"></a><span data-ttu-id="2ee3b-140">Adlandırılmış bağımsız değişkenler</span><span class="sxs-lookup"><span data-stu-id="2ee3b-140">Named Arguments</span></span>

<span data-ttu-id="2ee3b-141">Bağımsız değişkenler yöntemleri için bir virgülle ayrılmış bağımsız değişken listesindeki konumu ile belirtilebilir veya bunlar bir yönteme açıkça ardından bir eşittir işareti ve geçirilmesi değer adı sağlayarak geçirilebilir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-141">Arguments for methods can be specified by position in a comma-separated argument list, or they can be passed to a method explicitly by providing the name, followed by an equal sign and the value to be passed in.</span></span> <span data-ttu-id="2ee3b-142">Belirtilen ad sağlayarak, bildirimde kullanılan ile farklı bir sırada görünebilir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-142">If specified by providing the name, they can appear in a different order from that used in the declaration.</span></span>

<span data-ttu-id="2ee3b-143">Adlandırılmış bağımsız değişkenler kod daha okunabilir ve uyarlanabilir daha belirli türde bir yöntem parametreleri, yeniden sıralama API'sindeki değişiklikler yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-143">Named arguments can make code more readable and more adaptable to certain types of changes in the API, such as a reordering of method parameters.</span></span>

<span data-ttu-id="2ee3b-144">Adlandırılmış bağımsız değişkenler için değil yalnızca yöntemleri için verilir `let`-bağlı İşlevler, işlev değerleri veya lambda ifadeleri.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-144">Named arguments are allowed only for methods, not for `let`-bound functions, function values, or lambda expressions.</span></span>

<span data-ttu-id="2ee3b-145">Aşağıdaki kod örneği, adlandırılmış bağımsız değişkenler kullanımını gösterir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-145">The following code example demonstrates the use of named arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

<span data-ttu-id="2ee3b-146">Bir sınıf oluşturucusuna bir çağrı adlandırılmış bağımsız değişkenler için benzer bir sözdizimi kullanarak sınıfın özelliklerinin değerlerini ayarlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-146">In a call to a class constructor, you can set the values of properties of the class by using a syntax similar to that of named arguments.</span></span> <span data-ttu-id="2ee3b-147">Aşağıdaki örnek bu söz dizimini gösterir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-147">The following example shows this syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="2ee3b-148">Daha fazla bilgi için [oluşturucular (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span><span class="sxs-lookup"><span data-stu-id="2ee3b-148">For more information, see [Constructors (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span></span>

## <a name="optional-parameters"></a><span data-ttu-id="2ee3b-149">İsteğe Bağlı Parametreler</span><span class="sxs-lookup"><span data-stu-id="2ee3b-149">Optional Parameters</span></span>

<span data-ttu-id="2ee3b-150">İsteğe bağlı parametresi bir yöntem için parametre adının önüne bir soru işareti kullanarak belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-150">You can specify an optional parameter for a method by using a question mark in front of the parameter name.</span></span> <span data-ttu-id="2ee3b-151">İsteğe bağlı parametreler olarak yorumlanır F# seçenek türleri, kullanarak sorgulanır, normal şekilde sorgulayabilmesi seçenek türü, bir `match` ifadesiyle `Some` ve `None`.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-151">Optional parameters are interpreted as the F# option type, so you can query them in the regular way that option types are queried, by using a `match` expression with `Some` and `None`.</span></span> <span data-ttu-id="2ee3b-152">İsteğe bağlı parametreler kullanılarak oluşturulan işlevleri, üye üzerinde yalnızca verilen `let` bağlar.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-152">Optional parameters are permitted only on members, not on functions created by using `let` bindings.</span></span>

<span data-ttu-id="2ee3b-153">Var olan isteğe bağlı değerler yönteme parametre adıyla gibi geçirebilirsiniz `?arg=None` veya `?arg=Some(3)` veya `?arg=arg`.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-153">You can pass existing optional values to method by parameter name, such as `?arg=None` or `?arg=Some(3)` or `?arg=arg`.</span></span> <span data-ttu-id="2ee3b-154">Bir yöntem oluşturma isteğe bağlı bağımsız değişkenler için başka bir yöntem başarılı olduğunda bu yararlı olabilir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-154">This can be useful when building a method that passes optional arguments to another method.</span></span>

<span data-ttu-id="2ee3b-155">Bir işlev de kullanabilirsiniz `defaultArg`, isteğe bağlı varsayılan değerini ayarlar.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-155">You can also use a function `defaultArg`, which sets a default value of an optional argument.</span></span> <span data-ttu-id="2ee3b-156">`defaultArg` İşlevi isteğe bağlı parametre olarak ilk bağımsız değişken ve varsayılan değer olarak saniye alır.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-156">The `defaultArg` function takes the optional parameter as the first argument and the default value as the second.</span></span>

<span data-ttu-id="2ee3b-157">Aşağıdaki örnek, isteğe bağlı parametreler kullanımını gösterir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-157">The following example illustrates the use of optional parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

<span data-ttu-id="2ee3b-158">Çıktı aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="2ee3b-158">The output is as follows.</span></span>

```
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
```

<span data-ttu-id="2ee3b-159">Amacıyla C# ve Visual Basic birlikte çalışma özniteliklerini kullanabilirsiniz `[<Optional; DefaultParameterValue<(...)>]` içinde F#, Arayanların bir bağımsız değişken isteğe bağlı olarak görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-159">For the purposes of C# and Visual Basic interop you can use the attributes `[<Optional; DefaultParameterValue<(...)>]` in F#, so that callers will see an argument as optional.</span></span> <span data-ttu-id="2ee3b-160">Bu bağımsız değişken isteğe bağlı olarak tanımlamak için eşdeğerdir C# olarak `MyMethod(int i = 3)`.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-160">This is equivalent to defining the argument as optional in C# as in `MyMethod(int i = 3)`.</span></span>

```fsharp
open System
open System.Runtime.InteropServices
type C = 
    static member Foo([<Optional; DefaultParameterValue("Hello world")>] message) =
        printfn "%s" message
```

<span data-ttu-id="2ee3b-161">Bu gibi durumlarda, yeni bir nesne aynı zamanda varsayılan parametre değeri olarak belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-161">You can also specify a new object as a default parameter value.</span></span> <span data-ttu-id="2ee3b-162">Örneğin, `Foo` üyesi sahip isteğe bağlı `CanceallationToken` giriş olarak bunun yerine:</span><span class="sxs-lookup"><span data-stu-id="2ee3b-162">For example, the `Foo` member could have an optional `CanceallationToken` as input instead:</span></span>

```fsharp
open System.Threading
open System.Runtime.InteropServices
type C = 
    static member Foo([<Optional; DefaultParameterValue(CancellationToken())>] ct: CancellationToken) =
        printfn "%A" ct
```

<span data-ttu-id="2ee3b-163">Bağımsız değişken olarak verilen değer `DefaultParameterValue` parametre türüyle eşleşmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-163">The value given as argument to `DefaultParameterValue` must match the type of the parameter.</span></span> <span data-ttu-id="2ee3b-164">Örneğin, aşağıdaki izin verilmez:</span><span class="sxs-lookup"><span data-stu-id="2ee3b-164">For example, the following is not allowed:</span></span>

```fsharp
type C =
    static member Wrong([<Optional; DefaultParameterValue("string")>] i:int) = ()
```

<span data-ttu-id="2ee3b-165">Bu durumda, derleyici bir uyarı oluşturur ve her iki öznitelik tamamen göz ardı eder.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-165">In this case, the compiler generates a warning and will ignore both attributes altogether.</span></span> <span data-ttu-id="2ee3b-166">Unutmayın varsayılan değer `null` türü-açıklama, olması gerekir aksi belirtilmedikçe derleyici yanlış türde, yani çıkarsar `[<Optional; DefaultParameterValue(null:obj)>] o:obj`.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-166">Note that the default value `null` needs to be type-annotated, as otherwise the compiler infers the wrong type, i.e. `[<Optional; DefaultParameterValue(null:obj)>] o:obj`.</span></span>

## <a name="passing-by-reference"></a><span data-ttu-id="2ee3b-167">Başvuruya göre geçirme</span><span class="sxs-lookup"><span data-stu-id="2ee3b-167">Passing by Reference</span></span>

<span data-ttu-id="2ee3b-168">Geçen bir F# başvuruya göre değeri içerir [zkratka](byrefs.md), Yönetilen işaretçi türleri olduğu.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-168">Passing an F# value by reference involves [byrefs](byrefs.md), which are managed pointer types.</span></span> <span data-ttu-id="2ee3b-169">Kılavuz, hangi tür kullanmak aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="2ee3b-169">Guidance for which type to use is as follows:</span></span>

* <span data-ttu-id="2ee3b-170">Kullanım `inref<'T>` yalnızca işaretçi okumak gerekiyorsa.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-170">Use `inref<'T>` if you only need to read the pointer.</span></span>
* <span data-ttu-id="2ee3b-171">Kullanım `outref<'T>` yalnızca işaretçi yazmak gerekiyorsa.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-171">Use `outref<'T>` if you only need to write to the pointer.</span></span>
* <span data-ttu-id="2ee3b-172">Kullanım `byref<'T>` hem okuma hem de yazma işaretçisi gerekiyorsa.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-172">Use `byref<'T>` if you need to both read from and write to the pointer.</span></span>

```fsharp
let example1 (x: inref<int>) = printfn "It's %d" x

let example2 (x: outref<int>) = x <- x + 1

let example3 (x: byref<int>) =
    printfn "It'd %d" x
    x <- x + 1

// No need to make it mutable, since it's read-only
let x = 1
example1 &x

// Needs to be mutable, since we write to it
let mutable y = 2
example2 &y
example3 &y // Now 'y' is 3
```

<span data-ttu-id="2ee3b-173">Parametre bir işaretçi ve değer değişebilir olduğundan, işlevi yürütme sonrasında değeri herhangi bir değişiklik korunur.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-173">Because the parameter is a pointer and the value is mutable, any changes to the value are retained after the execution of the function.</span></span>

<span data-ttu-id="2ee3b-174">Tüm depolamak için bir dönüş değeri olarak bir tanımlama grubu kullanabilirsiniz `out` .NET kitaplığı yöntem parametreleri.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-174">You can use a tuple as a return value to store any `out` parameters in .NET library methods.</span></span> <span data-ttu-id="2ee3b-175">Alternatif olarak davranabileceğiniz `out` parametre olarak bir `byref` parametresi.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-175">Alternatively, you can treat the `out` parameter as a `byref` parameter.</span></span> <span data-ttu-id="2ee3b-176">Aşağıdaki kod örneği iki yolunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-176">The following code example illustrates both ways.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a><span data-ttu-id="2ee3b-177">Parametre Dizileri</span><span class="sxs-lookup"><span data-stu-id="2ee3b-177">Parameter Arrays</span></span>

<span data-ttu-id="2ee3b-178">Bazen tercihe bağlı sayıda heterojen türünde parametre alan bir işlev tanımlamak gereklidir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-178">Occasionally it is necessary to define a function that takes an arbitrary number of parameters of heterogeneous type.</span></span> <span data-ttu-id="2ee3b-179">Kullanılabilen tüm türleri için hesap için tüm olası aşırı yüklenmiş yöntemler oluşturmak pratik olmaz.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-179">It would not be practical to create all the possible overloaded methods to account for all the types that could be used.</span></span> <span data-ttu-id="2ee3b-180">.NET uygulamaları için parametre dizisi özelliği aracılığıyla bu tür yöntemler için destek sağlar.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-180">The .NET implementations provide support for such methods through the parameter array feature.</span></span> <span data-ttu-id="2ee3b-181">Bir parametre dizisi içinde imzasını alan bir yöntem rastgele sayıda parametre ile sağlanabilir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-181">A method that takes a parameter array in its signature can be provided with an arbitrary number of parameters.</span></span> <span data-ttu-id="2ee3b-182">Parametreler, bir dizi içine yerleştirilir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-182">The parameters are put into an array.</span></span> <span data-ttu-id="2ee3b-183">Dizi öğelerinin türü, işleve geçirilen parametre türleri belirler.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-183">The type of the array elements determines the parameter types that can be passed to the function.</span></span> <span data-ttu-id="2ee3b-184">Parametre dizisi ile tanımlarsanız `System.Object` öğe türü istemci kodu her türden değer geçirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-184">If you define the parameter array with `System.Object` as the element type, then client code can pass values of any type.</span></span>

<span data-ttu-id="2ee3b-185">İçinde F#, parametre dizileri yöntemleri yalnızca tanımlanabilir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-185">In F#, parameter arrays can only be defined in methods.</span></span> <span data-ttu-id="2ee3b-186">Tek başına işlevleri veya modül içinde tanımlanan işlevleri kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-186">They cannot be used in standalone functions or functions that are defined in modules.</span></span>

<span data-ttu-id="2ee3b-187">Bir parametre dizisi kullanarak tanımladığınız `ParamArray` özniteliği.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-187">You define a parameter array by using the `ParamArray` attribute.</span></span> <span data-ttu-id="2ee3b-188">`ParamArray` Özniteliği yalnızca en son parametreye uygulanabilir.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-188">The `ParamArray` attribute can only be applied to the last parameter.</span></span>

<span data-ttu-id="2ee3b-189">Aşağıdaki kod, her iki arama bir parametre dizisi ve tür tanımını alır bir .NET yöntemi gösterir F# bir parametre dizisi alan bir yöntem vardır.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-189">The following code illustrates both calling a .NET method that takes a parameter array and the definition of a type in F# that has a method that takes a parameter array.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

<span data-ttu-id="2ee3b-190">Bir projeyi çalıştırdığınızda, önceki kodun çıktısı aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="2ee3b-190">When run in a project, the output of the previous code is as follows:</span></span>

```console
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a><span data-ttu-id="2ee3b-191">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="2ee3b-191">See also</span></span>

- [<span data-ttu-id="2ee3b-192">Üyeler</span><span class="sxs-lookup"><span data-stu-id="2ee3b-192">Members</span></span>](members/index.md)
