---
title: ICorDebugManagedCallback::UnloadModule Yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadModule
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadModule method [.NET Framework debugging]
- UnloadModule method [.NET Framework debugging]
ms.assetid: b12bfcd9-1e29-48bf-9a3d-44bfae5df5e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12e42da015864e83663d2f4d74bab2a34052d760
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995091"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="b3267-102">ICorDebugManagedCallback::UnloadModule Yöntemi</span><span class="sxs-lookup"><span data-stu-id="b3267-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="b3267-103">Hata ayıklayıcı Ortak Dil Çalışma Zamanı Modülü (DLL) kaldırıldı bildirir.</span><span class="sxs-lookup"><span data-stu-id="b3267-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3267-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="b3267-104">Syntax</span></span>  
  
```  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3267-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="b3267-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="b3267-106">[in] Modül bulunan uygulama etki alanı temsil eden bir Icordebugappdomain nesne işaretçisi.</span><span class="sxs-lookup"><span data-stu-id="b3267-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="b3267-107">[in] Bir modülü temsil eden bir Icordebugmodule nesne işaretçisi.</span><span class="sxs-lookup"><span data-stu-id="b3267-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3267-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="b3267-108">Remarks</span></span>  
 <span data-ttu-id="b3267-109">Modül, bu çağrıdan sonra kullanılmamalıdır.</span><span class="sxs-lookup"><span data-stu-id="b3267-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3267-110">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="b3267-110">Requirements</span></span>  
 <span data-ttu-id="b3267-111">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3267-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3267-112">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b3267-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b3267-113">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3267-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3267-114">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3267-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3267-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="b3267-115">See also</span></span>

- [<span data-ttu-id="b3267-116">LoadModule Yöntemi</span><span class="sxs-lookup"><span data-stu-id="b3267-116">LoadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)
- [<span data-ttu-id="b3267-117">ICorDebugManagedCallback Arabirimi</span><span class="sxs-lookup"><span data-stu-id="b3267-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
