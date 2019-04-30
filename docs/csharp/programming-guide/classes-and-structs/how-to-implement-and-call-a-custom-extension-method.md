---
title: 'Nasıl yapılır: Uygulama ve özel bir genişletme yöntemi - arama C# Programlama Kılavuzu'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- extension methods [C#], implementing and calling
ms.assetid: 7dab2a56-cf8e-4a47-a444-fe610a02772a
ms.openlocfilehash: 2d3f6ec66a13638f0106537ad8b21bff801a53b3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61646481"
---
# <a name="how-to-implement-and-call-a-custom-extension-method-c-programming-guide"></a><span data-ttu-id="cfe83-102">Nasıl yapılır: Uygulama ve özel uzantı metodu çağırma (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="cfe83-102">How to: Implement and Call a Custom Extension Method (C# Programming Guide)</span></span>
<span data-ttu-id="cfe83-103">Bu konu, kendi herhangi bir .NET türü için genişletme yöntemlerini gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="cfe83-103">This topic shows how to implement your own extension methods for any .NET type.</span></span> <span data-ttu-id="cfe83-104">İstemci kodu, uzantı yöntemlerinizi kullanabilir, bunları içeren DLL bir başvuru eklemeyi ve ekleyerek bir [kullanarak](../../../csharp/language-reference/keywords/using-directive.md) yönergesi uzantı yöntemlerin tanımlandığı ad alanı belirtir.</span><span class="sxs-lookup"><span data-stu-id="cfe83-104">Client code can use your extension methods by adding a reference to the DLL that contains them, and adding a [using](../../../csharp/language-reference/keywords/using-directive.md) directive that specifies the namespace in which the extension methods are defined.</span></span>  
  
## <a name="to-define-and-call-the-extension-method"></a><span data-ttu-id="cfe83-105">Tanımlama ve uzantı metodu çağırma</span><span class="sxs-lookup"><span data-stu-id="cfe83-105">To define and call the extension method</span></span>  
  
1. <span data-ttu-id="cfe83-106">Statik bir tanımlama [sınıfı](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) genişletme yöntemini içerecek.</span><span class="sxs-lookup"><span data-stu-id="cfe83-106">Define a static [class](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) to contain the extension method.</span></span>  
  
     <span data-ttu-id="cfe83-107">Sınıfı için istemci kodu görünür olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="cfe83-107">The class must be visible to client code.</span></span> <span data-ttu-id="cfe83-108">Erişilebilirlik kuralları hakkında daha fazla bilgi için bkz. [erişim değiştiricileri](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="cfe83-108">For more information about accessibility rules, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
2. <span data-ttu-id="cfe83-109">En az bir genişletme yöntemi ile statik bir yöntem olarak uygulamak içeren sınıf olarak aynı görünürlük.</span><span class="sxs-lookup"><span data-stu-id="cfe83-109">Implement the extension method as a static method with at least the same visibility as the containing class.</span></span>  
  
3. <span data-ttu-id="cfe83-110">Yönteminin ilk parametresi, yöntemin işlediği türü belirtir. ile gelmelidir [bu](../../../csharp/language-reference/keywords/this.md) değiştiricisi.</span><span class="sxs-lookup"><span data-stu-id="cfe83-110">The first parameter of the method specifies the type that the method operates on; it must be preceded with the [this](../../../csharp/language-reference/keywords/this.md) modifier.</span></span>  
  
4. <span data-ttu-id="cfe83-111">Çağıran kodu ekleyin bir `using` belirtmek için yönergesi [ad alanı](../../../csharp/language-reference/keywords/namespace.md) uzantısı yöntemi sınıfı içeren.</span><span class="sxs-lookup"><span data-stu-id="cfe83-111">In the calling code, add a `using` directive to specify the [namespace](../../../csharp/language-reference/keywords/namespace.md) that contains the extension method class.</span></span>  
  
5. <span data-ttu-id="cfe83-112">Türün örnek yöntemleri değilmiş gibi yöntemler çağırır.</span><span class="sxs-lookup"><span data-stu-id="cfe83-112">Call the methods as if they were instance methods on the type.</span></span>  
  
     <span data-ttu-id="cfe83-113">İşleç uygulanmakta türü temsil ettiğinden, kod çağırarak ilk parametre belirtilmedi ve derleyici, nesnenin türünü zaten bilir unutmayın.</span><span class="sxs-lookup"><span data-stu-id="cfe83-113">Note that the first parameter is not specified by calling code because it represents the type on which the operator is being applied, and the compiler already knows the type of your object.</span></span> <span data-ttu-id="cfe83-114">Yalnızca 2 parametrelerin bağımsız değişkenleri sağlamak zorunda `n`.</span><span class="sxs-lookup"><span data-stu-id="cfe83-114">You only have to provide arguments for parameters 2 through `n`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfe83-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="cfe83-115">Example</span></span>  
 <span data-ttu-id="cfe83-116">Aşağıdaki örnekte adlı bir uzantı yöntemini uygulayan `WordCount` içinde `CustomExtensions.StringExtension` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="cfe83-116">The following example implements an extension method named `WordCount` in the `CustomExtensions.StringExtension` class.</span></span> <span data-ttu-id="cfe83-117">Yöntemin işlediği <xref:System.String> ilk yöntem parametresi olarak belirtilen sınıf.</span><span class="sxs-lookup"><span data-stu-id="cfe83-117">The method operates on the <xref:System.String> class, which is specified as the first method parameter.</span></span> <span data-ttu-id="cfe83-118">`CustomExtensions` Ad alanı uygulama ad alanına aktarılır ve yöntem içinde çağrılır `Main` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="cfe83-118">The `CustomExtensions` namespace is imported into the application namespace, and the method is called inside the `Main` method.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cfe83-119">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="cfe83-119">Compiling the Code</span></span>  
 <span data-ttu-id="cfe83-120">Bu kodu çalıştırmak için kopyalayın ve Visual Studio'da oluşturulan bir Visual C# konsol uygulaması projesi yapıştırın.</span><span class="sxs-lookup"><span data-stu-id="cfe83-120">To run this code, copy and paste it into a Visual C# console application project that has been created in Visual Studio.</span></span> <span data-ttu-id="cfe83-121">Varsayılan olarak, bu proje 3.5 sürümünü hedefleyen [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], ve bir System.Core.dll başvurusu vardır ve bir `using` System.Linq yönergesi.</span><span class="sxs-lookup"><span data-stu-id="cfe83-121">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it has a reference to System.Core.dll and a `using` directive for System.Linq.</span></span> <span data-ttu-id="cfe83-122">Projeden bir veya daha fazla bu gereksinimleri eksikse, bunları el ile ekleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="cfe83-122">If one or more of these requirements are missing from the project, you can add them manually.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="cfe83-123">.NET Framework Güvenliği</span><span class="sxs-lookup"><span data-stu-id="cfe83-123">.NET Framework Security</span></span>  
 <span data-ttu-id="cfe83-124">Genişletme yöntemleri, belirli güvenlik güvenlik açığı var.</span><span class="sxs-lookup"><span data-stu-id="cfe83-124">Extension methods present no specific security vulnerabilities.</span></span> <span data-ttu-id="cfe83-125">Tüm ad çakışmalarını örneği veya türü tarafından tanımlanan statik yöntem ile değiştiriliyor çözümlenir çünkü bir türün varolan yöntemleri kimliğine bürünmek için hiç kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="cfe83-125">They can never be used to impersonate existing methods on a type, because all name collisions are resolved in favor of the instance or static method defined by the type itself.</span></span> <span data-ttu-id="cfe83-126">Genişletme yöntemleri, genişletilmiş sınıf özel tüm verileri erişemez.</span><span class="sxs-lookup"><span data-stu-id="cfe83-126">Extension methods cannot access any private data in the extended class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfe83-127">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="cfe83-127">See also</span></span>

- [<span data-ttu-id="cfe83-128">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="cfe83-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="cfe83-129">Genişletme Yöntemleri</span><span class="sxs-lookup"><span data-stu-id="cfe83-129">Extension Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
- [<span data-ttu-id="cfe83-130">LINQ (dil ile tümleşik sorgu)</span><span class="sxs-lookup"><span data-stu-id="cfe83-130">LINQ (Language-Integrated Query)</span></span>](../../../csharp/linq/linq-in-csharp.md)
- [<span data-ttu-id="cfe83-131">Statik Sınıflar ve Statik Sınıf Üyeleri</span><span class="sxs-lookup"><span data-stu-id="cfe83-131">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
- [<span data-ttu-id="cfe83-132">protected</span><span class="sxs-lookup"><span data-stu-id="cfe83-132">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)
- [<span data-ttu-id="cfe83-133">internal</span><span class="sxs-lookup"><span data-stu-id="cfe83-133">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
- [<span data-ttu-id="cfe83-134">public</span><span class="sxs-lookup"><span data-stu-id="cfe83-134">public</span></span>](../../../csharp/language-reference/keywords/public.md)
- [<span data-ttu-id="cfe83-135">this</span><span class="sxs-lookup"><span data-stu-id="cfe83-135">this</span></span>](../../../csharp/language-reference/keywords/this.md)
- [<span data-ttu-id="cfe83-136">namespace</span><span class="sxs-lookup"><span data-stu-id="cfe83-136">namespace</span></span>](../../../csharp/language-reference/keywords/namespace.md)
