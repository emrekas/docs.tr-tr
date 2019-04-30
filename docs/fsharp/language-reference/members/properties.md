---
title: Özellikler
description: Hakkında bilgi edinin F# bir nesneyle ilişkili değerlerini temsil eden üyeleri olan özellikleri.
ms.date: 05/16/2016
ms.openlocfilehash: bf605ee1135bd3b3561bde9a8ae66353497931b0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666371"
---
# <a name="properties"></a><span data-ttu-id="fefa2-103">Özellikler</span><span class="sxs-lookup"><span data-stu-id="fefa2-103">Properties</span></span>

<span data-ttu-id="fefa2-104">*Özellikleri* bir nesneyle ilişkili değerlerini temsil eden üyeleridir.</span><span class="sxs-lookup"><span data-stu-id="fefa2-104">*Properties* are members that represent values associated with an object.</span></span>

## <a name="syntax"></a><span data-ttu-id="fefa2-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="fefa2-105">Syntax</span></span>

```fsharp
// Property that has both get and set defined.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with [accessibility-modifier] get() =
    get-function-body
and [accessibility-modifier] set parameter =
    set-function-body

// Alternative syntax for a property that has get and set.
[ attributes-for-get ]
[ static ] member [accessibility-modifier-for-get] [self-identifier.]PropertyName =
    get-function-body
[ attributes-for-set ]
[ static ] member [accessibility-modifier-for-set] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName =
    get-function-body

// Alternative syntax for property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with get() =
    get-function-body

// Property that has set only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Automatically implemented properties.
[ attributes ]
[ static ] member val [accessibility-modifier] PropertyName = initialization-expression [ with get, set ]
```

## <a name="remarks"></a><span data-ttu-id="fefa2-106">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="fefa2-106">Remarks</span></span>

<span data-ttu-id="fefa2-107">Özellikleri temsil eder "olan bir" nesne örnekleri ile veya türü ile statik özellikler ilişkili verileri temsil eden nesne yönelimli programlama, ilişkide.</span><span class="sxs-lookup"><span data-stu-id="fefa2-107">Properties represent the "has a" relationship in object-oriented programming, representing data that is associated with object instances or, for static properties, with the type.</span></span>

<span data-ttu-id="fefa2-108">Özellikleri veya (yedekleme deposu olarak da bilinir) temel alan değeri özellik için açıkça belirtmek istediğiniz yedekleme deposu sizin için otomatik olarak oluşturmak derleyicinin izin vermek isteyip istemediğinizi bağlı olarak iki yolla bildirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fefa2-108">You can declare properties in two ways, depending on whether you want to explicitly specify the underlying value (also called the backing store) for the property, or if you want to allow the compiler to automatically generate the backing store for you.</span></span> <span data-ttu-id="fefa2-109">Genellikle, özelliği bir değer ya da değişken için yalnızca basit bir sarmalayıcı olduğunda Önemsiz olmayan bir uygulama özelliği varsa, daha açık şekilde ve otomatik bir yolu kullanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="fefa2-109">Generally, you should use the more explicit way if the property has a non-trivial implementation and the automatic way when the property is just a simple wrapper for a value or variable.</span></span> <span data-ttu-id="fefa2-110">Bir özelliği açıkça bildirmek için kullanın `member` anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="fefa2-110">To declare a property explicitly, use the `member` keyword.</span></span> <span data-ttu-id="fefa2-111">Bu bildirim temelli söz dizimi belirten sözdizimi tarafından izlenir `get` ve `set` yöntemleri olarak da adlandırılan, *erişimcileri*.</span><span class="sxs-lookup"><span data-stu-id="fefa2-111">This declarative syntax is followed by the syntax that specifies the `get` and `set` methods, also named *accessors*.</span></span> <span data-ttu-id="fefa2-112">Çeşitli türleri söz dizimi bölümünde açık sözdizimini, okuma/yazma, salt okunur ve salt yazılır özellikler için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="fefa2-112">The various forms of the explicit syntax shown in the syntax section are used for read/write, read-only, and write-only properties.</span></span> <span data-ttu-id="fefa2-113">Salt okunur özellikler, yalnızca, tanımladığınız bir `get` yöntemi; salt yazılır özellikler yalnızca tanımlamak bir `set` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="fefa2-113">For read-only properties, you define only a `get` method; for write-only properties, define only a `set` method.</span></span> <span data-ttu-id="fefa2-114">Her ikisi de bir özelliğe sahip olduğunda dikkat `get` ve `set` erişimcileri, farklı bir sözdizimi öznitelikleri ve aşağıdaki kodda gösterildiği gibi her bir erişimci farklı erişilebilirlik değiştiricileri belirtmenize imkan tanır.</span><span class="sxs-lookup"><span data-stu-id="fefa2-114">Note that when a property has both `get` and `set` accessors, the alternative syntax enables you to specify attributes and accessibility modifiers that are different for each accessor, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

