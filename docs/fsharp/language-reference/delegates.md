---
title: Temsilciler
description: Temsilcilerde ile çalışmayı öğrenin F#.
ms.date: 05/16/2016
ms.openlocfilehash: 0596b67530b0399df41dffdf855a07bce2bf4761
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641978"
---
# <a name="delegates"></a><span data-ttu-id="227ee-103">Temsilciler</span><span class="sxs-lookup"><span data-stu-id="227ee-103">Delegates</span></span>

<span data-ttu-id="227ee-104">Bir temsilci, bir nesne olarak bir işlev çağrısını temsil eder.</span><span class="sxs-lookup"><span data-stu-id="227ee-104">A delegate represents a function call as an object.</span></span> <span data-ttu-id="227ee-105">İçinde F#, temsil eder; ilk sınıf değerleri olarak işlevler için işlev değerleri normalde kullanmalıdır Ancak, temsilciler .NET Framework'teki kullanılır ve bunları beklediğiniz API'leri ile birlikte çalışmak, bu nedenle gereklidir.</span><span class="sxs-lookup"><span data-stu-id="227ee-105">In F#, you ordinarily should use function values to represent functions as first-class values; however, delegates are used in the .NET Framework and so are needed when you interoperate with APIs that expect them.</span></span> <span data-ttu-id="227ee-106">Geliştirme kitaplıkları için tasarlanan diğer .NET Framework dillerde kullandığınızda da kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="227ee-106">They may also be used when authoring libraries designed for use from other .NET Framework languages.</span></span>

## <a name="syntax"></a><span data-ttu-id="227ee-107">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="227ee-107">Syntax</span></span>

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a><span data-ttu-id="227ee-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="227ee-108">Remarks</span></span>

<span data-ttu-id="227ee-109">Önceki sözdiziminde, `type1` bağımsız değişken türü veya türleri temsil eder ve `type2` dönüş türünü temsil eder.</span><span class="sxs-lookup"><span data-stu-id="227ee-109">In the previous syntax, `type1` represents the argument type or types and `type2` represents the return type.</span></span> <span data-ttu-id="227ee-110">Tarafından temsil edilen bağımsız değişken türleri `type1` otomatik olarak curried.</span><span class="sxs-lookup"><span data-stu-id="227ee-110">The argument types that are represented by `type1` are automatically curried.</span></span> <span data-ttu-id="227ee-111">Bu, bu tür hedef işlevinin bağımsız değişkenleri curried bir tanımlama grubu form kullanmanızı ve parantez içine alınmış demet tanımlama grubu biçiminde olan bağımsız değişkenler için önerir.</span><span class="sxs-lookup"><span data-stu-id="227ee-111">This suggests that for this type you use a tuple form if the arguments of the target function are curried, and a parenthesized tuple for arguments that are already in the tuple form.</span></span> <span data-ttu-id="227ee-112">Otomatik currying hedef yöntemin eşleşen bir tanımlama grubu bağımsız değişkenini bırakarak, parantez kümesi kaldırır.</span><span class="sxs-lookup"><span data-stu-id="227ee-112">The automatic currying removes a set of parentheses, leaving a tuple argument that matches the target method.</span></span> <span data-ttu-id="227ee-113">Her durumda kullanmalısınız söz dizimi kod örneğine bakın.</span><span class="sxs-lookup"><span data-stu-id="227ee-113">Refer to the code example for the syntax you should use in each case.</span></span>

<span data-ttu-id="227ee-114">Temsilciler için eklenebilir F# işlev değerleri ve statik veya örnek yöntemler.</span><span class="sxs-lookup"><span data-stu-id="227ee-114">Delegates can be attached to F# function values, and static or instance methods.</span></span> <span data-ttu-id="227ee-115">F#işlev değerleri oluşturucuları temsilci olarak doğrudan bağımsız değişken olarak geçirilebilir.</span><span class="sxs-lookup"><span data-stu-id="227ee-115">F# function values can be passed directly as arguments to delegate constructors.</span></span> <span data-ttu-id="227ee-116">Statik bir yöntem için temsilci sınıf ve yöntem adını kullanarak oluşturun.</span><span class="sxs-lookup"><span data-stu-id="227ee-116">For a static method, you construct the delegate by using the name of the class and the method.</span></span> <span data-ttu-id="227ee-117">Bir örnek yöntemi için nesne örneği ve bir bağımsız değişkende yöntemi sağlar.</span><span class="sxs-lookup"><span data-stu-id="227ee-117">For an instance method, you provide the object instance and method in one argument.</span></span> <span data-ttu-id="227ee-118">Her iki durumda da, üye erişim işleci (`.`) kullanılır.</span><span class="sxs-lookup"><span data-stu-id="227ee-118">In both cases, the member access operator (`.`) is used.</span></span>

<span data-ttu-id="227ee-119">`Invoke` Temsilci türünde yöntemi kapsüllenmiş işlevi çağırır.</span><span class="sxs-lookup"><span data-stu-id="227ee-119">The `Invoke` method on the delegate type calls the encapsulated function.</span></span> <span data-ttu-id="227ee-120">Ayrıca, parantezler olmadan Invoke yöntemi ada başvurarak Temsilciler, işlev değerleri ' e geçirilebilir.</span><span class="sxs-lookup"><span data-stu-id="227ee-120">Also, delegates can be passed as function values by referencing the Invoke method name without the parentheses.</span></span>

<span data-ttu-id="227ee-121">Aşağıdaki kod, bir sınıfta çeşitli yöntemleri temsil eden temsilciler oluşturmak için sözdizimi gösterir.</span><span class="sxs-lookup"><span data-stu-id="227ee-121">The following code shows the syntax for creating delegates that represent various methods in a class.</span></span> <span data-ttu-id="227ee-122">Yöntem statik bir yöntem veya bir örnek yöntemi olup ve demet veya curried formundaki değişkenlerinde olup bağlı olarak bildirmek ve temsilci atamak için söz dizimi biraz farklıdır.</span><span class="sxs-lookup"><span data-stu-id="227ee-122">Depending on whether the method is a static method or an instance method, and whether it has arguments in the tuple form or the curried form, the syntax for declaring and assigning the delegate is a little different.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

<span data-ttu-id="227ee-123">Aşağıdaki kod temsilcileri ile çalışabilir farklı yollardan bazılarını gösterir.</span><span class="sxs-lookup"><span data-stu-id="227ee-123">The following code shows some of the different ways you can work with delegates.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

<span data-ttu-id="227ee-124">Önceki kod örnek çıktısı aşağıdaki gibidir.</span><span class="sxs-lookup"><span data-stu-id="227ee-124">The output of the previous code example is as follows.</span></span>

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a><span data-ttu-id="227ee-125">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="227ee-125">See also</span></span>

- [<span data-ttu-id="227ee-126">F# Dili Başvurusu</span><span class="sxs-lookup"><span data-stu-id="227ee-126">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="227ee-127">Parametreler ve Bağımsız Değişkenler</span><span class="sxs-lookup"><span data-stu-id="227ee-127">Parameters and Arguments</span></span>](parameters-and-arguments.md)
- [<span data-ttu-id="227ee-128">Olaylar</span><span class="sxs-lookup"><span data-stu-id="227ee-128">Events</span></span>](members/events.md)
