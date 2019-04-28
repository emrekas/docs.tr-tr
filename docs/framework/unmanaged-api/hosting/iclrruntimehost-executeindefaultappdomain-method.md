---
title: ICLRRuntimeHost::ExecuteInDefaultAppDomain Yöntemi
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain method [.NET Framework hosting]
- ExecuteInDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 30b5cf9a-a762-4bd4-be12-d6c1442b78b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1e6805dc67f7ec5ceb8c67d77462a0200b6c0317
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641430"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a><span data-ttu-id="9a46d-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain Yöntemi</span><span class="sxs-lookup"><span data-stu-id="9a46d-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain Method</span></span>
<span data-ttu-id="9a46d-103">Belirtilen yönetilen derlemede belirtilen türdeki belirtilen yöntemi çağırır.</span><span class="sxs-lookup"><span data-stu-id="9a46d-103">Calls the specified method of the specified type in the specified managed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a46d-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="9a46d-104">Syntax</span></span>  
  
```  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,   
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a46d-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="9a46d-105">Parameters</span></span>  
 `pwzAssemblyPath`  
 <span data-ttu-id="9a46d-106">[in] Yolu <xref:System.Reflection.Assembly> tanımlayan <xref:System.Type> olan yöntemdir çağrılacak.</span><span class="sxs-lookup"><span data-stu-id="9a46d-106">[in] The path to the <xref:System.Reflection.Assembly> that defines the <xref:System.Type> whose method is to be invoked.</span></span>  
  
 `pwzTypeName`  
 <span data-ttu-id="9a46d-107">[in] Adını <xref:System.Type> çağrılacak yöntem tanımlar.</span><span class="sxs-lookup"><span data-stu-id="9a46d-107">[in] The name of the <xref:System.Type> that defines the method to invoke.</span></span>  
  
 `pwzMethodName`  
 <span data-ttu-id="9a46d-108">[in] Çağrılacak yöntemin adı.</span><span class="sxs-lookup"><span data-stu-id="9a46d-108">[in] The name of the method to invoke.</span></span>  
  
 `pwzArgument`  
 <span data-ttu-id="9a46d-109">[in] Yönteme dize parametresi.</span><span class="sxs-lookup"><span data-stu-id="9a46d-109">[in] The string parameter to pass to the method.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="9a46d-110">[out] Çağrılan yöntem tarafından döndürülen tamsayı değeri.</span><span class="sxs-lookup"><span data-stu-id="9a46d-110">[out] The integer value returned by the invoked method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a46d-111">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="9a46d-111">Return Value</span></span>  
  
|<span data-ttu-id="9a46d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9a46d-112">HRESULT</span></span>|<span data-ttu-id="9a46d-113">Açıklama</span><span class="sxs-lookup"><span data-stu-id="9a46d-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9a46d-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="9a46d-114">S_OK</span></span>|<span data-ttu-id="9a46d-115">`ExecuteInDefaultAppDomain` başarıyla döndürüldü.</span><span class="sxs-lookup"><span data-stu-id="9a46d-115">`ExecuteInDefaultAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="9a46d-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9a46d-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9a46d-117">Ortak dil çalışma zamanı (CLR) işlem içine yüklenmemiş olan veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı şekilde işleme bir durumda değil.</span><span class="sxs-lookup"><span data-stu-id="9a46d-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9a46d-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9a46d-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9a46d-119">Arama zaman aşımına uğradı.</span><span class="sxs-lookup"><span data-stu-id="9a46d-119">The call timed out.</span></span>|  
|<span data-ttu-id="9a46d-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9a46d-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9a46d-121">Arayan bir kilide sahip değil.</span><span class="sxs-lookup"><span data-stu-id="9a46d-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9a46d-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9a46d-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9a46d-123">Bir olay engellenen bir iş parçacığı iptal edildi veya fiber üzerinde bekleme süresi.</span><span class="sxs-lookup"><span data-stu-id="9a46d-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9a46d-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9a46d-124">E_FAIL</span></span>|<span data-ttu-id="9a46d-125">Bilinmeyen geri dönülemez bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="9a46d-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9a46d-126">Bir yöntem E_FAIL döndürürse, CRL artık işlem içinde kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="9a46d-126">If a method returns E_FAIL, the CRL is no longer usable within the process.</span></span> <span data-ttu-id="9a46d-127">Yöntemleri barındırma yapılan sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.</span><span class="sxs-lookup"><span data-stu-id="9a46d-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a46d-128">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="9a46d-128">Remarks</span></span>  
 <span data-ttu-id="9a46d-129">Çağrılan yöntemi aşağıdaki imzası sahip olmanız gerekir:</span><span class="sxs-lookup"><span data-stu-id="9a46d-129">The invoked method must have the following signature:</span></span>  
  
```  
static int pwzMethodName (String pwzArgument)  
```  
  
 <span data-ttu-id="9a46d-130">Burada `pwzMethodName` çağrılan yöntemin adını temsil eder ve `pwzArgument` dize değeri, yöntem için parametre olarak geçen temsil eder.</span><span class="sxs-lookup"><span data-stu-id="9a46d-130">where `pwzMethodName` represents the name of the invoked method, and `pwzArgument` represents the string value passed as a parameter to that method.</span></span> <span data-ttu-id="9a46d-131">S_OK için HRESULT değerini ayarlarsanız `pReturnValue` çağrılan yöntem tarafından döndürülen tamsayı değerine ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="9a46d-131">If the HRESULT value is set to S_OK, `pReturnValue` is set to the integer value returned by the invoked method.</span></span> <span data-ttu-id="9a46d-132">Aksi takdirde, `pReturnValue` ayarlı değil.</span><span class="sxs-lookup"><span data-stu-id="9a46d-132">Otherwise, `pReturnValue` is not set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a46d-133">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="9a46d-133">Requirements</span></span>  
 <span data-ttu-id="9a46d-134">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a46d-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a46d-135">**Üst bilgi:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9a46d-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9a46d-136">**Kitaplığı:** Bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="9a46d-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a46d-137">**.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a46d-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a46d-138">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="9a46d-138">See also</span></span>

- [<span data-ttu-id="9a46d-139">ICLRRuntimeHost Arabirimi</span><span class="sxs-lookup"><span data-stu-id="9a46d-139">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
