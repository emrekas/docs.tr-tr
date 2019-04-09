---
title: IDebuggerThreadControl::StartBlockingForDebugger Yöntemi
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.StartBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StartBlockingForDebugger
helpviewer_keywords:
- IDebuggerThreadControl::StartBlockingForDebugger method [.NET Framework hosting]
- StartBlockingForDebugger method [.NET Framework hosting]
ms.assetid: 5c8f11b4-35d3-4c39-9bbd-58b896ba5ba6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dfc94c2de1a14842cc017e5c4ef6023154c20f2a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194038"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="6be34-102">IDebuggerThreadControl::StartBlockingForDebugger Yöntemi</span><span class="sxs-lookup"><span data-stu-id="6be34-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="6be34-103">Konak, hata ayıklama Hizmetleri tüm iş parçacıklarının engellemesini başlamak üzere olduğunu bildirir.</span><span class="sxs-lookup"><span data-stu-id="6be34-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6be34-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="6be34-104">Syntax</span></span>  
  
```  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6be34-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="6be34-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="6be34-106">[in] Gelecekte kullanılmak üzere ayrılmış.</span><span class="sxs-lookup"><span data-stu-id="6be34-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6be34-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="6be34-107">Remarks</span></span>  
 <span data-ttu-id="6be34-108">`StartBlockingForDebugger` Yöntemi bir çalışma zamanı iş parçacığında çağrıldı.</span><span class="sxs-lookup"><span data-stu-id="6be34-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6be34-109">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="6be34-109">Requirements</span></span>  
 <span data-ttu-id="6be34-110">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6be34-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6be34-111">**Üst bilgi:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6be34-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6be34-112">**Kitaplığı:** Bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="6be34-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="6be34-113">.NET framework sürümleri:</span><span class="sxs-lookup"><span data-stu-id="6be34-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6be34-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="6be34-114">See also</span></span>

- [<span data-ttu-id="6be34-115">IDebuggerThreadControl Arabirimi</span><span class="sxs-lookup"><span data-stu-id="6be34-115">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
