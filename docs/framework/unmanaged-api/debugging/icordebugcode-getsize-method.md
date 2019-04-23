---
title: ICorDebugCode::GetSize Metodu
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetSize method [.NET Framework debugging]
ms.assetid: 115bc6de-f5e2-4e8e-bb38-c7cf54045434
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 678b7fbd595b1238b7025c22b0ed80b02ed4becd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085681"
---
# <a name="icordebugcodegetsize-method"></a><span data-ttu-id="196b5-102">ICorDebugCode::GetSize Metodu</span><span class="sxs-lookup"><span data-stu-id="196b5-102">ICorDebugCode::GetSize Method</span></span>
<span data-ttu-id="196b5-103">Bu "Icordebugcode" tarafından temsil edilen ikili kod bayt cinsinden boyutunu alır.</span><span class="sxs-lookup"><span data-stu-id="196b5-103">Gets the size, in bytes, of the binary code represented by this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="196b5-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="196b5-104">Syntax</span></span>  
  
```  
HRESULT GetSize (  
    [out] ULONG32    *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="196b5-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="196b5-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="196b5-106">[out] Bu kod boyutunu bayt cinsinden ikili bir işaretçiye `ICorDebugCode` nesnesini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="196b5-106">[out] A pointer to the size, in bytes, of the binary code that this `ICorDebugCode` object represents.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="196b5-107">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="196b5-107">Requirements</span></span>  
 <span data-ttu-id="196b5-108">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="196b5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="196b5-109">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="196b5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="196b5-110">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="196b5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="196b5-111">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="196b5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="196b5-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="196b5-112">See also</span></span>
