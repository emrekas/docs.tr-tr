---
title: Tür Uzantıları
description: Bilgi nasıl F# türü uzantılara izin ver bir önceden tanımlanmış nesne türü için yeni üye ekleyin.
ms.date: 01/23/2019
ms.openlocfilehash: d52bc38850219a142ff4f5d840e418ea4bd50cca
ms.sourcegitcommit: d9a0071d0fd490ae006c816f78a563b9946e269a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55066161"
---
# <a name="type-extensions"></a><span data-ttu-id="c1c6c-103">Tür uzantıları</span><span class="sxs-lookup"><span data-stu-id="c1c6c-103">Type extensions</span></span>

<span data-ttu-id="c1c6c-104">Tür Uzantıları (olarak da adlandırılan _genişletmelerinde_) olan bir aile özelliklerinin bir önceden tanımlanmış nesne türü için yeni üye eklemenizi sağlar.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-104">Type extensions (also called _augmentations_) are a family of features that let you add new members to a previously defined object type.</span></span> <span data-ttu-id="c1c6c-105">Üç özellikleri şunlardır:</span><span class="sxs-lookup"><span data-stu-id="c1c6c-105">The three features are:</span></span>

* <span data-ttu-id="c1c6c-106">İç tür uzantıları</span><span class="sxs-lookup"><span data-stu-id="c1c6c-106">Intrinsic type extensions</span></span>
* <span data-ttu-id="c1c6c-107">İsteğe bağlı türü uzantıları</span><span class="sxs-lookup"><span data-stu-id="c1c6c-107">Optional type extensions</span></span>
* <span data-ttu-id="c1c6c-108">Genişletme yöntemleri</span><span class="sxs-lookup"><span data-stu-id="c1c6c-108">Extension methods</span></span>

<span data-ttu-id="c1c6c-109">Her farklı senaryolarda kullanılabilir ve farklı Artıları ve eksileri vardır.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-109">Each can be used in different scenarios and has different tradeoffs.</span></span>

## <a name="syntax"></a><span data-ttu-id="c1c6c-110">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="c1c6c-110">Syntax</span></span>

```fsharp
// Intrinsic and optional extensions
type typename with
    member self-identifier.member-name =
        body
    ...

// Extension methods
open System.Runtime.CompilerServices

[<Extension>]
type Extensions() =
    [static] member self-identifier.extension-name (ty: typename, [args]) =
        body
    ...
```

## <a name="intrinsic-type-extensions"></a><span data-ttu-id="c1c6c-111">İç tür uzantıları</span><span class="sxs-lookup"><span data-stu-id="c1c6c-111">Intrinsic type extensions</span></span>

<span data-ttu-id="c1c6c-112">Gerçek tür uzantısı kullanıcı tarafından tanımlanan bir türü genişleten bir türü uzantısıdır.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-112">An intrinsic type extension is a type extension that extends a user-defined type.</span></span>

<span data-ttu-id="c1c6c-113">Aynı dosyada iç tür uzantıları tanımlanan **ve** aynı ad alanı veya modül olarak genişletme türü.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-113">Intrinsic type extensions must be defined in the same file **and** in the same namespace or module as the type they're extending.</span></span> <span data-ttu-id="c1c6c-114">Diğer bir tanımı bunları neden olacak olan [isteğe bağlı türü uzantıları](type-extensions.md#optional-type-extensions).</span><span class="sxs-lookup"><span data-stu-id="c1c6c-114">Any other definition will result in them being [optional type extensions](type-extensions.md#optional-type-extensions).</span></span>

<span data-ttu-id="c1c6c-115">İç tür uzantıları bazen işlevi türü bildirimden ayırmak için bir temizleme yoludur.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-115">Intrinsic type extensions are sometimes a cleaner way to separate functionality from the type declaration.</span></span> <span data-ttu-id="c1c6c-116">Aşağıdaki örnek, gerçek tür uzantısı tanımlamak gösterilmektedir:</span><span class="sxs-lookup"><span data-stu-id="c1c6c-116">The following example shows how to define an intrinsic type extension:</span></span>

```fsharp
namespace Example

type Variant =
    | Num of int
    | Str of string
  
module Variant =
    let print v =
        match v with
        | Num n -> printf "Num %d" n
        | Str s -> printf "Str %s" s

// Add a member to Variant as an extension
type Variant with
    member x.Print() = Variant.print x
```

<span data-ttu-id="c1c6c-117">Bir tür uzantısı kullanarak aşağıdakilerin her biri ayrı sağlar:</span><span class="sxs-lookup"><span data-stu-id="c1c6c-117">Using a type extension allows you to separate each of the following:</span></span>

