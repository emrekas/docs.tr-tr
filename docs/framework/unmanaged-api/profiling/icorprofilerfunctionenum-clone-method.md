---
title: ICorProfilerFunctionEnum::Clone Yöntemi
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Clone
helpviewer_keywords:
- ICorProfilerFunctionEnum::Clone method [.NET Framework profiling]
- Clone method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0c3d4835-e111-4e82-af6d-53f140b8f2c9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ded15608337d040ab58cb5be45deac4711668ac3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576180"
---
# <a name="icorprofilerfunctionenumclone-method"></a><span data-ttu-id="c9997-102">ICorProfilerFunctionEnum::Clone Yöntemi</span><span class="sxs-lookup"><span data-stu-id="c9997-102">ICorProfilerFunctionEnum::Clone Method</span></span>
<span data-ttu-id="c9997-103">Bu bir kopyasını bir arabirim işaretçisi alır [Icorprofilerfunctionenum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) arabirimi.</span><span class="sxs-lookup"><span data-stu-id="c9997-103">Gets an interface pointer to a copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9997-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="c9997-104">Syntax</span></span>  
  
```  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c9997-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="c9997-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="c9997-106">[out] Sırayla bu kopyasını işaret eden bir arabirim işaretçisi için bir işaretçi [Icorprofilerfunctionenum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) arabirimi.</span><span class="sxs-lookup"><span data-stu-id="c9997-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span> <span data-ttu-id="c9997-107">Numaralandırıcı kopyasını, bu Numaralandırıcının listesinden kendi sıralaması durumu korur.</span><span class="sxs-lookup"><span data-stu-id="c9997-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="c9997-108">Ancak, kopyanın ilk imleç konumu bu Numaralandırıcının geçerli imleç konumu aynıdır.</span><span class="sxs-lookup"><span data-stu-id="c9997-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9997-109">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="c9997-109">Requirements</span></span>  
 <span data-ttu-id="c9997-110">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9997-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9997-111">**Üst bilgi:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c9997-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c9997-112">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9997-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9997-113">**.NET framework sürümleri:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9997-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9997-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="c9997-114">See also</span></span>
- [<span data-ttu-id="c9997-115">ICorProfilerFunctionEnum Arabirimi</span><span class="sxs-lookup"><span data-stu-id="c9997-115">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="c9997-116">Profil Oluşturma Arabirimleri</span><span class="sxs-lookup"><span data-stu-id="c9997-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
