---
title: Kısıtlamalar
description: Hakkında bilgi edinin F# bir genel tür veya işlev içinde bir tür bağımsız değişkeni için gereksinimleri belirtmek için genel tür parametreleri uygulanan kısıtlamaları.
ms.date: 05/16/2016
ms.openlocfilehash: b253ce50707512a0d46c41bba2dde34adcc24d0e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937520"
---
# <a name="constraints"></a><span data-ttu-id="a66ce-103">Kısıtlamalar</span><span class="sxs-lookup"><span data-stu-id="a66ce-103">Constraints</span></span>

<span data-ttu-id="a66ce-104">Bu konu başlığı altında genel için uygulayabileceğiniz kısıtlamasını açıklayan bir genel tür veya işlev içinde bir tür bağımsız değişkeni için gereksinimleri belirleme için parametre türü.</span><span class="sxs-lookup"><span data-stu-id="a66ce-104">This topic describes constraints that you can apply to generic type parameters to specify the requirements for a type argument in a generic type or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="a66ce-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="a66ce-105">Syntax</span></span>

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a><span data-ttu-id="a66ce-106">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a66ce-106">Remarks</span></span>

<span data-ttu-id="a66ce-107">Genel tür içinde kullanılabilir türleri sınırlamak uygulayabileceğiniz çeşitli farklı kısıtlamaları vardır.</span><span class="sxs-lookup"><span data-stu-id="a66ce-107">There are several different constraints you can apply to limit the types that can be used in a generic type.</span></span> <span data-ttu-id="a66ce-108">Aşağıdaki tabloda, listeler ve bu kısıtlamaları açıklar.</span><span class="sxs-lookup"><span data-stu-id="a66ce-108">The following table lists and describes these constraints.</span></span>

