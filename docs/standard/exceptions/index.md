---
title: İşleme ve .NET özel durumları atma
ms.date: 06/19/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions [.NET], handling
- runtime, exceptions
- filtering exceptions
- errors [.NET], exceptions
- exceptions [.NET], throwing
- exceptions [.NET]
- common language runtime, exceptions
ms.assetid: f99a1d29-a2a8-47af-9707-9909f9010735
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a417e964c2f44c291892f9ddec6e32438fbff9a1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945437"
---
# <a name="handling-and-throwing-exceptions-in-net"></a><span data-ttu-id="15dda-102">İşleme ve .NET özel durumları atma</span><span class="sxs-lookup"><span data-stu-id="15dda-102">Handling and throwing exceptions in .NET</span></span>

<span data-ttu-id="15dda-103">Uygulamaları tutarlı bir şekilde yürütme sırasında oluşan hataları işleyebilir olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="15dda-103">Applications must be able to handle errors that occur during execution in a consistent manner.</span></span> <span data-ttu-id="15dda-104">.NET uygulamaları hataların Tekdüzen bir şekilde bildirmek için bir model sağlar: .NET işlemlerini özel durumları atma tarafından hata belirtin.</span><span class="sxs-lookup"><span data-stu-id="15dda-104">.NET provides a model for notifying applications of errors in a uniform way: .NET operations indicate failure by throwing exceptions.</span></span>

## <a name="exceptions"></a><span data-ttu-id="15dda-105">Özel Durumlar</span><span class="sxs-lookup"><span data-stu-id="15dda-105">Exceptions</span></span>

