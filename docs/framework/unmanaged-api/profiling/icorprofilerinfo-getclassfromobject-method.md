---
title: ICorProfilerInfo::GetClassFromObject Metodu
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromObject
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromObject
helpviewer_keywords:
- GetClassFromObject method [.NET Framework profiling]
- ICorProfilerInfo::GetClassFromObject method [.NET Framework profiling]
ms.assetid: b97493fb-713e-49d5-a73e-5688b2ad0700
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 57f57d67c4f7641495feca0b9c128e6ccf456cab
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780206"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="b6639-102">ICorProfilerInfo::GetClassFromObject Metodu</span><span class="sxs-lookup"><span data-stu-id="b6639-102">ICorProfilerInfo::GetClassFromObject Method</span></span>
<span data-ttu-id="b6639-103">Alır `ClassID` verilen bir nesnenin kendi `ObjectID`.</span><span class="sxs-lookup"><span data-stu-id="b6639-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6639-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="b6639-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6639-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="b6639-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="b6639-106">[in] Alınacağı nesnesinin Kimliğini `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="b6639-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="b6639-107">[out] Döndürülen işaretçi `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="b6639-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6639-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="b6639-108">Remarks</span></span>  
 <span data-ttu-id="b6639-109">Bir null `pClassId` belirten `objectId` kaldırılıyor türüne sahip.</span><span class="sxs-lookup"><span data-stu-id="b6639-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6639-110">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="b6639-110">Requirements</span></span>  
 <span data-ttu-id="b6639-111">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6639-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6639-112">**Üst bilgi:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b6639-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b6639-113">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6639-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6639-114">**.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6639-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6639-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="b6639-115">See also</span></span>

- [<span data-ttu-id="b6639-116">ICorProfilerInfo Arabirimi</span><span class="sxs-lookup"><span data-stu-id="b6639-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