|<span data-ttu-id="a66ce-109">Kısıtlama</span><span class="sxs-lookup"><span data-stu-id="a66ce-109">Constraint</span></span>|<span data-ttu-id="a66ce-110">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="a66ce-110">Syntax</span></span>|<span data-ttu-id="a66ce-111">Açıklama</span><span class="sxs-lookup"><span data-stu-id="a66ce-111">Description</span></span>|
|----------|------|-----------|
|<span data-ttu-id="a66ce-112">Tür kısıtlaması</span><span class="sxs-lookup"><span data-stu-id="a66ce-112">Type Constraint</span></span>|<span data-ttu-id="a66ce-113">*tür-parametresi* :&gt; *türü*</span><span class="sxs-lookup"><span data-stu-id="a66ce-113">*type-parameter* :&gt; *type*</span></span>|<span data-ttu-id="a66ce-114">Sağlanan türü belirtilen türünden eşit ya da bundan türetilmiş olmalıdır veya bir arabirim türü olduğundan, sağlanan türü arabirimini uygulaması gerekir.</span><span class="sxs-lookup"><span data-stu-id="a66ce-114">The provided type must be equal to or derived from the type specified, or, if the type is an interface, the provided type must implement the interface.</span></span>|
|<span data-ttu-id="a66ce-115">Null kısıtlaması</span><span class="sxs-lookup"><span data-stu-id="a66ce-115">Null Constraint</span></span>|<span data-ttu-id="a66ce-116">*tür-parametresi* : null</span><span class="sxs-lookup"><span data-stu-id="a66ce-116">*type-parameter* : null</span></span>|<span data-ttu-id="a66ce-117">Sağlanan türü null sabiti desteklemesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="a66ce-117">The provided type must support the null literal.</span></span> <span data-ttu-id="a66ce-118">Bu, tüm .NET nesne türlerini içerir ancak değil F# listesi, tanımlama grubu, işlevi, sınıf, kaydı veya birleşim türleri.</span><span class="sxs-lookup"><span data-stu-id="a66ce-118">This includes all .NET object types but not F# list, tuple, function, class, record, or union types.</span></span>|
|<span data-ttu-id="a66ce-119">Açık bir üye kısıtlaması</span><span class="sxs-lookup"><span data-stu-id="a66ce-119">Explicit Member Constraint</span></span>|<span data-ttu-id="a66ce-120">[(]*tür-parametresi* [veya... veya *tür-parametresi*)]: (*üye imzası*)</span><span class="sxs-lookup"><span data-stu-id="a66ce-120">[(]*type-parameter* [or ... or *type-parameter*)] : (*member-signature*)</span></span>|<span data-ttu-id="a66ce-121">Sağlanan tür bağımsız değişkenlerini en az biri belirtilen imzaya sahip bir üyesi olması gerekir; Genel kullanım için tasarlanmamıştır.</span><span class="sxs-lookup"><span data-stu-id="a66ce-121">At least one of the type arguments provided must have a member that has the specified signature; not intended for common use.</span></span> <span data-ttu-id="a66ce-122">Üyeleri ya da açıkça türü veya bir örtük tür uzantısı bir parçası için açık bir üye kısıtlaması geçerli hedefleri olarak tanımlanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="a66ce-122">Members must be either explicitly defined on the type or part of an implicit type extension to be valid targets for an Explicit Member Constraint.</span></span>|
|<span data-ttu-id="a66ce-123">Oluşturucu kısıtlaması</span><span class="sxs-lookup"><span data-stu-id="a66ce-123">Constructor Constraint</span></span>|<span data-ttu-id="a66ce-124">*tür-parametresi* : (yeni: birimi -&gt; ' bir)</span><span class="sxs-lookup"><span data-stu-id="a66ce-124">*type-parameter* : ( new : unit -&gt; 'a )</span></span>|<span data-ttu-id="a66ce-125">Sağlanan türü bir varsayılan oluşturucuya sahip olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="a66ce-125">The provided type must have a default constructor.</span></span>|
|<span data-ttu-id="a66ce-126">Değer türü kısıtlaması</span><span class="sxs-lookup"><span data-stu-id="a66ce-126">Value Type Constraint</span></span>|<span data-ttu-id="a66ce-127">: Yapı</span><span class="sxs-lookup"><span data-stu-id="a66ce-127">: struct</span></span>|<span data-ttu-id="a66ce-128">Sağlanan türü, bir .NET değer türü olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="a66ce-128">The provided type must be a .NET value type.</span></span>|
|<span data-ttu-id="a66ce-129">Başvuru türü kısıtlaması</span><span class="sxs-lookup"><span data-stu-id="a66ce-129">Reference Type Constraint</span></span>|<span data-ttu-id="a66ce-130">: Yapı değil</span><span class="sxs-lookup"><span data-stu-id="a66ce-130">: not struct</span></span>|<span data-ttu-id="a66ce-131">Sağlanan türü, bir .NET başvuru türü olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="a66ce-131">The provided type must be a .NET reference type.</span></span>|
|<span data-ttu-id="a66ce-132">Sabit listesi türü kısıtlaması</span><span class="sxs-lookup"><span data-stu-id="a66ce-132">Enumeration Type Constraint</span></span>|<span data-ttu-id="a66ce-133">: enum&lt;*underlying-type*&gt;</span><span class="sxs-lookup"><span data-stu-id="a66ce-133">: enum&lt;*underlying-type*&gt;</span></span>|<span data-ttu-id="a66ce-134">Sağlanan türü belirtilen temel türe sahip bir listeden seçimli türü olmalıdır; Genel kullanım için tasarlanmamıştır.</span><span class="sxs-lookup"><span data-stu-id="a66ce-134">The provided type must be an enumerated type that has the specified underlying type; not intended for common use.</span></span>|
|<span data-ttu-id="a66ce-135">Temsilci kısıtlaması</span><span class="sxs-lookup"><span data-stu-id="a66ce-135">Delegate Constraint</span></span>|<span data-ttu-id="a66ce-136">: delegate&lt;*tuple-parameter-type*, *return-type*&gt;</span><span class="sxs-lookup"><span data-stu-id="a66ce-136">: delegate&lt;*tuple-parameter-type*, *return-type*&gt;</span></span>|<span data-ttu-id="a66ce-137">Sağlanan türü belirtilen bağımsız değişkenler olan bir temsilci türü ve dönüş değeri; Genel kullanım için tasarlanmamıştır.</span><span class="sxs-lookup"><span data-stu-id="a66ce-137">The provided type must be a delegate type that has the specified arguments and return value; not intended for common use.</span></span>|
|<span data-ttu-id="a66ce-138">Karşılaştırma kısıtlaması</span><span class="sxs-lookup"><span data-stu-id="a66ce-138">Comparison Constraint</span></span>|<span data-ttu-id="a66ce-139">: karşılaştırma</span><span class="sxs-lookup"><span data-stu-id="a66ce-139">: comparison</span></span>|<span data-ttu-id="a66ce-140">Sağlanan türü karşılaştırma desteklemesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="a66ce-140">The provided type must support comparison.</span></span>|
|<span data-ttu-id="a66ce-141">Eşitliği kısıtlaması</span><span class="sxs-lookup"><span data-stu-id="a66ce-141">Equality Constraint</span></span>|<span data-ttu-id="a66ce-142">: Eşitlik</span><span class="sxs-lookup"><span data-stu-id="a66ce-142">: equality</span></span>|<span data-ttu-id="a66ce-143">Sağlanan türü eşitlik desteklemesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="a66ce-143">The provided type must support equality.</span></span>|
|<span data-ttu-id="a66ce-144">Yönetilmeyen kısıtlaması</span><span class="sxs-lookup"><span data-stu-id="a66ce-144">Unmanaged Constraint</span></span>|<span data-ttu-id="a66ce-145">: Yönetilmeyen</span><span class="sxs-lookup"><span data-stu-id="a66ce-145">: unmanaged</span></span>|<span data-ttu-id="a66ce-146">Sağlanan türü, yönetilmeyen bir türü olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="a66ce-146">The provided type must be an unmanaged type.</span></span> <span data-ttu-id="a66ce-147">Yönetilmeyen türler belirli temel türleri (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, veya `decimal`), numaralandırma türleri `nativeptr<_>`, veya alanları olmak üzere tüm yönetilmeyen tür genel olmayan yapısı.</span><span class="sxs-lookup"><span data-stu-id="a66ce-147">Unmanaged types are either certain primitive types (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, or `decimal`), enumeration types, `nativeptr<_>`, or a non-generic structure whose fields are all unmanaged types.</span></span>|

