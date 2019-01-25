---
title: ICorDebug::EnumerateProcesses Yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebug.EnumerateProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- EnumerateProcesses
helpviewer_keywords:
- EnumerateProcesses method [.NET Framework debugging]
- ICorDebug::EnumerateProcesses method [.NET Framework debugging]
ms.assetid: ba25d166-1d28-4f1d-aca2-de298bbca669
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 10741ef9d329986d869665ef3aae14196946bb22
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724427"
---
# <a name="icordebugenumerateprocesses-method"></a><span data-ttu-id="98c97-102">ICorDebug::EnumerateProcesses Yöntemi</span><span class="sxs-lookup"><span data-stu-id="98c97-102">ICorDebug::EnumerateProcesses Method</span></span>
<span data-ttu-id="98c97-103">Hatası ayıklanmakta işlemler için bir numaralandırıcı alır.</span><span class="sxs-lookup"><span data-stu-id="98c97-103">Gets an enumerator for the processes that are being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98c97-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="98c97-104">Syntax</span></span>  
  
```  
HRESULT EnumerateProcesses (  
    [out] ICorDebugProcessEnum      **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="98c97-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="98c97-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="98c97-106">Hataları ayıklanan işlemlerin Numaralandırıcı Icordebugprocessenum nesnenin adresi için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="98c97-106">A pointer to the address of an ICorDebugProcessEnum object that is the enumerator for the processes being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98c97-107">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="98c97-107">Requirements</span></span>  
 <span data-ttu-id="98c97-108">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98c97-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98c97-109">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98c97-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98c97-110">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98c97-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98c97-111">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98c97-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98c97-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="98c97-112">See also</span></span>
- [<span data-ttu-id="98c97-113">ICorDebug Arabirimi</span><span class="sxs-lookup"><span data-stu-id="98c97-113">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