<span data-ttu-id="fefa2-115">Her ikisi de okuma/yazma özellikleri için bir `get` ve `set` yöntemi, sırası `get` ve `set` ters çevrilebilir.</span><span class="sxs-lookup"><span data-stu-id="fefa2-115">For read/write properties, which have both a `get` and `set` method, the order of `get` and `set` can be reversed.</span></span> <span data-ttu-id="fefa2-116">Alternatif olarak, için sözdizimini sağlayabilir `get` yalnızca ve için sözdizimini `set` birleştirilmiş sözdizimi yerine yalnızca.</span><span class="sxs-lookup"><span data-stu-id="fefa2-116">Alternatively, you can provide the syntax shown for `get` only and the syntax shown for `set` only instead of using the combined syntax.</span></span> <span data-ttu-id="fefa2-117">Bunu kolaylaştırır, tek tek yorum `get` veya `set` yöntemi ise, bir şey yapmanız gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="fefa2-117">Doing this makes it easier to comment out the individual `get` or `set` method, if that is something you might need to do.</span></span> <span data-ttu-id="fefa2-118">Birleşik söz dizimini kullanarak bu alternatif aşağıdaki kodda gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="fefa2-118">This alternative to using the combined syntax is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

<span data-ttu-id="fefa2-119">Özel özellikler için verileri çağrılır, tutulan değerler *depolarını yedekleme*.</span><span class="sxs-lookup"><span data-stu-id="fefa2-119">Private values that hold the data for properties are called *backing stores*.</span></span> <span data-ttu-id="fefa2-120">Derleyicinin yedekleme deposu otomatik olarak oluşturmak için anahtar sözcükleri kullanın `member val`, kendi kendine tanımlayıcısı çıkarın ve ardından özelliğini başlatmak için bir ifade girin.</span><span class="sxs-lookup"><span data-stu-id="fefa2-120">To have the compiler create the backing store automatically, use the keywords `member val`, omit the self-identifier, then provide an expression to initialize the property.</span></span> <span data-ttu-id="fefa2-121">Özelliği değişebilir olmasını içermesi `with get, set`.</span><span class="sxs-lookup"><span data-stu-id="fefa2-121">If the property is to be mutable, include `with get, set`.</span></span> <span data-ttu-id="fefa2-122">Örneğin, aşağıdaki sınıf türü iki otomatik olarak uygulanan özellikler içerir.</span><span class="sxs-lookup"><span data-stu-id="fefa2-122">For example, the following class type includes two automatically implemented properties.</span></span> <span data-ttu-id="fefa2-123">`Property1` salt okunur ve birincil oluşturucuya, sağlanan bağımsız değişken olarak başlatılır ve `Property2` boş dize olarak başlatılmış bir ayarlanabilir özelliği:</span><span class="sxs-lookup"><span data-stu-id="fefa2-123">`Property1` is read-only and is initialized to the argument provided to the primary constructor, and `Property2` is a settable property initialized to an empty string:</span></span>

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

