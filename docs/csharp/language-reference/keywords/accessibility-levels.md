---
title: Erişilebilirlik düzeyleri - C# başvurusu
ms.custom: seodec18
ms.date: 12/06/2017
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
ms.openlocfilehash: ca7bef8bf68b80015128619336db9fc6a8f5c237
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661835"
---
# <a name="accessibility-levels-c-reference"></a><span data-ttu-id="a45de-102">Erişilebilirlik Düzeyleri (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="a45de-102">Accessibility Levels (C# Reference)</span></span>

<span data-ttu-id="a45de-103">Erişim değiştiricileri kullanma `public`, `protected`, `internal`, veya `private`, üyeleri için aşağıdaki bildirilen erişilebilirliği düzeylerinden birini belirtin.</span><span class="sxs-lookup"><span data-stu-id="a45de-103">Use the access modifiers, `public`, `protected`, `internal`, or `private`, to specify one of the following declared accessibility levels for members.</span></span>  
  
|<span data-ttu-id="a45de-104">Bildirilen erişilebilirliği</span><span class="sxs-lookup"><span data-stu-id="a45de-104">Declared accessibility</span></span>|<span data-ttu-id="a45de-105">Açıklama</span><span class="sxs-lookup"><span data-stu-id="a45de-105">Meaning</span></span>|  
|----------------------------|-------------|  
|[`public`](public.md)|<span data-ttu-id="a45de-106">Erişim sınırlı değildir.</span><span class="sxs-lookup"><span data-stu-id="a45de-106">Access is not restricted.</span></span>|  
|[`protected`](protected.md)|<span data-ttu-id="a45de-107">Erişim içeren sınıfı veya içeren sınıfından türetilen türler sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="a45de-107">Access is limited to the containing class or types derived from the containing class.</span></span>|  
|[`internal`](internal.md)|<span data-ttu-id="a45de-108">Geçerli derleme için erişim sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="a45de-108">Access is limited to the current assembly.</span></span>|  
|[`protected internal`](protected-internal.md)|<span data-ttu-id="a45de-109">Geçerli derleme veya içeren sınıfından türetilen türler için erişim sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="a45de-109">Access is limited to the current assembly or types derived from the containing class.</span></span>|  
|[`private`](private.md)|<span data-ttu-id="a45de-110">Erişimi, kapsadığı tür için sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="a45de-110">Access is limited to the containing type.</span></span>|  
|[`private protected`](private-protected.md)|<span data-ttu-id="a45de-111">Erişim içeren sınıfı veya geçerli derlemedeki içeren sınıfından türetilen türler sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="a45de-111">Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span> <span data-ttu-id="a45de-112">C# 7.2 sonrasında kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="a45de-112">Available since C# 7.2.</span></span> |  
  
 <span data-ttu-id="a45de-113">Yalnızca bir erişim değiştiricisi izin verilen bir üye veya tür, dışında kullandığınızda `protected internal` veya `private protected` birleşimleri.</span><span class="sxs-lookup"><span data-stu-id="a45de-113">Only one access modifier is allowed for a member or type, except when you use the `protected internal` or `private protected` combinations.</span></span>  
  
 <span data-ttu-id="a45de-114">Erişim değiştiricileri ad alanları üzerinde izin verilmez.</span><span class="sxs-lookup"><span data-stu-id="a45de-114">Access modifiers are not allowed on namespaces.</span></span> <span data-ttu-id="a45de-115">Ad alanları, hiçbir erişim kısıtlamasına sahip.</span><span class="sxs-lookup"><span data-stu-id="a45de-115">Namespaces have no access restrictions.</span></span>  
  
 <span data-ttu-id="a45de-116">Üye bildirimi oluştuğu bağlama bağlı olarak, yalnızca belirli bildirilen erişilebilirlikleri izin verilir.</span><span class="sxs-lookup"><span data-stu-id="a45de-116">Depending on the context in which a member declaration occurs, only certain declared accessibilities are permitted.</span></span> <span data-ttu-id="a45de-117">Hiçbir erişim değiştiricisi üye bildiriminde belirtilmezse, varsayılan erişilebilirlik kullanılır.</span><span class="sxs-lookup"><span data-stu-id="a45de-117">If no access modifier is specified in a member declaration, a default accessibility is used.</span></span>  
  
 <span data-ttu-id="a45de-118">Diğer türleri iç içe değil, en üst düzey türleri dbmigrationsconfiguration `internal` veya `public` erişilebilirlik.</span><span class="sxs-lookup"><span data-stu-id="a45de-118">Top-level types, which are not nested in other types, can only have `internal` or `public` accessibility.</span></span> <span data-ttu-id="a45de-119">Bu tür için varsayılan erişilebilirlik, `internal`.</span><span class="sxs-lookup"><span data-stu-id="a45de-119">The default accessibility for these types is `internal`.</span></span>  
  
 <span data-ttu-id="a45de-120">Diğer tür üyeleri olan iç içe geçmiş türleri erişilebilirlikleri aşağıdaki tabloda gösterildiği gibi bildirilen.</span><span class="sxs-lookup"><span data-stu-id="a45de-120">Nested types, which are members of other types, can have declared accessibilities as indicated in the following table.</span></span>  
  
