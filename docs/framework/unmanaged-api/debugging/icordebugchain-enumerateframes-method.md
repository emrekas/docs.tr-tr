---
title: ICorDebugChain::EnumerateFrames Yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugChain.EnumerateFrames
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7568f8ca3b92ef465ab595348f68895f389d61e4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489715"
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="108de-102">ICorDebugChain::EnumerateFrames Yöntemi</span><span class="sxs-lookup"><span data-stu-id="108de-102">ICorDebugChain::EnumerateFrames Method</span></span>
<span data-ttu-id="108de-103">En son çerçeve ile başlayan zincirindeki tüm yönetilen yığın çerçevesi içeren bir numaralandırıcı alır.</span><span class="sxs-lookup"><span data-stu-id="108de-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="108de-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="108de-104">Syntax</span></span>  
  
```  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="108de-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="108de-105">Parameters</span></span>  
 `ppFrames`  
 <span data-ttu-id="108de-106">[out] Yığın çerçevesi için Numaralandırıcı Icordebugframeenum nesnenin adresi için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="108de-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="108de-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="108de-107">Remarks</span></span>  
 <span data-ttu-id="108de-108">Zinciri, iş parçacığı için fiziksel çağrı yığınını temsil eder.</span><span class="sxs-lookup"><span data-stu-id="108de-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="108de-109">`EnumerateFrames` Yöntemi yalnızca yönetilen zincirleri için çağrılabilir.</span><span class="sxs-lookup"><span data-stu-id="108de-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="108de-110">Hata ayıklama API yöntemleri yönetilmeyen zincirde bulunan çerçeveleri almak için sağlamaz.</span><span class="sxs-lookup"><span data-stu-id="108de-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="108de-111">Hata ayıklayıcı bu bilgiyi elde etmek için başka bir yolla kullanmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="108de-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="108de-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="108de-112">Requirements</span></span>  
 <span data-ttu-id="108de-113">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="108de-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="108de-114">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="108de-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="108de-115">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="108de-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="108de-116">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="108de-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
