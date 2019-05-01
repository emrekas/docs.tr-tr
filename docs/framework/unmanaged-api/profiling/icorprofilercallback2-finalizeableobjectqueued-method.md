---
title: ICorProfilerCallback2::FinalizeableObjectQueued Yöntemi
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.FinalizeableObjectQueued
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::FinalizeableObjectQueued
helpviewer_keywords:
- FinalizeableObjectQueued method [.NET Framework profiling]
- ICorProfilerCallback2::FinalizeableObjectQueued method [.NET Framework profiling]
ms.assetid: 92d76893-683c-475d-9996-5bff03cdb10f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b99a942d5c5fb205a84dd3766c99cc1126998de8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61914439"
---
# <a name="icorprofilercallback2finalizeableobjectqueued-method"></a><span data-ttu-id="25f33-102">ICorProfilerCallback2::FinalizeableObjectQueued Yöntemi</span><span class="sxs-lookup"><span data-stu-id="25f33-102">ICorProfilerCallback2::FinalizeableObjectQueued Method</span></span>
<span data-ttu-id="25f33-103">Bir sonlandırıcı içeren bir nesne Sonlandırıcı iş parçacığı yürütülmesi için kuyruğa kod profil oluşturucu bildirir, `Finalize` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="25f33-103">Notifies the code profiler that an object with a finalizer has been queued to the finalizer thread for execution of its `Finalize` method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25f33-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="25f33-104">Syntax</span></span>  
  
```  
HRESULT FinalizeableObjectQueued(  
    [in] DWORD finalizerFlags,  
    [in] ObjectID objectID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25f33-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="25f33-105">Parameters</span></span>  
 `finalizerFlags`  
 <span data-ttu-id="25f33-106">[in] Değerini [cor_prf_fınalızer_flags](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md) Sonlandırıcı yönlerini açıklayan sabit listesi.</span><span class="sxs-lookup"><span data-stu-id="25f33-106">[in] A value of the [COR_PRF_FINALIZER_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md) enumeration that describes aspects of the finalizer.</span></span>  
  
 `objectID`  
 <span data-ttu-id="25f33-107">[in] Sıraya alınan nesnenin kimliği.</span><span class="sxs-lookup"><span data-stu-id="25f33-107">[in] The ID of the object that has been queued.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25f33-108">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="25f33-108">Requirements</span></span>  
 <span data-ttu-id="25f33-109">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25f33-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25f33-110">**Üst bilgi:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="25f33-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="25f33-111">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25f33-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25f33-112">**.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25f33-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25f33-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="25f33-113">See also</span></span>

- [<span data-ttu-id="25f33-114">ICorProfilerCallback Arabirimi</span><span class="sxs-lookup"><span data-stu-id="25f33-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="25f33-115">ICorProfilerCallback2 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="25f33-115">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