<span data-ttu-id="fefa2-124">Otomatik olarak uygulanan özellikler, bunlar diğer üye tanımları önce tıpkı dahil edilmesi için başlatma türünün bir parçası olan `let` bağlamaları ve `do` bağlamaları bir tür tanımı.</span><span class="sxs-lookup"><span data-stu-id="fefa2-124">Automatically implemented properties are part of the initialization of a type, so they must be included before any other member definitions, just like `let` bindings and `do` bindings in a type definition.</span></span> <span data-ttu-id="fefa2-125">Otomatik olarak uygulanan bir özellik başlatan ifade yalnızca ve başlatma sonrasında özelliği erişilmeyen her zaman değerlendirilir unutmayın.</span><span class="sxs-lookup"><span data-stu-id="fefa2-125">Note that the expression that initializes an automatically implemented property is only evaluated upon initialization, and not every time the property is accessed.</span></span> <span data-ttu-id="fefa2-126">Açıkça uygulanan bir özellik aksine bu davranışı davranıştır.</span><span class="sxs-lookup"><span data-stu-id="fefa2-126">This behavior is in contrast to the behavior of an explicitly implemented property.</span></span> <span data-ttu-id="fefa2-127">Ne bu etkili bir şekilde, bu özellikleri başlatmaya yarayacak koda anlamına gelir, bir sınıf oluşturucusuna eklenir.</span><span class="sxs-lookup"><span data-stu-id="fefa2-127">What this effectively means is that the code to initialize these properties is added to the constructor of a class.</span></span> <span data-ttu-id="fefa2-128">Bu fark gösteren aşağıdaki kodu göz önünde bulundurun:</span><span class="sxs-lookup"><span data-stu-id="fefa2-128">Consider the following code that shows this difference:</span></span>

```fsharp
type MyClass() =
    let random  = new System.Random()
    member val AutoProperty = random.Next() with get, set
    member this.ExplicitProperty = random.Next()

let class1 = new MyClass()

printfn "class1.AutoProperty = %d" class1.AutoProperty
printfn "class1.AutoProperty = %d" class1.AutoProperty
printfn "class1.ExplicitProperty = %d" class1.ExplicitProperty
printfn "class1.ExplicitProperty = %d" class1.ExplicitProperty
```

<span data-ttu-id="fefa2-129">**Output**</span><span class="sxs-lookup"><span data-stu-id="fefa2-129">**Output**</span></span>

```
class1.AutoProperty = 1853799794
class1.AutoProperty = 1853799794
class1.ExplicitProperty = 978922705
class1.ExplicitProperty = 1131210765
```

<span data-ttu-id="fefa2-130">Önceki kodun çıktısı her çağrıldığında ExplicitProperty değiştirir ancak AutoProperty değerini tekrar tekrar çağrıldığında değiştirilmemiş olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="fefa2-130">The output of the preceding code shows that the value of AutoProperty is unchanged when called repeatedly, whereas the ExplicitProperty changes each time it is called.</span></span> <span data-ttu-id="fefa2-131">Açık özelliği için alıcı yöntemi olduğundan her zaman otomatik olarak uygulanan bir özellik için ifade değerlendirilmez gösterir.</span><span class="sxs-lookup"><span data-stu-id="fefa2-131">This demonstrates that the expression for an automatically implemented property is not evaluated each time, as is the getter method for the explicit property.</span></span>

>[!WARNING]
><span data-ttu-id="fefa2-132">Entity Framework gibi bazı kitaplıklar vardır (`System.Data.Entity`) otomatik olarak uygulanan özellikler başlatma ile düzgün çalışmayan bir temel sınıf oluşturucuları, özel işlemler gerçekleştiren.</span><span class="sxs-lookup"><span data-stu-id="fefa2-132">There are some libraries, such as the Entity Framework (`System.Data.Entity`) that perform custom operations in base class constructors that don't work well with the initialization of automatically implemented properties.</span></span> <span data-ttu-id="fefa2-133">Bu gibi durumlarda, açık özelliklerini kullanmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="fefa2-133">In those cases, try using explicit properties.</span></span>

<span data-ttu-id="fefa2-134">Özellikler, sınıflar, yapılar, ayrılmış birleşimler, kayıtları, arabirimleri ve tür uzantıları üyesi olabilir ve nesne ifadelerinde da tanımlanabilir.</span><span class="sxs-lookup"><span data-stu-id="fefa2-134">Properties can be members of classes, structures, discriminated unions, records, interfaces, and type extensions and can also be defined in object expressions.</span></span>

