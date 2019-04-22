---
title: ICorPublishEnum::Skip Yöntemi
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Skip
helpviewer_keywords:
- ICorPublishEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 1680ec06-4ab0-447e-93ad-cdb8693fde5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a98892964eb21746580e9115f86fd1be0832d9f2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59082060"
---
# <a name="icorpublishenumskip-method"></a><span data-ttu-id="f8e81-102">ICorPublishEnum::Skip Yöntemi</span><span class="sxs-lookup"><span data-stu-id="f8e81-102">ICorPublishEnum::Skip Method</span></span>
<span data-ttu-id="f8e81-103">İmleci İleri numaralandırmada tarafından belirtilen sayıda öğeyi taşır.</span><span class="sxs-lookup"><span data-stu-id="f8e81-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8e81-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="f8e81-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8e81-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="f8e81-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="f8e81-106">[in] İmleç ilerlemek, öğe sayısı.</span><span class="sxs-lookup"><span data-stu-id="f8e81-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8e81-107">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="f8e81-107">Requirements</span></span>  
 <span data-ttu-id="f8e81-108">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8e81-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8e81-109">**Üst bilgi:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="f8e81-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="f8e81-110">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8e81-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8e81-111">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8e81-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8e81-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="f8e81-112">See also</span></span>

- [<span data-ttu-id="f8e81-113">ICorPublishEnum Arabirimi</span><span class="sxs-lookup"><span data-stu-id="f8e81-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
