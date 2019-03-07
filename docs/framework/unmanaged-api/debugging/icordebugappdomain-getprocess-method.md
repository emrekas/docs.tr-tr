---
title: ICorDebugAppDomain::GetProcess Metodu
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebugAppDomain interface [.NET Framework debugging]
- ICorDebugAppDomain::GetProcess method [.NET Framework debugging]
ms.assetid: 9d0b9628-a91c-40d0-b9bc-00b34a396b8f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b05c35c810630897e4a7bd28e1cbe8cedefefb1f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489374"
---
# <a name="icordebugappdomaingetprocess-method"></a><span data-ttu-id="8b1ae-102">ICorDebugAppDomain::GetProcess Metodu</span><span class="sxs-lookup"><span data-stu-id="8b1ae-102">ICorDebugAppDomain::GetProcess Method</span></span>
<span data-ttu-id="8b1ae-103">Uygulama etki alanını içeren işlemi alır.</span><span class="sxs-lookup"><span data-stu-id="8b1ae-103">Gets the process containing the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b1ae-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="8b1ae-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b1ae-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="8b1ae-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="8b1ae-106">[out] Bir işaretçi adresine Icordebugprocess nesnenin işlemi temsil eder.</span><span class="sxs-lookup"><span data-stu-id="8b1ae-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b1ae-107">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="8b1ae-107">Requirements</span></span>  
 <span data-ttu-id="8b1ae-108">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b1ae-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b1ae-109">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b1ae-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b1ae-110">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b1ae-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b1ae-111">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b1ae-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