* <span data-ttu-id="c1c6c-118">Bildirimi bir `Variant` türü</span><span class="sxs-lookup"><span data-stu-id="c1c6c-118">The declaration of a `Variant` type</span></span>
* <span data-ttu-id="c1c6c-119">Yazdırma işlevselliği `Variant` "şeklini" bağlı olarak sınıfı</span><span class="sxs-lookup"><span data-stu-id="c1c6c-119">Functionality to print the `Variant` class depending on its "shape"</span></span>
* <span data-ttu-id="c1c6c-120">Nesne stiliyle yazdırma işlevselliği erişmek için bir yol `.`-gösterimi</span><span class="sxs-lookup"><span data-stu-id="c1c6c-120">A way to access the printing functionality with object-style `.`-notation</span></span>

<span data-ttu-id="c1c6c-121">Bu üye olarak her şey üzerinde tanımlama alternatiftir `Variant`.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-121">This is an alternative to defining everything as a member on `Variant`.</span></span> <span data-ttu-id="c1c6c-122">Doğal olarak daha iyi bir yaklaşım olmasa da, bu işlevsellik bazı durumlarda daha net bir temsilini olabilir.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-122">Although it is not an inherently better approach, it can be a cleaner representation of functionality in some situations.</span></span>

<span data-ttu-id="c1c6c-123">İç tür uzantıları büyütmek ve tür yansıma tarafından incelendiğinde tür üzerinde görünür bir türün üyeleri olarak derlenir.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-123">Intrinsic type extensions are compiled as members of the type they augment, and appear on the type when the type is examined by reflection.</span></span>

## <a name="optional-type-extensions"></a><span data-ttu-id="c1c6c-124">İsteğe bağlı türü uzantıları</span><span class="sxs-lookup"><span data-stu-id="c1c6c-124">Optional type extensions</span></span>

<span data-ttu-id="c1c6c-125">İsteğe bağlı tür uzantısı özgün modülü, ad alanı veya Genişletilmekte olan türün derlemenin dışında görünür bir uzantısıdır.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-125">An optional type extension is an extension that appears outside the original module, namespace, or assembly of the type being extended.</span></span>

<span data-ttu-id="c1c6c-126">İsteğe bağlı türü uzantıları kendiniz tanımlamadığınız bir türü genişletmek için kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-126">Optional type extensions are useful for extending a type that you have not defined yourself.</span></span> <span data-ttu-id="c1c6c-127">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="c1c6c-127">For example:</span></span>

```fsharp
module Extensions

open System.Collections.Generic

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq {
            for x in xs do
                for i in 1 .. n do
                    yield x
        }
```

<span data-ttu-id="c1c6c-128">Artık erişebilirsiniz `RepeatElements` üyesi ise gibi <xref:System.Collections.Generic.IEnumerable%601> sürece `Extensions` modülü içinde çalışmakta olduğunuz kapsam içinde açılır.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-128">You can now access `RepeatElements` as if it's a member of <xref:System.Collections.Generic.IEnumerable%601> as long as the `Extensions` module is opened in the scope that you are working in.</span></span>

<span data-ttu-id="c1c6c-129">Genişletilmiş tür yansıma tarafından incelendiğinde, isteğe bağlı uzantılar görünmez.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-129">Optional extensions do not appear on the extended type when examined by reflection.</span></span> <span data-ttu-id="c1c6c-130">İsteğe bağlı uzantılar, modüller halinde olmalıdır ve uzantıyı içeren modül açık veya aksi halde kapsam içinde olduğunda yalnızca kapsamda oldukları.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-130">Optional extensions must be in modules, and they're only in scope when the module that contains the extension is open or is otherwise in scope.</span></span>

<span data-ttu-id="c1c6c-131">İsteğe bağlı uzantı üyeleri, nesne örneğinin örtülü olarak ilk parametre olarak geçirildiği statik üyeler için derlenmiştir.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-131">Optional extension members are compiled to static members for which the object instance is passed implicitly as the first parameter.</span></span> <span data-ttu-id="c1c6c-132">Örnek üyeleri veya göre nasıl bildirilen statik üye oldukları gibi ancak bunlar işlevi görür.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-132">However, they act as if they're instance members or static members according to how they're declared.</span></span>

## <a name="generic-limitation-of-intrinsic-and-optional-type-extensions"></a><span data-ttu-id="c1c6c-133">Genel SORUMLULUĞUN iç ve isteğe bağlı türü uzantıları</span><span class="sxs-lookup"><span data-stu-id="c1c6c-133">Generic limitation of intrinsic and optional type extensions</span></span>

<span data-ttu-id="c1c6c-134">Burada tür değişkeni kısıtlı genel türde bir tür uzantısı bildirmek mümkündür.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-134">It's possible to declare a type extension on a generic type where the type variable is constrained.</span></span> <span data-ttu-id="c1c6c-135">Uzantı bildirimi kısıtlaması bildirilen türü kısıtlamasını eşleştiğini gereksinimidir.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-135">The requirement is that the constraint of the extension declaration matches the constraint of the declared type.</span></span>

