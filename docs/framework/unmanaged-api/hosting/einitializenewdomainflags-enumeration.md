---
title: EInitializeNewDomainFlags Numaralandırması
ms.date: 03/30/2017
api_name:
- EInitializeNewDomainFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EInitializeNewDomainFlags
helpviewer_keywords:
- EInitializeNewDomainFlags enumeration [.NET Framework hosting]
ms.assetid: 3a120ab2-f5ef-4c9b-8595-d3ed7247c342
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 04b0d9989d66888c33de0359e4c93529fcfbf8d1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61628632"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="70216-102">EInitializeNewDomainFlags Numaralandırması</span><span class="sxs-lookup"><span data-stu-id="70216-102">EInitializeNewDomainFlags Enumeration</span></span>
<span data-ttu-id="70216-103">Çalışma zamanının bir uygulama etki alanının başlatma hakkında bilgi sağlamak konak sağlar.</span><span class="sxs-lookup"><span data-stu-id="70216-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70216-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="70216-104">Syntax</span></span>  
  
```  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="70216-105">Üyeler</span><span class="sxs-lookup"><span data-stu-id="70216-105">Members</span></span>  
  
|<span data-ttu-id="70216-106">Üye</span><span class="sxs-lookup"><span data-stu-id="70216-106">Member</span></span>|<span data-ttu-id="70216-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="70216-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="70216-108">Bayrak.</span><span class="sxs-lookup"><span data-stu-id="70216-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="70216-109">Konak güvenlik durumuna ilişkin uygulama etki alanında bir değişiklik değil, ortak dil çalışma zamanı (CLR) bildirir <xref:System.AppDomainManager.InitializeNewDomain%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="70216-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70216-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="70216-110">Remarks</span></span>  
 <span data-ttu-id="70216-111">[Iclrdomainmanager::setappdomainmanagertype](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) yöntemi türünde bir parametre alır `EInitializeNewDomainFlags`.</span><span class="sxs-lookup"><span data-stu-id="70216-111">The [ICLRDomainManager::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70216-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="70216-112">Requirements</span></span>  
 <span data-ttu-id="70216-113">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70216-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70216-114">**Üst bilgi:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="70216-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="70216-115">**Kitaplığı:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="70216-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="70216-116">**.NET framework sürümleri:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70216-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70216-117">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="70216-117">See also</span></span>

- [<span data-ttu-id="70216-118">Barındırma Sabit Listeleri</span><span class="sxs-lookup"><span data-stu-id="70216-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="70216-119">SetAppDomainManagerType Yöntemi</span><span class="sxs-lookup"><span data-stu-id="70216-119">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)
