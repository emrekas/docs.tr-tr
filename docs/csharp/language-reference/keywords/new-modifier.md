---
title: New değiştiricisi - C# başvurusu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- new modifier keyword [C#]
ms.assetid: a2e20856-33b9-4620-b535-a60dbce8349b
ms.openlocfilehash: 675369936b9f90620b03365104255a622855fa9f
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2019
ms.locfileid: "67401793"
---
# <a name="new-modifier-c-reference"></a><span data-ttu-id="90eca-102">New değiştiricisi (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="90eca-102">new modifier (C# Reference)</span></span>

<span data-ttu-id="90eca-103">Bir bildirim değiştirici olarak kullanıldığında `new` anahtar sözcüğü açıkça bir temel sınıftan devralınan üyeyi gizler.</span><span class="sxs-lookup"><span data-stu-id="90eca-103">When used as a declaration modifier, the `new` keyword explicitly hides a member that is inherited from a base class.</span></span> <span data-ttu-id="90eca-104">Devralınmış bir üyeyi gizlediğinizde, üyenin sürümü temel sınıftaki sürümün yerine geçer.</span><span class="sxs-lookup"><span data-stu-id="90eca-104">When you hide an inherited member, the derived version of the member replaces the base class version.</span></span> <span data-ttu-id="90eca-105">Üyeleri kullanmadan gizleyebilmenize rağmen `new` değiştiricisi, bir derleyici uyarısı alırsınız.</span><span class="sxs-lookup"><span data-stu-id="90eca-105">Although you can hide members without using the `new` modifier, you get a compiler warning.</span></span> <span data-ttu-id="90eca-106">Kullanırsanız `new` bir üyeyi açıkça gizlemek için bu uyarı bastırılır.</span><span class="sxs-lookup"><span data-stu-id="90eca-106">If you use `new` to explicitly hide a member, it suppresses this warning.</span></span>

<span data-ttu-id="90eca-107">Ayrıca `new` anahtar [bir türün bir örneğini oluşturmak](../operators/new-operator.md) veya farklı bir [genel tür kısıtlaması](../keywords/new-constraint.md).</span><span class="sxs-lookup"><span data-stu-id="90eca-107">You can also use the `new` keyword to [create an instance of a type](../operators/new-operator.md) or as a [generic type constraint](../keywords/new-constraint.md).</span></span>

<span data-ttu-id="90eca-108">Devralınan bir üyeyi gizlemek için türetilen sınıfta aynı üye adını kullanarak bildirin ve değiştirin `new` anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="90eca-108">To hide an inherited member, declare it in the derived class by using the same member name, and modify it with the `new` keyword.</span></span> <span data-ttu-id="90eca-109">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="90eca-109">For example:</span></span>

