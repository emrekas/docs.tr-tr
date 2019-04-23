---
title: out parametresi değiştiricisi - C# başvurusu
ms.custom: seodec18
ms.date: 03/26/2019
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.openlocfilehash: 769d1ac0b6266c87e99605c76a25e016f15eb11c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59125761"
---
# <a name="out-parameter-modifier-c-reference"></a><span data-ttu-id="84156-102">out parametresi değiştiricisi (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="84156-102">out parameter modifier (C# Reference)</span></span>
<span data-ttu-id="84156-103">`out` Anahtar sözcüğü, başvuruya göre geçirilecek bağımsız değişkenleri neden olur.</span><span class="sxs-lookup"><span data-stu-id="84156-103">The `out` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="84156-104">Bir değişken olmalıdır bağımsız değişkeni için bir diğer ad biçimsel parametre kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="84156-104">It makes the formal parameter an alias for the argument, which must be a variable.</span></span> <span data-ttu-id="84156-105">Diğer bir deyişle, herhangi bir işlem parametresinde bağımsız değişken üzerinde yapılır.</span><span class="sxs-lookup"><span data-stu-id="84156-105">In other words, any operation on the parameter is made on the argument.</span></span> <span data-ttu-id="84156-106">Nasıl olduğunu [ref](ref.md) hariç anahtar sözcüğü `ref` kendisine geçirilen önce değişkenin başlatılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="84156-106">It is like the [ref](ref.md) keyword, except that `ref` requires that the variable be initialized before it is passed.</span></span> <span data-ttu-id="84156-107">Aynı zamanda gibi olan [içinde](in-parameter-modifier.md) hariç anahtar sözcüğü `in` çağrılan yöntem bağımsız değişken değerini değiştirmek izin vermez.</span><span class="sxs-lookup"><span data-stu-id="84156-107">It is also like the [in](in-parameter-modifier.md) keyword, except that `in` does not allow the called method to modify the argument value.</span></span> <span data-ttu-id="84156-108">Kullanılacak bir `out` parametresi, yöntem tanımının hem yöntemi çağrılırken açıkça kullanmalıdır `out` anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="84156-108">To use an `out` parameter, both the method definition and the calling method must explicitly use the `out` keyword.</span></span> <span data-ttu-id="84156-109">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="84156-109">For example:</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#1)]  

