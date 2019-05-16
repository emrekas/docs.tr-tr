---
title: Oluşturucular
description: Oluşturucularda tanımlanacağını ve kullanılacağını öğrenmek F# oluşturup sınıfı ve yapı nesneleri.
ms.date: 05/16/2016
ms.openlocfilehash: 47fb6e77ce369d7aa4fce3aa2c97ecf7df280c03
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645226"
---
# <a name="constructors"></a><span data-ttu-id="885bf-103">Oluşturucular</span><span class="sxs-lookup"><span data-stu-id="885bf-103">Constructors</span></span>

<span data-ttu-id="885bf-104">Bu konu, oluşturmak ve sınıf ve yapı nesneleri için oluşturucu tanımlanacağını ve kullanılacağını açıklar.</span><span class="sxs-lookup"><span data-stu-id="885bf-104">This topic describes how to define and use constructors to create and initialize class and structure objects.</span></span>

## <a name="construction-of-class-objects"></a><span data-ttu-id="885bf-105">Sınıf nesnelerine yapımı</span><span class="sxs-lookup"><span data-stu-id="885bf-105">Construction of Class Objects</span></span>

<span data-ttu-id="885bf-106">Sınıf türü nesneleri oluşturuculara sahip.</span><span class="sxs-lookup"><span data-stu-id="885bf-106">Objects of class types have constructors.</span></span> <span data-ttu-id="885bf-107">Oluşturucular iki tür vardır.</span><span class="sxs-lookup"><span data-stu-id="885bf-107">There are two kinds of constructors.</span></span> <span data-ttu-id="885bf-108">Parametreleri yalnızca tür adından sonra parantez içinde görünmesi birincil Oluşturucusu biridir.</span><span class="sxs-lookup"><span data-stu-id="885bf-108">One is the primary constructor, whose parameters appear in parentheses just after the type name.</span></span> <span data-ttu-id="885bf-109">Diğer, isteğe bağlı ek oluşturucuları kullanarak belirttiğiniz `new` anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="885bf-109">You specify other, optional additional constructors by using the `new` keyword.</span></span> <span data-ttu-id="885bf-110">Böyle bir ek oluşturucular birincil Oluşturucu çağırmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="885bf-110">Any such additional constructors must call the primary constructor.</span></span>

