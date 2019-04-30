---
title: using static yönergesi - C# başvurusu
ms.custom: seodec18
ms.date: 03/10/2017
helpviewer_keywords:
- using static directive [C#]
ms.assetid: 8b8f9e34-c75e-469b-ba85-6f2eb4090314
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29610a77eadf587162731b5bddbcc4bbe7fa0714
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61660339"
---
# <a name="using-static-directive-c-reference"></a><span data-ttu-id="a1df0-102">using static yönergesi (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="a1df0-102">using static directive (C# Reference)</span></span>

<span data-ttu-id="a1df0-103">`using static` Yönergesi, statik üyeleri ve iç içe geçmiş türler erişebileceğiniz bir tür adı belirtmeden bir tür belirler.</span><span class="sxs-lookup"><span data-stu-id="a1df0-103">The `using static` directive designates a type whose static members and nested types you can access without specifying a type name.</span></span> <span data-ttu-id="a1df0-104">Kendi sözdizimi aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="a1df0-104">Its syntax is:</span></span>

```csharp
using static <fully-qualified-type-name>;
```

<span data-ttu-id="a1df0-105">Burada *tam olarak nitelenmiş-tür adı* türün statik üyeleri adıdır ve iç içe geçmiş türler, tür adı belirtmeden başvurulabilir.</span><span class="sxs-lookup"><span data-stu-id="a1df0-105">where *fully-qualified-type-name* is the name of the type whose static members and nested types can be referenced without specifying a type name.</span></span> <span data-ttu-id="a1df0-106">Tam nitelikli tür adı (tür adıyla birlikte tam ad alanı adı), sağlamaz, C# derleyici hatası oluşturur [CS0246](../compiler-messages/cs0246.md): "' Türü/ad alanı' tür veya ad alanı adı bulunamadı (bir using eksik yönergeniz veya derleme başvurunuz?)".</span><span class="sxs-lookup"><span data-stu-id="a1df0-106">If you do not provide a fully qualified type name (the full namespace name along with the type name), C# generates compiler error [CS0246](../compiler-messages/cs0246.md): "The type or namespace name 'type/namespace' could not be found (are you missing a using directive or an assembly reference?)".</span></span>

<span data-ttu-id="a1df0-107">`using static` Yönergesi Ayrıca örnek üyeleri sahip olsa bile statik üyeler (veya iç içe geçmiş türler) olan herhangi bir türü için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="a1df0-107">The `using static` directive applies to any type that has static members (or nested types), even if it also has instance members.</span></span> <span data-ttu-id="a1df0-108">Ancak, örnek üyeleri yalnızca tür örneği çağrılabilir.</span><span class="sxs-lookup"><span data-stu-id="a1df0-108">However, instance members can only be invoked through the type instance.</span></span>

<span data-ttu-id="a1df0-109">`using static` Yönergesi, C# 6'da sunulmuştur.</span><span class="sxs-lookup"><span data-stu-id="a1df0-109">The `using static` directive was introduced in C# 6.</span></span>

## <a name="remarks"></a><span data-ttu-id="a1df0-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a1df0-110">Remarks</span></span>

<span data-ttu-id="a1df0-111">Normalde, bir statik üye çağırdığınızda, üye adıyla birlikte tür adı sağlayın.</span><span class="sxs-lookup"><span data-stu-id="a1df0-111">Ordinarily, when you call a static member, you provide the type name along with the member name.</span></span> <span data-ttu-id="a1df0-112">Art arda türün üyeleri çağırmak için aynı tür adı girerek, ayrıntılı, belirsiz kodu neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="a1df0-112">Repeatedly entering the same type name to invoke members of the type can result in verbose, obscure code.</span></span> <span data-ttu-id="a1df0-113">Örneğin, aşağıdaki tanımını bir `Circle` sınıfına başvuran bir dizi üyeleri <xref:System.Math> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="a1df0-113">For example, the following definition of a `Circle` class references a number of members of the <xref:System.Math> class.</span></span>

[!code-csharp[using-static#1](~/samples/snippets/csharp/language-reference/keywords/using/using-static1.cs#1)]

<span data-ttu-id="a1df0-114">Açıkça başvuru gereksinimini ortadan kaldıran tarafından <xref:System.Math> sınıf üyesi başvuruluyor, her zaman `using static` yönergesi çok daha temiz bir kod üretir:</span><span class="sxs-lookup"><span data-stu-id="a1df0-114">By eliminating the need to explicitly reference the <xref:System.Math> class each time a member is referenced, the `using static` directive produces much cleaner code:</span></span>

[!code-csharp[using-static#2](~/samples/snippets/csharp/language-reference/keywords/using/using-static2.cs#1)]

<span data-ttu-id="a1df0-115">`using static` yalnızca erişilebilir statik üyeleri ve belirtilen türde bildirilen iç içe geçmiş türleri içeri aktarır.</span><span class="sxs-lookup"><span data-stu-id="a1df0-115">`using static` imports only accessible static members and nested types declared in the specified type.</span></span>  <span data-ttu-id="a1df0-116">Devralınan üyeleri içeri aktarılmaz.</span><span class="sxs-lookup"><span data-stu-id="a1df0-116">Inherited members are not imported.</span></span>  <span data-ttu-id="a1df0-117">Kullanarak herhangi bir adlandırılmış tür içeri aktarabileceğiniz static yönergesi, Visual Basic modülleri dahil.</span><span class="sxs-lookup"><span data-stu-id="a1df0-117">You can import from any named type with a using static directive, including Visual Basic modules.</span></span>  <span data-ttu-id="a1df0-118">Varsa F# adı, geçerli bir adlandırılmış bir türün statik üyeleri en üst düzey işlevler görünür meta verilerde C# tanımlayıcısı, ardından F# işlevleri alınabilir.</span><span class="sxs-lookup"><span data-stu-id="a1df0-118">If F# top-level functions appear in metadata as static members of a named type whose name is a valid C# identifier, then the F# functions can be imported.</span></span>

 <span data-ttu-id="a1df0-119">`using static` Uzantı yöntemi araması için kullanılabilen belirtilen türde bildirilen genişletme yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="a1df0-119">`using static` makes extension methods declared in the specified type available for extension method lookup.</span></span>  <span data-ttu-id="a1df0-120">Ancak, genişletme yöntemleri adlarını nitelenmemiş bir başvuru kod kapsama içeri aktarılmaz.</span><span class="sxs-lookup"><span data-stu-id="a1df0-120">However, the names of the extension methods are not imported into scope for unqualified reference in code.</span></span>

 <span data-ttu-id="a1df0-121">Farklı türlerden farklı tarafından alınan aynı ada sahip yöntem `using static` yönergeleri aynı derleme biriminde veya ad alanı bir yöntem grubu oluşturur.</span><span class="sxs-lookup"><span data-stu-id="a1df0-121">Methods with the same name imported from different types by different `using static` directives in the same compilation unit or namespace form a method group.</span></span>  <span data-ttu-id="a1df0-122">Bu yöntem grupları aşırı yükleme çözünürlüğüne normal C# kurallara uygun olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="a1df0-122">Overload resolution within these method groups follows normal C# rules.</span></span>

## <a name="example"></a><span data-ttu-id="a1df0-123">Örnek</span><span class="sxs-lookup"><span data-stu-id="a1df0-123">Example</span></span>

<span data-ttu-id="a1df0-124">Aşağıdaki örnekte `using static` statik üyelerinden birini yapmak için yönergesi <xref:System.Console>, <xref:System.Math>, ve <xref:System.String> sınıflarının kendi tür adını belirtmenize gerek kalmadan kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="a1df0-124">The following example uses the `using static` directive to make the static members of the <xref:System.Console>, <xref:System.Math>, and <xref:System.String> classes available without having to specify their type name.</span></span>

[!code-csharp[using-static#3](~/samples/snippets/csharp/language-reference/keywords/using/using-static3.cs)]

<span data-ttu-id="a1df0-125">Örnekte, `using static` yönergesi ayrıca uygulanıp uygulanmadığını için <xref:System.Double> türü.</span><span class="sxs-lookup"><span data-stu-id="a1df0-125">In the example, the `using static` directive could also have been applied to the <xref:System.Double> type.</span></span> <span data-ttu-id="a1df0-126">Bu, çağrılabilir alacağımızdı <xref:System.Double.TryParse(System.String,System.Double@)> türü adı belirtilmeden yöntemi.</span><span class="sxs-lookup"><span data-stu-id="a1df0-126">This would have made it possible to call the <xref:System.Double.TryParse(System.String,System.Double@)> method without specifying a type name.</span></span> <span data-ttu-id="a1df0-127">Ancak, bu daha okunabilir bir kod oluşturur denetlemek gerekli hale beri `using static` hangi sayısal türün belirlemek için ifadeleri `TryParse` yöntemi çağrılır.</span><span class="sxs-lookup"><span data-stu-id="a1df0-127">However, this creates less readable code, since it becomes necessary to check the `using static` statements to determine which numeric type's `TryParse` method is called.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1df0-128">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="a1df0-128">See also</span></span>

- [<span data-ttu-id="a1df0-129">using yönergesi</span><span class="sxs-lookup"><span data-stu-id="a1df0-129">using directive</span></span>](using-directive.md)
- [<span data-ttu-id="a1df0-130">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="a1df0-130">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a1df0-131">C# Anahtar Sözcükleri</span><span class="sxs-lookup"><span data-stu-id="a1df0-131">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a1df0-132">Ad Alanlarını Kullanma</span><span class="sxs-lookup"><span data-stu-id="a1df0-132">Using Namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)
- [<span data-ttu-id="a1df0-133">Ad Alanı Anahtar Sözcükleri</span><span class="sxs-lookup"><span data-stu-id="a1df0-133">Namespace Keywords</span></span>](namespace-keywords.md)
- [<span data-ttu-id="a1df0-134">Ad Alanları</span><span class="sxs-lookup"><span data-stu-id="a1df0-134">Namespaces</span></span>](../../programming-guide/namespaces/index.md)
