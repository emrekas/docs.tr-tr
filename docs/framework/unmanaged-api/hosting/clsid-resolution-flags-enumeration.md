---
title: CLSID_RESOLUTION_FLAGS Numaralandırması
ms.date: 03/30/2017
api_name:
- CLSID_RESOLUTION_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLSID_RESOLUTION_FLAGS
helpviewer_keywords:
- CLSID_RESOLUTION_FLAGS enumeration [.NET Framework hosting]
ms.assetid: cd8b9879-962a-4811-aa46-2e2b6bae0d84
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36792d01ebdad72271a8b0597a33d83cab34780e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59114037"
---
# <a name="clsidresolutionflags-enumeration"></a><span data-ttu-id="0354f-102">CLSID_RESOLUTION_FLAGS Numaralandırması</span><span class="sxs-lookup"><span data-stu-id="0354f-102">CLSID_RESOLUTION_FLAGS Enumeration</span></span>
<span data-ttu-id="0354f-103">Ortak dil çalışma zamanı (CLR) nasıl çözümlenmelidir gösteren değerleri içeren bir `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="0354f-103">Contains values that indicate how the common language runtime (CLR) should resolve a `CLSID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0354f-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="0354f-104">Syntax</span></span>  
  
```  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="0354f-105">Üyeler</span><span class="sxs-lookup"><span data-stu-id="0354f-105">Members</span></span>  
  
|<span data-ttu-id="0354f-106">Üye</span><span class="sxs-lookup"><span data-stu-id="0354f-106">Member</span></span>|<span data-ttu-id="0354f-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0354f-107">Description</span></span>|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|<span data-ttu-id="0354f-108">Varsayılan davranış gösterir.</span><span class="sxs-lookup"><span data-stu-id="0354f-108">Indicates the default behavior.</span></span>|  
|`CLSID_RESOLUTION_REGISTERED`|<span data-ttu-id="0354f-109">Çalışma zamanı kayıt defteri arar ve dolgu ilkenin geçerli olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="0354f-109">Indicates that the runtime searches the registry and applies shim policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0354f-110">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="0354f-110">Requirements</span></span>  
 <span data-ttu-id="0354f-111">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0354f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0354f-112">**Üst bilgi:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0354f-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0354f-113">**.NET framework sürümleri:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0354f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0354f-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="0354f-114">See also</span></span>

- [<span data-ttu-id="0354f-115">Barındırma Sabit Listeleri</span><span class="sxs-lookup"><span data-stu-id="0354f-115">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
