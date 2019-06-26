---
title: Derleyicinin ürettiği özel durumlar - C# Programlama Kılavuzu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], compiler-generated
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
ms.openlocfilehash: 28e6ba0c20948aa769a1517c664db80b5beb6b68
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2019
ms.locfileid: "67398024"
---
# <a name="compiler-generated-exceptions-c-programming-guide"></a><span data-ttu-id="4bd54-102">Derleyicinin Ürettiği Özel Durumlar (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="4bd54-102">Compiler-Generated Exceptions (C# Programming Guide)</span></span>
<span data-ttu-id="4bd54-103">Temel işlemleri başarısız olduğunda bazı özel durumlar, .NET Framework'ün ortak dil çalışma zamanı tarafından (CLR) otomatik olarak atılır.</span><span class="sxs-lookup"><span data-stu-id="4bd54-103">Some exceptions are thrown automatically by the .NET Framework's common language runtime (CLR) when basic operations fail.</span></span> <span data-ttu-id="4bd54-104">Bu özel durumları ve bunların hata koşulları aşağıdaki tabloda listelenmiştir.</span><span class="sxs-lookup"><span data-stu-id="4bd54-104">These exceptions and their error conditions are listed in the following table.</span></span>  
  
|<span data-ttu-id="4bd54-105">Özel Durum</span><span class="sxs-lookup"><span data-stu-id="4bd54-105">Exception</span></span>|<span data-ttu-id="4bd54-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="4bd54-106">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ArithmeticException>|<span data-ttu-id="4bd54-107">Gibi aritmetik işlemler sırasında oluşan özel durumlar için temel sınıf <xref:System.DivideByZeroException> ve <xref:System.OverflowException>.</span><span class="sxs-lookup"><span data-stu-id="4bd54-107">A base class for exceptions that occur during arithmetic operations, such as <xref:System.DivideByZeroException> and <xref:System.OverflowException>.</span></span>|  
|<xref:System.ArrayTypeMismatchException>|<span data-ttu-id="4bd54-108">Öğesinin gerçek türü dizinin gerçek türü ile uyumsuz olduğundan bir dizi belirli bir öğeyi depolanamıyor zaman oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="4bd54-108">Thrown when an array cannot store a given element because the actual type of the element is incompatible with the actual type of the array.</span></span>|  
|<xref:System.DivideByZeroException>|<span data-ttu-id="4bd54-109">Bir bölme bir tamsayı değeri sıfıra girişimde zaman oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="4bd54-109">Thrown when an attempt is made to divide an integral value by zero.</span></span>|  
|<xref:System.IndexOutOfRangeException>|<span data-ttu-id="4bd54-110">Dizi dizini sıfırdan küçük veya dizi sınırları dışında olduğunda dizin için bir girişimde zaman oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="4bd54-110">Thrown when an attempt is made to index an array when the index is less than zero or outside the bounds of the array.</span></span>|  
|<xref:System.InvalidCastException>|<span data-ttu-id="4bd54-111">Açık dönüştürme bir arabirim veya türetilmiş bir tür için bir temel türden çalışma zamanında başarısız olduğunda oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="4bd54-111">Thrown when an explicit conversion from a base type to an interface or to a derived type fails at runtime.</span></span>|  
|<xref:System.NullReferenceException>|<span data-ttu-id="4bd54-112">Değeri olan bir nesneye başvurmak denediğinizde durum [null](../../../csharp/language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="4bd54-112">Thrown when you attempt to reference an object whose value is [null](../../../csharp/language-reference/keywords/null.md).</span></span>|  
|<xref:System.OutOfMemoryException>|<span data-ttu-id="4bd54-113">Kullanarak bellek ayırma denemesi olduğunda oluşturulan [yeni](../../../csharp/language-reference/operators/new-operator.md) işleci başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="4bd54-113">Thrown when an attempt to allocate memory using the [new](../../../csharp/language-reference/operators/new-operator.md) operator fails.</span></span> <span data-ttu-id="4bd54-114">Bu, ortak dil çalışma zamanı için kullanılabilir bellek tükendi gösterir.</span><span class="sxs-lookup"><span data-stu-id="4bd54-114">This indicates that the memory available to the common language runtime has been exhausted.</span></span>|  
|<xref:System.OverflowException>|<span data-ttu-id="4bd54-115">Aritmetik işlemin içinde olduğunda oluşturulan bir `checked` bağlam taşıyor.</span><span class="sxs-lookup"><span data-stu-id="4bd54-115">Thrown when an arithmetic operation in a `checked` context overflows.</span></span>|  
|<xref:System.StackOverflowException>|<span data-ttu-id="4bd54-116">Çok fazla bekleyen yöntem çağrılarını sağlayarak yürütme yığın kaldığında oluşturulur; genellikle çok derin veya sonsuz özyineleme gösterir.</span><span class="sxs-lookup"><span data-stu-id="4bd54-116">Thrown when the execution stack is exhausted by having too many pending method calls; usually indicates a very deep or infinite recursion.</span></span>|  
|<xref:System.TypeInitializationException>|<span data-ttu-id="4bd54-117">Statik oluşturucu ve hiçbir uyumlu özel durum oluşturduğunda durum `catch` bunu yakalayıp yakalamayacağınıza karar yan tümcesi bulunmaktadır.</span><span class="sxs-lookup"><span data-stu-id="4bd54-117">Thrown when a static constructor throws an exception and no compatible `catch` clause exists to catch it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4bd54-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="4bd54-118">See also</span></span>

- [<span data-ttu-id="4bd54-119">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="4bd54-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="4bd54-120">Özel Durumlar ve Özel Durum İşleme</span><span class="sxs-lookup"><span data-stu-id="4bd54-120">Exceptions and Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/index.md)
- [<span data-ttu-id="4bd54-121">Özel Durum İşleme</span><span class="sxs-lookup"><span data-stu-id="4bd54-121">Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/exception-handling.md)
- [<span data-ttu-id="4bd54-122">try-catch</span><span class="sxs-lookup"><span data-stu-id="4bd54-122">try-catch</span></span>](../../../csharp/language-reference/keywords/try-catch.md)
- [<span data-ttu-id="4bd54-123">try-finally</span><span class="sxs-lookup"><span data-stu-id="4bd54-123">try-finally</span></span>](../../../csharp/language-reference/keywords/try-finally.md)
- [<span data-ttu-id="4bd54-124">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="4bd54-124">try-catch-finally</span></span>](../../../csharp/language-reference/keywords/try-catch-finally.md)
