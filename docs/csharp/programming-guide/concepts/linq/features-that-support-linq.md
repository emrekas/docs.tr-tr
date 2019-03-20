---
title: LINQ'i Destekleyen C# Özellikleri
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], features supporting LINQ
ms.assetid: 524b0078-ebfd-45a7-b390-f2ceb9d84797
ms.openlocfilehash: d0b35bec3bbc30f411a705220c468fa8961b83cb
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58186032"
---
# <a name="c-features-that-support-linq"></a><span data-ttu-id="2b226-102">LINQ'i Destekleyen C# Özellikleri</span><span class="sxs-lookup"><span data-stu-id="2b226-102">C# Features That Support LINQ</span></span>

<span data-ttu-id="2b226-103">Aşağıdaki bölümde, C# 3.0 sürümünde sunulan yeni dil yapıları sunar.</span><span class="sxs-lookup"><span data-stu-id="2b226-103">The following section introduces new language constructs introduced in C# 3.0.</span></span> <span data-ttu-id="2b226-104">Bu yeni özelliklerin tümünü bir dereceye kullanılsa [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] sorgular olmadıkları için sınırlı [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] ve burada, bunları kullanışlı her bağlamda kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="2b226-104">Although these new features are all used to a degree with [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, they are not limited to [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] and can be used in any context where you find them useful.</span></span>

## <a name="query-expressions"></a><span data-ttu-id="2b226-105">Sorgu İfadeleri</span><span class="sxs-lookup"><span data-stu-id="2b226-105">Query Expressions</span></span>

<span data-ttu-id="2b226-106">Sorgu ifadeleri IEnumerable koleksiyonları sorgulamak için SQL veya XQuery benzer bir tanımlayıcı sözdizimi kullanın.</span><span class="sxs-lookup"><span data-stu-id="2b226-106">Query expressions use a declarative syntax similar to SQL or XQuery to query over IEnumerable collections.</span></span> <span data-ttu-id="2b226-107">Derleme zamanı sorgu sözdizimi yöntem çağrıları için dönüştürülür bir [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] sağlayıcısının uygulaması standart sorgu işleci genişletme yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="2b226-107">At compile time query syntax is converted to method calls to a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider's implementation of the standard query operator extension methods.</span></span> <span data-ttu-id="2b226-108">Uygulama Denetim uygun ad belirterek kapsamındaki standart sorgu işleçleri bir `using` yönergesi.</span><span class="sxs-lookup"><span data-stu-id="2b226-108">Applications control the standard query operators that are in scope by specifying the appropriate namespace with a `using` directive.</span></span> <span data-ttu-id="2b226-109">Aşağıdaki sorgu ifadesi dizisini alır, bunları dizedeki ilk karakter göre gruplandırır ve grupları sıralar.</span><span class="sxs-lookup"><span data-stu-id="2b226-109">The following query expression takes an array of strings, groups them according to the first character in the string, and orders the groups.</span></span>

```csharp
var query = from str in stringArray
            group str by str[0] into stringGroup
            orderby stringGroup.Key
            select stringGroup;
```

<span data-ttu-id="2b226-110">Daha fazla bilgi için [LINQ Sorgu ifadeleri](../../../../csharp/programming-guide/linq-query-expressions/index.md).</span><span class="sxs-lookup"><span data-stu-id="2b226-110">For more information, see [LINQ Query Expressions](../../../../csharp/programming-guide/linq-query-expressions/index.md).</span></span>

## <a name="implicitly-typed-variables-var"></a><span data-ttu-id="2b226-111">Örtük olarak yazılan değişkenler (var)</span><span class="sxs-lookup"><span data-stu-id="2b226-111">Implicitly Typed Variables (var)</span></span>

<span data-ttu-id="2b226-112">Kullanabileceğiniz bildirme ve bir değişkeni başlatarak, açıkça bir tür belirtmek yerine, [var](../../../../csharp/language-reference/keywords/var.md) çıkarır ve atamak için burada gösterildiği gibi derleyicisinin değiştiricisi:</span><span class="sxs-lookup"><span data-stu-id="2b226-112">Instead of explicitly specifying a type when you declare and initialize a variable, you can use the [var](../../../../csharp/language-reference/keywords/var.md) modifier to instruct the compiler to infer and assign the type, as shown here:</span></span>

```csharp
var number = 5;
var name = "Virginia";
var query = from str in stringArray
            where str[0] == 'm'
            select str;
```

<span data-ttu-id="2b226-113">Olarak bildirilen değişkenler `var` yalnızca olarak türünü açıkça belirtmeniz değişkenleri olarak kesin olan.</span><span class="sxs-lookup"><span data-stu-id="2b226-113">Variables declared as `var` are just as strongly-typed as variables whose type you specify explicitly.</span></span> <span data-ttu-id="2b226-114">Kullanımını `var` anonim türler, ancak oluşturmak mümkün kullanılabileceği için yalnızca yerel değişkenler yapar.</span><span class="sxs-lookup"><span data-stu-id="2b226-114">The use of `var` makes it possible to create anonymous types, but it can be used only for local variables.</span></span> <span data-ttu-id="2b226-115">Diziler de örtülü yazma ile bildirilebilir.</span><span class="sxs-lookup"><span data-stu-id="2b226-115">Arrays can also be declared with implicit typing.</span></span>

