---
title: Module deyimi (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Module
- vb.Module
helpviewer_keywords:
- modules, classes
- modules
- Module statement [Visual Basic]
- modules, declaring
- standard modules
- classes [Visual Basic], vs. modules
- declarations [Visual Basic], modules
ms.assetid: a1243afc-14a5-45df-95d5-51118aeac362
ms.openlocfilehash: f546498e5282bcf58d07a06968bb4303e4e6d7b9
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838150"
---
# <a name="module-statement"></a><span data-ttu-id="f9f64-102">Module Deyimi</span><span class="sxs-lookup"><span data-stu-id="f9f64-102">Module Statement</span></span>
<span data-ttu-id="f9f64-103">Bir modülün adını bildirir ve değişkenleri, özellikleri, olayları ve modülü oluşturan yordamların tanımını tanıtır.</span><span class="sxs-lookup"><span data-stu-id="f9f64-103">Declares the name of a module and introduces the definition of the variables, properties, events, and procedures that the module comprises.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9f64-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="f9f64-104">Syntax</span></span>  
  
```vb 
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a><span data-ttu-id="f9f64-105">Bölümler</span><span class="sxs-lookup"><span data-stu-id="f9f64-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="f9f64-106">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="f9f64-106">Optional.</span></span> <span data-ttu-id="f9f64-107">Bkz: [öznitelik listesi](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="f9f64-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="f9f64-108">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="f9f64-108">Optional.</span></span> <span data-ttu-id="f9f64-109">Aşağıdakilerden biri olabilir:</span><span class="sxs-lookup"><span data-stu-id="f9f64-109">Can be one of the following:</span></span>  
  
-   [<span data-ttu-id="f9f64-110">Public</span><span class="sxs-lookup"><span data-stu-id="f9f64-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [<span data-ttu-id="f9f64-111">Friend</span><span class="sxs-lookup"><span data-stu-id="f9f64-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 <span data-ttu-id="f9f64-112">Bkz: [erişim düzeyini Visual Basic'te](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="f9f64-112">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `name`  
 <span data-ttu-id="f9f64-113">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="f9f64-113">Required.</span></span> <span data-ttu-id="f9f64-114">Bu modül adı.</span><span class="sxs-lookup"><span data-stu-id="f9f64-114">Name of this module.</span></span> <span data-ttu-id="f9f64-115">Bkz: [bildirilen öğe adları](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="f9f64-115">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 `statements`  
 <span data-ttu-id="f9f64-116">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="f9f64-116">Optional.</span></span> <span data-ttu-id="f9f64-117">Değişkenleri, özellikleri, olayları, yordamları ve bu modülün iç içe geçmiş türleri tanımlamak deyimler.</span><span class="sxs-lookup"><span data-stu-id="f9f64-117">Statements which define the variables, properties, events, procedures, and nested types of this module.</span></span>  
  
 `End Module`  
 <span data-ttu-id="f9f64-118">Sonlandırır `Module` tanımı.</span><span class="sxs-lookup"><span data-stu-id="f9f64-118">Terminates the `Module` definition.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9f64-119">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="f9f64-119">Remarks</span></span>  
 <span data-ttu-id="f9f64-120">A `Module` deyimi, ad alanı bir başvuru türü tanımlar.</span><span class="sxs-lookup"><span data-stu-id="f9f64-120">A `Module` statement defines a reference type available throughout its namespace.</span></span> <span data-ttu-id="f9f64-121">A *Modülü* (bazen adlı bir *standart modül*) benzer bir sınıf, ancak bazı önemli farklılıklar.</span><span class="sxs-lookup"><span data-stu-id="f9f64-121">A *module* (sometimes called a *standard module*)is similar to a class but with some important distinctions.</span></span> <span data-ttu-id="f9f64-122">Her bir modüle tam olarak bir örneği olduğu ve oluşturulamaz veya bir değişkene atanması gerekmez.</span><span class="sxs-lookup"><span data-stu-id="f9f64-122">Every module has exactly one instance and does not need to be created or assigned to a variable.</span></span> <span data-ttu-id="f9f64-123">Modüller devralmayı desteklemez veya arabirimlerini.</span><span class="sxs-lookup"><span data-stu-id="f9f64-123">Modules do not support inheritance or implement interfaces.</span></span> <span data-ttu-id="f9f64-124">Bir modül bildirimi bir *türü* bir sınıf veya yapı olan anlamında — bir modülün veri türü için bir programlama öğesi bildiremezsiniz.</span><span class="sxs-lookup"><span data-stu-id="f9f64-124">Notice that a module is not a *type* in the sense that a class or structure is — you cannot declare a programming element to have the data type of a module.</span></span>  
  
 <span data-ttu-id="f9f64-125">Kullanabileceğiniz `Module` yalnızca ad alanı düzeyinde.</span><span class="sxs-lookup"><span data-stu-id="f9f64-125">You can use `Module` only at namespace level.</span></span> <span data-ttu-id="f9f64-126">Başka bir deyişle *bildirim içeriğinin* bir modül, kaynak dosya veya ad alanı olmalıdır ve bir sınıf, yapı, modül, arabirimi, yordam veya blok olamayacağı için.</span><span class="sxs-lookup"><span data-stu-id="f9f64-126">This means the *declaration context* for a module must be a source file or namespace, and cannot be a class, structure, module, interface, procedure, or block.</span></span> <span data-ttu-id="f9f64-127">Bir modülün herhangi bir türü veya başka bir modül içinde iç içe olamaz.</span><span class="sxs-lookup"><span data-stu-id="f9f64-127">You cannot nest a module within another module, or within any type.</span></span> <span data-ttu-id="f9f64-128">Daha fazla bilgi için [bildirim bağlamları ve varsayılan erişim düzeyleri](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="f9f64-128">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="f9f64-129">Bir modül programınızı olarak aynı kullanım ömrü vardır.</span><span class="sxs-lookup"><span data-stu-id="f9f64-129">A module has the same lifetime as your program.</span></span> <span data-ttu-id="f9f64-130">Tüm üyeleri olduğundan `Shared`, ayrıca sahip oldukları yaşam süreleri, programın eşit.</span><span class="sxs-lookup"><span data-stu-id="f9f64-130">Because its members are all `Shared`, they also have lifetimes equal to that of the program.</span></span>  
  
 <span data-ttu-id="f9f64-131">Modüller için varsayılan değer [arkadaş](../../../visual-basic/language-reference/modifiers/friend.md) erişim.</span><span class="sxs-lookup"><span data-stu-id="f9f64-131">Modules default to [Friend](../../../visual-basic/language-reference/modifiers/friend.md) access.</span></span> <span data-ttu-id="f9f64-132">Erişim değiştiricileri ile kullanıcıların erişim düzeylerini ayarlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f9f64-132">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="f9f64-133">Daha fazla bilgi için [erişim düzeyini Visual Basic'te](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="f9f64-133">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="f9f64-134">Tüm modül örtük olarak üyeleri `Shared`.</span><span class="sxs-lookup"><span data-stu-id="f9f64-134">All members of a module are implicitly `Shared`.</span></span>  
  
## <a name="classes-and-modules"></a><span data-ttu-id="f9f64-135">Sınıflar ve modüller</span><span class="sxs-lookup"><span data-stu-id="f9f64-135">Classes and Modules</span></span>  
 <span data-ttu-id="f9f64-136">Bu öğeleri birçok benzerlikler, ancak bazı önemli farklar da mevcuttur.</span><span class="sxs-lookup"><span data-stu-id="f9f64-136">These elements have many similarities, but there are some important differences as well.</span></span>  
  
-   <span data-ttu-id="f9f64-137">**Terimler.**</span><span class="sxs-lookup"><span data-stu-id="f9f64-137">**Terminology.**</span></span> <span data-ttu-id="f9f64-138">Visual Basic'in önceki sürümlerindeki tanımak modülleri iki tür: *sınıf modülleri* (.cls dosyaları) ve *Standart modüller* (.bas dosyaları).</span><span class="sxs-lookup"><span data-stu-id="f9f64-138">Previous versions of Visual Basic recognize two types of modules: *class modules* (.cls files) and *standard modules* (.bas files).</span></span> <span data-ttu-id="f9f64-139">Bu sürümdeki çağırır *sınıfları* ve *modülleri*sırasıyla.</span><span class="sxs-lookup"><span data-stu-id="f9f64-139">The current version calls these *classes* and *modules*, respectively.</span></span>  
  
-   <span data-ttu-id="f9f64-140">**Paylaşılan üyeler.**</span><span class="sxs-lookup"><span data-stu-id="f9f64-140">**Shared Members.**</span></span> <span data-ttu-id="f9f64-141">Bir sınıfın üyesi bir paylaşılan olup veya örnek üye denetleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f9f64-141">You can control whether a member of a class is a shared or instance member.</span></span>  
  
-   <span data-ttu-id="f9f64-142">**Nesne yönü.**</span><span class="sxs-lookup"><span data-stu-id="f9f64-142">**Object Orientation.**</span></span> <span data-ttu-id="f9f64-143">Nesne yönelimli sınıflardır, ancak modüller değildir.</span><span class="sxs-lookup"><span data-stu-id="f9f64-143">Classes are object-oriented, but modules are not.</span></span> <span data-ttu-id="f9f64-144">Bu nedenle tek sınıf nesneleri olarak oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="f9f64-144">So only classes can be instantiated as objects.</span></span> <span data-ttu-id="f9f64-145">Daha fazla bilgi için [nesneler ve sınıflar](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span><span class="sxs-lookup"><span data-stu-id="f9f64-145">For more information, see [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="f9f64-146">Kurallar</span><span class="sxs-lookup"><span data-stu-id="f9f64-146">Rules</span></span>  
  
-   <span data-ttu-id="f9f64-147">**Değiştiriciler.**</span><span class="sxs-lookup"><span data-stu-id="f9f64-147">**Modifiers.**</span></span> <span data-ttu-id="f9f64-148">Tüm modül örtük olarak üyeleridir [paylaşılan](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="f9f64-148">All module members are implicitly [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="f9f64-149">Kullanamazsınız `Shared` bildirme üyesi ve herhangi bir üyenin paylaşılan durumu değiştirilemiyor, anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="f9f64-149">You cannot use the `Shared` keyword when declaring a member, and you cannot alter the shared status of any member.</span></span>  
  
-   <span data-ttu-id="f9f64-150">**Devralma.**</span><span class="sxs-lookup"><span data-stu-id="f9f64-150">**Inheritance.**</span></span> <span data-ttu-id="f9f64-151">Bir modül dışında herhangi bir türden devralamaz <xref:System.Object>, hangi tüm modüllerden devralır.</span><span class="sxs-lookup"><span data-stu-id="f9f64-151">A module cannot inherit from any type other than <xref:System.Object>, from which all modules inherit.</span></span> <span data-ttu-id="f9f64-152">Özellikle, bir modül bir başkasından devralınamaz.</span><span class="sxs-lookup"><span data-stu-id="f9f64-152">In particular, one module cannot inherit from another.</span></span>  
  
     <span data-ttu-id="f9f64-153">Kullanamazsınız [devralan deyimi](../../../visual-basic/language-reference/statements/inherits-statement.md) belirtmek için bir modül tanımında bile <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="f9f64-153">You cannot use the [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) in a module definition, even to specify <xref:System.Object>.</span></span>  
  
-   <span data-ttu-id="f9f64-154">**Varsayılan özellik.**</span><span class="sxs-lookup"><span data-stu-id="f9f64-154">**Default Property.**</span></span> <span data-ttu-id="f9f64-155">Bir modülün herhangi bir varsayılan özelliği tanımlanamaz.</span><span class="sxs-lookup"><span data-stu-id="f9f64-155">You cannot define any default properties in a module.</span></span> <span data-ttu-id="f9f64-156">Daha fazla bilgi için [varsayılan](../../../visual-basic/language-reference/modifiers/default.md).</span><span class="sxs-lookup"><span data-stu-id="f9f64-156">For more information, see [Default](../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="f9f64-157">Davranış</span><span class="sxs-lookup"><span data-stu-id="f9f64-157">Behavior</span></span>  
  
-   <span data-ttu-id="f9f64-158">**Erişim düzeyi.**</span><span class="sxs-lookup"><span data-stu-id="f9f64-158">**Access Level.**</span></span> <span data-ttu-id="f9f64-159">Bir modül her bir üyeyi kendi erişim düzeyiyle bildirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f9f64-159">Within a module, you can declare each member with its own access level.</span></span> <span data-ttu-id="f9f64-160">Modül üyeler için varsayılan değer [genel](../../../visual-basic/language-reference/modifiers/public.md) erişim, değişkenler ve sabitler, dışında varsayılan [özel](../../../visual-basic/language-reference/modifiers/private.md) erişim.</span><span class="sxs-lookup"><span data-stu-id="f9f64-160">Module members default to [Public](../../../visual-basic/language-reference/modifiers/public.md) access, except variables and constants, which default to [Private](../../../visual-basic/language-reference/modifiers/private.md) access.</span></span> <span data-ttu-id="f9f64-161">Bir modül daha üyelerinin birden sınırlı erişimi Belirtilen modül erişim düzeyi önceliklidir.</span><span class="sxs-lookup"><span data-stu-id="f9f64-161">When a module has more restricted access than one of its members, the specified module access level takes precedence.</span></span>  
  
-   <span data-ttu-id="f9f64-162">**Kapsam.**</span><span class="sxs-lookup"><span data-stu-id="f9f64-162">**Scope.**</span></span> <span data-ttu-id="f9f64-163">Ad alanı kapsamdadır bir modüldür.</span><span class="sxs-lookup"><span data-stu-id="f9f64-163">A module is in scope throughout its namespace.</span></span>  
  
     <span data-ttu-id="f9f64-164">Her modülü üye kapsamı bütün bir modüldür.</span><span class="sxs-lookup"><span data-stu-id="f9f64-164">The scope of every module member is the entire module.</span></span> <span data-ttu-id="f9f64-165">Tüm üyeleri geçmeleri bildirimi *türü promosyon*, modülü içeren ad alanına yükseltilecek kapsamlarına neden olur.</span><span class="sxs-lookup"><span data-stu-id="f9f64-165">Notice that all members undergo *type promotion*, which causes their scope to be promoted to the namespace containing the module.</span></span> <span data-ttu-id="f9f64-166">Daha fazla bilgi için [tür promosyonu](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span><span class="sxs-lookup"><span data-stu-id="f9f64-166">For more information, see [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span></span>  
  
-   <span data-ttu-id="f9f64-167">**Nitelik.**</span><span class="sxs-lookup"><span data-stu-id="f9f64-167">**Qualification.**</span></span> <span data-ttu-id="f9f64-168">Bir projede birden çok modül sahip olabilir ve iki veya daha fazla modül aynı ada sahip üye bildirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f9f64-168">You can have multiple modules in a project, and you can declare members with the same name in two or more modules.</span></span> <span data-ttu-id="f9f64-169">Ancak, başvurusu bu modül dışında ise herhangi bir referans gibi bir üye uygun modül adıyla nitelemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="f9f64-169">However, you must qualify any reference to such a member with the appropriate module name if the reference is from outside that module.</span></span> <span data-ttu-id="f9f64-170">Daha fazla bilgi için [bildirilmiş öğelere başvurular](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="f9f64-170">For more information, see [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9f64-171">Örnek</span><span class="sxs-lookup"><span data-stu-id="f9f64-171">Example</span></span>  
 [!code-vb[VbVbalrStatements#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#69)]  
  
## <a name="see-also"></a><span data-ttu-id="f9f64-172">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="f9f64-172">See also</span></span>

- [<span data-ttu-id="f9f64-173">Class Deyimi</span><span class="sxs-lookup"><span data-stu-id="f9f64-173">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="f9f64-174">Namespace Deyimi</span><span class="sxs-lookup"><span data-stu-id="f9f64-174">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="f9f64-175">Structure Deyimi</span><span class="sxs-lookup"><span data-stu-id="f9f64-175">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="f9f64-176">Interface Deyimi</span><span class="sxs-lookup"><span data-stu-id="f9f64-176">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="f9f64-177">Property Deyimi</span><span class="sxs-lookup"><span data-stu-id="f9f64-177">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="f9f64-178">Tür Yükseltme</span><span class="sxs-lookup"><span data-stu-id="f9f64-178">Type Promotion</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
