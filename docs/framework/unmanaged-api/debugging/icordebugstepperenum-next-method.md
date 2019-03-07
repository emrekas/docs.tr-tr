---
title: ICorDebugStepperEnum::Next Yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugStepperEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepperEnum::Next
helpviewer_keywords:
- Next method, ICorDebugStepperEnum interface [.NET Framework debugging]
- ICorDebugStepperEnum::Next method [.NET Framework debugging]
ms.assetid: d0ea0f30-e8d2-48b0-8477-e1a029ceb4dd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ac3165ab17eb1b4bc55a4bee4d2d2b467f8aefe
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494603"
---
# <a name="icordebugstepperenumnext-method"></a><span data-ttu-id="22a05-102">ICorDebugStepperEnum::Next Yöntemi</span><span class="sxs-lookup"><span data-stu-id="22a05-102">ICorDebugStepperEnum::Next Method</span></span>
<span data-ttu-id="22a05-103">Geçerli konumunda başlayan bir numaralandırma ICorDebugStepper örneği belirtilen sayısını alır.</span><span class="sxs-lookup"><span data-stu-id="22a05-103">Gets the specified number of ICorDebugStepper instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22a05-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="22a05-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugStepper *steppers[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22a05-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="22a05-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="22a05-106">[in] Sayısını `ICorDebugStepper` alınacak örnekleri.</span><span class="sxs-lookup"><span data-stu-id="22a05-106">[in] The number of `ICorDebugStepper` instances to be retrieved.</span></span>  
  
 `steppers`  
 <span data-ttu-id="22a05-107">[out] Bir dizi işaretçileri, her biri için işaret eden bir `ICorDebugStepper` nesne.</span><span class="sxs-lookup"><span data-stu-id="22a05-107">[out] An array of pointers, each of which points to an `ICorDebugStepper` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="22a05-108">[out] İşaretçi sayısına `ICorDebugStepper` gerçekte döndürülen örnekleri.</span><span class="sxs-lookup"><span data-stu-id="22a05-108">[out] Pointer to the number of `ICorDebugStepper` instances actually returned.</span></span> <span data-ttu-id="22a05-109">Bu değer null olabilir, `celt` biridir.</span><span class="sxs-lookup"><span data-stu-id="22a05-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22a05-110">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="22a05-110">Requirements</span></span>  
 <span data-ttu-id="22a05-111">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22a05-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22a05-112">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22a05-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22a05-113">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22a05-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22a05-114">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22a05-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
