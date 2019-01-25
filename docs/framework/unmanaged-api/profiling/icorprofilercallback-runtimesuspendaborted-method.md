---
title: ICorProfilerCallback::RuntimeSuspendAborted Yöntemi
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendAborted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted method [.NET Framework profiling]
- RuntimeSuspendAborted method [.NET Framework profiling]
ms.assetid: 5a8a4277-345b-448b-a028-fc8cff9998aa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 63d03e83e1688979e4fffe5d31d1f3c393f60e44
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573589"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="043c8-102">ICorProfilerCallback::RuntimeSuspendAborted Yöntemi</span><span class="sxs-lookup"><span data-stu-id="043c8-102">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>
<span data-ttu-id="043c8-103">Profil Oluşturucu çalışma zamanı oluşan çalışma zamanı askıya alınması iptal edildiğini bildirir.</span><span class="sxs-lookup"><span data-stu-id="043c8-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="043c8-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="043c8-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="043c8-105">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="043c8-105">Remarks</span></span>  
 <span data-ttu-id="043c8-106">Çalışma zamanı askıya almak iki iş parçacığı aynı anda denerseniz çalışma zamanı askıya alınması iptal.</span><span class="sxs-lookup"><span data-stu-id="043c8-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="043c8-107">Her iki [Icorprofilercallback::runtimesuspendfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) geri çağırma veya `RuntimeSuspendAborted` geri çağırma bir tek iş parçacığı şu oluşacak bir [Icorprofilercallback::runtimesuspendstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) geri çağırma.</span><span class="sxs-lookup"><span data-stu-id="043c8-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="043c8-108">`RuntimeSuspendAborted` Aynı iş parçacığı üzerinde gerçekleşmesi için geri çağırma garantisi `RuntimeSuspendStarted` geri çağırma.</span><span class="sxs-lookup"><span data-stu-id="043c8-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="043c8-109">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="043c8-109">Requirements</span></span>  
 <span data-ttu-id="043c8-110">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="043c8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="043c8-111">**Üst bilgi:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="043c8-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="043c8-112">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="043c8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="043c8-113">**.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="043c8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="043c8-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="043c8-114">See also</span></span>
- [<span data-ttu-id="043c8-115">ICorProfilerCallback Arabirimi</span><span class="sxs-lookup"><span data-stu-id="043c8-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