<span data-ttu-id="fefa2-135">Öznitelikleri özelliklerine uygulanabilir.</span><span class="sxs-lookup"><span data-stu-id="fefa2-135">Attributes can be applied to properties.</span></span> <span data-ttu-id="fefa2-136">Bir özellik için bir öznitelik uygulamak için önce özelliği ayrı bir satırda öznitelik yazın.</span><span class="sxs-lookup"><span data-stu-id="fefa2-136">To apply an attribute to a property, write the attribute on a separate line before the property.</span></span> <span data-ttu-id="fefa2-137">Daha fazla bilgi için [öznitelikleri](../attributes.md).</span><span class="sxs-lookup"><span data-stu-id="fefa2-137">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="fefa2-138">Varsayılan olarak, özellikleri ortaktır.</span><span class="sxs-lookup"><span data-stu-id="fefa2-138">By default, properties are public.</span></span> <span data-ttu-id="fefa2-139">Erişilebilirlik değiştiricileri özellikleri için de uygulanabilir.</span><span class="sxs-lookup"><span data-stu-id="fefa2-139">Accessibility modifiers can also be applied to properties.</span></span> <span data-ttu-id="fefa2-140">Her ikisini de uygulamak için kullanılacaksa bir erişilebilirlik değiştiricisine uygulamak için özelliğin adı hemen önce ekleme `get` ve `set` yöntemleri; önce ekleme `get` ve `set` farklı erişilebilirlik ise anahtar sözcükleri Her erişimcisi için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="fefa2-140">To apply an accessibility modifier, add it immediately before the name of the property if it is meant to apply to both the `get` and `set` methods; add it before the `get` and `set` keywords if different accessibility is required for each accessor.</span></span> <span data-ttu-id="fefa2-141">*Erişilebilirlik değiştiricisi* aşağıdakilerden biri olabilir: `public`, `private`, `internal`.</span><span class="sxs-lookup"><span data-stu-id="fefa2-141">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="fefa2-142">Daha fazla bilgi için [erişim denetimi](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="fefa2-142">For more information, see [Access Control](../access-control.md).</span></span>

<span data-ttu-id="fefa2-143">Özellik uygulamaları bir özelliğine erişinceye her zaman yürütülür.</span><span class="sxs-lookup"><span data-stu-id="fefa2-143">Property implementations are executed each time a property is accessed.</span></span>

## <a name="static-and-instance-properties"></a><span data-ttu-id="fefa2-144">Statik ve örnek özellikleri</span><span class="sxs-lookup"><span data-stu-id="fefa2-144">Static and Instance Properties</span></span>

<span data-ttu-id="fefa2-145">Özellikler, statik veya örnek özellikleri.</span><span class="sxs-lookup"><span data-stu-id="fefa2-145">Properties can be static or instance properties.</span></span> <span data-ttu-id="fefa2-146">Statik özellikler örneği olmadan çağrılabilir ve ayrı ayrı nesneleri ile değil, türü ile ilişkili değerler için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="fefa2-146">Static properties can be invoked without an instance and are used for values associated with the type, not with individual objects.</span></span> <span data-ttu-id="fefa2-147">Statik özellikler için kendi kendine tanımlayıcısı yok sayın.</span><span class="sxs-lookup"><span data-stu-id="fefa2-147">For static properties, omit the self-identifier.</span></span> <span data-ttu-id="fefa2-148">Kendi kendine tanımlayıcı, örnek özellikleri için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="fefa2-148">The self-identifier is required for instance properties.</span></span>

<span data-ttu-id="fefa2-149">Aşağıdaki statik özellik tanımı, statik bir alana sahip bir senaryoya bağlıdır `myStaticValue` özelliği için diğer bir deyişle yedekleme deposu.</span><span class="sxs-lookup"><span data-stu-id="fefa2-149">The following static property definition is based on a scenario in which you have a static field `myStaticValue` that is the backing store for the property.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

<span data-ttu-id="fefa2-150">Özellikleri de olabilir dizi benzeri, bu durumda adlı *özellikleri dizine*.</span><span class="sxs-lookup"><span data-stu-id="fefa2-150">Properties can also be array-like, in which case they are called *indexed properties*.</span></span> <span data-ttu-id="fefa2-151">Daha fazla bilgi için [dizini oluşturulmamış Özellikler](indexed-properties.md).</span><span class="sxs-lookup"><span data-stu-id="fefa2-151">For more information, see [Indexed Properties](indexed-properties.md).</span></span>

## <a name="type-annotation-for-properties"></a><span data-ttu-id="fefa2-152">Özelliklerin tür ek açıklaması</span><span class="sxs-lookup"><span data-stu-id="fefa2-152">Type Annotation for Properties</span></span>

<span data-ttu-id="fefa2-153">Çoğu durumda, derleyici yedekleme deposu türünden bir özelliğinin türünü çıkarsamak için yeterli bilgiye sahip, ancak bir tür ek açıklamasına ekleyerek türü açıkça ayarlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fefa2-153">In many cases, the compiler has enough information to infer the type of a property from the type of the backing store, but you can set the type explicitly by adding a type annotation.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a><span data-ttu-id="fefa2-154">Set erişimcilerine özelliğini kullanma</span><span class="sxs-lookup"><span data-stu-id="fefa2-154">Using Property set Accessors</span></span>

<span data-ttu-id="fefa2-155">Sağlayan özellikleri ayarlayabilirsiniz `set` kullanarak erişimcileri `<-` işleci.</span><span class="sxs-lookup"><span data-stu-id="fefa2-155">You can set properties that provide `set` accessors by using the `<-` operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

<span data-ttu-id="fefa2-156">Çıktı **20**.</span><span class="sxs-lookup"><span data-stu-id="fefa2-156">The output is **20**.</span></span>

## <a name="abstract-properties"></a><span data-ttu-id="fefa2-157">Soyut Özellikler</span><span class="sxs-lookup"><span data-stu-id="fefa2-157">Abstract Properties</span></span>

<span data-ttu-id="fefa2-158">Özellikler, soyut olabilir.</span><span class="sxs-lookup"><span data-stu-id="fefa2-158">Properties can be abstract.</span></span> <span data-ttu-id="fefa2-159">Yöntemleriyle yönteminde olduğu gibi `abstract` yalnızca özellikle ilişkili bir sanal dağıtım olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="fefa2-159">As with methods, `abstract` just means that there is a virtual dispatch associated with the property.</span></span> <span data-ttu-id="fefa2-160">Diğer bir deyişle, soyut özellikler aynı sınıftaki bir tanımı olmadan tamamen soyut olabilir.</span><span class="sxs-lookup"><span data-stu-id="fefa2-160">Abstract properties can be truly abstract, that is, without a definition in the same class.</span></span> <span data-ttu-id="fefa2-161">Böyle bir özellik içeren sınıf bu nedenle bir soyut sınıftır.</span><span class="sxs-lookup"><span data-stu-id="fefa2-161">The class that contains such a property is therefore an abstract class.</span></span> <span data-ttu-id="fefa2-162">Alternatif olarak, Özet, yalnızca bir sanal bir özelliktir ve bu durumda, bir tanımı aynı sınıf içinde bulunmalıdır gelebilir.</span><span class="sxs-lookup"><span data-stu-id="fefa2-162">Alternatively, abstract can just mean that a property is virtual, and in that case, a definition must be present in the same class.</span></span> <span data-ttu-id="fefa2-163">Soyut özellikler özel olmamalıdır ve bir erişimci soyut ise, diğeri de soyut olmalıdır unutmayın.</span><span class="sxs-lookup"><span data-stu-id="fefa2-163">Note that abstract properties must not be private, and if one accessor is abstract, the other must also be abstract.</span></span> <span data-ttu-id="fefa2-164">Soyut sınıflar hakkında daha fazla bilgi için bkz: [soyut sınıflar](../abstract-classes.md).</span><span class="sxs-lookup"><span data-stu-id="fefa2-164">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a><span data-ttu-id="fefa2-165">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="fefa2-165">See also</span></span>

- [<span data-ttu-id="fefa2-166">Üyeler</span><span class="sxs-lookup"><span data-stu-id="fefa2-166">Members</span></span>](index.md)
- [<span data-ttu-id="fefa2-167">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="fefa2-167">Methods</span></span>](methods.md)
