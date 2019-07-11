---
title: ICLRGCManager2::SetGCStartupLimitsEx Yöntemi
ms.date: 03/30/2017
api_name:
- ICLRGCManager2.SetGCStartupLimitsEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2::SetCLRGCStartupLimitsEx
helpviewer_keywords:
- ICLRGCManager2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 6c3a08a9-5d65-48d4-8bbf-2a86ed7d356a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 356678afb537ab5e5e1653c4f71140ce704e55ef
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779679"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="3fd27-102">ICLRGCManager2::SetGCStartupLimitsEx Yöntemi</span><span class="sxs-lookup"><span data-stu-id="3fd27-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="3fd27-103">Bir çöp toplama kesim boyutunu ve çöp toplama sistemin nesil 0 en büyük boyutunu ayarlar.</span><span class="sxs-lookup"><span data-stu-id="3fd27-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fd27-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="3fd27-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,   
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3fd27-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="3fd27-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="3fd27-106">[in] Bir çöp toplama kesim belirtilen boyutu.</span><span class="sxs-lookup"><span data-stu-id="3fd27-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="3fd27-107">En düşük kesim boyutu 4 MB'dir.</span><span class="sxs-lookup"><span data-stu-id="3fd27-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="3fd27-108">Parçaları, 1 MB'lık artışlarla daha yüksek veya daha büyük olabilir.</span><span class="sxs-lookup"><span data-stu-id="3fd27-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="3fd27-109">[in] Nesil 0 için belirtilen en büyük boyutu.</span><span class="sxs-lookup"><span data-stu-id="3fd27-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="3fd27-110">En düşük nesil 0, 64 KB büyüklüğünde.</span><span class="sxs-lookup"><span data-stu-id="3fd27-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3fd27-111">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="3fd27-111">Return Value</span></span>  
  
|<span data-ttu-id="3fd27-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3fd27-112">HRESULT</span></span>|<span data-ttu-id="3fd27-113">Açıklama</span><span class="sxs-lookup"><span data-stu-id="3fd27-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3fd27-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="3fd27-114">S_OK</span></span>|<span data-ttu-id="3fd27-115">`SetGCStartupLimitsEx` başarıyla döndürüldü.</span><span class="sxs-lookup"><span data-stu-id="3fd27-115">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="3fd27-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3fd27-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3fd27-117">Ortak dil çalışma zamanı (CLR) işlem içine yüklenmemiş olan veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı şekilde işleme bir durumda değil.</span><span class="sxs-lookup"><span data-stu-id="3fd27-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3fd27-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3fd27-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3fd27-119">Arama zaman aşımına uğradı.</span><span class="sxs-lookup"><span data-stu-id="3fd27-119">The call timed out.</span></span>|  
|<span data-ttu-id="3fd27-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3fd27-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3fd27-121">Arayan bir kilide sahip değil.</span><span class="sxs-lookup"><span data-stu-id="3fd27-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3fd27-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3fd27-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3fd27-123">Bir olay engellenen bir iş parçacığı iptal edildi veya fiber üzerinde bekleme süresi.</span><span class="sxs-lookup"><span data-stu-id="3fd27-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3fd27-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3fd27-124">E_FAIL</span></span>|<span data-ttu-id="3fd27-125">Bilinmeyen geri dönülemez bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="3fd27-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3fd27-126">CLR, artık E_FAIL bir yöntemin dönüşünün ardından, işlem içinde kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="3fd27-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3fd27-127">Yöntemleri barındırma yapılan sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.</span><span class="sxs-lookup"><span data-stu-id="3fd27-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fd27-128">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="3fd27-128">Remarks</span></span>  
 <span data-ttu-id="3fd27-129">Değerleri, `SetGCStartupLimitsEx` kümeleri yalnızca ana bilgisayar başlatılmadan önce belirtilebilir.</span><span class="sxs-lookup"><span data-stu-id="3fd27-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="3fd27-130">Sonraki çağrılar `SetGCStartupLimitsEx` göz ardı edilir.</span><span class="sxs-lookup"><span data-stu-id="3fd27-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="3fd27-131">Her iki parametre, diğer planı etkilemeden ayarlamak için değiştirmek istemiyorsanız parametresi için 0 (sıfır) belirtin.</span><span class="sxs-lookup"><span data-stu-id="3fd27-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fd27-132">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="3fd27-132">Requirements</span></span>  
 <span data-ttu-id="3fd27-133">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fd27-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fd27-134">**Üst bilgi:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3fd27-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3fd27-135">**Kitaplığı:** Bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="3fd27-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3fd27-136">**.NET framework sürümleri:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fd27-136">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fd27-137">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="3fd27-137">See also</span></span>

- [<span data-ttu-id="3fd27-138">Otomatik Bellek Yönetimi</span><span class="sxs-lookup"><span data-stu-id="3fd27-138">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="3fd27-139">Atık Toplama</span><span class="sxs-lookup"><span data-stu-id="3fd27-139">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
- [<span data-ttu-id="3fd27-140">ICLRControl Arabirimi</span><span class="sxs-lookup"><span data-stu-id="3fd27-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="3fd27-141">ICLRGCManager2 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="3fd27-141">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