<span data-ttu-id="2b226-116">Daha fazla bilgi için [örtük olarak yazılan yerel değişkenler](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span><span class="sxs-lookup"><span data-stu-id="2b226-116">For more information, see [Implicitly Typed Local Variables](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span></span>

## <a name="object-and-collection-initializers"></a><span data-ttu-id="2b226-117">Nesne ve Koleksiyon Başlatıcıları</span><span class="sxs-lookup"><span data-stu-id="2b226-117">Object and Collection Initializers</span></span>

<span data-ttu-id="2b226-118">Nesne ve koleksiyon başlatıcıları nesne için açıkça bir oluşturucu çağırmaya gerek kalmadan nesneleri başlatmak mümkün kılar.</span><span class="sxs-lookup"><span data-stu-id="2b226-118">Object and collection initializers make it possible to initialize objects without explicitly calling a constructor for the object.</span></span> <span data-ttu-id="2b226-119">Bunlar kaynak verileri yeni bir veri türüne projenizin başlatıcılar genellikle sorgu ifadelerinde kullanılır.</span><span class="sxs-lookup"><span data-stu-id="2b226-119">Initializers are typically used in query expressions when they project the source data into a new data type.</span></span> <span data-ttu-id="2b226-120">Adlı bir sınıf varsayılarak `Customer` ortak `Name` ve `Phone` nesne Başlatıcı özellikleri, aşağıdaki kodda gösterildiği gibi kullanılabilir:</span><span class="sxs-lookup"><span data-stu-id="2b226-120">Assuming a class named `Customer` with public `Name` and `Phone` properties, the object initializer can be used as in the following code:</span></span>

```csharp
Customer cust = new Customer { Name = "Mike", Phone = "555-1212" };
```

<span data-ttu-id="2b226-121">Devam etmeden bizim `Customer` sınıfı, adlandırılan bir veri kaynağı olduğunu varsayın `IncomingOrders`ve her sipariş büyük ile ilgili `OrderSize`, yeni bir istiyoruz `Customer` dışına o sırada temel.</span><span class="sxs-lookup"><span data-stu-id="2b226-121">Continuing with our `Customer` class, assume that there is a data source called `IncomingOrders`, and that for each order with a large `OrderSize`, we would like to create a new `Customer` based off of that order.</span></span> <span data-ttu-id="2b226-122">LINQ sorgusu, bu veri kaynağında yürütülen ve bir koleksiyonu doldurmak için nesne başlatmayı kullanın:</span><span class="sxs-lookup"><span data-stu-id="2b226-122">A LINQ query can be executed on this data source and use object initialization to fill a collection:</span></span>

```csharp
var newLargeOrderCustomers = from o in IncomingOrders
                            where o.OrderSize > 5
                            select new Customer { Name = o.Name, Phone = o.Phone };
```

<span data-ttu-id="2b226-123">Veri kaynağını daha fazla özellik dizinimizin duran olabilir `Customer` gibi sınıf `OrderSize`, ancak ile nesne başlatmayı, istenen veri türüne sorgudan döndürülen verileri ekleme; biz bizim sınıfına ilgili verileri seçin.</span><span class="sxs-lookup"><span data-stu-id="2b226-123">The data source may have more properties lying under the hood than the `Customer` class such as `OrderSize`, but with object initialization, the data returned from the query is molded into the desired data type; we choose the data that is relevant to our class.</span></span> <span data-ttu-id="2b226-124">Sonuç olarak, artık sahip olduğumuz bir `IEnumerable` yeni doldurulmuş `Customer`s istedik.</span><span class="sxs-lookup"><span data-stu-id="2b226-124">As a result, we now have an `IEnumerable` filled with the new `Customer`s we wanted.</span></span> <span data-ttu-id="2b226-125">Yukarıdaki, ayrıca LINQ'ın yöntemi sözdiziminde yazılabilir:</span><span class="sxs-lookup"><span data-stu-id="2b226-125">The above can also be written in LINQ's method syntax:</span></span>

```csharp
var newLargeOrderCustomers = IncomingOrders.Where(x => x.OrderSize > 5).Select(y => new Customer { Name = y.Name, Phone = y.Phone });
```

<span data-ttu-id="2b226-126">Daha fazla bilgi için bkz.:</span><span class="sxs-lookup"><span data-stu-id="2b226-126">For more information, see:</span></span>

- [<span data-ttu-id="2b226-127">Nesne ve Koleksiyon Başlatıcıları</span><span class="sxs-lookup"><span data-stu-id="2b226-127">Object and Collection Initializers</span></span>](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)

- [<span data-ttu-id="2b226-128">Standart Sorgu İşleçleri için Sorgu İfade Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="2b226-128">Query Expression Syntax for Standard Query Operators</span></span>](../../../../csharp/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md)

## <a name="anonymous-types"></a><span data-ttu-id="2b226-129">Anonim Türler</span><span class="sxs-lookup"><span data-stu-id="2b226-129">Anonymous Types</span></span>

<span data-ttu-id="2b226-130">Anonim bir tür derleyici tarafından oluşturulmuş olan ve yalnızca tür adı derleyici için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="2b226-130">An anonymous type is constructed by the compiler and the type name is only available to the compiler.</span></span> <span data-ttu-id="2b226-131">Anonim türler bir sorgu sonucu özelliklerinde geçici olarak bir dizi türü adlı ayrı bir tanımlamak zorunda kalmadan gruplandırmak için kullanışlı bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="2b226-131">Anonymous types provide a convenient way to group a set of properties temporarily in a query result without having to define a separate named type.</span></span> <span data-ttu-id="2b226-132">Anonim türler, burada gösterildiği gibi bir new ifadesi ve bir nesne Başlatıcı ile başlatılır:</span><span class="sxs-lookup"><span data-stu-id="2b226-132">Anonymous types are initialized with a new expression and an object initializer, as shown here:</span></span>

```csharp
select new {name = cust.Name, phone = cust.Phone};
```

<span data-ttu-id="2b226-133">Daha fazla bilgi için [anonim türler](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="2b226-133">For more information, see [Anonymous Types](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span>

## <a name="extension-methods"></a><span data-ttu-id="2b226-134">Genişletme Yöntemleri</span><span class="sxs-lookup"><span data-stu-id="2b226-134">Extension Methods</span></span>

<span data-ttu-id="2b226-135">Böylece türünde bir örnek yöntemi gibi çağrılabilen bir genişletme yöntemi, bir tür ile ilişkilendirilebilir bir statik yöntemidir.</span><span class="sxs-lookup"><span data-stu-id="2b226-135">An extension method is a static method that can be associated with a type, so that it can be called as if it were an instance method on the type.</span></span> <span data-ttu-id="2b226-136">Bu özellik, aslında "yeni yöntemler varolan türleri için bunları gerçekten değiştirmeden eklemek," sağlar.</span><span class="sxs-lookup"><span data-stu-id="2b226-136">This feature enables you to, in effect, "add" new methods to existing types without actually modifying them.</span></span> <span data-ttu-id="2b226-137">Standart sorgu işleçleri sağlayan genişletme yöntemleri kümesidir [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] işlevselliğini uygulayan herhangi bir türü için sorgu <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="2b226-137">The standard query operators are a set of extension methods that provide [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query functionality for any type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span>

<span data-ttu-id="2b226-138">Daha fazla bilgi için [genişletme yöntemleri](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="2b226-138">For more information, see [Extension Methods](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span></span>

## <a name="lambda-expressions"></a><span data-ttu-id="2b226-139">Lambda İfadeleri</span><span class="sxs-lookup"><span data-stu-id="2b226-139">Lambda Expressions</span></span>

<span data-ttu-id="2b226-140">Bir lambda ifadesi = kullanan bir satır içi işlevdir > işleci ayırmak için giriş parametreleri işlevi gövdesinden ve derleme zamanında bir temsilci veya ifade ağacı dönüştürülebilir.</span><span class="sxs-lookup"><span data-stu-id="2b226-140">A lambda expression is an inline function that uses the => operator to separate input parameters from the function body and can be converted at compile time to a delegate or an expression tree.</span></span> <span data-ttu-id="2b226-141">İçinde [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] standart sorgu işleçleri için doğrudan yöntem çağrıları yaptığınızda programlama, lambda ifadeleri karşılaşırsınız.</span><span class="sxs-lookup"><span data-stu-id="2b226-141">In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] programming, you will encounter lambda expressions when you make direct method calls to the standard query operators.</span></span>

<span data-ttu-id="2b226-142">Daha fazla bilgi için bkz.:</span><span class="sxs-lookup"><span data-stu-id="2b226-142">For more information, see:</span></span>

- [<span data-ttu-id="2b226-143">Anonim İşlevler</span><span class="sxs-lookup"><span data-stu-id="2b226-143">Anonymous Functions</span></span>](../../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)

- [<span data-ttu-id="2b226-144">Lambda İfadeleri</span><span class="sxs-lookup"><span data-stu-id="2b226-144">Lambda Expressions</span></span>](../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)

- [<span data-ttu-id="2b226-145">İfade ağaçları (C#)</span><span class="sxs-lookup"><span data-stu-id="2b226-145">Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/index.md)

## <a name="see-also"></a><span data-ttu-id="2b226-146">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="2b226-146">See also</span></span>

- [<span data-ttu-id="2b226-147">Dil ile tümleşik sorgu (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="2b226-147">Language-Integrated Query (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/index.md)
