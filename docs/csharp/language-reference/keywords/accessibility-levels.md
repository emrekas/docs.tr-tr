---
title: Erişilebilirlik düzeyleri - C# başvurusu
ms.custom: seodec18
ms.date: 12/06/2017
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
ms.openlocfilehash: da49c6f0b44ab0eefbd338963a744a11502f75da
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130474"
---
# <a name="accessibility-levels-c-reference"></a><span data-ttu-id="40a26-102">Erişilebilirlik Düzeyleri (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="40a26-102">Accessibility Levels (C# Reference)</span></span>

<span data-ttu-id="40a26-103">Erişim değiştiricileri kullanma `public`, `protected`, `internal`, veya `private`, üyeleri için aşağıdaki bildirilen erişilebilirliği düzeylerinden birini belirtin.</span><span class="sxs-lookup"><span data-stu-id="40a26-103">Use the access modifiers, `public`, `protected`, `internal`, or `private`, to specify one of the following declared accessibility levels for members.</span></span>  
  
|<span data-ttu-id="40a26-104">Bildirilen erişilebilirliği</span><span class="sxs-lookup"><span data-stu-id="40a26-104">Declared accessibility</span></span>|<span data-ttu-id="40a26-105">Açıklama</span><span class="sxs-lookup"><span data-stu-id="40a26-105">Meaning</span></span>|  
|----------------------------|-------------|  
|[`public`](public.md)|<span data-ttu-id="40a26-106">Erişim sınırlı değildir.</span><span class="sxs-lookup"><span data-stu-id="40a26-106">Access is not restricted.</span></span>|  
|[`protected`](protected.md)|<span data-ttu-id="40a26-107">Erişim içeren sınıfı veya içeren sınıfından türetilen türler sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="40a26-107">Access is limited to the containing class or types derived from the containing class.</span></span>|  
|[`internal`](internal.md)|<span data-ttu-id="40a26-108">Geçerli derleme için erişim sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="40a26-108">Access is limited to the current assembly.</span></span>|  
|[`protected internal`](protected-internal.md)|<span data-ttu-id="40a26-109">Geçerli derleme veya içeren sınıfından türetilen türler için erişim sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="40a26-109">Access is limited to the current assembly or types derived from the containing class.</span></span>|  
|[`private`](private.md)|<span data-ttu-id="40a26-110">Erişimi, kapsadığı tür için sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="40a26-110">Access is limited to the containing type.</span></span>|  
|[`private protected`](private-protected.md)|<span data-ttu-id="40a26-111">Erişim içeren sınıfı veya geçerli derlemedeki içeren sınıfından türetilen türler sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="40a26-111">Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span> <span data-ttu-id="40a26-112">C# 7.2 sonrasında kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="40a26-112">Available since C# 7.2.</span></span> |  
  
 <span data-ttu-id="40a26-113">Yalnızca bir erişim değiştiricisi izin verilen bir üye veya tür, dışında kullandığınızda `protected internal` veya `private protected` birleşimleri.</span><span class="sxs-lookup"><span data-stu-id="40a26-113">Only one access modifier is allowed for a member or type, except when you use the `protected internal` or `private protected` combinations.</span></span>  
  
 <span data-ttu-id="40a26-114">Erişim değiştiricileri ad alanları üzerinde izin verilmez.</span><span class="sxs-lookup"><span data-stu-id="40a26-114">Access modifiers are not allowed on namespaces.</span></span> <span data-ttu-id="40a26-115">Ad alanları, hiçbir erişim kısıtlamasına sahip.</span><span class="sxs-lookup"><span data-stu-id="40a26-115">Namespaces have no access restrictions.</span></span>  
  
 <span data-ttu-id="40a26-116">Üye bildirimi oluştuğu bağlama bağlı olarak, yalnızca belirli bildirilen erişilebilirlikleri izin verilir.</span><span class="sxs-lookup"><span data-stu-id="40a26-116">Depending on the context in which a member declaration occurs, only certain declared accessibilities are permitted.</span></span> <span data-ttu-id="40a26-117">Hiçbir erişim değiştiricisi üye bildiriminde belirtilmezse, varsayılan erişilebilirlik kullanılır.</span><span class="sxs-lookup"><span data-stu-id="40a26-117">If no access modifier is specified in a member declaration, a default accessibility is used.</span></span>  
  
 <span data-ttu-id="40a26-118">Diğer türleri iç içe değil, en üst düzey türleri dbmigrationsconfiguration `internal` veya `public` erişilebilirlik.</span><span class="sxs-lookup"><span data-stu-id="40a26-118">Top-level types, which are not nested in other types, can only have `internal` or `public` accessibility.</span></span> <span data-ttu-id="40a26-119">Bu tür için varsayılan erişilebilirlik, `internal`.</span><span class="sxs-lookup"><span data-stu-id="40a26-119">The default accessibility for these types is `internal`.</span></span>  
  
 <span data-ttu-id="40a26-120">Diğer tür üyeleri olan iç içe geçmiş türleri erişilebilirlikleri aşağıdaki tabloda gösterildiği gibi bildirilen.</span><span class="sxs-lookup"><span data-stu-id="40a26-120">Nested types, which are members of other types, can have declared accessibilities as indicated in the following table.</span></span>  
  
