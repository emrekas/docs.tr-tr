---
title: EBindPolicyLevels Numaralandırması
ms.date: 03/30/2017
api_name:
- EBindPolicyLevels
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EBindPolicyLevels
helpviewer_keywords:
- EBindPolicyLevels enumeration [.NET Framework hosting]
ms.assetid: a9e00b4f-b6d0-4257-bd88-4fe9af97b8fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8f2b08662e719a3308a62ab5b60f5dc490f2a6a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985679"
---
# <a name="ebindpolicylevels-enumeration"></a><span data-ttu-id="cecd0-102">EBindPolicyLevels Numaralandırması</span><span class="sxs-lookup"><span data-stu-id="cecd0-102">EBindPolicyLevels Enumeration</span></span>
<span data-ttu-id="cecd0-103">Derleme ilkesini uygulamak veya değiştirmek istediğiniz düzeyinde belirtmek için bayrakları sağlar.</span><span class="sxs-lookup"><span data-stu-id="cecd0-103">Provides flags to specify the level at which to apply or modify assembly policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cecd0-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="cecd0-104">Syntax</span></span>  
  
```  
typedef enum {  
    ePolicyLevelNone         = 0x0,  
    ePolicyLevelRetargetable = 0x1,  
    ePolicyUnifiedToCLR      = 0x2,  
    ePolicyLevelApp          = 0x4,  
    ePolicyLevelPublisher    = 0x8,  
    ePolicyLevelHost         = 0x10,  
    ePolicyLevelAdmin        = 0x20  
    ePolicyPortability       = 0x40  
} EBindPolicyLevels;  
```  
  
## <a name="members"></a><span data-ttu-id="cecd0-105">Üyeler</span><span class="sxs-lookup"><span data-stu-id="cecd0-105">Members</span></span>  
  
|<span data-ttu-id="cecd0-106">Üye</span><span class="sxs-lookup"><span data-stu-id="cecd0-106">Member</span></span>|<span data-ttu-id="cecd0-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="cecd0-107">Description</span></span>|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|<span data-ttu-id="cecd0-108">İlke yönetici düzeyinde uygulanması gerektiğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="cecd0-108">Specifies that policy should be applied at the administrator level.</span></span>|  
|`ePolicyLevelApp`|<span data-ttu-id="cecd0-109">İlke uygulama düzeyinde uygulanması gerektiğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="cecd0-109">Specifies that policy should be applied at the application level.</span></span>|  
|`ePolicyLevelHost`|<span data-ttu-id="cecd0-110">İlkenin ana bilgisayar düzeyinde geçerli olduğunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="cecd0-110">Specifies that policy should be applied at the host level.</span></span>|  
|`ePolicyLevelNone`|<span data-ttu-id="cecd0-111">Hiçbir ilke düzeyi bayrakları belirtir.</span><span class="sxs-lookup"><span data-stu-id="cecd0-111">Specifies no policy-level flags.</span></span>|  
|`ePolicyLevelPublisher`|<span data-ttu-id="cecd0-112">İlke yayımcı düzeyinde uygulanması gerektiğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="cecd0-112">Specifies that policy should be applied at the publisher level.</span></span>|  
|`ePolicyLevelRetargetable`|<span data-ttu-id="cecd0-113">İlke değişken düzeylerinde uygulanabilir olacağını belirtir.</span><span class="sxs-lookup"><span data-stu-id="cecd0-113">Specifies that policy should be applicable at variable levels.</span></span>|  
|`ePolicyPortability`|<span data-ttu-id="cecd0-114">.NET Framework derlemesinin uygulamaları arasındaki taşınabilir destek ilkesi belirtir.</span><span class="sxs-lookup"><span data-stu-id="cecd0-114">Specifies that policy should support portability between implementations of a .NET Framework assembly.</span></span> <span data-ttu-id="cecd0-115">Bkz: [ \<supportPortability >](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) yapılandırma dosyası öğesi.</span><span class="sxs-lookup"><span data-stu-id="cecd0-115">See the [\<supportPortability>](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) configuration file element.</span></span>|  
|`ePolicyUnifiedToCLR`|<span data-ttu-id="cecd0-116">İlke, ortak dil çalışma zamanı (CLR) birleşik olduğunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="cecd0-116">Specifies that policy should be unified to that of the common language runtime (CLR).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cecd0-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="cecd0-117">Remarks</span></span>  
 <span data-ttu-id="cecd0-118">Bu numaralandırma yöntemlerini için geçirilen [Iclrhostbindingpolicymanager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) uygulama ilkesi değişiklikleri belirtmek için arabirim.</span><span class="sxs-lookup"><span data-stu-id="cecd0-118">This enumeration is passed to methods of the [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) interface to specify changes in application policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cecd0-119">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="cecd0-119">Requirements</span></span>  
 <span data-ttu-id="cecd0-120">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cecd0-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cecd0-121">**Üst bilgi:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cecd0-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cecd0-122">**Kitaplığı:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cecd0-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cecd0-123">**.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cecd0-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cecd0-124">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="cecd0-124">See also</span></span>

- [<span data-ttu-id="cecd0-125">ICLRAssemblyIdentityManager Arabirimi</span><span class="sxs-lookup"><span data-stu-id="cecd0-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="cecd0-126">Barındırma Sabit Listeleri</span><span class="sxs-lookup"><span data-stu-id="cecd0-126">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
