---
title: Ortak Dil Çalışma Zamanında Tür İletme
ms.date: 03/30/2017
dev_langs:
- csharp
- cpp
helpviewer_keywords:
- assemblies [.NET Framework], type forwarding
- type forwarding
ms.assetid: 51f8ffa3-c253-4201-a3d3-c4fad85ae097
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c262e8a20eb9a805f6c64cac412f0d0fd6eeb80
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109986"
---
# <a name="type-forwarding-in-the-common-language-runtime"></a><span data-ttu-id="51165-102">Ortak Dil Çalışma Zamanında Tür İletme</span><span class="sxs-lookup"><span data-stu-id="51165-102">Type Forwarding in the Common Language Runtime</span></span>
<span data-ttu-id="51165-103">Tür iletme orijinal derleme kullanan uygulamaları yeniden derlemenize gerek kalmadan bir tür için başka bir derleme taşımanızı sağlar.</span><span class="sxs-lookup"><span data-stu-id="51165-103">Type forwarding allows you to move a type to another assembly without having to recompile applications that use the original assembly.</span></span>  
  
 <span data-ttu-id="51165-104">Örneğin, bir uygulamanın kullandığı varsayalım `Example` adlı bir derlemede sınıfı, `Utility.dll`.</span><span class="sxs-lookup"><span data-stu-id="51165-104">For example, suppose an application uses the `Example` class in an assembly named `Utility.dll`.</span></span> <span data-ttu-id="51165-105">Geliştiriciler `Utility.dll` derlemeyi yeniden karar verebilirsiniz ve işlemin taşınabilecek `Example` başka bir derleme için sınıf.</span><span class="sxs-lookup"><span data-stu-id="51165-105">The developers of `Utility.dll` might decide to refactor the assembly, and in the process they might move the `Example` class to another assembly.</span></span> <span data-ttu-id="51165-106">Varsa eski sürümünü `Utility.dll` yeni sürümü tarafından değiştirilir `Utility.dll` Yardımcısı derlemesi, uygulamayı kullanan ve `Example` sınıfı, bunu konumlandıramadığından başarısız `Example` yeni sürümünü sınıfında `Utility.dll`.</span><span class="sxs-lookup"><span data-stu-id="51165-106">If the old version of `Utility.dll` is replaced by the new version of `Utility.dll` and its companion assembly, the application that uses the `Example` class fails because it cannot locate the `Example` class in the new version of `Utility.dll`.</span></span>  
  
 <span data-ttu-id="51165-107">Geliştiriciler `Utility.dll` bu istekleri ileterek kaçınabilirsiniz `Example` kullanarak sınıf <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> özniteliği.</span><span class="sxs-lookup"><span data-stu-id="51165-107">The developers of `Utility.dll` can avoid this by forwarding requests for the `Example` class, using the <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> attribute.</span></span> <span data-ttu-id="51165-108">Öznitelik en yeni sürümüne uygulanıp uygulanmadığını `Utility.dll`, için istekleri `Example` sınıfı artık sınıfı içeren derlemeye iletilir.</span><span class="sxs-lookup"><span data-stu-id="51165-108">If the attribute has been applied to the new version of `Utility.dll`, requests for the `Example` class are forwarded to the assembly that now contains the class.</span></span> <span data-ttu-id="51165-109">Var olan uygulamayı, normalde, yeniden derleme çalışmaya devam eder.</span><span class="sxs-lookup"><span data-stu-id="51165-109">The existing application continues to function normally, without recompilation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51165-110">.NET Framework 2.0 sürümünde, Visual Basic'te yazılmış derlemelerden türler iletemez.</span><span class="sxs-lookup"><span data-stu-id="51165-110">In the .NET Framework version 2.0, you cannot forward types from assemblies written in Visual Basic.</span></span> <span data-ttu-id="51165-111">Ancak, Visual Basic ile yazılan bir uygulamanın iletilen türlerini kullanabilir.</span><span class="sxs-lookup"><span data-stu-id="51165-111">However, an application written in Visual Basic can consume forwarded types.</span></span> <span data-ttu-id="51165-112">Diğer bir deyişle, C# veya C++ ortamında kodlanmış bir derleme uygulama kullanır ve bu derlemeden bir tür için başka bir derleme iletilir, Visual Basic uygulama iletilen türü kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="51165-112">That is, if the application uses an assembly coded in C# or C++, and a type from that assembly is forwarded to another assembly, the Visual Basic application can use the forwarded type.</span></span>  
  