<span data-ttu-id="885bf-111">Birincil kurucu içeriyorsa `let` ve `do` sınıf tanımının başlangıcında görünür bağlar.</span><span class="sxs-lookup"><span data-stu-id="885bf-111">The primary constructor contains `let` and `do` bindings that appear at the start of the class definition.</span></span> <span data-ttu-id="885bf-112">A `let` bağlama bildirir özel alanlar ve yöntemler sınıf; bir `do` bağlama kodu yürütür.</span><span class="sxs-lookup"><span data-stu-id="885bf-112">A `let` binding declares private fields and methods of the class; a `do` binding executes code.</span></span> <span data-ttu-id="885bf-113">Hakkında daha fazla bilgi için `let` sınıfı Yapıcılardaki bağlamaları görmek [ `let` sınıflardaki bağlamaları](let-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="885bf-113">For more information about `let` bindings in class constructors, see [`let` Bindings in Classes](let-bindings-in-classes.md).</span></span> <span data-ttu-id="885bf-114">Hakkında daha fazla bilgi için `do` , oluşturucularda bağlamaları görmek [ `do` sınıflardaki bağlamaları](do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="885bf-114">For more information about `do` bindings in constructors, see [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

<span data-ttu-id="885bf-115">Oluşturucu çağırmak istediğiniz birincil bir oluşturucu veya ek bir oluşturucuda olup olmadığına bakılmaksızın, nesneleri kullanarak oluşturabileceğiniz bir `new` ifade, içeren veya içermeyen isteğe bağlı `new` anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="885bf-115">Regardless of whether the constructor you want to call is a primary constructor or an additional constructor, you can create objects by using a `new` expression, with or without the optional `new` keyword.</span></span> <span data-ttu-id="885bf-116">Virgülle ayırarak oluşturucu bağımsız değişkenleri, bağımsız değişken listesi ile birlikte, nesneleri ve parantez içinde adlandırılmış bağımsız değişkenler ve değerleri kullanarak veya parantez içine alınmış.</span><span class="sxs-lookup"><span data-stu-id="885bf-116">You initialize your objects together with constructor arguments, either by listing the arguments in order and separated by commas and enclosed in parentheses, or by using named arguments and values in parentheses.</span></span> <span data-ttu-id="885bf-117">Ayrıca özellikleri bir nesne üzerinde nesne oluşturma sırasında özellik adlarını kullanarak ayarlayabilirsiniz ve yalnızca kullandığınız gibi değerler atama adlı oluşturucu bağımsız değişkenleri.</span><span class="sxs-lookup"><span data-stu-id="885bf-117">You can also set properties on an object during the construction of the object by using the property names and assigning values just as you use named constructor arguments.</span></span>

<span data-ttu-id="885bf-118">Aşağıdaki kod, bir oluşturucu ve nesneleri oluşturmak için çeşitli yöntemler sahip bir sınıfı gösterir.</span><span class="sxs-lookup"><span data-stu-id="885bf-118">The following code illustrates a class that has a constructor and various ways of creating objects.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

<span data-ttu-id="885bf-119">Çıktı aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="885bf-119">The output is as follows.</span></span>

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a><span data-ttu-id="885bf-120">Yapıları oluşturma</span><span class="sxs-lookup"><span data-stu-id="885bf-120">Construction of Structures</span></span>

<span data-ttu-id="885bf-121">Yapıları sınıflarının tüm kuralları uygulayın.</span><span class="sxs-lookup"><span data-stu-id="885bf-121">Structures follow all the rules of classes.</span></span> <span data-ttu-id="885bf-122">Bu nedenle, birincil bir oluşturucuya sahip olabilir ve ek oluşturucuları kullanarak sağlayabilirsiniz `new`.</span><span class="sxs-lookup"><span data-stu-id="885bf-122">Therefore, you can have a primary constructor, and you can provide additional constructors by using `new`.</span></span> <span data-ttu-id="885bf-123">Ancak, yapılar ve sınıflar arasında önemli bir fark yoktur: yapıları birincil hiçbir oluşturucu tanımlansa bile bir varsayılan Oluşturucusu (diğer bir deyişle, bir bağımsız değişken olmadan) sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="885bf-123">However, there is one important difference between structures and classes: structures can have a default constructor (that is, one with no arguments) even if no primary constructor is defined.</span></span> <span data-ttu-id="885bf-124">Varsayılan Oluşturucu tüm alanları varsayılan değer türü, genellikle sıfır ya da eşdeğerine başlatır.</span><span class="sxs-lookup"><span data-stu-id="885bf-124">The default constructor initializes all the fields to the default value for that type, usually zero or its equivalent.</span></span> <span data-ttu-id="885bf-125">Varsayılan Oluşturucu ile çakışmadığından emin yapıları için tanımladığınız tüm oluşturucular en az bir bağımsız değişken olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="885bf-125">Any constructors that you define for structures must have at least one argument so that they do not conflict with the default constructor.</span></span>

<span data-ttu-id="885bf-126">Ayrıca, yapıları kullanılarak oluşturulan alanlar genellikle sahip `val` anahtar sözcüğü; sınıfları bu alanlar da içerebilir.</span><span class="sxs-lookup"><span data-stu-id="885bf-126">Also, structures often have fields that are created by using the `val` keyword; classes can also have these fields.</span></span> <span data-ttu-id="885bf-127">Yapılar ve sınıflar tarafından tanımlanan alanlara sahip `val` anahtar sözcüğü de başlatılabilir ek oluşturucularda kayıt ifadelerini kullanarak aşağıdaki kodda gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="885bf-127">Structures and classes that have fields defined by using the `val` keyword can also be initialized in additional constructors by using record expressions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

<span data-ttu-id="885bf-128">Daha fazla bilgi için [açık alanlar: `val` Anahtar sözcüğü](explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="885bf-128">For more information, see [Explicit Fields: The `val` Keyword](explicit-fields-the-val-keyword.md).</span></span>

## <a name="executing-side-effects-in-constructors"></a><span data-ttu-id="885bf-129">Oluşturucularda yan etkileri yürütülüyor</span><span class="sxs-lookup"><span data-stu-id="885bf-129">Executing Side Effects in Constructors</span></span>

<span data-ttu-id="885bf-130">Birincil bir oluşturucu bir sınıftaki kod yürütebilir bir `do` bağlama.</span><span class="sxs-lookup"><span data-stu-id="885bf-130">A primary constructor in a class can execute code in a `do` binding.</span></span> <span data-ttu-id="885bf-131">Ancak, varsa ne olmadan kod ek bir oluşturucuda, yürütülecek bir `do` bağlama?</span><span class="sxs-lookup"><span data-stu-id="885bf-131">However, what if you have to execute code in an additional constructor, without a `do` binding?</span></span> <span data-ttu-id="885bf-132">Bunu yapmak için kullandığınız `then` anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="885bf-132">To do this, you use the `then` keyword.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

<span data-ttu-id="885bf-133">Birincil Oluşturucusu yan etkilerini hala yürütün.</span><span class="sxs-lookup"><span data-stu-id="885bf-133">The side effects of the primary constructor still execute.</span></span> <span data-ttu-id="885bf-134">Bu nedenle, çıkış aşağıdaki gibidir.</span><span class="sxs-lookup"><span data-stu-id="885bf-134">Therefore, the output is as follows.</span></span>

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

## <a name="self-identifiers-in-constructors"></a><span data-ttu-id="885bf-135">Oluşturucularda kendine yönelik tanımlayıcılar</span><span class="sxs-lookup"><span data-stu-id="885bf-135">Self Identifiers in Constructors</span></span>

<span data-ttu-id="885bf-136">Diğer üyeleri, her üyesinin tanımındaki geçerli nesne için bir ad sağlayın.</span><span class="sxs-lookup"><span data-stu-id="885bf-136">In other members, you provide a name for the current object in the definition of each member.</span></span> <span data-ttu-id="885bf-137">Kullanarak sınıf tanımının ilk satıra kendini tanımlayıcısı koyabilirsiniz `as` Oluşturucu parametresi takip anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="885bf-137">You can also put the self identifier on the first line of the class definition by using the `as` keyword immediately following the constructor parameters.</span></span> <span data-ttu-id="885bf-138">Aşağıdaki örnek bu söz dizimini gösterir.</span><span class="sxs-lookup"><span data-stu-id="885bf-138">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

<span data-ttu-id="885bf-139">Ek oluşturucularda de kendi kendine bir tanımlayıcı koyarak tanımlayabilirsiniz `as` Oluşturucu parametresi hemen sonra yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="885bf-139">In additional constructors, you can also define a self identifier by putting the `as` clause right after the constructor parameters.</span></span> <span data-ttu-id="885bf-140">Aşağıdaki örnek bu söz dizimini gösterir.</span><span class="sxs-lookup"><span data-stu-id="885bf-140">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

<span data-ttu-id="885bf-141">Tam olarak tanımlanmadan önce bir nesne kullanmaya çalıştığınızda sorunlar oluşabilir.</span><span class="sxs-lookup"><span data-stu-id="885bf-141">Problems can occur when you try to use an object before it is fully defined.</span></span> <span data-ttu-id="885bf-142">Bu nedenle, kendi kendine tanımlayıcı kullanımlarını, derleyici bir uyarı verir ve nesne başlatılmadan önce bir nesnenin üyelerine erişilemeyen emin olmak için ek denetimler eklemek neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="885bf-142">Therefore, uses of the self identifier can cause the compiler to emit a warning and insert additional checks to ensure the members of an object are not accessed before the object is initialized.</span></span> <span data-ttu-id="885bf-143">Yalnızca kendi kendine tanımlayıcıda kullanmalısınız `do` bağlamaları birincil oluşturucunun ya da sonra `then` ek Yapıcılardaki anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="885bf-143">You should only use the self identifier in the `do` bindings of the primary constructor, or after the `then` keyword in additional constructors.</span></span>

<span data-ttu-id="885bf-144">Kendi kendine tanımlayıcı adı olmak zorunda değil `this`.</span><span class="sxs-lookup"><span data-stu-id="885bf-144">The name of the self identifier does not have to be `this`.</span></span> <span data-ttu-id="885bf-145">Bu, herhangi bir geçerli tanımlayıcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="885bf-145">It can be any valid identifier.</span></span>

## <a name="assigning-values-to-properties-at-initialization"></a><span data-ttu-id="885bf-146">Başlatma sırasında özelliklere değerler atama</span><span class="sxs-lookup"><span data-stu-id="885bf-146">Assigning Values to Properties at Initialization</span></span>

<span data-ttu-id="885bf-147">Formun atamaları listesini ekleyerek başlatma kodu sınıf nesnesinde özelliklerine değerler atayabilirsiniz `property = value` bir oluşturucu için bağımsız değişken listesi.</span><span class="sxs-lookup"><span data-stu-id="885bf-147">You can assign values to the properties of a class object in the initialization code by appending a list of assignments of the form `property = value` to the argument list for a constructor.</span></span> <span data-ttu-id="885bf-148">Bu aşağıdaki kod örneğinde gösterilir.</span><span class="sxs-lookup"><span data-stu-id="885bf-148">This is shown in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="885bf-149">Önceki kod aşağıdaki sürümü sıradan bağımsız değişkenler, isteğe bağlı bağımsız değişkenler ve özellik ayarlarını bir oluşturucu çağrısı birleşimi gösterir.</span><span class="sxs-lookup"><span data-stu-id="885bf-149">The following version of the previous code illustrates the combination of ordinary arguments, optional arguments, and property settings in one constructor call.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]

## <a name="constructors-in-inherited-class"></a><span data-ttu-id="885bf-150">Devralınan sınıf oluşturucular</span><span class="sxs-lookup"><span data-stu-id="885bf-150">Constructors in inherited class</span></span>

<span data-ttu-id="885bf-151">Bir oluşturucuya sahip bir taban sınıftan devralınırken devral yan tümcesinde bağımsız değişkenleri belirtmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="885bf-151">When inheriting from a base class that has a constructor, you must specify its arguments in the inherit clause.</span></span> <span data-ttu-id="885bf-152">Daha fazla bilgi için [oluşturucular ve devralma](../inheritance.md#constructors-and-inheritance).</span><span class="sxs-lookup"><span data-stu-id="885bf-152">For more information, see [Constructors and inheritance](../inheritance.md#constructors-and-inheritance).</span></span>

## <a name="static-constructors-or-type-constructors"></a><span data-ttu-id="885bf-153">Statik oluşturucular veya tür Oluşturucu</span><span class="sxs-lookup"><span data-stu-id="885bf-153">Static Constructors or Type Constructors</span></span>

<span data-ttu-id="885bf-154">Statik nesneler oluşturmak için kod belirtme yanı sıra `let` ve `do` bağlamaları yazılan türünü ilk tür düzeyinde başlatma gerçekleştirmek için kullanılmadan önce yürütülen sınıf türleri.</span><span class="sxs-lookup"><span data-stu-id="885bf-154">In addition to specifying code for creating objects, static `let` and `do` bindings can be authored in class types that execute before the type is first used to perform initialization at the type level.</span></span> <span data-ttu-id="885bf-155">Daha fazla bilgi için [ `let` sınıflardaki bağlamaları](let-bindings-in-classes.md) ve [ `do` sınıflardaki bağlamaları](do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="885bf-155">For more information, see [`let` Bindings in Classes](let-bindings-in-classes.md) and [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="885bf-156">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="885bf-156">See also</span></span>

- [<span data-ttu-id="885bf-157">Üyeler</span><span class="sxs-lookup"><span data-stu-id="885bf-157">Members</span></span>](index.md)
