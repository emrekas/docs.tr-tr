---
title: "'<parametername>' parametresinin türü CLS uyumlu değil"
ms.date: 07/20/2015
f1_keywords:
- vbc40028
- bc40028
helpviewer_keywords:
- BC40028
ms.assetid: dfa1f6f9-bb88-44ad-b85f-149144363d41
ms.openlocfilehash: a719b3f1cbd972e79d057730ac1d89e5d91d97e5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664317"
---
# <a name="type-of-parameter-parametername-is-not-cls-compliant"></a><span data-ttu-id="54fbd-102">Parametrenin türü '\<parametername >' CLS uyumlu değil</span><span class="sxs-lookup"><span data-stu-id="54fbd-102">Type of parameter '\<parametername>' is not CLS-compliant</span></span>
<span data-ttu-id="54fbd-103">Bir yordam olarak işaretlenmiş `<CLSCompliant(True)>` ancak bir parametre olarak işaretlenmiş bir tür ile bildirir `<CLSCompliant(False)>`işaret konulmadıysa veya uyumlu olmayan bir tür olduğu için uygun değil.</span><span class="sxs-lookup"><span data-stu-id="54fbd-103">A procedure is marked as `<CLSCompliant(True)>` but declares a parameter with a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>  
  
 <span data-ttu-id="54fbd-104">İle uyumlu olması için bir yordam için [dil bağımsızlığı ve dilden bağımsız bileşenler](../../../standard/language-independence-and-language-independent-components.md) (CLS), yalnızca CLS uyumlu türler kullanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="54fbd-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="54fbd-105">Bu parametre türleri, dönüş türü ve tüm yerel değişkenlerin türleri için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="54fbd-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>  
  
 <span data-ttu-id="54fbd-106">Aşağıdaki Visual Basic veri türleri CLS uyumlu değildir:</span><span class="sxs-lookup"><span data-stu-id="54fbd-106">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="54fbd-107">SByte Veri Türü</span><span class="sxs-lookup"><span data-stu-id="54fbd-107">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="54fbd-108">UInteger Veri Türü</span><span class="sxs-lookup"><span data-stu-id="54fbd-108">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="54fbd-109">ULong Veri Türü</span><span class="sxs-lookup"><span data-stu-id="54fbd-109">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="54fbd-110">UShort Veri Türü</span><span class="sxs-lookup"><span data-stu-id="54fbd-110">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="54fbd-111">Uyguladığınızda <xref:System.CLSCompliantAttribute> bir programlama öğesine özniteliğin ayarladığınız `isCompliant` ya da parametre `True` veya `False` uyumluluk veya uyumsuzluk belirtmek için.</span><span class="sxs-lookup"><span data-stu-id="54fbd-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="54fbd-112">Bu parametre için varsayılan yok ve bir değer sağlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="54fbd-112">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="54fbd-113">Geçerli <xref:System.CLSCompliantAttribute> bir öğe için uyumsuz olarak değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="54fbd-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="54fbd-114">Varsayılan olarak, bu iletiyi bir uyarıdır.</span><span class="sxs-lookup"><span data-stu-id="54fbd-114">By default, this message is a warning.</span></span> <span data-ttu-id="54fbd-115">Uyarıları gizleme veya uyarıları hata olarak değerlendirmesini hakkında daha fazla bilgi için bkz: [Visual Basic'teki uyarıları yapılandırma](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="54fbd-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="54fbd-116">**Hata Kimliği:** BC40028</span><span class="sxs-lookup"><span data-stu-id="54fbd-116">**Error ID:** BC40028</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="54fbd-117">Bu hatayı düzeltmek için</span><span class="sxs-lookup"><span data-stu-id="54fbd-117">To correct this error</span></span>  
  
- <span data-ttu-id="54fbd-118">Yordamın bu belirli türünde bir parametre almalıdır, kaldırmanız <xref:System.CLSCompliantAttribute>.</span><span class="sxs-lookup"><span data-stu-id="54fbd-118">If the procedure must take a parameter of this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="54fbd-119">Yordamı, CLS uyumlu olamaz.</span><span class="sxs-lookup"><span data-stu-id="54fbd-119">The procedure cannot be CLS-compliant.</span></span>  
  
- <span data-ttu-id="54fbd-120">Yordamı CLS uyumlu olması gerekiyorsa, bu parametrenin türü en yakın CLS uyumlu türüne değiştirin.</span><span class="sxs-lookup"><span data-stu-id="54fbd-120">If the procedure must be CLS-compliant, change the type of this parameter to the closest CLS-compliant type.</span></span> <span data-ttu-id="54fbd-121">Örneğin, içinde yerine, `UInteger` kullanmanız mümkün olabilir `Integer` 2.147.483.647 yukarıda değer aralığı gerekmiyorsa.</span><span class="sxs-lookup"><span data-stu-id="54fbd-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="54fbd-122">Genişletilmiş aralık gerekiyorsa, değiştirebileceğiniz `UInteger` ile `Long`.</span><span class="sxs-lookup"><span data-stu-id="54fbd-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="54fbd-123">Otomasyon ve COM nesneleri ile arabirim, bazı türleri farklı veri genişliği kıyasla olduğunu aklınızda bulundurun [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54fbd-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="54fbd-124">Örneğin, `int` 16 bit diğer ortamlarda genellikle olur.</span><span class="sxs-lookup"><span data-stu-id="54fbd-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="54fbd-125">Böyle bir bileşenin bir 16 bitlik tamsayı kabul ediyorsanız, olarak bildirin `Short` yerine `Integer` Yönetilen Visual Basic kodunuzda.</span><span class="sxs-lookup"><span data-stu-id="54fbd-125">If you are accepting a 16-bit integer from such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>