[!code-csharp[csrefKeywordsOperator#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#8)]

<span data-ttu-id="90eca-110">Bu örnekte, `BaseC.Invoke` tarafından gizleniyor `DerivedC.Invoke`.</span><span class="sxs-lookup"><span data-stu-id="90eca-110">In this example, `BaseC.Invoke` is hidden by `DerivedC.Invoke`.</span></span> <span data-ttu-id="90eca-111">Alan `x` çünkü benzer bir adla gizlenmediğinden etkilenmez.</span><span class="sxs-lookup"><span data-stu-id="90eca-111">The field `x` is not affected because it is not hidden by a similar name.</span></span>

<span data-ttu-id="90eca-112">Devralma üzerinden ad gizleme aşağıdaki biçimlerden birini alır:</span><span class="sxs-lookup"><span data-stu-id="90eca-112">Name hiding through inheritance takes one of the following forms:</span></span>

- <span data-ttu-id="90eca-113">Genellikle, bir sabit, alan, özelliği veya bir sınıf veya yapı içinde tanıtılan türü kendi adını paylaşan tüm taban sınıfı üyelerini gizler.</span><span class="sxs-lookup"><span data-stu-id="90eca-113">Generally, a constant, field, property, or type that is introduced in a class or struct hides all base class members that share its name.</span></span> <span data-ttu-id="90eca-114">Özel durumlar vardır.</span><span class="sxs-lookup"><span data-stu-id="90eca-114">There are special cases.</span></span> <span data-ttu-id="90eca-115">Örneğin, adı ile yeni bir alan bildirmek `N` çağrılmayan bir tür ve temel tür olduğunu `N` bir yöntemi olması için yeni alan taban bildirimini çağırma sözdiziminde gizlemez.</span><span class="sxs-lookup"><span data-stu-id="90eca-115">For example, if you declare a new field with name `N` to have a type that is not invocable, and a base type declares `N` to be a method, the new field does not hide the base declaration in invocation syntax.</span></span> <span data-ttu-id="90eca-116">Daha fazla bilgi için [üye araması](~/_csharplang/spec/expressions.md#member-lookup) bölümünü [ C# dil belirtimi](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="90eca-116">For more information, see the [Member lookup](~/_csharplang/spec/expressions.md#member-lookup) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

- <span data-ttu-id="90eca-117">Bir sınıf ya da struct'a dahil edilen bir yöntem özellikleri, alanları ve temel sınıfta bu adı paylaşan türleri gizler.</span><span class="sxs-lookup"><span data-stu-id="90eca-117">A method introduced in a class or struct hides properties, fields, and types that share that name in the base class.</span></span> <span data-ttu-id="90eca-118">Ayrıca, aynı imzaya sahip tüm taban sınıfı yöntemlerini gizler.</span><span class="sxs-lookup"><span data-stu-id="90eca-118">It also hides all base class methods that have the same signature.</span></span>

- <span data-ttu-id="90eca-119">Bir sınıf veya yapı içinde tanıtılan bir dizin oluşturucu, aynı imzaya sahip tüm taban sınıfı dizin oluşturucularını gizler.</span><span class="sxs-lookup"><span data-stu-id="90eca-119">An indexer introduced in a class or struct hides all base class indexers that have the same signature.</span></span>

<span data-ttu-id="90eca-120">Her ikisi de kullanmak için bir hata olduğunu `new` ve [geçersiz kılma](override.md) aynı üyede, çünkü iki değiştirici karşılıklı özel anlamlara sahiptir.</span><span class="sxs-lookup"><span data-stu-id="90eca-120">It is an error to use both `new` and [override](override.md) on the same member, because the two modifiers have mutually exclusive meanings.</span></span> <span data-ttu-id="90eca-121">`new` Değiştiricisi, aynı ada sahip yeni bir üye oluşturur ve ilk üyenin gizli hale gelmesine neden olur.</span><span class="sxs-lookup"><span data-stu-id="90eca-121">The `new` modifier creates a new member with the same name and causes the original member to become hidden.</span></span> <span data-ttu-id="90eca-122">`override` Değiştiricisi devralınan bir üyenin uygulanmasını genişletir.</span><span class="sxs-lookup"><span data-stu-id="90eca-122">The `override` modifier extends the implementation for an inherited member.</span></span>

<span data-ttu-id="90eca-123">Kullanarak `new` değiştiricisi devralınan bir üyeyi gizlemek olmayan bir bildirimde kullanmak bir uyarı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="90eca-123">Using the `new` modifier in a declaration that does not hide an inherited member generates a warning.</span></span>

## <a name="example"></a><span data-ttu-id="90eca-124">Örnek</span><span class="sxs-lookup"><span data-stu-id="90eca-124">Example</span></span>

<span data-ttu-id="90eca-125">Bu örnekte, bir temel sınıf `BaseC`ve bir türetilen sınıf `DerivedC`, aynı alan adını kullanan `x`, devralınan alandaki değeri gizleyen.</span><span class="sxs-lookup"><span data-stu-id="90eca-125">In this example, a base class, `BaseC`, and a derived class, `DerivedC`, use the same field name `x`, which hides the value of the inherited field.</span></span> <span data-ttu-id="90eca-126">Bu örnek kullanımını gösterir `new` değiştiricisi.</span><span class="sxs-lookup"><span data-stu-id="90eca-126">The example demonstrates the use of the `new` modifier.</span></span> <span data-ttu-id="90eca-127">Ayrıca bunların tam nitelikli adlarını kullanarak taban sınıfının gizlenmiş üyelerine nasıl erişileceğini gösteren.</span><span class="sxs-lookup"><span data-stu-id="90eca-127">It also demonstrates how to access the hidden members of the base class by using their fully qualified names.</span></span>

[!code-csharp[csrefKeywordsOperator#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#9)]

## <a name="example"></a><span data-ttu-id="90eca-128">Örnek</span><span class="sxs-lookup"><span data-stu-id="90eca-128">Example</span></span>

<span data-ttu-id="90eca-129">Bu örnekte, iç içe geçmiş bir sınıf taban sınıfında aynı ada sahip bir sınıfı gizler.</span><span class="sxs-lookup"><span data-stu-id="90eca-129">In this example, a nested class hides a class that has the same name in the base class.</span></span> <span data-ttu-id="90eca-130">Bu örnek nasıl kullanılacağını gösterir `new` değiştiricisi uyarı iletisini ve gizli sınıf üyelerine bunların tam nitelikli adlarını kullanarak erişmek nasıl ortadan kaldırmak için.</span><span class="sxs-lookup"><span data-stu-id="90eca-130">The example demonstrates how to use the `new` modifier to eliminate the warning message and how to access the hidden class members by using their fully qualified names.</span></span>

[!code-csharp[csrefKeywordsOperator#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#10)]

<span data-ttu-id="90eca-131">Kaldırırsanız `new` değiştiricisi, program hala derler ve çalışır, ancak aşağıdaki uyarıyı alırsınız:</span><span class="sxs-lookup"><span data-stu-id="90eca-131">If you remove the `new` modifier, the program will still compile and run, but you will get the following warning:</span></span>

```text
The keyword new is required on 'MyDerivedC.x' because it hides inherited member 'MyBaseC.x'.
```

## <a name="c-language-specification"></a><span data-ttu-id="90eca-132">C# dili belirtimi</span><span class="sxs-lookup"><span data-stu-id="90eca-132">C# language specification</span></span>

<span data-ttu-id="90eca-133">Daha fazla bilgi için [yeni değiştiricisini](~/_csharplang/spec/classes.md#the-new-modifier) bölümünü [ C# dil belirtimi](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="90eca-133">For more information, see [The new modifier](~/_csharplang/spec/classes.md#the-new-modifier) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="90eca-134">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="90eca-134">See also</span></span>

- [<span data-ttu-id="90eca-135">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="90eca-135">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="90eca-136">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="90eca-136">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="90eca-137">C# Anahtar Sözcükleri</span><span class="sxs-lookup"><span data-stu-id="90eca-137">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="90eca-138">Değiştiriciler</span><span class="sxs-lookup"><span data-stu-id="90eca-138">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="90eca-139">Geçersiz Kılma ve Yeni Anahtar Sözcüklerle Sürüm Oluşturma</span><span class="sxs-lookup"><span data-stu-id="90eca-139">Versioning with the Override and New Keywords</span></span>](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)
- [<span data-ttu-id="90eca-140">Geçersiz Kılmanın ve Yeni Anahtar Sözcüklerin Ne Zaman Kullanılacağını Bilme</span><span class="sxs-lookup"><span data-stu-id="90eca-140">Knowing When to Use Override and New Keywords</span></span>](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)
