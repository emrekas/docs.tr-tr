---
title: ICorDebugAppDomain::EnumerateBreakpoints Yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateBreakpoints
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints method [.NET Framework debugging]
- EnumerateBreakpoints method [.NET Framework debugging]
ms.assetid: 206069c5-25cb-4794-9d69-67c5aa7ed0af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b00afc900a27aea94389ee81065ea22ae359440d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498347"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="4894f-102">ICorDebugAppDomain::EnumerateBreakpoints Yöntemi</span><span class="sxs-lookup"><span data-stu-id="4894f-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>
<span data-ttu-id="4894f-103">Bir numaralandırıcı, uygulama etki alanı için tüm etkin kesme noktalarını alır.</span><span class="sxs-lookup"><span data-stu-id="4894f-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4894f-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="4894f-104">Syntax</span></span>  
  
```  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4894f-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="4894f-105">Parameters</span></span>  
 `ppBreakpoints`  
 <span data-ttu-id="4894f-106">[out] Icordebugbreakpointenum nesnenin uygulama etki alanındaki tüm etkin kesme noktaları için bir numaralandırıcı adresi için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="4894f-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4894f-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="4894f-107">Remarks</span></span>  
 <span data-ttu-id="4894f-108">Numaralandırıcı, kesme noktaları, işlev kesme noktaları ve veri kesme noktaları da dahil olmak üzere tüm türleri içerir.</span><span class="sxs-lookup"><span data-stu-id="4894f-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4894f-109">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="4894f-109">Requirements</span></span>  
 <span data-ttu-id="4894f-110">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4894f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4894f-111">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4894f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4894f-112">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4894f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4894f-113">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4894f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