## <a name="forwarding-types"></a><span data-ttu-id="51165-113">Tür iletme</span><span class="sxs-lookup"><span data-stu-id="51165-113">Forwarding Types</span></span>  
 <span data-ttu-id="51165-114">Bir tür iletme gereken dört adım vardır:</span><span class="sxs-lookup"><span data-stu-id="51165-114">There are four steps to forwarding a type:</span></span>  
  
1.  <span data-ttu-id="51165-115">Kaynak kodu türü için özgün derlemeden hedef derlemeye taşıyın.</span><span class="sxs-lookup"><span data-stu-id="51165-115">Move the source code for the type from the original assembly to the destination assembly.</span></span>  
  
2.  <span data-ttu-id="51165-116">Derleme türü kullanıldığı yer almasını, ekleme bir <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> taşındı türü.</span><span class="sxs-lookup"><span data-stu-id="51165-116">In the assembly where the type used to be located, add a <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> for the type that was moved.</span></span> <span data-ttu-id="51165-117">Aşağıdaki kod adlı bir tür özniteliğini gösterir `Example` , taşındı.</span><span class="sxs-lookup"><span data-stu-id="51165-117">The following code shows the attribute for a type named `Example` that was moved.</span></span>  
  
    ```csharp  
    [assembly:TypeForwardedToAttribute(typeof(Example))]  
    ```  
  
    ```cpp  
    [assembly:TypeForwardedToAttribute(Example::typeid)]  
    ```  
  
3.  <span data-ttu-id="51165-118">Artık türü içeren derlemenin derleme.</span><span class="sxs-lookup"><span data-stu-id="51165-118">Compile the assembly that now contains the type.</span></span>  
  
4.  <span data-ttu-id="51165-119">Türü artık türü içeren derlemeye bir başvuru ile konum için kullanıldığı derlemeyi yeniden derleyin.</span><span class="sxs-lookup"><span data-stu-id="51165-119">Recompile the assembly where the type used to be located, with a reference to the assembly that now contains the type.</span></span> <span data-ttu-id="51165-120">Örneğin, C# dosyasına komut satırında derleme yapıyorsanız kullanın [/Reference (C# Derleyici Seçenekleri)](~/docs/csharp/language-reference/compiler-options/reference-compiler-option.md) türü içeren derlemenin belirtmek için seçeneği.</span><span class="sxs-lookup"><span data-stu-id="51165-120">For example, if you are compiling a C# file from the command line, use the [/reference (C# Compiler Options)](~/docs/csharp/language-reference/compiler-options/reference-compiler-option.md) option to specify the assembly that contains the type.</span></span> <span data-ttu-id="51165-121">C++'ta kullanmak [#using](/cpp/preprocessor/hash-using-directive-cpp) türü içeren derlemenin belirtmek için kaynak dosyadaki yönergesi.</span><span class="sxs-lookup"><span data-stu-id="51165-121">In C++, use the [#using](/cpp/preprocessor/hash-using-directive-cpp) directive in the source file to specify the assembly that contains the type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51165-122">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="51165-122">See also</span></span>

- <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>
- [<span data-ttu-id="51165-123">Tür İletme (C++/CLI)</span><span class="sxs-lookup"><span data-stu-id="51165-123">Type Forwarding (C++/CLI)</span></span>](/cpp/windows/type-forwarding-cpp-cli)
- [<span data-ttu-id="51165-124">#using Yönergesi</span><span class="sxs-lookup"><span data-stu-id="51165-124">#using Directive</span></span>](/cpp/preprocessor/hash-using-directive-cpp)
