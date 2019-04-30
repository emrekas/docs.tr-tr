---
title: ICorDebugHeapEnum::Next Yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum::Next
helpviewer_keywords:
- ICorDebugHeapEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 2221fd06-9e27-4113-972e-2530db8c3594
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bd993eb26f26818117a20d376c3331f88c46b26
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61780907"
---
# <a name="icordebugheapenumnext-method"></a><span data-ttu-id="9473a-102">ICorDebugHeapEnum::Next Yöntemi</span><span class="sxs-lookup"><span data-stu-id="9473a-102">ICorDebugHeapEnum::Next Method</span></span>
<span data-ttu-id="9473a-103">Belirtilen sayıda alır [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) yönetilen yığındaki nesneler hakkında bilgi içeren örnekleri.</span><span class="sxs-lookup"><span data-stu-id="9473a-103">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9473a-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="9473a-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9473a-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="9473a-105">Parameters</span></span>  
 <span data-ttu-id="9473a-106">celt</span><span class="sxs-lookup"><span data-stu-id="9473a-106">celt</span></span>  
 <span data-ttu-id="9473a-107">[in] Alınacak nesne sayısı.</span><span class="sxs-lookup"><span data-stu-id="9473a-107">[in] The number of objects to be retrieved.</span></span>  
  
 <span data-ttu-id="9473a-108"> nesneleri</span><span class="sxs-lookup"><span data-stu-id="9473a-108">objects</span></span>  
 <span data-ttu-id="9473a-109">[out] Bir dizi işaretçileri, her biri için işaret eden bir [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) yönetilen yığındaki bir nesneyle ilgili bilgileri sağlayan nesne.</span><span class="sxs-lookup"><span data-stu-id="9473a-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) object that provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="9473a-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="9473a-110">pceltFetched</span></span>  
 <span data-ttu-id="9473a-111">[out] Bir işaretçi sayısına [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) gerçekte döndürülen nesneleri `objects`.</span><span class="sxs-lookup"><span data-stu-id="9473a-111">[out] A pointer to the number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects actually returned in `objects`.</span></span> <span data-ttu-id="9473a-112">Bu değer olabilir `null` varsa `celt` 1'dir.</span><span class="sxs-lookup"><span data-stu-id="9473a-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9473a-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="9473a-113">Remarks</span></span>  
 <span data-ttu-id="9473a-114">`COR_HEAPOBJECT.type` Alanı, iç içe geçmiş bir başvuru sayılan COM arabirimi tanımlayıcısıdır.</span><span class="sxs-lookup"><span data-stu-id="9473a-114">The `COR_HEAPOBJECT.type` field is the identifier of a nested reference-counted COM interface.</span></span> <span data-ttu-id="9473a-115">Bu başvuru çağıran tarafından serbest bırakılması `ICorDebugHeapEnum::Next`.</span><span class="sxs-lookup"><span data-stu-id="9473a-115">This reference must be released by the caller of `ICorDebugHeapEnum::Next`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9473a-116">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="9473a-116">Requirements</span></span>  
 <span data-ttu-id="9473a-117">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9473a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9473a-118">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9473a-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9473a-119">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9473a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9473a-120">**.NET framework sürümleri:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9473a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9473a-121">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="9473a-121">See also</span></span>

- [<span data-ttu-id="9473a-122">ICorDebugHeapEnum Arabirimi</span><span class="sxs-lookup"><span data-stu-id="9473a-122">ICorDebugHeapEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)
- [<span data-ttu-id="9473a-123">Hata Ayıklama Arabirimleri</span><span class="sxs-lookup"><span data-stu-id="9473a-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
