---
title: Güvenli olmayan kod ve işaretçiler - C# Programlama Kılavuzu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- security [C#], type safety
- C# language, unsafe code
- type safety [C#]
- unsafe keyword [C#]
- unsafe code [C#]
- C# language, pointers
- pointers [C#], about pointers
ms.assetid: b0fcca10-a92d-4f2a-835b-b0ccae6739ee
ms.openlocfilehash: 3712e04d4496d13178843564b5d0753f62e28fa0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61678109"
---
# <a name="unsafe-code-and-pointers-c-programming-guide"></a><span data-ttu-id="643ec-102">Güvenli Olmayan Kod ve İşaretçiler (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="643ec-102">Unsafe Code and Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="643ec-103">Tür güvenliği ve emniyeti korumak için C# işaretçi aritmetik, varsayılan olarak desteklemez.</span><span class="sxs-lookup"><span data-stu-id="643ec-103">To maintain type safety and security, C# does not support pointer arithmetic, by default.</span></span> <span data-ttu-id="643ec-104">Kullanarak ancak [güvenli](../../../csharp/language-reference/keywords/unsafe.md) anahtar sözcüğü, işaretçileri kullanılabilecek güvenli olmayan bir bağlam tanımlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="643ec-104">However, by using the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, you can define an unsafe context in which pointers can be used.</span></span> <span data-ttu-id="643ec-105">İşaretçiler hakkında daha fazla bilgi için Ek Yardım konusuna [işaretçi türleri](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="643ec-105">For more information about pointers, see the topic [Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="643ec-106">Ortak dil çalışma zamanı (CLR), güvenli olmayan kod, doğrulanamayan kodu adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="643ec-106">In the common language runtime (CLR), unsafe code is referred to as unverifiable code.</span></span> <span data-ttu-id="643ec-107">C# güvenli olmayan kod tehlikeli olmak zorunda değildir; Bu, güvenlik CLR tarafından doğrulanamıyor yalnızca kodudur.</span><span class="sxs-lookup"><span data-stu-id="643ec-107">Unsafe code in C# is not necessarily dangerous; it is just code whose safety cannot be verified by the CLR.</span></span> <span data-ttu-id="643ec-108">Tam olarak güvenilen bir derlemede ise CLR bu nedenle güvenli olmayan kod yalnızca yürütülür.</span><span class="sxs-lookup"><span data-stu-id="643ec-108">The CLR will therefore only execute unsafe code if it is in a fully trusted assembly.</span></span> <span data-ttu-id="643ec-109">Güvenli olmayan kod kullanın, kodunuz güvenlik riskleri veya işaretçi hataları sunmaz sağlamak sizin sorumluluğunuzdadır olur.</span><span class="sxs-lookup"><span data-stu-id="643ec-109">If you use unsafe code, it is your responsibility to ensure that your code does not introduce security risks or pointer errors.</span></span>  
  
## <a name="unsafe-code-overview"></a><span data-ttu-id="643ec-110">Güvenli Olmayan Koda Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="643ec-110">Unsafe Code Overview</span></span>  
 <span data-ttu-id="643ec-111">Güvenli olmayan kod, aşağıdaki özelliklere sahiptir:</span><span class="sxs-lookup"><span data-stu-id="643ec-111">Unsafe code has the following properties:</span></span>  
  
- <span data-ttu-id="643ec-112">Yöntemleri, türleri ve kod blokları güvenli olarak tanımlanabilir.</span><span class="sxs-lookup"><span data-stu-id="643ec-112">Methods, types, and code blocks can be defined as unsafe.</span></span>  
  
- <span data-ttu-id="643ec-113">Bazı durumlarda, güvenli olmayan kod dizi sınırları denetimleri kaldırarak bir uygulamanın performansı artırabilir.</span><span class="sxs-lookup"><span data-stu-id="643ec-113">In some cases, unsafe code may increase an application's performance by removing array bounds checks.</span></span>  
  
- <span data-ttu-id="643ec-114">İşaretçileri gerektiren yerel işlevler çağırdığınızda, güvenli olmayan kod gereklidir.</span><span class="sxs-lookup"><span data-stu-id="643ec-114">Unsafe code is required when you call native functions that require pointers.</span></span>  
  
- <span data-ttu-id="643ec-115">Güvenli olmayan kod kullanarak güvenlik ve sağlamlık risklerini de beraberinde getirir.</span><span class="sxs-lookup"><span data-stu-id="643ec-115">Using unsafe code introduces security and stability risks.</span></span>  
  
- <span data-ttu-id="643ec-116">Güvenli olmayan kod derlemek C# için sırada, uygulama ile derlenmelidir [/ unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="643ec-116">In order for C# to compile unsafe code, the application must be compiled with [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="643ec-117">İlgili Bölümler</span><span class="sxs-lookup"><span data-stu-id="643ec-117">Related Sections</span></span>  
 <span data-ttu-id="643ec-118">Daha fazla bilgi için bkz.:</span><span class="sxs-lookup"><span data-stu-id="643ec-118">For more information, see:</span></span>  
  
- [<span data-ttu-id="643ec-119">İşaretçi türleri</span><span class="sxs-lookup"><span data-stu-id="643ec-119">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
  
- [<span data-ttu-id="643ec-120">Sabit Boyutlu Arabellekler</span><span class="sxs-lookup"><span data-stu-id="643ec-120">Fixed Size Buffers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)  
  
- [<span data-ttu-id="643ec-121">Nasıl yapılır: Bir bayt dizisine kopyalamak için işaretçiler kullanma</span><span class="sxs-lookup"><span data-stu-id="643ec-121">How to: Use Pointers to Copy an Array of Bytes</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/how-to-use-pointers-to-copy-an-array-of-bytes.md)  
  
- [<span data-ttu-id="643ec-122">unsafe</span><span class="sxs-lookup"><span data-stu-id="643ec-122">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="643ec-123">C# Dil Belirtimi</span><span class="sxs-lookup"><span data-stu-id="643ec-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="643ec-124">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="643ec-124">See also</span></span>

- [<span data-ttu-id="643ec-125">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="643ec-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
