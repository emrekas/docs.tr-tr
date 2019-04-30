---
title: '#tanımlama - C# başvurusu'
ms.custom: seodec18
ms.date: 06/30/2018
f1_keywords:
- '#define'
helpviewer_keywords:
- '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
ms.openlocfilehash: 3b543181e3d836226759e77f0d56ed3c3e57e7ea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61688702"
---
# <a name="define-c-reference"></a><span data-ttu-id="91579-102">#define (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="91579-102">#define (C# Reference)</span></span>
<span data-ttu-id="91579-103">Kullandığınız `#define` simge tanımlamak için.</span><span class="sxs-lookup"><span data-stu-id="91579-103">You use `#define` to define a symbol.</span></span> <span data-ttu-id="91579-104">Geçirilen ifade olarak sembol kullanırken [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) yönergesi, ifade için değerlendirilecek olan `true`aşağıdaki örnekte gösterildiği gibi:</span><span class="sxs-lookup"><span data-stu-id="91579-104">When you use the symbol as the expression that's passed to the [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive, the expression will evaluate to `true`, as the following example shows:</span></span>  
 
 ```csharp
 #define DEBUG
 ```
  
## <a name="remarks"></a><span data-ttu-id="91579-105">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="91579-105">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91579-106">`#define` Yönergesi, genellikle C ve C++ içinde olduğu gibi sabit değerler bildirmek için kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="91579-106">The `#define` directive cannot be used to declare constant values as is typically done in C and C++.</span></span> <span data-ttu-id="91579-107">C# içinde sabitleri en iyi bir sınıfın veya yapının üyeleri statik olarak tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="91579-107">Constants in C# are best defined as static members of a class or struct.</span></span> <span data-ttu-id="91579-108">Birkaç sabitiniz varsa, bunları tutmak için ayrı bir "Sabitler" sınıfı oluşturmayı göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="91579-108">If you have several such constants, consider creating a separate "Constants" class to hold them.</span></span>  
  
 <span data-ttu-id="91579-109">Derleme koşullarını belirtmek için simgeler kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="91579-109">Symbols can be used to specify conditions for compilation.</span></span> <span data-ttu-id="91579-110">Sembolü ile ya da test [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) veya [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md).</span><span class="sxs-lookup"><span data-stu-id="91579-110">You can test for the symbol with either [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) or [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md).</span></span> <span data-ttu-id="91579-111">Ayrıca <xref:System.Diagnostics.ConditionalAttribute> koşullu derleme yapılacak.</span><span class="sxs-lookup"><span data-stu-id="91579-111">You can also use the <xref:System.Diagnostics.ConditionalAttribute> to perform conditional compilation.</span></span>  
  
 <span data-ttu-id="91579-112">Bir simge tanımlayabilir ancak bir simgeye değer atayamazsınız.</span><span class="sxs-lookup"><span data-stu-id="91579-112">You can define a symbol, but you cannot assign a value to a symbol.</span></span> <span data-ttu-id="91579-113">`#define` Önişlemci yönergesi de olmayan yönergeleri kullanmadan önce yönergesinin dosyada görünmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="91579-113">The `#define` directive must appear in the file before you use any instructions that aren't also preprocessor directives.</span></span>  
  
 <span data-ttu-id="91579-114">Ayrıca bir simge tanımlayabilirsiniz [-tanımlama](../../../csharp/language-reference/compiler-options/define-compiler-option.md) derleyici seçeneği.</span><span class="sxs-lookup"><span data-stu-id="91579-114">You can also define a symbol with the [-define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="91579-115">Sahip bir simge tanımlarını Kaldır [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="91579-115">You can undefine a symbol with [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span></span>  
  
 <span data-ttu-id="91579-116">İle tanımladığınız bir sembol `-define` veya `#define` aynı ada sahip bir değişkenle çakışmaz.</span><span class="sxs-lookup"><span data-stu-id="91579-116">A symbol that you define with `-define` or with `#define` does not conflict with a variable of the same name.</span></span> <span data-ttu-id="91579-117">Diğer bir deyişle, bir değişken adı bir önişlemci yönergesine geçmemiş olmalıdır ve bir simge yalnızca bir önişlemci yönergesince değerlendirilebilir.</span><span class="sxs-lookup"><span data-stu-id="91579-117">That is, a variable name should not be passed to a preprocessor directive and a symbol can only be evaluated by a preprocessor directive.</span></span>  
  
 <span data-ttu-id="91579-118">Kullanılarak oluşturulan bir simgenin kapsamı `#define` simgenin tanımlandığı dosyadır.</span><span class="sxs-lookup"><span data-stu-id="91579-118">The scope of a symbol that was created by using `#define` is the file in which the symbol was defined.</span></span>  
  
 <span data-ttu-id="91579-119">Aşağıdaki örnekte gösterildiği gibi yerleştirmelisiniz `#define` yönergelerini dosyanın üst.</span><span class="sxs-lookup"><span data-stu-id="91579-119">As the following example shows, you must put `#define` directives at the top of the file.</span></span>  
  
```csharp  
#define DEBUG  
//#define TRACE  
#undef TRACE  
  
using System;  
  
public class TestDefine  
{  
    static void Main()  
    {  
#if (DEBUG)  
        Console.WriteLine("Debugging is enabled.");  
#endif  
  
#if (TRACE)  
     Console.WriteLine("Tracing is enabled.");  
#endif  
    }  
}  
// Output:  
// Debugging is enabled.  
```  
  
 <span data-ttu-id="91579-120">Bir sembolün tanımını kaldırmaya ilişkin bir örnek için bkz. [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="91579-120">For an example of how to undefine a symbol, see [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91579-121">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="91579-121">See also</span></span>

- [<span data-ttu-id="91579-122">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="91579-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="91579-123">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="91579-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="91579-124">C# Ön İşlemci Yönergeleri</span><span class="sxs-lookup"><span data-stu-id="91579-124">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
- [<span data-ttu-id="91579-125">const</span><span class="sxs-lookup"><span data-stu-id="91579-125">const</span></span>](../../../csharp/language-reference/keywords/const.md)
- [<span data-ttu-id="91579-126">Nasıl yapılır: İzleme ve hata ayıklama ile koşullu derleme</span><span class="sxs-lookup"><span data-stu-id="91579-126">How to: Compile Conditionally with Trace and Debug</span></span>](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)
- [<span data-ttu-id="91579-127">#undef</span><span class="sxs-lookup"><span data-stu-id="91579-127">#undef</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)
- [<span data-ttu-id="91579-128">#if</span><span class="sxs-lookup"><span data-stu-id="91579-128">#if</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)