<span data-ttu-id="c1c6c-136">Bildirilen tür ve tür uzantısı arasında kısıtlamaları bile eşleştirilir, ancak bildirilen türünden tür parametresi üzerinde farklı bir gereksinim uygular genişletilmiş bir üyesinin gövdesi tarafından çıkarılan için bir kısıtlama mümkündür.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-136">However, even when constraints are matched between a declared type and a type extension, it's possible for a constraint to be inferred by the body of an extended member that imposes a different requirement on the type parameter than the declared type.</span></span> <span data-ttu-id="c1c6c-137">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="c1c6c-137">For example:</span></span>

```fsharp
open System.Collections.Generic

// NOT POSSIBLE AND FAILS TO COMPILE!
//
// The member 'Sum' has a different requirement on 'T than the type IEnumerable<'T>
type IEnumerable<'T> with
    member this.Sum() = Seq.sum this
```

<span data-ttu-id="c1c6c-138">Bir isteğe bağlı tür uzantısı ile çalışmak için bu kodu erişmenin bir yolu vardır:</span><span class="sxs-lookup"><span data-stu-id="c1c6c-138">There is no way to get this code to work with an optional type extension:</span></span>

* <span data-ttu-id="c1c6c-139">Olduğu gibi `Sum` üye var. farklı bir kısıtlama `'T` (`static member get_Zero` ve `static member (+)`) daha ne tür uzantısı tanımlar.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-139">As is, the `Sum` member has a different constraint on `'T` (`static member get_Zero` and `static member (+)`) than what the type extension defines.</span></span>
* <span data-ttu-id="c1c6c-140">Tür uzantısı olarak aynı kısıtlamasına sahip değiştirme `Sum` üzerinde tanımlanan kısıtlaması artık eşleşecektir `IEnumerable<'T>`.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-140">Modifying the type extension to have the same constraint as `Sum` will no longer match the defined constraint on `IEnumerable<'T>`.</span></span>
* <span data-ttu-id="c1c6c-141">Değiştirme `member this.Sum` için `member inline this.Sum` tür kısıtlamaları uyumsuz bir hata verir.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-141">Changing `member this.Sum` to `member inline this.Sum` will give an error that type constraints are mismatched.</span></span>

<span data-ttu-id="c1c6c-142">İstenildiği gibi bir türü genişletmek gibi sunulan ve "alanında kayan" statik yöntem bulunmaktadır.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-142">What is desired are static methods that "float in space" and can be presented as if they're extending a type.</span></span> <span data-ttu-id="c1c6c-143">Burada uzantı yöntemleri gerekli hale budur.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-143">This is where extension methods become necessary.</span></span>

## <a name="extension-methods"></a><span data-ttu-id="c1c6c-144">Genişletme yöntemleri</span><span class="sxs-lookup"><span data-stu-id="c1c6c-144">Extension methods</span></span>

<span data-ttu-id="c1c6c-145">Son olarak, genişletme yöntemleri (olarak da adlandırılır "C# stili uzantı üyeleri") içinde bildirilebilir F# olarak bir sınıf üzerinde bir statik üye yöntemi.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-145">Finally, extension methods (sometimes called "C# style extension members") can be declared in F# as a static member method on a class.</span></span>

<span data-ttu-id="c1c6c-146">Genişletme yöntemleri, ne zaman uzantılar tür değişkeni sınırlamak bir genel tür tanımlamak istediğiniz için kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-146">Extension methods are useful for when you wish to define extensions on a generic type that will constrain the type variable.</span></span> <span data-ttu-id="c1c6c-147">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="c1c6c-147">For example:</span></span>

