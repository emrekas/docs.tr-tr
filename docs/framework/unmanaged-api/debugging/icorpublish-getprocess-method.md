---
title: ICorPublish::GetProcess Yöntemi
ms.date: 03/30/2017
api_name:
- ICorPublish.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b2dcdaed34044122dd2a61c9e0b5bb02f8cc0d9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774276"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="a592b-102">ICorPublish::GetProcess Yöntemi</span><span class="sxs-lookup"><span data-stu-id="a592b-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="a592b-103">Alır bir [Icorpublishprocess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) belirtilen tanımlayıcıya sahip bir işlemi temsil eden örneği.</span><span class="sxs-lookup"><span data-stu-id="a592b-103">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a592b-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="a592b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,   
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a592b-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="a592b-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="a592b-106">[in] İşlem tanımlayıcısı.</span><span class="sxs-lookup"><span data-stu-id="a592b-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="a592b-107">[out] Adresine bir işaretçi bir `ICorPublishProcess` işlemini temsil eden örneği.</span><span class="sxs-lookup"><span data-stu-id="a592b-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a592b-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a592b-108">Remarks</span></span>  
 <span data-ttu-id="a592b-109">`GetProcess` işlem yok veya geçerli kullanıcı tarafından ayıklanabilir yönetilen bir işlem olmadığından başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="a592b-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a592b-110">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="a592b-110">Requirements</span></span>  
 <span data-ttu-id="a592b-111">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a592b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a592b-112">**Üst bilgi:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="a592b-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="a592b-113">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a592b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a592b-114">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a592b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a592b-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="a592b-115">See also</span></span>

- [<span data-ttu-id="a592b-116">ICorPublish Arabirimi</span><span class="sxs-lookup"><span data-stu-id="a592b-116">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