|<span data-ttu-id="40a26-121">Üyeleri</span><span class="sxs-lookup"><span data-stu-id="40a26-121">Members of</span></span>|<span data-ttu-id="40a26-122">Varsayılan üye erişilebilirliği</span><span class="sxs-lookup"><span data-stu-id="40a26-122">Default member accessibility</span></span>|<span data-ttu-id="40a26-123">İzin verilen, üyenin bildirilen erişilebilirliği</span><span class="sxs-lookup"><span data-stu-id="40a26-123">Allowed declared accessibility of the member</span></span>|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|<span data-ttu-id="40a26-124">Yok.</span><span class="sxs-lookup"><span data-stu-id="40a26-124">None</span></span>|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|<span data-ttu-id="40a26-125">None</span><span class="sxs-lookup"><span data-stu-id="40a26-125">None</span></span>|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 <span data-ttu-id="40a26-126">İç içe türün erişilebilirliği bağlıdır, [erişilebilirlik etki alanı](../../../csharp/language-reference/keywords/accessibility-domain.md), üyenin bildirilen erişilebilirliği ve hemen içeren türün erişilebilirlik etki alanı tarafından belirlenir.</span><span class="sxs-lookup"><span data-stu-id="40a26-126">The accessibility of a nested type depends on its [accessibility domain](../../../csharp/language-reference/keywords/accessibility-domain.md), which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="40a26-127">Ancak, iç içe türün erişilebilirlik etki alanı, kapsayan türdeki aşamaz.</span><span class="sxs-lookup"><span data-stu-id="40a26-127">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="40a26-128">C# Dil Belirtimi</span><span class="sxs-lookup"><span data-stu-id="40a26-128">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="40a26-129">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="40a26-129">See also</span></span>

- [<span data-ttu-id="40a26-130">C# Başvurusu</span><span class="sxs-lookup"><span data-stu-id="40a26-130">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="40a26-131">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="40a26-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="40a26-132">C# Anahtar Sözcükleri</span><span class="sxs-lookup"><span data-stu-id="40a26-132">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="40a26-133">Erişim Değiştiricileri</span><span class="sxs-lookup"><span data-stu-id="40a26-133">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)
- [<span data-ttu-id="40a26-134">Erişilebilirlik Etki Alanı</span><span class="sxs-lookup"><span data-stu-id="40a26-134">Accessibility Domain</span></span>](../../../csharp/language-reference/keywords/accessibility-domain.md)
- [<span data-ttu-id="40a26-135">Erişilebilirlik Düzeylerinin Kullanılmasındaki Kısıtlamalar</span><span class="sxs-lookup"><span data-stu-id="40a26-135">Restrictions on Using Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)
- [<span data-ttu-id="40a26-136">Erişim Değiştiricileri</span><span class="sxs-lookup"><span data-stu-id="40a26-136">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="40a26-137">public</span><span class="sxs-lookup"><span data-stu-id="40a26-137">public</span></span>](../../../csharp/language-reference/keywords/public.md)
- [<span data-ttu-id="40a26-138">private</span><span class="sxs-lookup"><span data-stu-id="40a26-138">private</span></span>](../../../csharp/language-reference/keywords/private.md)
- [<span data-ttu-id="40a26-139">protected</span><span class="sxs-lookup"><span data-stu-id="40a26-139">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)
- [<span data-ttu-id="40a26-140">internal</span><span class="sxs-lookup"><span data-stu-id="40a26-140">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
