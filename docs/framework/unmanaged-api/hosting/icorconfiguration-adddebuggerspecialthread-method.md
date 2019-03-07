---
title: ICorConfiguration::AddDebuggerSpecialThread Yöntemi
ms.date: 03/30/2017
api_name:
- ICorConfiguration.AddDebuggerSpecialThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AddDebuggerSpecialThread
helpviewer_keywords:
- AddDebuggerSpecialThread method [.NET Framework hosting]
- ICorConfiguration::AddDebuggerSpecialThread method [.NET Framework hosting]
ms.assetid: 1f1e3239-438e-4be9-a3bb-7d0722d3a76d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 067765fbf500b2d20d84273d8df70c8e05a6ddc4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485906"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="48dfc-102">ICorConfiguration::AddDebuggerSpecialThread Yöntemi</span><span class="sxs-lookup"><span data-stu-id="48dfc-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="48dfc-103">Hata Ayıklama Hizmetleri için hata ayıklayıcı durduruldu sırasında yönetilen veya yönetilmeyen hata ayıklama senaryoları uygulama varken yürütme devam etmek için belirli bir iş parçacığına izin verileceğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="48dfc-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48dfc-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="48dfc-104">Syntax</span></span>  
  
```  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48dfc-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="48dfc-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="48dfc-106">[in] Yürütmeye devam izin verilmesi iş parçacığı kimliği.</span><span class="sxs-lookup"><span data-stu-id="48dfc-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48dfc-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="48dfc-107">Remarks</span></span>  
 <span data-ttu-id="48dfc-108">Belirtilen iş parçacığı herhangi bir şekilde çalışma zamanı girmek veya yönetilen kodu çalıştırmak için izin verilmiyor.</span><span class="sxs-lookup"><span data-stu-id="48dfc-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="48dfc-109">Böyle bir iş parçacığı örneği, eski kod hata ayıklayıcıları desteklemek için bir işlemdeki iş parçacığı olacaktır.</span><span class="sxs-lookup"><span data-stu-id="48dfc-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48dfc-110">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="48dfc-110">Requirements</span></span>  
 <span data-ttu-id="48dfc-111">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48dfc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48dfc-112">**Üst bilgi:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="48dfc-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="48dfc-113">**Kitaplığı:** Bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="48dfc-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48dfc-114">**.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48dfc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48dfc-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="48dfc-115">See also</span></span>
- [<span data-ttu-id="48dfc-116">ICorConfiguration Arabirimi</span><span class="sxs-lookup"><span data-stu-id="48dfc-116">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
