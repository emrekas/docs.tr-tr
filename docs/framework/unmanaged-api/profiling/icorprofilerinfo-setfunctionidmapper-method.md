---
title: ICorProfilerInfo::SetFunctionIDMapper Yöntemi
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetFunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetFunctionIDMapper
helpviewer_keywords:
- ICorProfilerInfo::SetFunctionIDMapper method [.NET Framework profiling]
- SetFunctionIDMapper method [.NET Framework profiling]
ms.assetid: 1a6e5dae-d366-4497-9c02-7b5b1f43f9ec
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c4eefbb100b215cf4ac98352f37488b21cde49d8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772141"
---
# <a name="icorprofilerinfosetfunctionidmapper-method"></a><span data-ttu-id="dd45f-102">ICorProfilerInfo::SetFunctionIDMapper Yöntemi</span><span class="sxs-lookup"><span data-stu-id="dd45f-102">ICorProfilerInfo::SetFunctionIDMapper Method</span></span>
<span data-ttu-id="dd45f-103">Profil Oluşturucu uygulanan eşlemek için çağrılacak işlevi belirtir `FunctionID` değerleri oluşturucunun geçirilen alternatif, işlev girişi/çıkışı kancaları.</span><span class="sxs-lookup"><span data-stu-id="dd45f-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd45f-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="dd45f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFunctionIDMapper (  
    [in] FunctionIDMapper *pFunc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd45f-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="dd45f-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="dd45f-106">[in] Bir işaretçi [Functionıdmapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) eşlemek için çağrılacak olan uygulama `FunctionID` alternatif değerlerine değerleri.</span><span class="sxs-lookup"><span data-stu-id="dd45f-106">[in] A pointer to the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd45f-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="dd45f-107">Remarks</span></span>  
 <span data-ttu-id="dd45f-108">Alternatifleri için `FunctionID` profil oluşturucunun işlev girişi/çıkışı kancaları için değerleri geçirilir ([FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), ve [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)) tarafından belirtilen [Icorprofilerınfo2::setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="dd45f-108">The alternatives for the `FunctionID` values will be passed to the profiler's function entry/exit hooks ([FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), and [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)) that are specified by the [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) method.</span></span>  
  
 <span data-ttu-id="dd45f-109">`FunctionIDMapper` Yalnızca bir kez ayarlanabilir ve onu ayarladığınız önerilir [Icorprofilercallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) geri çağırma.</span><span class="sxs-lookup"><span data-stu-id="dd45f-109">The `FunctionIDMapper` can be set only once and it is recommended that you set it in the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd45f-110">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="dd45f-110">Requirements</span></span>  
 <span data-ttu-id="dd45f-111">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd45f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd45f-112">**Üst bilgi:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dd45f-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dd45f-113">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd45f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd45f-114">**.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd45f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd45f-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="dd45f-115">See also</span></span>

- [<span data-ttu-id="dd45f-116">ICorProfilerInfo Arabirimi</span><span class="sxs-lookup"><span data-stu-id="dd45f-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
