---
title: Public (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
ms.openlocfilehash: 062d6276ab91705a4554da2afa8459a26453906f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54703620"
---
# <a name="public-visual-basic"></a><span data-ttu-id="0e41b-102">Public (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e41b-102">Public (Visual Basic)</span></span>
<span data-ttu-id="0e41b-103">Bir veya daha fazla bildirilmiş programlama öğesine hiçbir erişim kısıtlamasına sahip olmadığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="0e41b-103">Specifies that one or more declared programming elements have no access restrictions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e41b-104">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="0e41b-104">Remarks</span></span>  
 <span data-ttu-id="0e41b-105">Bir bileşen ya da bir sınıf kitaplığı gibi bir bileşenler kümesi yayımlıyorsanız genellikle programlama öğeleri, derleme ile birlikte çalışır herhangi bir kod tarafından erişilebilir olmasını istersiniz.</span><span class="sxs-lookup"><span data-stu-id="0e41b-105">If you are publishing a component or set of components, such as a class library, you usually want the programming elements to be accessible by any code that interoperates with your assembly.</span></span> <span data-ttu-id="0e41b-106">Bir öğe üzerinde sınırsız erişimi confer için onunla bildirebilirsiniz `Public`.</span><span class="sxs-lookup"><span data-stu-id="0e41b-106">To confer such unlimited access on an element, you can declare it with `Public`.</span></span>  
  
 <span data-ttu-id="0e41b-107">Erişimi sınırlamak gerekmediğinde genel erişim bir programlama öğesi için normal düzeydir.</span><span class="sxs-lookup"><span data-stu-id="0e41b-107">Public access is the normal level for a programming element when you do not need to limit access to it.</span></span> <span data-ttu-id="0e41b-108">Bir öğenin erişim düzeyi bir arabirimi, modül, sınıf veya yapı içinde bildirilen Not Varsayılan olarak `Public` , aksi takdirde değil bildirirseniz.</span><span class="sxs-lookup"><span data-stu-id="0e41b-108">Note that the access level of an element declared within an interface, module, class, or structure defaults to `Public` if you do not declare it otherwise.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="0e41b-109">Kurallar</span><span class="sxs-lookup"><span data-stu-id="0e41b-109">Rules</span></span>  
  
-   <span data-ttu-id="0e41b-110">**Bildirim bağlamı.**</span><span class="sxs-lookup"><span data-stu-id="0e41b-110">**Declaration Context.**</span></span> <span data-ttu-id="0e41b-111">Kullanabileceğiniz `Public` yalnızca düzeyinde modülü, arabirim veya ad alanı.</span><span class="sxs-lookup"><span data-stu-id="0e41b-111">You can use `Public` only at module, interface, or namespace level.</span></span> <span data-ttu-id="0e41b-112">Bildirim bağlamı başka bir deyişle bir `Public` öğesi bir kaynak dosyası, ad alanı, arabirim, modül, sınıf veya yapı olmalıdır ve bir yordam olamaz.</span><span class="sxs-lookup"><span data-stu-id="0e41b-112">This means the declaration context for a `Public` element must be a source file, namespace, interface, module, class, or structure, and cannot be a procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="0e41b-113">Davranış</span><span class="sxs-lookup"><span data-stu-id="0e41b-113">Behavior</span></span>  
  
-   <span data-ttu-id="0e41b-114">**Erişim düzeyi.**</span><span class="sxs-lookup"><span data-stu-id="0e41b-114">**Access Level.**</span></span> <span data-ttu-id="0e41b-115">Bir modül, sınıf veya yapı erişebilen tüm kod erişip kendi `Public` öğeleri.</span><span class="sxs-lookup"><span data-stu-id="0e41b-115">All code that can access a module, class, or structure can access its `Public` elements.</span></span>  
  
-   <span data-ttu-id="0e41b-116">**Varsayılan erişim.**</span><span class="sxs-lookup"><span data-stu-id="0e41b-116">**Default Access.**</span></span> <span data-ttu-id="0e41b-117">Yerel değişkenleri ve ortak erişimi için bir yordam varsayılan içinde herhangi bir erişim değiştiricileri üzerlerinde kullanamazsınız.</span><span class="sxs-lookup"><span data-stu-id="0e41b-117">Local variables inside a procedure default to public access, and you cannot use any access modifiers on them.</span></span>  
  
-   <span data-ttu-id="0e41b-118">**Erişim değiştiricileri.**</span><span class="sxs-lookup"><span data-stu-id="0e41b-118">**Access Modifiers.**</span></span> <span data-ttu-id="0e41b-119">Erişim düzeyini sağlayacaklarını anahtar sözcükleri adlı *erişim değiştiricilerine*.</span><span class="sxs-lookup"><span data-stu-id="0e41b-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="0e41b-120">Erişim değiştiricileri bir karşılaştırması için bkz: [erişim düzeyini Visual Basic'te](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="0e41b-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="0e41b-121">`Public` Bu bağlamda değiştirici kullanılabilir:</span><span class="sxs-lookup"><span data-stu-id="0e41b-121">The `Public` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="0e41b-122">Class Deyimi</span><span class="sxs-lookup"><span data-stu-id="0e41b-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="0e41b-123">Const Deyimi</span><span class="sxs-lookup"><span data-stu-id="0e41b-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="0e41b-124">Declare Deyimi</span><span class="sxs-lookup"><span data-stu-id="0e41b-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="0e41b-125">Delegate Deyimi</span><span class="sxs-lookup"><span data-stu-id="0e41b-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="0e41b-126">Dim Deyimi</span><span class="sxs-lookup"><span data-stu-id="0e41b-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="0e41b-127">Enum Deyimi</span><span class="sxs-lookup"><span data-stu-id="0e41b-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="0e41b-128">Event Deyimi</span><span class="sxs-lookup"><span data-stu-id="0e41b-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="0e41b-129">Function Deyimi</span><span class="sxs-lookup"><span data-stu-id="0e41b-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="0e41b-130">Interface Deyimi</span><span class="sxs-lookup"><span data-stu-id="0e41b-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="0e41b-131">Module Deyimi</span><span class="sxs-lookup"><span data-stu-id="0e41b-131">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="0e41b-132">Operator Deyimi</span><span class="sxs-lookup"><span data-stu-id="0e41b-132">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="0e41b-133">Property Deyimi</span><span class="sxs-lookup"><span data-stu-id="0e41b-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="0e41b-134">Structure Deyimi</span><span class="sxs-lookup"><span data-stu-id="0e41b-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="0e41b-135">Sub Deyimi</span><span class="sxs-lookup"><span data-stu-id="0e41b-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="0e41b-136">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="0e41b-136">See also</span></span>
- [<span data-ttu-id="0e41b-137">Protected</span><span class="sxs-lookup"><span data-stu-id="0e41b-137">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="0e41b-138">Friend</span><span class="sxs-lookup"><span data-stu-id="0e41b-138">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="0e41b-139">Private</span><span class="sxs-lookup"><span data-stu-id="0e41b-139">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="0e41b-140">Private Protected</span><span class="sxs-lookup"><span data-stu-id="0e41b-140">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="0e41b-141">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="0e41b-141">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="0e41b-142">Visual Basic'de erişim düzeyleri</span><span class="sxs-lookup"><span data-stu-id="0e41b-142">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="0e41b-143">Yordamlar</span><span class="sxs-lookup"><span data-stu-id="0e41b-143">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="0e41b-144">Yapılar</span><span class="sxs-lookup"><span data-stu-id="0e41b-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="0e41b-145">Nesneler ve Sınıflar</span><span class="sxs-lookup"><span data-stu-id="0e41b-145">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