<span data-ttu-id="a66ce-148">Genel kısıtlama türü ancak çalıştırılmadı türleri üzerinde kullanılabilir olan bir özelliği kullanmak kodunuzu sahip olduğunda bir kısıtlama eklemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="a66ce-148">You have to add a constraint when your code has to use a feature that is available on the constraint type but not on types in general.</span></span> <span data-ttu-id="a66ce-149">Örneğin, bir sınıf türünü belirtmek için tür kısıtlaması kullanırsanız, bu sınıfın genel işlev veya tür yöntemlerden birini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a66ce-149">For example, if you use the type constraint to specify a class type, you can use any one of the methods of that class in the generic function or type.</span></span>

<span data-ttu-id="a66ce-150">Bir kısıtlama derleyici, kullandığınız özellikleri türü için çalışma zamanında sağlanan herhangi bir türü üzerinde kullanılabilir olacağını doğrulama yolu yoktur çünkü kısıtlamaları belirtme bazen açıkça tür parametreleri yazarken gereklidir parametre.</span><span class="sxs-lookup"><span data-stu-id="a66ce-150">Specifying constraints is sometimes required when writing type parameters explicitly, because without a constraint, the compiler has no way of verifying that the features that you are using will be available on any type that might be supplied at run time for the type parameter.</span></span>