|<span data-ttu-id="a45de-121">Üyeleri</span><span class="sxs-lookup"><span data-stu-id="a45de-121">Members of</span></span>|<span data-ttu-id="a45de-122">Varsayılan üye erişilebilirliği</span><span class="sxs-lookup"><span data-stu-id="a45de-122">Default member accessibility</span></span>|<span data-ttu-id="a45de-123">İzin verilen, üyenin bildirilen erişilebilirliği</span><span class="sxs-lookup"><span data-stu-id="a45de-123">Allowed declared accessibility of the member</span></span>|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|<span data-ttu-id="a45de-124">Hiçbiri</span><span class="sxs-lookup"><span data-stu-id="a45de-124">None</span></span>|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|<span data-ttu-id="a45de-125">Hiçbiri</span><span class="sxs-lookup"><span data-stu-id="a45de-125">None</span></span>|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 <span data-ttu-id="a45de-126">İç içe türün erişilebilirliği bağlıdır, [erişilebilirlik etki alanı](../../../csharp/language-reference/keywords/accessibility-domain.md), üyenin bildirilen erişilebilirliği ve hemen içeren türün erişilebilirlik etki alanı tarafından belirlenir.</span><span class="sxs-lookup"><span data-stu-id="a45de-126">The accessibility of a nested type depends on its [accessibility domain](../../../csharp/language-reference/keywords/accessibility-domain.md), which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="a45de-127">Ancak, iç içe türün erişilebilirlik etki alanı, kapsayan türdeki aşamaz.</span><span class="sxs-lookup"><span data-stu-id="a45de-127">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="a45de-128">C# Dil Belirtimi</span><span class="sxs-lookup"><span data-stu-id="a45de-128">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a45de-129">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="a45de-129">See also</span></span>
- [<span data-ttu-id="a45de-130">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="a45de-130">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="a45de-131">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="a45de-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="a45de-132">C# Anahtar Sözcükleri</span><span class="sxs-lookup"><span data-stu-id="a45de-132">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="a45de-133">Erişim Değiştiricileri</span><span class="sxs-lookup"><span data-stu-id="a45de-133">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)
- [<span data-ttu-id="a45de-134">Erişilebilirlik Etki Alanı</span><span class="sxs-lookup"><span data-stu-id="a45de-134">Accessibility Domain</span></span>](../../../csharp/language-reference/keywords/accessibility-domain.md)
- [<span data-ttu-id="a45de-135">Erişilebilirlik Düzeylerinin Kullanılmasındaki Kısıtlamalar</span><span class="sxs-lookup"><span data-stu-id="a45de-135">Restrictions on Using Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)
- [<span data-ttu-id="a45de-136">Erişim Değiştiricileri</span><span class="sxs-lookup"><span data-stu-id="a45de-136">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="a45de-137">public</span><span class="sxs-lookup"><span data-stu-id="a45de-137">public</span></span>](../../../csharp/language-reference/keywords/public.md)
- [<span data-ttu-id="a45de-138">private</span><span class="sxs-lookup"><span data-stu-id="a45de-138">private</span></span>](../../../csharp/language-reference/keywords/private.md)
- [<span data-ttu-id="a45de-139">protected</span><span class="sxs-lookup"><span data-stu-id="a45de-139">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)
- [<span data-ttu-id="a45de-140">internal</span><span class="sxs-lookup"><span data-stu-id="a45de-140">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