> [!NOTE] 
> <span data-ttu-id="84156-110">`out` Anahtar sözcüğü de kullanılabilir bir genel tür parametresi tür parametresi birlikte değişken olduğunu belirtmek için.</span><span class="sxs-lookup"><span data-stu-id="84156-110">The `out` keyword can also be used with a generic type parameter to specify that the type parameter is covariant.</span></span> <span data-ttu-id="84156-111">Kullanımı hakkında daha fazla bilgi için `out` anahtar sözcüğü bu bağlamda bkz [out (genel değiştirici)](out-generic-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="84156-111">For more information on the use of the `out` keyword in this context, see [out (Generic Modifier)](out-generic-modifier.md).</span></span>
  
<span data-ttu-id="84156-112">Değişkenleri olarak geçirildi `out` bağımsız değişken bir yöntem çağrısında iletilmeden önce başlatılmış gerekmez.</span><span class="sxs-lookup"><span data-stu-id="84156-112">Variables passed as `out` arguments do not have to be initialized before being passed in a method call.</span></span> <span data-ttu-id="84156-113">Ancak, çağrılan yöntem yöntemi döndürmeden önce bir değer atamak için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="84156-113">However, the called method is required to assign a value before the method returns.</span></span>  
  
<span data-ttu-id="84156-114">`in`, `ref`, Ve `out` anahtar sözcükleri aşırı yükleme çözünürlüğü amacıyla yöntem imzasının parçası dikkate alınmaz.</span><span class="sxs-lookup"><span data-stu-id="84156-114">The `in`, `ref`, and `out` keywords are not considered part of the method signature for the purpose of overload resolution.</span></span> <span data-ttu-id="84156-115">Tek fark, bir yöntem aldığını ise, bu nedenle, yöntemler aşırı yüklenemez bir `ref` veya `in` bağımsız değişkeni ve diğer alır bir `out` bağımsız değişken.</span><span class="sxs-lookup"><span data-stu-id="84156-115">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="84156-116">Örneğin, aşağıdaki kod derlemeyecektir:</span><span class="sxs-lookup"><span data-stu-id="84156-116">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="84156-117">Aşırı yükleme yasal, ancak bir yöntem uzun sürerse bir `ref`, `in`, veya `out` bağımsız değişken ve diğer sahip böyle bu değiştiricileri hiçbiri:</span><span class="sxs-lookup"><span data-stu-id="84156-117">Overloading is legal, however, if one method takes a `ref`, `in`, or `out` argument and the other has none of those modifiers, like this:</span></span>  
  
[!code-csharp[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#2)]  

<span data-ttu-id="84156-118">Derleyici, yöntem çağrısında kullanılan parametre değiştiriciler çağrı sitesinde parametre değiştiriciler eşleştirerek en iyi aşırı yüklemede seçer.</span><span class="sxs-lookup"><span data-stu-id="84156-118">The compiler chooses the best overload by matching the parameter modifiers at the call site to the parameter modifiers used in the method call.</span></span>
 
<span data-ttu-id="84156-119">Özellikler değişkenleri değildir ve olarak gönderilemez `out` parametreleri.</span><span class="sxs-lookup"><span data-stu-id="84156-119">Properties are not variables and therefore cannot be passed as `out` parameters.</span></span>
  
<span data-ttu-id="84156-120">Kullanamazsınız `in`, `ref`, ve `out` yöntemleri aşağıdaki türde için anahtar sözcükler:</span><span class="sxs-lookup"><span data-stu-id="84156-120">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
-   <span data-ttu-id="84156-121">Kullanarak tanımladığınız zaman uyumsuz yöntemlerde [zaman uyumsuz](../../../csharp/language-reference/keywords/async.md) değiştiricisi.</span><span class="sxs-lookup"><span data-stu-id="84156-121">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
-   <span data-ttu-id="84156-122">Yineleyici yöntemleri dahil bir [yield return](../../../csharp/language-reference/keywords/yield.md) veya `yield break` deyimi.</span><span class="sxs-lookup"><span data-stu-id="84156-122">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

## <a name="declaring-out-parameters"></a><span data-ttu-id="84156-123">Bildirme `out` parametreleri</span><span class="sxs-lookup"><span data-stu-id="84156-123">Declaring `out` parameters</span></span>   

<span data-ttu-id="84156-124">Bir yöntemi bildirmek `out` bağımsız değişkenleri olan birden çok değer döndürmek için Klasik bir geçici çözüm.</span><span class="sxs-lookup"><span data-stu-id="84156-124">Declaring a method with `out` arguments is a classic workaround to return multiple values.</span></span> <span data-ttu-id="84156-125">İle başlayarak C# 7.0 göz önünde bulundurun [diziler](../../tuples.md) benzer senaryolar için.</span><span class="sxs-lookup"><span data-stu-id="84156-125">Beginning with C# 7.0, consider [tuples](../../tuples.md) for similar scenarios.</span></span> <span data-ttu-id="84156-126">Aşağıdaki örnekte `out` üç değişkenin tek bir yöntem çağrısı ile döndürülecek.</span><span class="sxs-lookup"><span data-stu-id="84156-126">The following example uses `out` to return three variables with a single method call.</span></span> <span data-ttu-id="84156-127">Üçüncü bağımsız değişken null olarak atandığını dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="84156-127">Note that the third argument is assigned to null.</span></span> <span data-ttu-id="84156-128">Bu isteğe bağlı olarak dönüş değerleri için yöntemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="84156-128">This enables methods to return values optionally.</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#3)]  

## <a name="calling-a-method-with-an-out-argument"></a><span data-ttu-id="84156-129">Bir yöntemi çağırmak bir `out` bağımsız değişken</span><span class="sxs-lookup"><span data-stu-id="84156-129">Calling a method with an `out` argument</span></span>

<span data-ttu-id="84156-130">Olarak geçirmeden önce C# 6 ve önceki sürümlerinde, ayrı bir deyimde değişken bildirmelidir bir `out` bağımsız değişken.</span><span class="sxs-lookup"><span data-stu-id="84156-130">In C# 6 and earlier, you must declare a variable in a separate statement before you pass it as an `out` argument.</span></span> <span data-ttu-id="84156-131">Aşağıdaki örnek adlı bir değişken bildirir `number` için geçirilmeden önce [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) yöntemi bir dizeyi sayıya dönüştürmek için çalışır.</span><span class="sxs-lookup"><span data-stu-id="84156-131">The following example declares a variable named `number` before it is passed to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method, which attempts to convert a string to a number.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#4)]  

<span data-ttu-id="84156-132">C# 7.0 ile başlayarak, bildirebilirsiniz `out` değişkeni yöntem çağrısında bağımsız değişken listesi yerine ayrı bir değişken bildirimi.</span><span class="sxs-lookup"><span data-stu-id="84156-132">Starting with C# 7.0, you can declare the `out` variable in the argument list of the method call, rather than in a separate variable declaration.</span></span> <span data-ttu-id="84156-133">Bu daha kompakt ve okunabilir bir kod üretir ve ayrıca yöntem çağrısından önce değişkenine yanlışlıkla bir değer atamadan önler.</span><span class="sxs-lookup"><span data-stu-id="84156-133">This produces more compact, readable code, and also prevents you from inadvertently assigning a value to the variable before the method call.</span></span> <span data-ttu-id="84156-134">Tanımladığı dışında önceki örnekteki gibi aşağıdaki örnek, `number` çağrısında değişken [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="84156-134">The following example is like the previous example, except that it defines the `number` variable in the call to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#5)]  
   
<span data-ttu-id="84156-135">Önceki örnekte, `number` değişkeni türü kesin olarak belirtilmiş bir `int`.</span><span class="sxs-lookup"><span data-stu-id="84156-135">In the previous example, the `number` variable is strongly typed as an `int`.</span></span> <span data-ttu-id="84156-136">Aşağıdaki örnekte olduğu gibi bir türü örtük olarak belirlenmiş yerel değişken de bildirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="84156-136">You can also declare an implicitly typed local variable, as the following example does.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#6)]  
   
## <a name="c-language-specification"></a><span data-ttu-id="84156-137">C# Dil Belirtimi</span><span class="sxs-lookup"><span data-stu-id="84156-137">C# Language Specification</span></span>  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="84156-138">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="84156-138">See also</span></span>

- [<span data-ttu-id="84156-139">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="84156-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="84156-140">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="84156-140">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="84156-141">C# Anahtar Sözcükleri</span><span class="sxs-lookup"><span data-stu-id="84156-141">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="84156-142">Yöntem Parametreleri</span><span class="sxs-lookup"><span data-stu-id="84156-142">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)
