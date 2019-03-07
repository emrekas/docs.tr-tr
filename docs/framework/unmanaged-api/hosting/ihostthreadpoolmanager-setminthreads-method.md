---
title: IHostThreadPoolManager::SetMinThreads Yöntemi
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.SetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: 10409db9-9fd2-4e4d-b8cd-cf6fec0afaa2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed172ca9f10e941938ae43bd730a3fc6d658aca2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484647"
---
# <a name="ihostthreadpoolmanagersetminthreads-method"></a><span data-ttu-id="854ec-102">IHostThreadPoolManager::SetMinThreads Yöntemi</span><span class="sxs-lookup"><span data-stu-id="854ec-102">IHostThreadPoolManager::SetMinThreads Method</span></span>
<span data-ttu-id="854ec-103">En az sayıda konak korumalıdır boşta iş parçacıkları istekleri olasılığına ayarlar.</span><span class="sxs-lookup"><span data-stu-id="854ec-103">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="854ec-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="854ec-104">Syntax</span></span>  
  
```  
HRESULT SetMinThreads (  
    [in] DWORD MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="854ec-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="854ec-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="854ec-106">[in] Yeni en düşük, konak korumalıdır iş parçacığı sayısı.</span><span class="sxs-lookup"><span data-stu-id="854ec-106">[in] The new minimum number of threads that the host must maintain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="854ec-107">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="854ec-107">Return Value</span></span>  
  
|<span data-ttu-id="854ec-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="854ec-108">HRESULT</span></span>|<span data-ttu-id="854ec-109">Açıklama</span><span class="sxs-lookup"><span data-stu-id="854ec-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="854ec-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="854ec-110">S_OK</span></span>|<span data-ttu-id="854ec-111">`SetMinThreads` başarıyla döndürüldü.</span><span class="sxs-lookup"><span data-stu-id="854ec-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="854ec-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="854ec-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="854ec-113">Ortak dil çalışma zamanı (CLR) işlem içine yüklenmemiş olan veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı şekilde işleme bir durumda değil.</span><span class="sxs-lookup"><span data-stu-id="854ec-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="854ec-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="854ec-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="854ec-115">Arama zaman aşımına uğradı.</span><span class="sxs-lookup"><span data-stu-id="854ec-115">The call timed out.</span></span>|  
|<span data-ttu-id="854ec-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="854ec-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="854ec-117">Arayan bir kilide sahip değil.</span><span class="sxs-lookup"><span data-stu-id="854ec-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="854ec-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="854ec-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="854ec-119">Bir olay engellenen bir iş parçacığı iptal edildi veya fiber üzerinde bekleme süresi.</span><span class="sxs-lookup"><span data-stu-id="854ec-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="854ec-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="854ec-120">E_FAIL</span></span>|<span data-ttu-id="854ec-121">Bilinmeyen geri dönülemez bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="854ec-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="854ec-122">Bir yöntem E_FAIL döndüğünde, CLR artık işlem içinde kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="854ec-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="854ec-123">Yöntemleri barındırma yapılan sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.</span><span class="sxs-lookup"><span data-stu-id="854ec-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="854ec-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="854ec-124">E_NOTIMPL</span></span>|<span data-ttu-id="854ec-125">Ana bilgisayar uygulaması sağlamaz `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="854ec-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="854ec-126">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="854ec-126">Remarks</span></span>  
 <span data-ttu-id="854ec-127">Bir konağa bir uygulamasını sağlamak için gerekli olmayan `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="854ec-127">A host is not required to provide an implementation of `SetMinThreads`.</span></span> <span data-ttu-id="854ec-128">Bu durumda, bir E_NOTIMPL HRESULT değerini döndürmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="854ec-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="854ec-129">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="854ec-129">Requirements</span></span>  
 <span data-ttu-id="854ec-130">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="854ec-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="854ec-131">**Üst bilgi:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="854ec-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="854ec-132">**Kitaplığı:** Bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="854ec-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="854ec-133">**.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="854ec-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="854ec-134">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="854ec-134">See also</span></span>
- <xref:System.Threading.ThreadPool.SetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="854ec-135">GetMinThreads Yöntemi</span><span class="sxs-lookup"><span data-stu-id="854ec-135">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="854ec-136">SetMaxThreads Yöntemi</span><span class="sxs-lookup"><span data-stu-id="854ec-136">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="854ec-137">IHostThreadPoolManager Arabirimi</span><span class="sxs-lookup"><span data-stu-id="854ec-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
