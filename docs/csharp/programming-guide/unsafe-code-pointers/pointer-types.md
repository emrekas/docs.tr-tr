---
title: İşaretçi türleri - C# Programlama Kılavuzu
ms.custom: seodec18
ms.date: 04/20/2018
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.openlocfilehash: 028497bbeae26ded126ba4d7ce459a6a85e0bcb5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724050"
---
# <a name="pointer-types-c-programming-guide"></a><span data-ttu-id="75627-102">İşaretçi türleri (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="75627-102">Pointer types (C# Programming Guide)</span></span>

<span data-ttu-id="75627-103">Güvensiz bir bağlamda, bir işaretçi türü, bir değer türü veya bir başvuru türü bir tür olabilir.</span><span class="sxs-lookup"><span data-stu-id="75627-103">In an unsafe context, a type may be a pointer type, a value type, or a reference type.</span></span> <span data-ttu-id="75627-104">Bir işaretçi türü bildirimi, aşağıdaki biçimlerden birini alır:</span><span class="sxs-lookup"><span data-stu-id="75627-104">A pointer type declaration takes one of the following forms:</span></span>

``` csharp
type* identifier;
void* identifier; //allowed but not recommended
```

<span data-ttu-id="75627-105">Önce belirtilen tür `*` bir işaretçi türü olarak adlandırılır **başvurulan türü**.</span><span class="sxs-lookup"><span data-stu-id="75627-105">The type specified before the `*` in a pointer type is called the **referent type**.</span></span> <span data-ttu-id="75627-106">Aşağıdaki türlerde herhangi bir grup türü olabilir:</span><span class="sxs-lookup"><span data-stu-id="75627-106">Any of the following types may be a referent type:</span></span>

