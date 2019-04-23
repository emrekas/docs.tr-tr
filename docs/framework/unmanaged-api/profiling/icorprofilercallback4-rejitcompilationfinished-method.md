---
title: ICorProfilerCallback4::ReJITCompilationFinished Yöntemi
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished
helpviewer_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished method [.NET Framework profiling]
- ReJITCompilationFinished method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 3b5cff02-2005-44eb-a2bc-50214c4b0e1d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0ec2981cbee4675f9cd2a4fd13d507f50ad2a3ff
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127965"
---
# <a name="icorprofilercallback4rejitcompilationfinished-method"></a><span data-ttu-id="a2feb-102">ICorProfilerCallback4::ReJITCompilationFinished Yöntemi</span><span class="sxs-lookup"><span data-stu-id="a2feb-102">ICorProfilerCallback4::ReJITCompilationFinished Method</span></span>
<span data-ttu-id="a2feb-103">Profil Oluşturucu, just-ın-time (JIT) derleyici bir işlevi yeniden derlemeden tamamlandığını bildirir.</span><span class="sxs-lookup"><span data-stu-id="a2feb-103">Notifies the profiler that the just-in-time (JIT) compiler has finished recompiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2feb-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="a2feb-104">Syntax</span></span>  
  
```  
HRESULT ReJITCompilationFinished(  
    [in] FunctionID functionId,    [in] ReJITID rejitId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2feb-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="a2feb-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="a2feb-106">[in] Derlendiğini işlevi kimliği.</span><span class="sxs-lookup"><span data-stu-id="a2feb-106">[in] The ID of the function that was recompiled.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="a2feb-107">[in] JIT yeniden derlenen işlevi kimliği.</span><span class="sxs-lookup"><span data-stu-id="a2feb-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="a2feb-108">[in] JIT yeniden derlemesi başarılı olup olmadığını belirten bir değer.</span><span class="sxs-lookup"><span data-stu-id="a2feb-108">[in] A value that indicates whether the JIT recompilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="a2feb-109">[in] `true` engelleme bu geri çağrısından; döndürmek çağıran iş parçacığını beklemek çalışma zamanı neden olabileceğini göstermek için `false` engelleme zamanının işlemi etkilemez belirtmek için.</span><span class="sxs-lookup"><span data-stu-id="a2feb-109">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  
  
 <span data-ttu-id="a2feb-110">Değerini `true` çalışma zamanı zarar değil, ancak profil oluşturma sonuçlarından etkileyebilir.</span><span class="sxs-lookup"><span data-stu-id="a2feb-110">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2feb-111">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="a2feb-111">Requirements</span></span>  
 <span data-ttu-id="a2feb-112">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2feb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2feb-113">**Üst bilgi:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a2feb-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a2feb-114">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2feb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2feb-115">**.NET framework sürümleri:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2feb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2feb-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="a2feb-116">See also</span></span>

- [<span data-ttu-id="a2feb-117">ICorProfilerCallback Arabirimi</span><span class="sxs-lookup"><span data-stu-id="a2feb-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="a2feb-118">ICorProfilerCallback4 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="a2feb-118">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [<span data-ttu-id="a2feb-119">JITCompilationStarted Yöntemi</span><span class="sxs-lookup"><span data-stu-id="a2feb-119">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
- [<span data-ttu-id="a2feb-120">ReJITCompilationStarted Yöntemi</span><span class="sxs-lookup"><span data-stu-id="a2feb-120">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
