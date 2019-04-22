---
title: FunctionEnter İşlevi
ms.date: 03/30/2017
api_name:
- FunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter
helpviewer_keywords:
- FunctionEnter function [.NET Framework profiling]
ms.assetid: bf4ffa50-4506-4dd4-aa13-a0457b47ca74
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e6018b5b06a138b38b7b97df280a3e4c4ea0512d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59208416"
---
# <a name="functionenter-function"></a><span data-ttu-id="f72ae-102">FunctionEnter İşlevi</span><span class="sxs-lookup"><span data-stu-id="f72ae-102">FunctionEnter Function</span></span>
<span data-ttu-id="f72ae-103">Profil Oluşturucu, denetim bir işleve geçirilen olduğunu bildirir.</span><span class="sxs-lookup"><span data-stu-id="f72ae-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f72ae-104">`FunctionEnter` İşlevi, .NET Framework 2.0 sürümünde kullanım dışı ve kullanımı bir performans cezasına sebep olabilir.</span><span class="sxs-lookup"><span data-stu-id="f72ae-104">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span></span> <span data-ttu-id="f72ae-105">Kullanım [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) işlevini.</span><span class="sxs-lookup"><span data-stu-id="f72ae-105">Use the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f72ae-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="f72ae-106">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f72ae-107">Parametreler</span><span class="sxs-lookup"><span data-stu-id="f72ae-107">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="f72ae-108">[in] Denetimin geçtiğini işlevi tanımlayıcısı.</span><span class="sxs-lookup"><span data-stu-id="f72ae-108">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f72ae-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="f72ae-109">Remarks</span></span>  
 <span data-ttu-id="f72ae-110">`FunctionEnter` Bir geri çağırma işlevidir; uygulamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="f72ae-110">The `FunctionEnter` function is a callback; you must implement it.</span></span> <span data-ttu-id="f72ae-111">Uygulama kullanmalısınız `__declspec`(`naked`) depolama sınıfı özniteliği.</span><span class="sxs-lookup"><span data-stu-id="f72ae-111">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="f72ae-112">Yürütme altyapısı, bu işlevi çağırmadan önce tüm kayıtları kaydetmez.</span><span class="sxs-lookup"><span data-stu-id="f72ae-112">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="f72ae-113">Kayan nokta birimi (FPU) de dahil olmak üzere, kullandığınız tüm kayıtları girişte kaydetmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="f72ae-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="f72ae-114">Çıkışta, yığın, arayan tarafından gönderildi tüm parametreleri kapalı pencerelerinin tarafından geri yüklemelisiniz.</span><span class="sxs-lookup"><span data-stu-id="f72ae-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="f72ae-115">Uygulamasını `FunctionEnter` çöp toplamanın gecikeceğini çünkü engellemelisiniz değil.</span><span class="sxs-lookup"><span data-stu-id="f72ae-115">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="f72ae-116">Uygulama, yığını bir çöp toplama kullanımı kolay durumda olmayabilir çünkü bir çöp toplama çalışmamalıdır.</span><span class="sxs-lookup"><span data-stu-id="f72ae-116">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="f72ae-117">Bir çöp toplama girişiminde bulunulursa, çalışma zamanı kadar engeller `FunctionEnter` döndürür.</span><span class="sxs-lookup"><span data-stu-id="f72ae-117">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span></span>  
  
 <span data-ttu-id="f72ae-118">Ayrıca, `FunctionEnter` işlevi değil çağırmalıdır yönetilen koda veya herhangi bir şekilde neden yönetilen bellek ayırma.</span><span class="sxs-lookup"><span data-stu-id="f72ae-118">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f72ae-119">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="f72ae-119">Requirements</span></span>  
 <span data-ttu-id="f72ae-120">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f72ae-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f72ae-121">**Üst bilgi:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="f72ae-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="f72ae-122">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f72ae-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f72ae-123">**.NET framework sürümleri:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="f72ae-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f72ae-124">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="f72ae-124">See also</span></span>

- [<span data-ttu-id="f72ae-125">FunctionEnter2 İşlevi</span><span class="sxs-lookup"><span data-stu-id="f72ae-125">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="f72ae-126">FunctionLeave2 İşlevi</span><span class="sxs-lookup"><span data-stu-id="f72ae-126">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="f72ae-127">FunctionTailcall2 İşlevi</span><span class="sxs-lookup"><span data-stu-id="f72ae-127">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="f72ae-128">SetEnterLeaveFunctionHooks2 Yöntemi</span><span class="sxs-lookup"><span data-stu-id="f72ae-128">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="f72ae-129">Profil Oluşturma Genel Statik İşlevleri</span><span class="sxs-lookup"><span data-stu-id="f72ae-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
