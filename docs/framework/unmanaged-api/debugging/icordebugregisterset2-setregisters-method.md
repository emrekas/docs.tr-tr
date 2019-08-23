---
title: ICorDebugRegisterSet2::SetRegisters Yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.SetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::SetRegisters
helpviewer_keywords:
- ICorDebugRegisterSet2::SetRegisters method [.NET Framework debugging]
- SetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: fe0ac7e7-c9e1-4ec1-9f4e-1c56d63d73ac
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3013a0bc0cdcfa0d714328bfe86a87f44a11e829
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935103"
---
# <a name="icordebugregisterset2setregisters-method"></a><span data-ttu-id="27d4a-102">ICorDebugRegisterSet2::SetRegisters Yöntemi</span><span class="sxs-lookup"><span data-stu-id="27d4a-102">ICorDebugRegisterSet2::SetRegisters Method</span></span>
<span data-ttu-id="27d4a-103">`SetRegisters`.NET Framework sürüm 2,0 ' de uygulanmıyor.</span><span class="sxs-lookup"><span data-stu-id="27d4a-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="27d4a-104">Bu yöntemi çağırmayın.</span><span class="sxs-lookup"><span data-stu-id="27d4a-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="27d4a-105">[ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) veya [ICorDebugNativeFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)gibi daha üst düzey işlemleri kullanın.</span><span class="sxs-lookup"><span data-stu-id="27d4a-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27d4a-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="27d4a-106">Syntax</span></span>  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="27d4a-107">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="27d4a-107">Requirements</span></span>  
 <span data-ttu-id="27d4a-108">**Platform** Bkz. [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27d4a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27d4a-109">**Üst bilgi** CorDebug. IDL, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="27d4a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27d4a-110">**Kitaplığı** Corguid. lib</span><span class="sxs-lookup"><span data-stu-id="27d4a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27d4a-111">**.NET Framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27d4a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27d4a-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="27d4a-112">See also</span></span>

- [<span data-ttu-id="27d4a-113">ICorDebugRegisterSet2 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="27d4a-113">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
- [<span data-ttu-id="27d4a-114">ICorDebugRegisterSet Arabirimi</span><span class="sxs-lookup"><span data-stu-id="27d4a-114">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
