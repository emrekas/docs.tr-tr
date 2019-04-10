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
ms.openlocfilehash: db1b19c1499f7e8a126933b4d0635a0ab73e72a8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218595"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="88fef-102">ICorConfiguration::AddDebuggerSpecialThread Yöntemi</span><span class="sxs-lookup"><span data-stu-id="88fef-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="88fef-103">Hata Ayıklama Hizmetleri için hata ayıklayıcı durduruldu sırasında yönetilen veya yönetilmeyen hata ayıklama senaryoları uygulama varken yürütme devam etmek için belirli bir iş parçacığına izin verileceğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="88fef-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88fef-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="88fef-104">Syntax</span></span>  
  
```  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88fef-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="88fef-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="88fef-106">[in] Yürütmeye devam izin verilmesi iş parçacığı kimliği.</span><span class="sxs-lookup"><span data-stu-id="88fef-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88fef-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="88fef-107">Remarks</span></span>  
 <span data-ttu-id="88fef-108">Belirtilen iş parçacığı herhangi bir şekilde çalışma zamanı girmek veya yönetilen kodu çalıştırmak için izin verilmiyor.</span><span class="sxs-lookup"><span data-stu-id="88fef-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="88fef-109">Böyle bir iş parçacığı örneği, eski kod hata ayıklayıcıları desteklemek için bir işlemdeki iş parçacığı olacaktır.</span><span class="sxs-lookup"><span data-stu-id="88fef-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88fef-110">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="88fef-110">Requirements</span></span>  
 <span data-ttu-id="88fef-111">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88fef-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88fef-112">**Üst bilgi:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="88fef-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="88fef-113">**Kitaplığı:** Bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="88fef-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="88fef-114">.NET framework sürümleri:</span><span class="sxs-lookup"><span data-stu-id="88fef-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="88fef-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="88fef-115">See also</span></span>

- [<span data-ttu-id="88fef-116">ICorConfiguration Arabirimi</span><span class="sxs-lookup"><span data-stu-id="88fef-116">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
