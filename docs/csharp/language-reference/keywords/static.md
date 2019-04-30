---
title: statik değiştirici - C# başvurusu
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: 90b043fa13f1737db81518151daaeceabf930c5c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61660690"
---
# <a name="static-c-reference"></a><span data-ttu-id="d3181-102">static (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="d3181-102">static (C# Reference)</span></span>

<span data-ttu-id="d3181-103">Kullanım `static` belirli bir nesne yerine türün kendisine ait olduğu statik bir üye bildirmek için değiştiricisi.</span><span class="sxs-lookup"><span data-stu-id="d3181-103">Use the `static` modifier to declare a static member, which belongs to the type itself rather than to a specific object.</span></span> <span data-ttu-id="d3181-104">`static` Değiştiricisi sınıflar, alanları, yöntemleri, özellikleri, işleçler, olaylar ve oluşturucular ile kullanılabilir, ancak dizin oluşturucular, bir sonlandırıcı ya da sınıfları dışındaki türler ile kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="d3181-104">The `static` modifier can be used with classes, fields, methods, properties, operators, events, and constructors, but it cannot be used with indexers, finalizers, or types other than classes.</span></span> <span data-ttu-id="d3181-105">Daha fazla bilgi için [statik sınıflar ve statik sınıf üyeleri](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="d3181-105">For more information, see [Static Classes and Static Class Members](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>

## <a name="example"></a><span data-ttu-id="d3181-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="d3181-106">Example</span></span>

<span data-ttu-id="d3181-107">Aşağıdaki sınıf olarak bildirilir `static` ve yalnızca içeren `static` yöntemleri:</span><span class="sxs-lookup"><span data-stu-id="d3181-107">The following class is declared as `static` and contains only `static` methods:</span></span>

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

<span data-ttu-id="d3181-108">Bir sabit değer veya tür bildirimi örtük olarak statik bir üyedir.</span><span class="sxs-lookup"><span data-stu-id="d3181-108">A constant or type declaration is implicitly a static member.</span></span>

<span data-ttu-id="d3181-109">Statik bir üyeye bir örnek başvurulamaz.</span><span class="sxs-lookup"><span data-stu-id="d3181-109">A static member cannot be referenced through an instance.</span></span> <span data-ttu-id="d3181-110">Bunun yerine, bu tür adı ile başvurulur.</span><span class="sxs-lookup"><span data-stu-id="d3181-110">Instead, it is referenced through the type name.</span></span> <span data-ttu-id="d3181-111">Örneğin, aşağıdaki sınıf göz önünde bulundurun:</span><span class="sxs-lookup"><span data-stu-id="d3181-111">For example, consider the following class:</span></span>

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

<span data-ttu-id="d3181-112">Statik bir üyeye başvuruda bulunmak için `x`, tam adı kullanmanız `MyBaseC.MyStruct.x`, üye aynı kapsamdan erişilebilir değilse:</span><span class="sxs-lookup"><span data-stu-id="d3181-112">To refer to the static member `x`, use the fully qualified name, `MyBaseC.MyStruct.x`, unless the member is accessible from the same scope:</span></span>

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

<span data-ttu-id="d3181-113">Bir sınıf örneği ayrı bir sınıfın tüm örnek alanları kopyasını içerirken, her bir statik alanı yalnızca bir kopyası yoktur.</span><span class="sxs-lookup"><span data-stu-id="d3181-113">While an instance of a class contains a separate copy of all instance fields of the class, there is only one copy of each static field.</span></span>

<span data-ttu-id="d3181-114">Kullanmak mümkün değil [bu](this.md) statik yöntemler veya özellik erişimcileri başvurmak için.</span><span class="sxs-lookup"><span data-stu-id="d3181-114">It is not possible to use [this](this.md) to reference static methods or property accessors.</span></span>

<span data-ttu-id="d3181-115">Varsa `static` anahtar sözcüğü, bir sınıfa uygulandığında, sınıfın tüm üyeleri statik olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="d3181-115">If the `static` keyword is applied to a class, all the members of the class must be static.</span></span>

<span data-ttu-id="d3181-116">Sınıflar ve statik sınıfların statik oluşturucuları olabilir.</span><span class="sxs-lookup"><span data-stu-id="d3181-116">Classes and static classes may have static constructors.</span></span> <span data-ttu-id="d3181-117">Statik oluşturucular arasında belirli bir noktada program başlar ve sınıfın örneği çağrılır.</span><span class="sxs-lookup"><span data-stu-id="d3181-117">Static constructors are called at some point between when the program starts and the class is instantiated.</span></span>

> [!NOTE]
> <span data-ttu-id="d3181-118">`static` Anahtar sözcüğü C++'ta kullanımı daha fazla sınırlı sahiptir.</span><span class="sxs-lookup"><span data-stu-id="d3181-118">The `static` keyword has more limited uses than in C++.</span></span> <span data-ttu-id="d3181-119">C++ anahtar sözcüğüyle karşılaştırmak için bkz [depolama sınıfları (C++)](/cpp/cpp/storage-classes-cpp#static).</span><span class="sxs-lookup"><span data-stu-id="d3181-119">To compare with the C++ keyword, see [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static).</span></span>

<span data-ttu-id="d3181-120">Statik üyeleri göstermek için bir şirket çalışanı temsil eden bir sınıf göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="d3181-120">To demonstrate static members, consider a class that represents a company employee.</span></span> <span data-ttu-id="d3181-121">Sınıf sayısı çalışan ve bir alan çalışanların sayısını depolamak için bir yöntem içerdiğini varsayın.</span><span class="sxs-lookup"><span data-stu-id="d3181-121">Assume that the class contains a method to count employees and a field to store the number of employees.</span></span> <span data-ttu-id="d3181-122">Yöntemi hem de alan hiçbir örneği çalışana ait değil.</span><span class="sxs-lookup"><span data-stu-id="d3181-122">Both the method and the field do not belong to any instance employee.</span></span> <span data-ttu-id="d3181-123">Bunun yerine şirket sınıfa ait.</span><span class="sxs-lookup"><span data-stu-id="d3181-123">Instead they belong to the company class.</span></span> <span data-ttu-id="d3181-124">Bu nedenle, statik sınıf üyeleri olarak bildirilmelidir.</span><span class="sxs-lookup"><span data-stu-id="d3181-124">Therefore, they should be declared as static members of the class.</span></span>

## <a name="example"></a><span data-ttu-id="d3181-125">Örnek</span><span class="sxs-lookup"><span data-stu-id="d3181-125">Example</span></span>

<span data-ttu-id="d3181-126">Bu örnekte yeni bir çalışanın Kimliğini ve adını okur, çalışan sayacı bir artar ve yeni çalışan ve yeni kaç kişi bilgilerini görüntüler.</span><span class="sxs-lookup"><span data-stu-id="d3181-126">This example reads the name and ID of a new employee, increments the employee counter by one, and displays the information for the new employee and the new number of employees.</span></span> <span data-ttu-id="d3181-127">Kolaylık olması için bu programı klavyeden çalışanların geçerli sayısını okur.</span><span class="sxs-lookup"><span data-stu-id="d3181-127">For simplicity, this program reads the current number of employees from the keyboard.</span></span> <span data-ttu-id="d3181-128">Gerçek bir uygulamada, bu bilgileri bir dosyadan okunmalıdır.</span><span class="sxs-lookup"><span data-stu-id="d3181-128">In a real application, this information should be read from a file.</span></span>

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example"></a><span data-ttu-id="d3181-129">Örnek</span><span class="sxs-lookup"><span data-stu-id="d3181-129">Example</span></span>

<span data-ttu-id="d3181-130">Bu örnek, henüz bildirilen başka bir statik alan kullanarak statik alanı başlatabilirsiniz, ancak açıkça statik alanı için bir değer atamak kadar sonuçlar tanımsız olacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="d3181-130">This example shows that although you can initialize a static field by using another static field not yet declared, the results will be undefined until you explicitly assign a value to the static field.</span></span>

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a><span data-ttu-id="d3181-131">C# dili belirtimi</span><span class="sxs-lookup"><span data-stu-id="d3181-131">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="d3181-132">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d3181-132">See also</span></span>

- [<span data-ttu-id="d3181-133">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="d3181-133">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d3181-134">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="d3181-134">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d3181-135">C# Anahtar Sözcükleri</span><span class="sxs-lookup"><span data-stu-id="d3181-135">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="d3181-136">Değiştiriciler</span><span class="sxs-lookup"><span data-stu-id="d3181-136">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="d3181-137">Statik Sınıflar ve Statik Sınıf Üyeleri</span><span class="sxs-lookup"><span data-stu-id="d3181-137">Static Classes and Static Class Members</span></span>](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)