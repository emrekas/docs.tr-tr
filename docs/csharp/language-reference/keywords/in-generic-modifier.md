---
title: in (genel değiştirici) - C# başvurusu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- contravariance, in keyword [C#]
- in keyword [C#]
ms.openlocfilehash: f736540a37d3226bccfc07749dcf06ca018663e8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61661470"
---
# <a name="in-generic-modifier-c-reference"></a><span data-ttu-id="6ba62-102">in (Genel Değiştirici) (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="6ba62-102">in (Generic Modifier) (C# Reference)</span></span>

<span data-ttu-id="6ba62-103">Genel tür parametreleri için `in` anahtar sözcüğü, tür parametresi değişken karşıtı olduğunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="6ba62-103">For generic type parameters, the `in` keyword specifies that the type parameter is contravariant.</span></span> <span data-ttu-id="6ba62-104">Kullanabileceğiniz `in` genel arabirimlerde ve temsilcilerde anahtar sözcük.</span><span class="sxs-lookup"><span data-stu-id="6ba62-104">You can use the `in` keyword in generic interfaces and delegates.</span></span>

<span data-ttu-id="6ba62-105">Kontravaryans, genel parametre olarak belirtilenden daha az türetilmiş bir tür belirtmenize olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="6ba62-105">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="6ba62-106">Bu değişken karşıtı arabirimleri uygulayan sınıflar örtük dönüştürülmesi ve temsilci türlerinin örtük dönüştürme için sağlar.</span><span class="sxs-lookup"><span data-stu-id="6ba62-106">This allows for implicit conversion of classes that implement contravariant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="6ba62-107">Kovaryans ve kontravaryans, genel tür parametreleri başvuru türleri için desteklenir ancak değer türleri için desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="6ba62-107">Covariance and contravariance in generic type parameters are supported for reference types, but they are not supported for value types.</span></span>

<span data-ttu-id="6ba62-108">Yalnızca bir yöntemin dönüş türü ve bir yöntemin parametre türü tanımlıyorsa türü değişken karşıtı genel arabirim veya temsilci olarak bildirilebilir.</span><span class="sxs-lookup"><span data-stu-id="6ba62-108">A type can be declared contravariant in a generic interface or delegate only if it defines the type of a method's parameters and not of a method's return type.</span></span> <span data-ttu-id="6ba62-109">`In`, `ref`, ve `out` parametreleri ne olduklarından yani sabit olmalıdır birlikte değişken veya değişken karşıtı.</span><span class="sxs-lookup"><span data-stu-id="6ba62-109">`In`, `ref`, and `out` parameters must be invariant, meaning they are neither covariant or contravariant.</span></span>

<span data-ttu-id="6ba62-110">Yöntemlerinden daha az türetilmiş türler arabirim türü parametresi ile belirtilen değerinden bağımsız değişkenleri kabul etmek bir değişken karşıtı tür parametresine sahip bir arabirim sağlar.</span><span class="sxs-lookup"><span data-stu-id="6ba62-110">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="6ba62-111">Örneğin, <xref:System.Collections.Generic.IComparer%601> arabirimi, T türü değişken karşıtı olduğundan, bir nesnenin atayabilirsiniz `IComparer<Person>` bir nesne türüne `IComparer<Employee>` özel dönüştürme yöntemleri kullanılarak olmadan türü `Employee` devralan `Person`.</span><span class="sxs-lookup"><span data-stu-id="6ba62-111">For example, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer<Person>` type to an object of the `IComparer<Employee>` type without using any special conversion methods if `Employee` inherits `Person`.</span></span>

<span data-ttu-id="6ba62-112">Başka bir temsilci aynı türden, ancak daha az türetilmiş bir genel tür parametresi değişken karşıtı temsilci atanabilir.</span><span class="sxs-lookup"><span data-stu-id="6ba62-112">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>

<span data-ttu-id="6ba62-113">Daha fazla bilgi için [Kovaryans ve kontravaryans](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="6ba62-113">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

## <a name="contravariant-generic-interface"></a><span data-ttu-id="6ba62-114">Değişken karşıtı genel arabirimi</span><span class="sxs-lookup"><span data-stu-id="6ba62-114">Contravariant generic interface</span></span>

<span data-ttu-id="6ba62-115">Aşağıdaki örnek, bildirmek, genişletin ve değişken karşıtı genel bir arabirim uygulamak gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="6ba62-115">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="6ba62-116">Ayrıca, bu arabirimi uygulayan sınıflar için örtük dönüştürme nasıl kullanabileceğinizi gösterir.</span><span class="sxs-lookup"><span data-stu-id="6ba62-116">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>

[!code-csharp[csVarianceKeywords#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#1)]

## <a name="contravariant-generic-delegate"></a><span data-ttu-id="6ba62-117">Değişken karşıtı Genel temsilci</span><span class="sxs-lookup"><span data-stu-id="6ba62-117">Contravariant generic delegate</span></span>

<span data-ttu-id="6ba62-118">Aşağıdaki örnek, bildirme, oluşturma ve değişken karşıtı Genel temsilci çağırma gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="6ba62-118">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="6ba62-119">Ayrıca, bir temsilci türü örtük olarak nasıl dönüştürebilirsiniz gösterir.</span><span class="sxs-lookup"><span data-stu-id="6ba62-119">It also shows how you can implicitly convert a delegate type.</span></span>

[!code-csharp[csVarianceKeywords#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="6ba62-120">C# dili belirtimi</span><span class="sxs-lookup"><span data-stu-id="6ba62-120">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="6ba62-121">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="6ba62-121">See also</span></span>

- [<span data-ttu-id="6ba62-122">out</span><span class="sxs-lookup"><span data-stu-id="6ba62-122">out</span></span>](out-generic-modifier.md)
- [<span data-ttu-id="6ba62-123">Kovaryans ve Kontravaryans</span><span class="sxs-lookup"><span data-stu-id="6ba62-123">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)
- [<span data-ttu-id="6ba62-124">Değiştiriciler</span><span class="sxs-lookup"><span data-stu-id="6ba62-124">Modifiers</span></span>](modifiers.md)