- <span data-ttu-id="75627-107">Herhangi bir tamsayı türü: [sbyte](../../language-reference/keywords/sbyte.md), [bayt](../../language-reference/keywords/byte.md), [kısa](../../language-reference/keywords/short.md), [ushort](../../language-reference/keywords/ushort.md), [int](../../language-reference/keywords/int.md), [uint](../../language-reference/keywords/uint.md), [uzun](../../language-reference/keywords/long.md), [ulong](../../language-reference/keywords/ulong.md).</span><span class="sxs-lookup"><span data-stu-id="75627-107">Any integral type: [sbyte](../../language-reference/keywords/sbyte.md), [byte](../../language-reference/keywords/byte.md), [short](../../language-reference/keywords/short.md), [ushort](../../language-reference/keywords/ushort.md), [int](../../language-reference/keywords/int.md), [uint](../../language-reference/keywords/uint.md), [long](../../language-reference/keywords/long.md), [ulong](../../language-reference/keywords/ulong.md).</span></span>
- <span data-ttu-id="75627-108">Herhangi bir kayan nokta türü: [float](../../language-reference/keywords/float.md), [çift](../../language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="75627-108">Any floating-point type: [float](../../language-reference/keywords/float.md), [double](../../language-reference/keywords/double.md).</span></span>
- <span data-ttu-id="75627-109">[char](../../language-reference/keywords/char.md).</span><span class="sxs-lookup"><span data-stu-id="75627-109">[char](../../language-reference/keywords/char.md).</span></span>
- <span data-ttu-id="75627-110">[bool](../../language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="75627-110">[bool](../../language-reference/keywords/bool.md).</span></span>
- <span data-ttu-id="75627-111">[ondalık](../../language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="75627-111">[decimal](../../language-reference/keywords/decimal.md).</span></span>
- <span data-ttu-id="75627-112">Tüm [enum](../../language-reference/keywords/enum.md) türü.</span><span class="sxs-lookup"><span data-stu-id="75627-112">Any [enum](../../language-reference/keywords/enum.md) type.</span></span>
- <span data-ttu-id="75627-113">Herhangi bir işaretçi türü.</span><span class="sxs-lookup"><span data-stu-id="75627-113">Any pointer type.</span></span> <span data-ttu-id="75627-114">Bu ifadeler gibi sağlar `void**`.</span><span class="sxs-lookup"><span data-stu-id="75627-114">This allows expressions such as `void**`.</span></span>
- <span data-ttu-id="75627-115">Yalnızca yönetilmeyen türlerde alanlar içeren, kullanıcı tarafından tanımlanmış herhangi bir yapı türü.</span><span class="sxs-lookup"><span data-stu-id="75627-115">Any user-defined struct type that contains fields of unmanaged types only.</span></span>

<span data-ttu-id="75627-116">İşaretçi türleri öğesinden devralmaz [nesne](../../language-reference/keywords/object.md) ve işaretçi türleri arasında dönüştürme işlemi yok var ve `object`.</span><span class="sxs-lookup"><span data-stu-id="75627-116">Pointer types do not inherit from [object](../../language-reference/keywords/object.md) and no conversions exist between pointer types and `object`.</span></span> <span data-ttu-id="75627-117">Ayrıca, kutulama ve kutudan çıkarma işaretçileri desteklemez.</span><span class="sxs-lookup"><span data-stu-id="75627-117">Also, boxing and unboxing do not support pointers.</span></span> <span data-ttu-id="75627-118">Ancak, farklı işaretçi türleri ve işaretçi türleri ve tamsayı türleri arasında dönüştürme yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="75627-118">However, you can convert between different pointer types and between pointer types and integral types.</span></span>

<span data-ttu-id="75627-119">Aynı bildirimde birden çok işaretçi bildirdiğinizde, yıldız işareti (\*) yalnızca altı çizili türle birlikte yazılır; her bir işaretçi adı için önek olarak kullanılmaz.</span><span class="sxs-lookup"><span data-stu-id="75627-119">When you declare multiple pointers in the same declaration, the asterisk (\*) is written together with the underlying type only; it is not used as a prefix to each pointer name.</span></span> <span data-ttu-id="75627-120">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="75627-120">For example:</span></span>

```csharp
int* p1, p2, p3;   // Ok
int *p1, *p2, *p3;   // Invalid in C#
```

<span data-ttu-id="75627-121">Bir işaretçi, başvuru veya çok işaret edemez bir [yapı](../../language-reference/keywords/struct.md) bir nesne başvurusu bir işaretçi kendisine işaret ettiği bile çöpten toplanmış olabileceğinden başvurular içeren.</span><span class="sxs-lookup"><span data-stu-id="75627-121">A pointer cannot point to a reference or to a [struct](../../language-reference/keywords/struct.md) that contains references, because an object reference can be garbage collected even if a pointer is pointing to it.</span></span> <span data-ttu-id="75627-122">Çöp toplayıcı, bir nesneye herhangi bir işaretçi türü tarafından işaret edilip edilmediğini izlemez.</span><span class="sxs-lookup"><span data-stu-id="75627-122">The garbage collector does not keep track of whether an object is being pointed to by any pointer types.</span></span>

<span data-ttu-id="75627-123">Türündeki işaretçi değişkeninin değerini `myType*` türünde bir değişkenin adresidir `myType`.</span><span class="sxs-lookup"><span data-stu-id="75627-123">The value of the pointer variable of type `myType*` is the address of a variable of type `myType`.</span></span> <span data-ttu-id="75627-124">Aşağıda, işaretçi türü bildirimi örnekleri verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="75627-124">The following are examples of pointer type declarations:</span></span>

|<span data-ttu-id="75627-125">Örnek</span><span class="sxs-lookup"><span data-stu-id="75627-125">Example</span></span>|<span data-ttu-id="75627-126">Açıklama</span><span class="sxs-lookup"><span data-stu-id="75627-126">Description</span></span>|
|-------------|-----------------|
|`int* p`|<span data-ttu-id="75627-127">`p` bir tamsayının bir işaretçisidir.</span><span class="sxs-lookup"><span data-stu-id="75627-127">`p` is a pointer to an integer.</span></span>|
|`int** p`|<span data-ttu-id="75627-128">`p` bir tamsayı işaretçisi için bir işaretçidir.</span><span class="sxs-lookup"><span data-stu-id="75627-128">`p` is a pointer to a pointer to an integer.</span></span>|
|`int*[] p`|<span data-ttu-id="75627-129">`p` işaretçileri dizisidir tek boyutlu bir dizidir.</span><span class="sxs-lookup"><span data-stu-id="75627-129">`p` is a single-dimensional array of pointers to integers.</span></span>|
|`char* p`|<span data-ttu-id="75627-130">`p` bir karakterin bir işaretçisidir.</span><span class="sxs-lookup"><span data-stu-id="75627-130">`p` is a pointer to a char.</span></span>|
|`void* p`|<span data-ttu-id="75627-131">`p` Bilinmeyen bir türün bir işaretçisidir.</span><span class="sxs-lookup"><span data-stu-id="75627-131">`p` is a pointer to an unknown type.</span></span>|

<span data-ttu-id="75627-132">İşaretçi yöneltme işleci \*, işaretçi değişkeninin işaret ettiği yerdeki içeriğe erişebilir.</span><span class="sxs-lookup"><span data-stu-id="75627-132">The pointer indirection operator \* can be used to access the contents at the location pointed to by the pointer variable.</span></span> <span data-ttu-id="75627-133">Örneğin, aşağıdaki bildirimi ele alalım:</span><span class="sxs-lookup"><span data-stu-id="75627-133">For example, consider the following declaration:</span></span>

```csharp
int* myVariable;
```

<span data-ttu-id="75627-134">İfade `*myVariable` gösterir `int` yer alan adreste bulunan değişkeni `myVariable`.</span><span class="sxs-lookup"><span data-stu-id="75627-134">The expression `*myVariable` denotes the `int` variable found at the address contained in `myVariable`.</span></span>

<span data-ttu-id="75627-135">Çeşitli konularda işaretçi örnekleri vardır [fixed Statement](../../language-reference/keywords/fixed-statement.md) ve [işaretçi dönüşümleri](../../programming-guide/unsafe-code-pointers/pointer-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="75627-135">There are several examples of pointers in the topics [fixed Statement](../../language-reference/keywords/fixed-statement.md) and [Pointer Conversions](../../programming-guide/unsafe-code-pointers/pointer-conversions.md).</span></span> <span data-ttu-id="75627-136">Aşağıdaki örnekte `unsafe` anahtar sözcüğü ve `fixed` ifadesi ve bir iç işaretçinin nasıl artırılacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="75627-136">The following example uses the `unsafe` keyword and the `fixed` statement, and shows how to increment an interior pointer.</span></span>  <span data-ttu-id="75627-137">Bu kodu çalıştırmak için bir konsolun Ana işlevine yapıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="75627-137">You can paste this code into the Main function of a console application to run it.</span></span> <span data-ttu-id="75627-138">Bu örnekler ile derlenmelidir [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) derleyici seçeneği ayarlanmış.</span><span class="sxs-lookup"><span data-stu-id="75627-138">These examples must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option set.</span></span>

[!code-csharp[Using pointer types](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#5)]

<span data-ttu-id="75627-139">Yöneltme işleci türünde bir işaretçiye uygulayamazsınız `void*`.</span><span class="sxs-lookup"><span data-stu-id="75627-139">You cannot apply the indirection operator to a pointer of type `void*`.</span></span> <span data-ttu-id="75627-140">Ancak, boş bir işaretçiyi başka herhangi bir türü dönüştürmek veya bunun tersini yapmak için bir yayın kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="75627-140">However, you can use a cast to convert a void pointer to any other pointer type, and vice versa.</span></span>

<span data-ttu-id="75627-141">Bir işaretçi olabilir `null`.</span><span class="sxs-lookup"><span data-stu-id="75627-141">A pointer can be `null`.</span></span> <span data-ttu-id="75627-142">Yönlendirme işlecini bir null işaretçiye uygulamak, uygulama tarafından tanımlanan bir davranışa neden olur.</span><span class="sxs-lookup"><span data-stu-id="75627-142">Applying the indirection operator to a null pointer causes an implementation-defined behavior.</span></span>

<span data-ttu-id="75627-143">İşaretçilerin yöntemler arasında aktarılmasının tanımlanmamış davranışa neden.</span><span class="sxs-lookup"><span data-stu-id="75627-143">Passing pointers between methods can cause undefined behavior.</span></span> <span data-ttu-id="75627-144">Bir yerel değişken için bir işaretçi döndüren bir yöntem düşünün bir `in`, `out`, veya `ref` parametresi veya işlev sonucu olarak.</span><span class="sxs-lookup"><span data-stu-id="75627-144">Consider a method that returns a pointer to a local variable through an `in`, `out`, or `ref` parameter or as the function result.</span></span> <span data-ttu-id="75627-145">İşaretçi sabit bir blokta ayarlandıysa, işaret ettiği değişken artık sabit olamaz.</span><span class="sxs-lookup"><span data-stu-id="75627-145">If the pointer was set in a fixed block, the variable to which it points may no longer be fixed.</span></span>

<span data-ttu-id="75627-146">Aşağıdaki tabloda, güvenli olmayan bir bağlamda işaretçiler üzerinde işlem yapabilecek işleçler ve deyimler listelenmektedir:</span><span class="sxs-lookup"><span data-stu-id="75627-146">The following table lists the operators and statements that can operate on pointers in an unsafe context:</span></span>

|<span data-ttu-id="75627-147">İşleç/Deyim</span><span class="sxs-lookup"><span data-stu-id="75627-147">Operator/Statement</span></span>|<span data-ttu-id="75627-148">Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında</span><span class="sxs-lookup"><span data-stu-id="75627-148">Use</span></span>|
|-------------------------|---------|
|*|<span data-ttu-id="75627-149">İşaretçi yöneltmesi gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="75627-149">Performs pointer indirection.</span></span>|
|->|<span data-ttu-id="75627-150">Bir yapının bir üyesine bir işaretçi yoluyla erişir.</span><span class="sxs-lookup"><span data-stu-id="75627-150">Accesses a member of a struct through a pointer.</span></span>|
|<span data-ttu-id="75627-151">[]</span><span class="sxs-lookup"><span data-stu-id="75627-151">[]</span></span>|<span data-ttu-id="75627-152">Bir işaretçiyi dizine ekler.</span><span class="sxs-lookup"><span data-stu-id="75627-152">Indexes a pointer.</span></span>|
|`&`|<span data-ttu-id="75627-153">Bir değişkenin adresini alır.</span><span class="sxs-lookup"><span data-stu-id="75627-153">Obtains the address of a variable.</span></span>|
|<span data-ttu-id="75627-154">++ ve --</span><span class="sxs-lookup"><span data-stu-id="75627-154">++ and --</span></span>|<span data-ttu-id="75627-155">İşaretçileri artırır ve azaltır.</span><span class="sxs-lookup"><span data-stu-id="75627-155">Increments and decrements pointers.</span></span>|
|<span data-ttu-id="75627-156">+ ve -</span><span class="sxs-lookup"><span data-stu-id="75627-156">+ and -</span></span>|<span data-ttu-id="75627-157">İşaretçi aritmetiği gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="75627-157">Performs pointer arithmetic.</span></span>|
|<span data-ttu-id="75627-158">==,! =, \<, >, \<= ve > =</span><span class="sxs-lookup"><span data-stu-id="75627-158">==, !=, \<, >, \<=, and >=</span></span>|<span data-ttu-id="75627-159">İşaretçileri karşılaştırır.</span><span class="sxs-lookup"><span data-stu-id="75627-159">Compares pointers.</span></span>|
|`stackalloc`|<span data-ttu-id="75627-160">Yığında bellek ayırır.</span><span class="sxs-lookup"><span data-stu-id="75627-160">Allocates memory on the stack.</span></span>|
|<span data-ttu-id="75627-161">`fixed` Deyimi</span><span class="sxs-lookup"><span data-stu-id="75627-161">`fixed` statement</span></span>|<span data-ttu-id="75627-162">Adresinin bulunamaması için bir değişkeni geçici olarak sabitler.</span><span class="sxs-lookup"><span data-stu-id="75627-162">Temporarily fixes a variable so that its address may be found.</span></span>|

## <a name="c-language-specification"></a><span data-ttu-id="75627-163">C# Dil Belirtimi</span><span class="sxs-lookup"><span data-stu-id="75627-163">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="75627-164">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="75627-164">See also</span></span>

- [<span data-ttu-id="75627-165">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="75627-165">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="75627-166">Güvenli Olmayan Kod ve İşaretçiler</span><span class="sxs-lookup"><span data-stu-id="75627-166">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="75627-167">İşaretçi Dönüştürmeler</span><span class="sxs-lookup"><span data-stu-id="75627-167">Pointer Conversions</span></span>](pointer-conversions.md)
- [<span data-ttu-id="75627-168">İşaretçi İfadeleri</span><span class="sxs-lookup"><span data-stu-id="75627-168">Pointer Expressions</span></span>](pointer-expressions.md)
- [<span data-ttu-id="75627-169">Türler</span><span class="sxs-lookup"><span data-stu-id="75627-169">Types</span></span>](../../language-reference/keywords/types.md)
- [<span data-ttu-id="75627-170">unsafe</span><span class="sxs-lookup"><span data-stu-id="75627-170">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
- [<span data-ttu-id="75627-171">fixed Deyimi</span><span class="sxs-lookup"><span data-stu-id="75627-171">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="75627-172">stackalloc</span><span class="sxs-lookup"><span data-stu-id="75627-172">stackalloc</span></span>](../../language-reference/keywords/stackalloc.md)
- [<span data-ttu-id="75627-173">Kutulama ve Kutudan Çıkarma</span><span class="sxs-lookup"><span data-stu-id="75627-173">Boxing and Unboxing</span></span>](../types/boxing-and-unboxing.md)
