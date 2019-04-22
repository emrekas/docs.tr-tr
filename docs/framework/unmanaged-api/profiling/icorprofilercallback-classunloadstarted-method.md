---
title: ICorProfilerCallback::ClassUnloadStarted Yöntemi
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadStarted
helpviewer_keywords:
- ClassUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ClassUnloadStarted method [.NET Framework profiling]
ms.assetid: bc93bead-f3a9-415c-b919-ddd3ca80facc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0707351d28ef75083b7bfb6ded38bc2a8460131
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136220"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="c5098-102">ICorProfilerCallback::ClassUnloadStarted Yöntemi</span><span class="sxs-lookup"><span data-stu-id="c5098-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="c5098-103">Profil Oluşturucu, bir sınıf boşaltılıyor bildirir.</span><span class="sxs-lookup"><span data-stu-id="c5098-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5098-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="c5098-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5098-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="c5098-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="c5098-106">[in] Boşaltılıyor sınıfı tanımlar.</span><span class="sxs-lookup"><span data-stu-id="c5098-106">[in] Identifies the class that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5098-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c5098-107">Remarks</span></span>  
 <span data-ttu-id="c5098-108">Değerini `classId` sonra bir bilgi isteği için geçerli değil `ClassUnloadStarted` yöntemi döndürür; Bu sınıf hakkında bilgi edinmek için profil oluşturucunun son şans budur.</span><span class="sxs-lookup"><span data-stu-id="c5098-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5098-109">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="c5098-109">Requirements</span></span>  
 <span data-ttu-id="c5098-110">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5098-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5098-111">**Üst bilgi:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c5098-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c5098-112">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5098-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5098-113">**.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5098-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5098-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="c5098-114">See also</span></span>

- [<span data-ttu-id="c5098-115">ICorProfilerCallback Arabirimi</span><span class="sxs-lookup"><span data-stu-id="c5098-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="c5098-116">ClassUnloadFinished Yöntemi</span><span class="sxs-lookup"><span data-stu-id="c5098-116">ClassUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)
