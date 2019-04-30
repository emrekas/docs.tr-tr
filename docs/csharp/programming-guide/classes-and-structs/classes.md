---
title: Sınıfları - C# Programlama Kılavuzu
ms.custom: seodec18
description: Sınıf türleri ve bunların nasıl oluşturulacağı hakkında bilgi edinin
ms.date: 08/21/2018
helpviewer_keywords:
- classes [C#]
- C# language, classes
ms.assetid: e8848524-7273-429f-8aba-c658d5eff5ad
ms.openlocfilehash: 4cea68e76c17e5393ab7213f457c0875cdc5b53b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651890"
---
# <a name="classes-c-programming-guide"></a><span data-ttu-id="63f46-103">Sınıflar (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="63f46-103">Classes (C# Programming Guide)</span></span>

## <a name="reference-types"></a><span data-ttu-id="63f46-104">Başvuru türleri</span><span class="sxs-lookup"><span data-stu-id="63f46-104">Reference types</span></span>  
<span data-ttu-id="63f46-105">Olarak tanımlanan bir tür bir [sınıfı](../../../csharp/language-reference/keywords/class.md) olduğu bir *başvuru türüne*.</span><span class="sxs-lookup"><span data-stu-id="63f46-105">A type that is defined as a [class](../../../csharp/language-reference/keywords/class.md) is a *reference type*.</span></span> <span data-ttu-id="63f46-106">Bir değişken bildirdiğinizde başvuru türü, çalışma zamanında değişken değeri içeren [null](../../../csharp/language-reference/keywords/null.md) açıkça kullanarak sınıfının bir örneğini oluşturana kadar [yeni](../../../csharp/language-reference/keywords/new.md) işleci veya bir nesne atama bir başka bir yerde, aşağıdaki örnekte gösterildiği gibi oluşturulmuş olabilir uyumlu türü:</span><span class="sxs-lookup"><span data-stu-id="63f46-106">At run time, when you declare a variable of a reference type, the variable contains the value [null](../../../csharp/language-reference/keywords/null.md) until you explicitly create an instance of the class by using the [new](../../../csharp/language-reference/keywords/new.md) operator, or assign it an object of a compatible type that may have been created elsewhere, as shown in the following example:</span></span>

```csharp
//Declaring an object of type MyClass.
MyClass mc = new MyClass();

//Declaring another object of the same type, assigning it the value of the first object.
MyClass mc2 = mc;
```

<span data-ttu-id="63f46-107">Nesne oluşturulduğunda, yeterli bellek, belirli bir nesnesi için yönetilen yığında ayrılır ve değişken yalnızca söz konusu nesnenin konumuna yönelik bir başvuru tutar.</span><span class="sxs-lookup"><span data-stu-id="63f46-107">When the object is created, enough memory is allocated on the managed heap for that specific object, and the variable holds only a reference to the location of said object.</span></span> <span data-ttu-id="63f46-108">Yönetilen yığındaki türler ayrıldıkları zaman hem olarak da bilinen CLR'nin otomatik bellek yönetimi işlevinin tarafından talep edilen zaman ek yükü gerektirir *çöp toplama*.</span><span class="sxs-lookup"><span data-stu-id="63f46-108">Types on the managed heap require overhead both when they are allocated and when they are reclaimed by the automatic memory management functionality of the CLR, which is known as *garbage collection*.</span></span> <span data-ttu-id="63f46-109">Ancak, çöp toplama yüksek oranda iyileştirilmiştir ve çoğu senaryoda, bir performans sorununa neden olmaz.</span><span class="sxs-lookup"><span data-stu-id="63f46-109">However, garbage collection is also highly optimized and in most scenarios, it does not create a performance issue.</span></span> <span data-ttu-id="63f46-110">Çöp toplama hakkında daha fazla bilgi için bkz: [otomatik bellek yönetimi ve çöp toplama](../../../standard/garbage-collection/gc.md).</span><span class="sxs-lookup"><span data-stu-id="63f46-110">For more information about garbage collection, see [Automatic memory management and garbage collection](../../../standard/garbage-collection/gc.md).</span></span>  
  
## <a name="declaring-classes"></a><span data-ttu-id="63f46-111">Sınıfları Bildirme</span><span class="sxs-lookup"><span data-stu-id="63f46-111">Declaring Classes</span></span>

 <span data-ttu-id="63f46-112">Sınıfları kullanarak bildirilir [sınıfı](../../../csharp/language-reference/keywords/class.md) benzersiz bir tanımlayıcı aşağıdaki örnekte gösterildiği gibi anahtar sözcüğünü:</span><span class="sxs-lookup"><span data-stu-id="63f46-112">Classes are declared by using the [class](../../../csharp/language-reference/keywords/class.md) keyword followed by a unique identifier, as shown in the following example:</span></span>

 ```csharp
//[access modifier] - [class] - [identifier]
 public class Customer
 {
    // Fields, properties, methods and events go here...
 }
```

 <span data-ttu-id="63f46-113">`class` Anahtar sözcüğü erişim düzeyi tarafından öncesinde.</span><span class="sxs-lookup"><span data-stu-id="63f46-113">The `class` keyword is preceded by the access level.</span></span> <span data-ttu-id="63f46-114">Çünkü [genel](../../language-reference/keywords/public.md) kullanılan herkes bu sınıfın örnekleri, bu durumda, oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="63f46-114">Because [public](../../language-reference/keywords/public.md) is used in this case, anyone can create instances of this class.</span></span> <span data-ttu-id="63f46-115">Sınıf adını izleyen `class` anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="63f46-115">The name of the class follows the `class` keyword.</span></span> <span data-ttu-id="63f46-116">Sınıfın adı geçerli C# olmalıdır [tanımlayıcı adı](../inside-a-program/identifier-names.md).</span><span class="sxs-lookup"><span data-stu-id="63f46-116">The name of the class must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span> <span data-ttu-id="63f46-117">Tanımı geri kalanında sınıfı, davranış ve veri tanımlandığı gövdesidir.</span><span class="sxs-lookup"><span data-stu-id="63f46-117">The remainder of the definition is the class body, where the behavior and data are defined.</span></span> <span data-ttu-id="63f46-118">Alanlar, özellikler, yöntemler ve olaylar sınıfta topluca denir *sınıf üyeleri*.</span><span class="sxs-lookup"><span data-stu-id="63f46-118">Fields, properties, methods, and events on a class are collectively referred to as *class members*.</span></span>  
  
## <a name="creating-objects"></a><span data-ttu-id="63f46-119">Nesneleri oluşturma</span><span class="sxs-lookup"><span data-stu-id="63f46-119">Creating objects</span></span>

<span data-ttu-id="63f46-120">Bazen kavramlarının birbirinin yerine kullanıldığı olsa da, bir sınıf ve nesne farklı noktalardır.</span><span class="sxs-lookup"><span data-stu-id="63f46-120">Although they are sometimes used interchangeably, a class and an object are different things.</span></span> <span data-ttu-id="63f46-121">Bir nesne türüyle bir sınıf tanımlar, ancak bir nesne değil.</span><span class="sxs-lookup"><span data-stu-id="63f46-121">A class defines a type of object, but it is not an object itself.</span></span> <span data-ttu-id="63f46-122">Bir nesne sınıfına göre somut bir varlık ve bazen bir sınıfın bir örneği da adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="63f46-122">An object is a concrete entity based on a class, and is sometimes referred to as an instance of a class.</span></span>  
  
 <span data-ttu-id="63f46-123">Nesneleri kullanarak oluşturulabilir [yeni](../../language-reference/keywords/new.md) anahtar sözcüğü bir nesne, temel sınıfın adını ardından şöyle:</span><span class="sxs-lookup"><span data-stu-id="63f46-123">Objects can be created by using the [new](../../language-reference/keywords/new.md) keyword followed by the name of the class that the object will be based on, like this:</span></span>  

 ```csharp
 Customer object1 = new Customer();
 ```

 <span data-ttu-id="63f46-124">Bir sınıfın bir örneği oluşturulduğunda nesnesine bir başvuru programcıya geçirilir.</span><span class="sxs-lookup"><span data-stu-id="63f46-124">When an instance of a class is created, a reference to the object is passed back to the programmer.</span></span> <span data-ttu-id="63f46-125">Önceki örnekte, `object1` temel alan bir nesneye bir başvurudur `Customer`.</span><span class="sxs-lookup"><span data-stu-id="63f46-125">In the previous example, `object1` is a reference to an object that is based on `Customer`.</span></span> <span data-ttu-id="63f46-126">Bu başvuru yeni bir nesneye başvuruyor, ancak nesne verisi içermiyor.</span><span class="sxs-lookup"><span data-stu-id="63f46-126">This reference refers to the new object but does not contain the object data itself.</span></span> <span data-ttu-id="63f46-127">Aslında, bir nesne başvurusu bir nesne oluşturulmadan oluşturabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="63f46-127">In fact, you can create an object reference without creating an object at all:</span></span>  
 
```csharp
 Customer object2;
```
 
 <span data-ttu-id="63f46-128">Bunun gibi bir nesne gibi bir başvuru erişmeye çalışıyor, çalışma zamanında başarısız olacağı için bir nesneye başvuran olmayan nesne başvuruları oluşturmak önerilmemektedir.</span><span class="sxs-lookup"><span data-stu-id="63f46-128">We don't recommend creating object references such as this one that don't refer to an object because trying to access an object through such a reference will fail at run time.</span></span> <span data-ttu-id="63f46-129">Ancak, bir nesneye yeni bir nesne oluşturarak veya atayarak bu gibi varolan bir nesneye başvurmak için böyle bir başvuruyu yapılabilir:</span><span class="sxs-lookup"><span data-stu-id="63f46-129">However, such a reference can be made to refer to an object, either by creating a new object, or by assigning it to an existing object, such as this:</span></span>  

 ```csharp
 Customer object3 = new Customer();
 Customer object4 = object3;
```
  
 <span data-ttu-id="63f46-130">Bu kod, iki nesne başvuru oluşturur hem de aynı nesneye başvurur.</span><span class="sxs-lookup"><span data-stu-id="63f46-130">This code creates two object references that both refer to the same object.</span></span> <span data-ttu-id="63f46-131">Bu nedenle, nesne aracılığıyla yapılan değişiklikleri `object3` sonraki kullanımları içinde yansıtılır `object4`.</span><span class="sxs-lookup"><span data-stu-id="63f46-131">Therefore, any changes to the object made through `object3` are reflected in subsequent uses of `object4`.</span></span> <span data-ttu-id="63f46-132">Sınıflara göre nesneleri başvuruya göre adlandırılır çünkü sınıflar başvuru türleri olarak bilinir.</span><span class="sxs-lookup"><span data-stu-id="63f46-132">Because objects that are based on classes are referred to by reference, classes are known as reference types.</span></span>  
  
## <a name="class-inheritance"></a><span data-ttu-id="63f46-133">Sınıf devralma</span><span class="sxs-lookup"><span data-stu-id="63f46-133">Class inheritance</span></span>  

<span data-ttu-id="63f46-134">Sınıfları tam destek *devralma*, nesne yönelimli programlama temel bir özelliğidir.</span><span class="sxs-lookup"><span data-stu-id="63f46-134">Classes fully support *inheritance*, a fundamental characteristic of object-oriented programming.</span></span> <span data-ttu-id="63f46-135">Bir sınıf oluşturduğunuz zaman, herhangi bir arabirim veya tanımlanmamış sınıfı devralabilirsiniz [korumalı](../../../csharp/language-reference/keywords/sealed.md), ve diğer sınıflar, sizin sınıfınızdan miras ve sınıf sanal yöntemleri geçersiz kılın.</span><span class="sxs-lookup"><span data-stu-id="63f46-135">When you create a class, you can inherit from any other interface or class that is not defined as [sealed](../../../csharp/language-reference/keywords/sealed.md), and other classes can inherit from your class and override class virtual methods.</span></span>

<span data-ttu-id="63f46-136">Devralma kullanılarak gerçekleştirilir bir *türetme*, yani bir sınıf kullanılarak bildirilen bir *temel sınıfı* aldığı verilerini ve davranışlarını devralır.</span><span class="sxs-lookup"><span data-stu-id="63f46-136">Inheritance is accomplished by using a *derivation*, which means a class is declared by using a *base class* from which it inherits data and behavior.</span></span> <span data-ttu-id="63f46-137">Bir temel sınıf, bir iki nokta üst üste ve bunun gibi türetilmiş sınıf adını izleyen temel sınıfın adını ekleyerek belirtilir:</span><span class="sxs-lookup"><span data-stu-id="63f46-137">A base class is specified by appending a colon and the name of the base class following the derived class name, like this:</span></span>  

 ```csharp
 public class Manager : Employee
 {
     // Employee fields, properties, methods and events are inherited
     // New Manager fields, properties, methods and events go here...
 }
 ```

<span data-ttu-id="63f46-138">Bir sınıf bir taban sınıfı bildirir, temel sınıf oluşturucuları dışındaki tüm üyelerini devralır.</span><span class="sxs-lookup"><span data-stu-id="63f46-138">When a class declares a base class, it inherits all the members of the base class except the constructors.</span></span> <span data-ttu-id="63f46-139">Daha fazla bilgi için [devralma](inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="63f46-139">For more information, see [Inheritance](inheritance.md).</span></span>
  
<span data-ttu-id="63f46-140">C++ programında farklı olarak, C# ' ta bir sınıf yalnızca doğrudan bir taban sınıftan devralabilir.</span><span class="sxs-lookup"><span data-stu-id="63f46-140">Unlike C++, a class in C# can only directly inherit from one base class.</span></span> <span data-ttu-id="63f46-141">Ancak, bir temel sınıf kendisi başka bir sınıftan devralabilir olduğundan, bir sınıf dolaylı olarak birden çok taban sınıfı devralabilir.</span><span class="sxs-lookup"><span data-stu-id="63f46-141">However, because a base class may itself inherit from another class, a class may indirectly inherit multiple base classes.</span></span> <span data-ttu-id="63f46-142">Ayrıca, bir sınıf doğrudan birden fazla arabirim uygulayabilir.</span><span class="sxs-lookup"><span data-stu-id="63f46-142">Furthermore, a class can directly implement more than one interface.</span></span> <span data-ttu-id="63f46-143">Daha fazla bilgi için [arabirimleri](../interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="63f46-143">For more information, see [Interfaces](../interfaces/index.md).</span></span>  
  
<span data-ttu-id="63f46-144">Bir sınıf bildirilebilir [soyut](../../language-reference/keywords/abstract.md).</span><span class="sxs-lookup"><span data-stu-id="63f46-144">A class can be declared [abstract](../../language-reference/keywords/abstract.md).</span></span> <span data-ttu-id="63f46-145">Bir Özet sınıf, bir imza tanımı ancak hiçbir uygulama soyut yöntemler içerir.</span><span class="sxs-lookup"><span data-stu-id="63f46-145">An abstract class contains abstract methods that have a signature definition but no implementation.</span></span> <span data-ttu-id="63f46-146">Soyut sınıflar oluşturulamaz.</span><span class="sxs-lookup"><span data-stu-id="63f46-146">Abstract classes cannot be instantiated.</span></span> <span data-ttu-id="63f46-147">Soyut yöntemlerini uygulayan türetilmiş sınıfları yalnızca kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="63f46-147">They can only be used through derived classes that implement the abstract methods.</span></span> <span data-ttu-id="63f46-148">Bunun aksine, bir [korumalı](../../language-reference/keywords/sealed.md) sınıfı diğer sınıfların türetmeniz izin vermez.</span><span class="sxs-lookup"><span data-stu-id="63f46-148">By contrast, a [sealed](../../language-reference/keywords/sealed.md) class does not allow other classes to derive from it.</span></span> <span data-ttu-id="63f46-149">Daha fazla bilgi için [soyut ve korumalı sınıflar ve sınıf üyeleri](abstract-and-sealed-classes-and-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="63f46-149">For more information, see [Abstract and Sealed Classes and Class Members](abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
<span data-ttu-id="63f46-150">Sınıf tanımları farklı kaynak dosyaları arasında bölünebilir.</span><span class="sxs-lookup"><span data-stu-id="63f46-150">Class definitions can be split between different source files.</span></span> <span data-ttu-id="63f46-151">Daha fazla bilgi için [kısmi sınıflar ve yöntemler](partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="63f46-151">For more information, see [Partial Classes and Methods](partial-classes-and-methods.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="63f46-152">Örnek</span><span class="sxs-lookup"><span data-stu-id="63f46-152">Example</span></span>

<span data-ttu-id="63f46-153">Aşağıdaki örnek, içeren genel bir sınıf tanımlar. bir [otomatik uygulanan özellik](auto-implemented-properties.md), bir yöntem ve oluşturucu olarak adlandırılan özel bir yöntem.</span><span class="sxs-lookup"><span data-stu-id="63f46-153">The following example defines a public class that contains an [auto-implemented property](auto-implemented-properties.md), a method, and a special method called a constructor.</span></span> <span data-ttu-id="63f46-154">Daha fazla bilgi için [özellikleri](properties.md), [yöntemleri](methods.md), ve [oluşturucular](constructors.md) konuları.</span><span class="sxs-lookup"><span data-stu-id="63f46-154">For more information, see [Properties](properties.md), [Methods](methods.md), and [Constructors](constructors.md) topics.</span></span> <span data-ttu-id="63f46-155">Sınıf örnekleri, ile örneği oluşturulur `new` anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="63f46-155">The instances of the class are then instantiated with the `new` keyword.</span></span>  
  
[!code-csharp[Class Example](~/samples/snippets/csharp/programming-guide/classes-and-structs/class-example.cs)] 
  
## <a name="c-language-specification"></a><span data-ttu-id="63f46-156">C# Dil Belirtimi</span><span class="sxs-lookup"><span data-stu-id="63f46-156">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="63f46-157">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="63f46-157">See also</span></span>

- [<span data-ttu-id="63f46-158">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="63f46-158">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="63f46-159">Nesne Odaklı Programlama</span><span class="sxs-lookup"><span data-stu-id="63f46-159">Object-Oriented Programming</span></span>](../concepts/object-oriented-programming.md)
- [<span data-ttu-id="63f46-160">Çok biçimlilik</span><span class="sxs-lookup"><span data-stu-id="63f46-160">Polymorphism</span></span>](polymorphism.md)
- [<span data-ttu-id="63f46-161">Tanımlayıcı adları</span><span class="sxs-lookup"><span data-stu-id="63f46-161">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="63f46-162">Üyeler</span><span class="sxs-lookup"><span data-stu-id="63f46-162">Members</span></span>](members.md)
- [<span data-ttu-id="63f46-163">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="63f46-163">Methods</span></span>](methods.md)
- [<span data-ttu-id="63f46-164">Oluşturucular</span><span class="sxs-lookup"><span data-stu-id="63f46-164">Constructors</span></span>](constructors.md)
- [<span data-ttu-id="63f46-165">Sonlandırıcılar</span><span class="sxs-lookup"><span data-stu-id="63f46-165">Finalizers</span></span>](destructors.md)
- [<span data-ttu-id="63f46-166">Nesneler</span><span class="sxs-lookup"><span data-stu-id="63f46-166">Objects</span></span>](objects.md)