```fsharp
namespace Extensions

open System.Runtime.CompilerServices

[<Extension>]
type IEnumerableExtensions() =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

<span data-ttu-id="c1c6c-148">Kullanıldığında, bu kod görünmesini yapar gibi `Sum` tanımlanan <xref:System.Collections.Generic.IEnumerable%601>, sürece `Extensions` açılmış veya kapsamdadır.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-148">When used, this code will make it appear as if `Sum` is defined on <xref:System.Collections.Generic.IEnumerable%601>, so long as `Extensions` has been opened or is in scope.</span></span>

## <a name="other-remarks"></a><span data-ttu-id="c1c6c-149">Diğer açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c1c6c-149">Other remarks</span></span>

<span data-ttu-id="c1c6c-150">Tür uzantıları ayrıca aşağıdaki özniteliklere sahiptir:</span><span class="sxs-lookup"><span data-stu-id="c1c6c-150">Type extensions also have the following attributes:</span></span>

* <span data-ttu-id="c1c6c-151">Erişilebilen herhangi bir türü genişletilebilir.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-151">Any type that can be accessed can be extended.</span></span>
* <span data-ttu-id="c1c6c-152">İç ve isteğe bağlı türü uzantıları tanımlayabilirsiniz _herhangi_ üye türü, yalnızca yöntemi.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-152">Intrinsic and optional type extensions can define _any_ member type, not just methods.</span></span> <span data-ttu-id="c1c6c-153">Bu nedenle uzantı özellikleri da örneğin, mümkündür.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-153">So extension properties are also possible, for example.</span></span>
* <span data-ttu-id="c1c6c-154">`self-identifier` Belirtecini [söz dizimi](type-extensions.md#syntax) , sıradan üyelerdeki gibi çağrılmakta olan türün örneğini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-154">The `self-identifier` token in the [syntax](type-extensions.md#syntax) represents the instance of the type being invoked, just like ordinary members.</span></span>
* <span data-ttu-id="c1c6c-155">Genişletilmiş üyeleri, statik veya örnek üyeler.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-155">Extended members can be static or instance members.</span></span>
* <span data-ttu-id="c1c6c-156">Bir tür uzantısı türü değişkenlerde bildirilen tür kısıtlamaları eşleşmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-156">Type variables on a type extension must match the constraints of the declared type.</span></span>

<span data-ttu-id="c1c6c-157">Aşağıdaki sınırlamalar türü uzantıları için de mevcuttur:</span><span class="sxs-lookup"><span data-stu-id="c1c6c-157">The following limitations also exist for type extensions:</span></span>

* <span data-ttu-id="c1c6c-158">Tür uzantıları sanal veya soyut yöntemleri desteklemez.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-158">Type extensions do not support virtual or abstract methods.</span></span>
* <span data-ttu-id="c1c6c-159">Tür uzantıları genişletmeleri geçersiz kılma yöntemleri desteklemez.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-159">Type extensions do not support override methods as augmentations.</span></span>
* <span data-ttu-id="c1c6c-160">Tür uzantıları desteklemez [statik olarak çözümlenmiş tür Parametreleri'nde](generics/statically-resolved-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="c1c6c-160">Type extensions do not support [Statically Resolved Type Parameters](generics/statically-resolved-type-parameters.md).</span></span>
* <span data-ttu-id="c1c6c-161">İsteğe bağlı türü uzantıları genişletmelerinde oluşturucuları desteklemez.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-161">Optional Type extensions do not support constructors as augmentations.</span></span>
* <span data-ttu-id="c1c6c-162">Tür uzantıları tanımlanamaz [yazın kısaltmalar](type-abbreviations.md).</span><span class="sxs-lookup"><span data-stu-id="c1c6c-162">Type extensions cannot be defined on [type abbreviations](type-abbreviations.md).</span></span>
* <span data-ttu-id="c1c6c-163">Tür uzantıları için geçerli olmayan `byref<'T>` (bunlar bildirilebilir rağmen).</span><span class="sxs-lookup"><span data-stu-id="c1c6c-163">Type extensions are not valid for `byref<'T>` (though they can be declared).</span></span>
* <span data-ttu-id="c1c6c-164">Tür Uzantıları (bunlar bildirilebilir rağmen) öznitelikler için geçerli değildir.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-164">Type extensions are not valid for attributes (though they can be declared).</span></span>
* <span data-ttu-id="c1c6c-165">Aynı ada sahip diğer yöntemleri aşırı uzantıları tanımlayabilirsiniz ancak F# derleyici tercihi uzantısı olmayan yöntemlere belirsiz bir çağrı ise sağlar.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-165">You can define extensions that overload other methods of the same name, but the F# compiler gives preference to non-extension methods if there is an ambiguous call.</span></span>

<span data-ttu-id="c1c6c-166">Son olarak, bir tür için birden çok gerçek tür uzantısı varsa, tüm üyelerin benzersiz olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-166">Finally, if multiple intrinsic type extensions exist for one type, all members must be unique.</span></span> <span data-ttu-id="c1c6c-167">İsteğe bağlı türü uzantıları için farklı tür Uzantılardaki aynı türe üyeleri aynı adları olabilir.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-167">For optional type extensions, members in different type extensions to the same type can have the same names.</span></span> <span data-ttu-id="c1c6c-168">Belirsizlik hataları yalnızca istemci kodu aynı üye adını tanımlayan iki farklı kapsamı açarsa oluşur.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-168">Ambiguity errors occur only if client code opens two different scopes that define the same member names.</span></span>

## <a name="see-also"></a><span data-ttu-id="c1c6c-169">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="c1c6c-169">See also</span></span>

- [<span data-ttu-id="c1c6c-170">F# Dili Başvurusu</span><span class="sxs-lookup"><span data-stu-id="c1c6c-170">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="c1c6c-171">Üyeler</span><span class="sxs-lookup"><span data-stu-id="c1c6c-171">Members</span></span>](members/index.md)
