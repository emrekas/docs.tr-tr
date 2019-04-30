---
title: out anahtar sözcüğü (genel değiştirici) - C# başvurusu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, out keyword [C#]
- out keyword [C#]
ms.assetid: f8c20dec-a8bc-426a-9882-4076b1db1e00
ms.openlocfilehash: 1316228a186976f313bb9f10032262974243a3ae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61661041"
---
# <a name="out-generic-modifier-c-reference"></a><span data-ttu-id="427b3-102">out (genel değiştirici) (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="427b3-102">out (generic modifier) (C# Reference)</span></span>

<span data-ttu-id="427b3-103">Genel tür parametreleri için `out` anahtar sözcüğü, tür parametresi birlikte değişken olduğunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="427b3-103">For generic type parameters, the `out` keyword specifies that the type parameter is covariant.</span></span> <span data-ttu-id="427b3-104">Kullanabileceğiniz `out` genel arabirimlerde ve temsilcilerde anahtar sözcük.</span><span class="sxs-lookup"><span data-stu-id="427b3-104">You can use the `out` keyword in generic interfaces and delegates.</span></span>

<span data-ttu-id="427b3-105">Kovaryans genel parametre olarak belirtilenden daha türetilmiş bir tür belirtmenize olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="427b3-105">Covariance enables you to use a more derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="427b3-106">Bu, birlikte değişken arabirimleri uygulayan sınıflar örtük dönüştürülmesi ve temsilci türlerinin örtük dönüştürme için sağlar.</span><span class="sxs-lookup"><span data-stu-id="427b3-106">This allows for implicit conversion of classes that implement covariant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="427b3-107">Kovaryans ve kontravaryans başvuru türleri için desteklenir ancak değer türleri için desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="427b3-107">Covariance and contravariance are supported for reference types, but they are not supported for value types.</span></span>

<span data-ttu-id="427b3-108">Dönüş türü parametresi tarafından belirtilenlerden daha türetilmiş türleri metotlarını bir birlikte değişen türde parametresi olan bir arabirim sağlar.</span><span class="sxs-lookup"><span data-stu-id="427b3-108">An interface that has a covariant type parameter enables its methods to return more derived types than those specified by the type parameter.</span></span> <span data-ttu-id="427b3-109">Örneğin, çünkü .NET Framework 4 içinde <xref:System.Collections.Generic.IEnumerable%601>T türü birlikte değişken, bir nesnenin atayabilirsiniz `IEnumerable(Of String)` bir nesne türüne `IEnumerable(Of Object)` herhangi bir özel dönüştürme yöntemini kullanmadan türü.</span><span class="sxs-lookup"><span data-stu-id="427b3-109">For example, because in .NET Framework 4, in <xref:System.Collections.Generic.IEnumerable%601>, type T is covariant, you can assign an object of the `IEnumerable(Of String)` type to an object of the `IEnumerable(Of Object)` type without using any special conversion methods.</span></span>

<span data-ttu-id="427b3-110">Birlikte değişen bir temsilci, aynı türden, ancak daha fazla türetilmiş bir genel tür parametresi ile başka bir temsilci atanabilir.</span><span class="sxs-lookup"><span data-stu-id="427b3-110">A covariant delegate can be assigned another delegate of the same type, but with a more derived generic type parameter.</span></span>

<span data-ttu-id="427b3-111">Daha fazla bilgi için [Kovaryans ve kontravaryans](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="427b3-111">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

## <a name="example---covariant-generic-interface"></a><span data-ttu-id="427b3-112">Örnek - birlikte değişken genel arabirim</span><span class="sxs-lookup"><span data-stu-id="427b3-112">Example - covariant generic interface</span></span>

<span data-ttu-id="427b3-113">Aşağıdaki örnek, bildirmek, genişletin ve bir değişken genel arabirim uygulamak gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="427b3-113">The following example shows how to declare, extend, and implement a covariant generic interface.</span></span> <span data-ttu-id="427b3-114">Ayrıca, birlikte değişen bir arabirimi uygulayan sınıflar için örtük dönüştürme kullanmayı gösterir.</span><span class="sxs-lookup"><span data-stu-id="427b3-114">It also shows how to use implicit conversion for classes that implement a covariant interface.</span></span>

[!code-csharp[csVarianceKeywords#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#3)]

<span data-ttu-id="427b3-115">Genel arabiriminin tür parametresi aşağıdaki koşulları karşılıyorsa, birlikte değişken bildirilebilir:</span><span class="sxs-lookup"><span data-stu-id="427b3-115">In a generic interface, a type parameter can be declared covariant if it satisfies the following conditions:</span></span>

- <span data-ttu-id="427b3-116">Tür parametresi yalnızca bir dönüş türü arabirim yöntemleri olarak kullanılan ve yöntem bağımsız bir türü olarak kullanılmaz.</span><span class="sxs-lookup"><span data-stu-id="427b3-116">The type parameter is used only as a return type of interface methods and not used as a type of method arguments.</span></span>

    > [!NOTE]
    > <span data-ttu-id="427b3-117">Bu kuralın tek istisnası yoktur.</span><span class="sxs-lookup"><span data-stu-id="427b3-117">There is one exception to this rule.</span></span> <span data-ttu-id="427b3-118">Birlikte değişen bir arabirimde bir yöntem parametresi olarak bir değişken karşıtı Genel temsilci varsa, birlikte değişken türünde genel tür parametre olarak bu metot temsilcisi için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="427b3-118">If in a covariant interface you have a contravariant generic delegate as a method parameter, you can use the covariant type as a generic type parameter for this delegate.</span></span> <span data-ttu-id="427b3-119">Birlikte değişken hakkında daha fazla bilgi ve değişken karşıtı genel temsilciler [Temsilcilerde varyans](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) ve [işlev ve eylem genel temsilcileri için varyans kullanma](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="427b3-119">For more information about covariant and contravariant generic delegates, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>

- <span data-ttu-id="427b3-120">Tür parametresi, arabirim yöntemleri için genel bir kısıtlama kullanılmaz.</span><span class="sxs-lookup"><span data-stu-id="427b3-120">The type parameter is not used as a generic constraint for the interface methods.</span></span>

## <a name="example---covariant-generic-delegate"></a><span data-ttu-id="427b3-121">Örnek - birlikte değişken Genel temsilci</span><span class="sxs-lookup"><span data-stu-id="427b3-121">Example - covariant generic delegate</span></span>

<span data-ttu-id="427b3-122">Aşağıdaki örnek, bildirme, oluşturma ve birlikte değişken temsilci çağırma gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="427b3-122">The following example shows how to declare, instantiate, and invoke a covariant generic delegate.</span></span> <span data-ttu-id="427b3-123">Ayrıca, örtük olarak temsilci türleri dönüştürme yapılacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="427b3-123">It also shows how to implicitly convert delegate types.</span></span>

[!code-csharp[csVarianceKeywords#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#4)]

<span data-ttu-id="427b3-124">Yalnızca bir yöntem dönüş türü kullanılan ve kullanılmayan yöntem bağımsız değişkenleri için genel bir temsilci türü birlikte değişken olarak bildirilebilir.</span><span class="sxs-lookup"><span data-stu-id="427b3-124">In a generic delegate, a type can be declared covariant if it is used only as a method return type and not used for method arguments.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="427b3-125">C# dili belirtimi</span><span class="sxs-lookup"><span data-stu-id="427b3-125">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="427b3-126">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="427b3-126">See also</span></span>

- [<span data-ttu-id="427b3-127">Genel Arabirimlerde Varyans</span><span class="sxs-lookup"><span data-stu-id="427b3-127">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [<span data-ttu-id="427b3-128">in</span><span class="sxs-lookup"><span data-stu-id="427b3-128">in</span></span>](in-generic-modifier.md)
- [<span data-ttu-id="427b3-129">Değiştiriciler</span><span class="sxs-lookup"><span data-stu-id="427b3-129">Modifiers</span></span>](modifiers.md)
