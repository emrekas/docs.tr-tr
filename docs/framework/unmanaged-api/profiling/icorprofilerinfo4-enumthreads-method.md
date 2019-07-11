---
title: ICorProfilerInfo4::EnumThreads Yöntemi
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.EnumThreads
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumThreads
helpviewer_keywords:
- ICorProfilerInfo4::EnumThreads method [.NET Framework profiling]
- EnumThreads method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: bca7a5b4-c207-4894-918c-0733926296dd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d4cffc7c407db6acd15462e1e00769101e44b40
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780863"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="3e560-102">ICorProfilerInfo4::EnumThreads Yöntemi</span><span class="sxs-lookup"><span data-stu-id="3e560-102">ICorProfilerInfo4::EnumThreads Method</span></span>
<span data-ttu-id="3e560-103">Profili oluşturulan işlemdeki tüm yönetilen iş parçacıkları koleksiyonu sırayla yinelemek için yöntemler sağlayan bir numaralandırıcı döndürür.</span><span class="sxs-lookup"><span data-stu-id="3e560-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e560-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="3e560-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e560-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="3e560-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="3e560-106">[out] Bir işaretçi bir [Icorprofilerthreadenum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) arabirimi.</span><span class="sxs-lookup"><span data-stu-id="3e560-106">[out] A pointer to an [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e560-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="3e560-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e560-108">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="3e560-108">Requirements</span></span>  
 <span data-ttu-id="3e560-109">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e560-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e560-110">**Üst bilgi:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3e560-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3e560-111">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e560-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e560-112">**.NET framework sürümleri:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e560-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e560-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="3e560-113">See also</span></span>

- [<span data-ttu-id="3e560-114">ICorProfilerThreadEnum Arabirimi</span><span class="sxs-lookup"><span data-stu-id="3e560-114">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="3e560-115">ICorProfilerInfo4 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="3e560-115">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="3e560-116">Profil Oluşturma Arabirimleri</span><span class="sxs-lookup"><span data-stu-id="3e560-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="3e560-117">Profil Oluşturma</span><span class="sxs-lookup"><span data-stu-id="3e560-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
