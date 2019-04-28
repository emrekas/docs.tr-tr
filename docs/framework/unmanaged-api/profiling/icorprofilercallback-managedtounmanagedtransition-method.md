---
title: ICorProfilerCallback::ManagedToUnmanagedTransition Yöntemi
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ManagedToUnmanagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ManagedToUnmanagedTransition
helpviewer_keywords:
- ManagedToUnmanagedTransition method [.NET Framework profiling]
- ICorProfilerCallback::ManagedToUnmanagedTransition method [.NET Framework profiling]
ms.assetid: ef3cd619-912d-40c5-a449-03ba02a39ee7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b00394d0b08e7e4a02b95437908dd65a51d0a042
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597680"
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a><span data-ttu-id="0691b-102">ICorProfilerCallback::ManagedToUnmanagedTransition Yöntemi</span><span class="sxs-lookup"><span data-stu-id="0691b-102">ICorProfilerCallback::ManagedToUnmanagedTransition Method</span></span>
<span data-ttu-id="0691b-103">Profil Oluşturucu, yönetilen koddan yönetilmeyen koda geçiş oluştuğunu bildirir.</span><span class="sxs-lookup"><span data-stu-id="0691b-103">Notifies the profiler that a transition from managed code to unmanaged code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0691b-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="0691b-104">Syntax</span></span>  
  
```  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0691b-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="0691b-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="0691b-106">[in] Aranan işlev kimliği.</span><span class="sxs-lookup"><span data-stu-id="0691b-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="0691b-107">[in] Değerini [cor_prf_transıtıon_reason](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) geçiş nedeniyle yönetilen koddan yönetilmeyen koda bir çağrı veya yönetilmeyen bir tarafından çağrılan yönetilen bir işlev geri döndürme nedeniyle oluşup oluşmadığını belirten sabit listesi.</span><span class="sxs-lookup"><span data-stu-id="0691b-107">[in] A value of the [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into unmanaged code from managed code, or because of a return from a managed function called by an unmanaged one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0691b-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="0691b-108">Remarks</span></span>  
 <span data-ttu-id="0691b-109">Varsa değerini `reason` COR_PRF_TRANSITION_CALL, kimliğidir yönetilmeyen işlevi, hangi asla tam zamanında derleyici kullanarak derlenen, işlevi olduğu.</span><span class="sxs-lookup"><span data-stu-id="0691b-109">If the value of `reason` is COR_PRF_TRANSITION_CALL, the function ID is that of the unmanaged function, which will never have been compiled using the just-in-time compiler.</span></span> <span data-ttu-id="0691b-110">Yönetilmeyen işlevleri, kendileriyle bir ad ve bazı meta veriler gibi ilgili temel bilgiler vardır.</span><span class="sxs-lookup"><span data-stu-id="0691b-110">Unmanaged functions have basic information associated with them, such as a name and some metadata.</span></span> <span data-ttu-id="0691b-111">Örtük platform kullanarak yönetilmeyen işlev çağrıldı (PInvoke) çağırmak, çalışma zamanının çağrı hedefi ve değeri belirlenemiyor `functionId` null olacaktır.</span><span class="sxs-lookup"><span data-stu-id="0691b-111">If the unmanaged function was called by using implicit platform invoke (PInvoke), the runtime cannot determine the destination of the call and the value of `functionId` will be null.</span></span> <span data-ttu-id="0691b-112">Örtük PInvoke hakkında daha fazla bilgi için bkz. [C++ Çalışabilirliği kullanma (örtük PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span><span class="sxs-lookup"><span data-stu-id="0691b-112">For more information on implicit PInvoke, see [Using C++ Interop (Implicit PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0691b-113">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="0691b-113">Requirements</span></span>  
 <span data-ttu-id="0691b-114">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0691b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0691b-115">**Üst bilgi:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0691b-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0691b-116">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0691b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0691b-117">**.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0691b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0691b-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="0691b-118">See also</span></span>

- [<span data-ttu-id="0691b-119">ICorProfilerCallback Arabirimi</span><span class="sxs-lookup"><span data-stu-id="0691b-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="0691b-120">UnmanagedToManagedTransition Yöntemi</span><span class="sxs-lookup"><span data-stu-id="0691b-120">UnmanagedToManagedTransition Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)
- [<span data-ttu-id="0691b-121">C++'ta Açık PInvoke Kullanma (DllImport Özniteliği)</span><span class="sxs-lookup"><span data-stu-id="0691b-121">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