<span data-ttu-id="a66ce-151">En yaygın kısıtlamaları, kullandığınız F# kod olan tür kısıtlamaları, temel sınıflar veya arabirimleri belirtin.</span><span class="sxs-lookup"><span data-stu-id="a66ce-151">The most common constraints you use in F# code are type constraints that specify base classes or interfaces.</span></span> <span data-ttu-id="a66ce-152">Diğer kısıtlamalar da tarafından kullanılan F# İşleç aşırı yüklemesi aritmetik işleçler için uygulamak için kullanılan ya da devre dışı olduğundan, esas olarak sağlanan açık üye kısıtlaması gibi belirli işlevleri uygulamak için Kitaplık F# Ortak dil çalışma zamanı tarafından desteklenen tüm kısıtlamaları kümesini destekler.</span><span class="sxs-lookup"><span data-stu-id="a66ce-152">The other constraints are either used by the F# library to implement certain functionality, such as the explicit member constraint, which is used to implement operator overloading for arithmetic operators, or are provided mainly because F# supports the complete set of constraints that is supported by the common language runtime.</span></span>

<span data-ttu-id="a66ce-153">Tür çıkarımı işlemi sırasında bazı kısıtlamalar, derleyici tarafından otomatik olarak algılanır.</span><span class="sxs-lookup"><span data-stu-id="a66ce-153">During the type inference process, some constraints are inferred automatically by the compiler.</span></span> <span data-ttu-id="a66ce-154">Örneğin, kullanırsanız `+` işleci bir işlevde, derleyici bir açık bir üye kısıtlama ifadesinde kullanılan değişken türleri algılar.</span><span class="sxs-lookup"><span data-stu-id="a66ce-154">For example, if you use the `+` operator in a function, the compiler infers an explicit member constraint on variable types that are used in the expression.</span></span>

<span data-ttu-id="a66ce-155">Aşağıdaki kod, bazı kısıtlaması bildirimlerini gösterir.</span><span class="sxs-lookup"><span data-stu-id="a66ce-155">The following code illustrates some constraint declarations.</span></span>

```fsharp
// Base Type Constraint
type Class1<'T when 'T :> System.Exception> =
class end

// Interface Type Constraint
type Class2<'T when 'T :> System.IComparable> = 
class end

// Null constraint
type Class3<'T when 'T : null> =
class end

// Member constraint with static member
type Class4<'T when 'T : (static member staticMethod1 : unit -> 'T) > =
class end

// Member constraint with instance member
type Class5<'T when 'T : (member Method1 : 'T -> int)> =
class end

// Member constraint with property
type Class6<'T when 'T : (member Property1 : int)> =
class end

// Constructor constraint
type Class7<'T when 'T : (new : unit -> 'T)>() =
member val Field = new 'T()

// Reference type constraint
type Class8<'T when 'T : not struct> =
class end

// Enumeration constraint with underlying value specified
type Class9<'T when 'T : enum<uint32>> =
class end

// 'T must implement IComparable, or be an array type with comparable
// elements, or be System.IntPtr or System.UIntPtr. Also, 'T must not have
// the NoComparison attribute.
type Class10<'T when 'T : comparison> =
class end

// 'T must support equality. This is true for any type that does not
// have the NoEquality attribute.
type Class11<'T when 'T : equality> =
class end

type Class12<'T when 'T : delegate<obj * System.EventArgs, unit>> =
class end

type Class13<'T when 'T : unmanaged> =
class end

// Member constraints with two type parameters
// Most often used with static type parameters in inline functions
let inline add(value1 : ^T when ^T : (static member (+) : ^T * ^T -> ^T), value2: ^T) =
value1 + value2

// ^T and ^U must support operator +
let inline heterogenousAdd(value1 : ^T when (^T or ^U) : (static member (+) : ^T * ^U -> ^T), value2 : ^U) =
value1 + value2

// If there are multiple constraints, use the and keyword to separate them.
type Class14<'T,'U when 'T : equality and 'U : equality> =
class end
```

## <a name="see-also"></a><span data-ttu-id="a66ce-156">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="a66ce-156">See also</span></span>

- [<span data-ttu-id="a66ce-157">Genel Türler</span><span class="sxs-lookup"><span data-stu-id="a66ce-157">Generics</span></span>](index.md)
- [<span data-ttu-id="a66ce-158">Kısıtlamalar</span><span class="sxs-lookup"><span data-stu-id="a66ce-158">Constraints</span></span>](constraints.md)