---
title: IcorDebugVariableHome::GetLiveRange yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLiveRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLiveRange
helpviewer_keywords:
- ICorDebugVariableHome::GetLiveRange method [.NET Framework debugging]
- GetLiveRange method, ICorDebugVariableFrame interface [.NET Framework debugging]
ms.assetid: 87277e1a-1595-4729-9e25-d1c3ac18ce5f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06c8ae378c10eda986740dfb73f3bf60ea8647a6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468851"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="fd224-102">IcorDebugVariableHome::GetLiveRange yöntemi</span><span class="sxs-lookup"><span data-stu-id="fd224-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="fd224-103">Bu değişken Canlı yerel aralığı alır.</span><span class="sxs-lookup"><span data-stu-id="fd224-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd224-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="fd224-104">Syntax</span></span>  
  
```  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd224-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="fd224-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="fd224-106">[out] Değişken Canlı ilk olduğu mantıksal uzaklığı.</span><span class="sxs-lookup"><span data-stu-id="fd224-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="fd224-107">[out] Hemen değişkeni Canlı son olduğu noktadan sonra mantıksal uzaklığı.</span><span class="sxs-lookup"><span data-stu-id="fd224-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd224-108">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="fd224-108">Requirements</span></span>  
 <span data-ttu-id="fd224-109">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd224-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd224-110">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd224-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd224-111">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd224-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd224-112">**.NET framework sürümleri:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd224-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd224-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="fd224-113">See also</span></span>
- [<span data-ttu-id="fd224-114">ICorDebugVariableHome Arabirimi</span><span class="sxs-lookup"><span data-stu-id="fd224-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