<span data-ttu-id="15dda-106">Herhangi bir hata koşulu veya yürütülen bir program tarafından karşılaşılan beklenmeyen davranışı bir özel durumdur.</span><span class="sxs-lookup"><span data-stu-id="15dda-106">An exception is any error condition or unexpected behavior that is encountered by an executing program.</span></span> <span data-ttu-id="15dda-107">Kodunuzu veya (gibi paylaşılan bir kitaplık) çağıran kod, kullanılamayan işletim sistem kaynakları, çalışma zamanı (doğrulanamayan kodu gibi) karşılaştığında beklenmeyen koşulları ve benzeri bir hata nedeniyle özel durumlar.</span><span class="sxs-lookup"><span data-stu-id="15dda-107">Exceptions can be thrown because of a fault in your code or in code that you call (such as a shared library), unavailable operating system resources, unexpected conditions that the runtime encounters (such as code that can't be verified), and so on.</span></span> <span data-ttu-id="15dda-108">Uygulamanız bazı bu koşulların, ancak diğerleri kurtarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="15dda-108">Your application can recover from some of these conditions, but not from others.</span></span> <span data-ttu-id="15dda-109">Çoğu uygulama özel durumlarından kurtulmak olsa da, birçok çalışma zamanı özel durumları kurtaramazsınız.</span><span class="sxs-lookup"><span data-stu-id="15dda-109">Although you can recover from most application exceptions, you can't recover from most runtime exceptions.</span></span>

<span data-ttu-id="15dda-110">. NET'te, bir özel durum devralınan bir nesnedir <xref:System.Exception?displayProperty=nameWithType> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="15dda-110">In .NET, an exception is an object that inherits from the <xref:System.Exception?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="15dda-111">Bir sorun oluştuğu bir alandan kod bir özel durum oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="15dda-111">An exception is thrown from an area of code where a problem has occurred.</span></span> <span data-ttu-id="15dda-112">Özel durum yığını uygulama, işleme veya program sona erer kadar geçirilir.</span><span class="sxs-lookup"><span data-stu-id="15dda-112">The exception is passed up the stack until the application handles it or the program terminates.</span></span>

## <a name="exceptions-vs-traditional-error-handling-methods"></a><span data-ttu-id="15dda-113">Özel durumlar ile geleneksel hata işleme yöntemleri</span><span class="sxs-lookup"><span data-stu-id="15dda-113">Exceptions vs. traditional error-handling methods</span></span>

<span data-ttu-id="15dda-114">Geleneksel olarak, bir dil hata işleme modeli, benzersiz şekilde hataları algılama ve bunlar için işleyiciler bulma dil veya işletim sistemi tarafından sağlanan hata işleme mekanizması yararlandı.</span><span class="sxs-lookup"><span data-stu-id="15dda-114">Traditionally, a language's error-handling model relied on either the language's unique way of detecting errors and locating handlers for them, or on the error-handling mechanism provided by the operating system.</span></span> <span data-ttu-id="15dda-115">.NET özel durum işleme uygular. yol, aşağıdaki avantajları sağlar:</span><span class="sxs-lookup"><span data-stu-id="15dda-115">The way .NET implements exception handling provides the following advantages:</span></span>

- <span data-ttu-id="15dda-116">Özel durum işleme ve atma .NET programlama dilleri için aynı şekilde çalışır.</span><span class="sxs-lookup"><span data-stu-id="15dda-116">Exception throwing and handling works the same for .NET programming languages.</span></span>

- <span data-ttu-id="15dda-117">Özel durumları işlemek için herhangi bir dilin sözdizimi gerektirmez, ancak kendi sözdizimi tanımlamak her bir dilin izin verir.</span><span class="sxs-lookup"><span data-stu-id="15dda-117">Doesn't require any particular language syntax for handling exceptions, but allows each language to define its own syntax.</span></span>

- <span data-ttu-id="15dda-118">İşlem ve hatta makine sınırları içinde özel durumlar atılabilir.</span><span class="sxs-lookup"><span data-stu-id="15dda-118">Exceptions can be thrown across process and even machine boundaries.</span></span>

- <span data-ttu-id="15dda-119">Özel durum işleme kodu program güvenilirliğini artırmak için bir uygulamaya eklenebilir.</span><span class="sxs-lookup"><span data-stu-id="15dda-119">Exception-handling code can be added to an application to increase program reliability.</span></span>

<span data-ttu-id="15dda-120">Özel durumları hata bildirimin dönüş kodları gibi diğer yöntemleri avantaj sunar.</span><span class="sxs-lookup"><span data-stu-id="15dda-120">Exceptions offer advantages over other methods of error notification, such as return codes.</span></span> <span data-ttu-id="15dda-121">Bir özel durum oluşturulur ve bu işlemez, çalışma zamanının uygulamanızı bittiğinden hataları gözden kaçan yapılmaz.</span><span class="sxs-lookup"><span data-stu-id="15dda-121">Failures don't go unnoticed because if an exception is thrown and you don't handle it, the runtime terminates your application.</span></span> <span data-ttu-id="15dda-122">Hata dönüş kodunu denetlemek için başarısız olan kod sonucu olarak sistem aracılığıyla yaymak geçersiz değer geçmeyin.</span><span class="sxs-lookup"><span data-stu-id="15dda-122">Invalid values don't continue to propagate through the system as a result of code that fails to check for a failure return code.</span></span>

## <a name="common-exceptions"></a><span data-ttu-id="15dda-123">Sık karşılaşılan özel durumlar</span><span class="sxs-lookup"><span data-stu-id="15dda-123">Common exceptions</span></span>

<span data-ttu-id="15dda-124">Aşağıdaki tabloda neler bunlara neden olabilecek örnekleri ile sık kullanılan bazı özel durumlar listeler.</span><span class="sxs-lookup"><span data-stu-id="15dda-124">The following table lists some common exceptions with examples of what can cause them.</span></span>

| <span data-ttu-id="15dda-125">Özel durum türü</span><span class="sxs-lookup"><span data-stu-id="15dda-125">Exception type</span></span> | <span data-ttu-id="15dda-126">Açıklama</span><span class="sxs-lookup"><span data-stu-id="15dda-126">Description</span></span> | <span data-ttu-id="15dda-127">Örnek</span><span class="sxs-lookup"><span data-stu-id="15dda-127">Example</span></span> |
| -------------- | ----------- | ------- |
| <xref:System.Exception> | <span data-ttu-id="15dda-128">Tüm özel durumları için temel sınıf.</span><span class="sxs-lookup"><span data-stu-id="15dda-128">Base class for all exceptions.</span></span> | <span data-ttu-id="15dda-129">Hiçbiri (Bu özel durumun türetilmiş bir sınıf kullanın).</span><span class="sxs-lookup"><span data-stu-id="15dda-129">None (use a derived class of this exception).</span></span> |
| <xref:System.IndexOutOfRangeException> | <span data-ttu-id="15dda-130">Yalnızca bir dizi yanlış sıralandığında çalışma zamanı tarafından oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="15dda-130">Thrown by the runtime only when an array is indexed improperly.</span></span> | <span data-ttu-id="15dda-131">Geçerli aralığın dışında bir dizi dizini oluşturma:</span><span class="sxs-lookup"><span data-stu-id="15dda-131">Indexing an array outside its valid range:</span></span> <br /> `arr[arr.Length+1]` |
| <xref:System.NullReferenceException> | <span data-ttu-id="15dda-132">Çalışma zamanı tarafından yalnızca bir null Nesne başvurulduğunda oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="15dda-132">Thrown by the runtime only when a null object is referenced.</span></span> | `object o = null;` <br /> `o.ToString();` |
| <xref:System.InvalidOperationException> | <span data-ttu-id="15dda-133">Geçersiz bir durumda olduğunda yöntemlerle oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="15dda-133">Thrown by methods when in an invalid state.</span></span> | <span data-ttu-id="15dda-134">Çağırma `Enumerator.MoveNext()` bir öğe temel alınan koleksiyonundan kaldırdıktan sonra.</span><span class="sxs-lookup"><span data-stu-id="15dda-134">Calling `Enumerator.MoveNext()` after removing an item from the underlying collection.</span></span> |
| <xref:System.ArgumentException> | <span data-ttu-id="15dda-135">Tüm bağımsız değişken özel durumları için temel sınıf.</span><span class="sxs-lookup"><span data-stu-id="15dda-135">Base class for all argument exceptions.</span></span> | <span data-ttu-id="15dda-136">Hiçbiri (Bu özel durumun türetilmiş bir sınıf kullanın).</span><span class="sxs-lookup"><span data-stu-id="15dda-136">None (use a derived class of this exception).</span></span> |
| <xref:System.ArgumentNullException> | <span data-ttu-id="15dda-137">Bağımsız değişken null olması izin vermeyen yöntemleri tarafından oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="15dda-137">Thrown by methods that do not allow an argument to be null.</span></span> | `String s = null;` <br /> `"Calculate".IndexOf(s);`|
| <xref:System.ArgumentOutOfRangeException> | <span data-ttu-id="15dda-138">Verili bir aralıktaki bağımsız değişkenlerini doğrulayın yöntemlerle oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="15dda-138">Thrown by methods that verify that arguments are in a given range.</span></span> | `String s = "string";` <br /> `s.Substring(s.Length+1);` |

## <a name="see-also"></a><span data-ttu-id="15dda-139">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="15dda-139">See also</span></span>

- [<span data-ttu-id="15dda-140">Özel Durum Sınıfı ve Özellikleri</span><span class="sxs-lookup"><span data-stu-id="15dda-140">Exception Class and Properties</span></span>](exception-class-and-properties.md)
- [<span data-ttu-id="15dda-141">Nasıl yapılır: Özel durumları yakalamak için Try-Catch bloğu kullanma</span><span class="sxs-lookup"><span data-stu-id="15dda-141">How to: Use the Try-Catch Block to Catch Exceptions</span></span>](how-to-use-the-try-catch-block-to-catch-exceptions.md)
- [<span data-ttu-id="15dda-142">Nasıl yapılır: Bir Catch bloğunda belirli özel durumları kullanma</span><span class="sxs-lookup"><span data-stu-id="15dda-142">How to: Use Specific Exceptions in a Catch Block</span></span>](how-to-use-specific-exceptions-in-a-catch-block.md)
- [<span data-ttu-id="15dda-143">Nasıl yapılır: Açıkça özel durumlar oluşturma</span><span class="sxs-lookup"><span data-stu-id="15dda-143">How to: Explicitly Throw Exceptions</span></span>](how-to-explicitly-throw-exceptions.md)
- [<span data-ttu-id="15dda-144">Nasıl yapılır: Kullanıcı tanımlı özel durumlar oluşturma</span><span class="sxs-lookup"><span data-stu-id="15dda-144">How to: Create User-Defined Exceptions</span></span>](how-to-create-user-defined-exceptions.md)
- [<span data-ttu-id="15dda-145">Kullanıcı Tarafından Filtrelenmiş Özel Durum İşleyicilerini Kullanma</span><span class="sxs-lookup"><span data-stu-id="15dda-145">Using User-Filtered Exception Handlers</span></span>](using-user-filtered-exception-handlers.md)
- [<span data-ttu-id="15dda-146">Nasıl yapılır: Finally bloklarını kullanma</span><span class="sxs-lookup"><span data-stu-id="15dda-146">How to: Use Finally Blocks</span></span>](how-to-use-finally-blocks.md)
- [<span data-ttu-id="15dda-147">COM Birlikte Çalışma Özel Durumlarını İşleme</span><span class="sxs-lookup"><span data-stu-id="15dda-147">Handling COM Interop Exceptions</span></span>](handling-com-interop-exceptions.md)
- [<span data-ttu-id="15dda-148">Özel Durumlar için En İyi Yöntemler</span><span class="sxs-lookup"><span data-stu-id="15dda-148">Best Practices for Exceptions</span></span>](best-practices-for-exceptions.md)
- [<span data-ttu-id="15dda-149">Her geliştiricinin bilmesi hakkında özel durumlar çalışma zamanında için gerekenler</span><span class="sxs-lookup"><span data-stu-id="15dda-149">What Every Dev needs to Know About Exceptions in the Runtime</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/botr/exceptions.md)
