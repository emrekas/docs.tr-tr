---
title: IHostCrst::SetSpinCount Yöntemi
ms.date: 03/30/2017
api_name:
- IHostCrst.SetSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::SetSpinCount
helpviewer_keywords:
- IHostCrst::SetSpinCount method [.NET Framework hosting]
- SetSpinCount method [.NET Framework hosting]
ms.assetid: 863fc8ce-9b8a-477e-8dd8-75c8544bb43a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ddae8f64eca348afa337b986ac81d59c37e51701
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504307"
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="29ff5-102">IHostCrst::SetSpinCount Yöntemi</span><span class="sxs-lookup"><span data-stu-id="29ff5-102">IHostCrst::SetSpinCount Method</span></span>
<span data-ttu-id="29ff5-103">Döngü sayısı için geçerli ayarlar [Ihostcrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) örneği.</span><span class="sxs-lookup"><span data-stu-id="29ff5-103">Sets the spin count for the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29ff5-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="29ff5-104">Syntax</span></span>  
  
```  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="29ff5-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="29ff5-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="29ff5-106">[in] Yeni sayaç sayısı geçerli `IHostCrst` örneği.</span><span class="sxs-lookup"><span data-stu-id="29ff5-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="29ff5-107">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="29ff5-107">Return Value</span></span>  
  
|<span data-ttu-id="29ff5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="29ff5-108">HRESULT</span></span>|<span data-ttu-id="29ff5-109">Açıklama</span><span class="sxs-lookup"><span data-stu-id="29ff5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="29ff5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="29ff5-110">S_OK</span></span>|<span data-ttu-id="29ff5-111">`SetSpinCount` başarıyla döndürüldü.</span><span class="sxs-lookup"><span data-stu-id="29ff5-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="29ff5-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="29ff5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="29ff5-113">Ortak dil çalışma zamanı (CLR) işlem içine yüklenmemiş olan veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı şekilde işleme bir durumda değil.</span><span class="sxs-lookup"><span data-stu-id="29ff5-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="29ff5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="29ff5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="29ff5-115">Arama zaman aşımına uğradı.</span><span class="sxs-lookup"><span data-stu-id="29ff5-115">The call timed out.</span></span>|  
|<span data-ttu-id="29ff5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="29ff5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="29ff5-117">Arayan bir kilide sahip değil.</span><span class="sxs-lookup"><span data-stu-id="29ff5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="29ff5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="29ff5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="29ff5-119">Bir olay engellenen bir iş parçacığı iptal edildi veya fiber üzerinde bekleme süresi.</span><span class="sxs-lookup"><span data-stu-id="29ff5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="29ff5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="29ff5-120">E_FAIL</span></span>|<span data-ttu-id="29ff5-121">Bilinmeyen geri dönülemez bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="29ff5-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="29ff5-122">Bir yöntem E_FAIL döndüğünde, CLR artık işlem içinde kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="29ff5-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="29ff5-123">Yöntemleri barındırma yapılan sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.</span><span class="sxs-lookup"><span data-stu-id="29ff5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29ff5-124">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="29ff5-124">Remarks</span></span>  
 <span data-ttu-id="29ff5-125">Birden çok işlemcili sistemlerde, kritik bölüm geçerli tarafından temsil edilen `IHostCrst` örneği kullanılamıyorsa, çağıran iş parçacığı dönerek `dwSpinCount` çağırmadan önce kez [Ihostsemaphore::wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) ilişkili semafor üzerinde Kritik Bölümü.</span><span class="sxs-lookup"><span data-stu-id="29ff5-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="29ff5-126">Kritik bölüm döndürme işlemi sırasında boş hale gelirse, çağıran iş parçacığını bekleme işlemi önler.</span><span class="sxs-lookup"><span data-stu-id="29ff5-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="29ff5-127">Kullanımını `dwSpinCount` Win32'de aynı ada sahip parametre kullanımı aynıdır `InitializeCriticalSectionAndSpinCount` işlevi.</span><span class="sxs-lookup"><span data-stu-id="29ff5-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29ff5-128">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="29ff5-128">Requirements</span></span>  
 <span data-ttu-id="29ff5-129">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29ff5-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29ff5-130">**Üst bilgi:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="29ff5-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="29ff5-131">**Kitaplığı:** Bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="29ff5-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="29ff5-132">**.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29ff5-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29ff5-133">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="29ff5-133">See also</span></span>
- [<span data-ttu-id="29ff5-134">ICLRSyncManager Arabirimi</span><span class="sxs-lookup"><span data-stu-id="29ff5-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="29ff5-135">IHostCrst Arabirimi</span><span class="sxs-lookup"><span data-stu-id="29ff5-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="29ff5-136">IHostSyncManager Arabirimi</span><span class="sxs-lookup"><span data-stu-id="29ff5-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
