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
ms.openlocfilehash: b4cd4f7e1b0737672f33bdd7fec4f7953e20593f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782817"
---
# <a name="icordebugregisterset2setregisters-method"></a><span data-ttu-id="dfe9c-102">ICorDebugRegisterSet2::SetRegisters Yöntemi</span><span class="sxs-lookup"><span data-stu-id="dfe9c-102">ICorDebugRegisterSet2::SetRegisters Method</span></span>
<span data-ttu-id="dfe9c-103">`SetRegisters` .NET Framework 2.0 sürümünde uygulanmadı.</span><span class="sxs-lookup"><span data-stu-id="dfe9c-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="dfe9c-104">Bu yöntemi çağırmanız gerekmez.</span><span class="sxs-lookup"><span data-stu-id="dfe9c-104">Do not call this method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dfe9c-105">Üst düzey işlemleri gibi kullanın [Icordebugılframe::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) veya [Icordebugnativeframe::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span><span class="sxs-lookup"><span data-stu-id="dfe9c-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfe9c-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="dfe9c-106">Syntax</span></span>  
  
```  
HRESULT SetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="dfe9c-107">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="dfe9c-107">Requirements</span></span>  
 <span data-ttu-id="dfe9c-108">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfe9c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfe9c-109">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dfe9c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dfe9c-110">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dfe9c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dfe9c-111">**.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfe9c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfe9c-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="dfe9c-112">See also</span></span>

- [<span data-ttu-id="dfe9c-113">ICorDebugRegisterSet2 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="dfe9c-113">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
- [<span data-ttu-id="dfe9c-114">ICorDebugRegisterSet Arabirimi</span><span class="sxs-lookup"><span data-stu-id="dfe9c-114">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
