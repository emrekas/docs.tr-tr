---
title: ICLRAssemblyIdentityManager::GetBindingIdentityFromFile Yöntemi
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
helpviewer_keywords:
- GetBindingIdentityFromFile method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentifyFromFile method [.NET Framework hosting]
ms.assetid: 7797562d-7b4c-4bd9-8b93-f35e0e2869e4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a3d5e53dd0845fbd01dbd9d20ce8feef12748c04
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213929"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a><span data-ttu-id="58cda-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile Yöntemi</span><span class="sxs-lookup"><span data-stu-id="58cda-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile Method</span></span>
<span data-ttu-id="58cda-103">Belirtilen dosya yolunda derleme için veri bağlama derleme kimliğini alır.</span><span class="sxs-lookup"><span data-stu-id="58cda-103">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58cda-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="58cda-104">Syntax</span></span>  
  
```  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58cda-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="58cda-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="58cda-106">[in] Değerlendirilecek dosyanın yolu.</span><span class="sxs-lookup"><span data-stu-id="58cda-106">[in] The path to the file to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="58cda-107">[in] Değerini [Eclrassemblyıdentityflags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) bir derlemenin kimlik türü belirten sabit listesi.</span><span class="sxs-lookup"><span data-stu-id="58cda-107">[in] A value of the [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) enumeration that indicates an assembly's identity type.</span></span> <span data-ttu-id="58cda-108">Sonra genişletilebilmek için sağlanır.</span><span class="sxs-lookup"><span data-stu-id="58cda-108">Provided for future extensibility.</span></span> <span data-ttu-id="58cda-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT ortak dil çalışma zamanı (CLR) sürüm 2. 0'ı destekleyen tek bir değerdir.</span><span class="sxs-lookup"><span data-stu-id="58cda-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the common language runtime (CLR) version 2.0 supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="58cda-110">[out] Donuk derleme kimlik verilerini içeren arabellek.</span><span class="sxs-lookup"><span data-stu-id="58cda-110">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="58cda-111">[out içinde] Bir işaretçinin boyutuna `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="58cda-111">[in, out] A pointer to the size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58cda-112">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="58cda-112">Return Value</span></span>  
  
|<span data-ttu-id="58cda-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="58cda-113">HRESULT</span></span>|<span data-ttu-id="58cda-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="58cda-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="58cda-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="58cda-115">S_OK</span></span>|<span data-ttu-id="58cda-116">Yöntemi başarıyla döndürüldü.</span><span class="sxs-lookup"><span data-stu-id="58cda-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="58cda-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="58cda-117">E_INVALIDARG</span></span>|<span data-ttu-id="58cda-118">Sağlanan `pwzFilePath` null.</span><span class="sxs-lookup"><span data-stu-id="58cda-118">The supplied `pwzFilePath` is null.</span></span>|  
|<span data-ttu-id="58cda-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="58cda-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="58cda-120">Boyutu `pwzBuffer` çok küçük.</span><span class="sxs-lookup"><span data-stu-id="58cda-120">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="58cda-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="58cda-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="58cda-122">CLR'yi bir işleme yüklü değil veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı şekilde işleme bir durumda.</span><span class="sxs-lookup"><span data-stu-id="58cda-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="58cda-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="58cda-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="58cda-124">Arama zaman aşımına uğradı.</span><span class="sxs-lookup"><span data-stu-id="58cda-124">The call timed out.</span></span>|  
|<span data-ttu-id="58cda-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="58cda-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="58cda-126">Arayan bir kilide sahip değil.</span><span class="sxs-lookup"><span data-stu-id="58cda-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="58cda-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="58cda-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="58cda-128">Bir olay engellenen bir iş parçacığı iptal edildi veya fiber üzerinde bekleme süresi.</span><span class="sxs-lookup"><span data-stu-id="58cda-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="58cda-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="58cda-129">E_FAIL</span></span>|<span data-ttu-id="58cda-130">Bilinmeyen geri dönülemez bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="58cda-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="58cda-131">CLR, artık bir yöntem E_FAIL döndürürse, işlem içinde kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="58cda-131">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="58cda-132">Yöntemleri barındırma yapılan sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.</span><span class="sxs-lookup"><span data-stu-id="58cda-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58cda-133">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="58cda-133">Remarks</span></span>  
 `GetBindingIdentityFromFile` <span data-ttu-id="58cda-134">genellikle iki kez çağrılır.</span><span class="sxs-lookup"><span data-stu-id="58cda-134">is typically called twice.</span></span> <span data-ttu-id="58cda-135">İlk çağrı için bir null değer sağlayan `pwzBuffer`, ve yöntemi içinde uygun boyutta `pcchBufferSize`.</span><span class="sxs-lookup"><span data-stu-id="58cda-135">The first call supplies a null value for `pwzBuffer`, and the method returns the appropriate size in `pcchBufferSize`.</span></span> <span data-ttu-id="58cda-136">İkinci çağrı uygun şekilde ayrılan bir arabellek sağlar ve tamamlandığında gerçek arabellek verilerle yöntemi döndürür.</span><span class="sxs-lookup"><span data-stu-id="58cda-136">The second call supplies an appropriately allocated buffer, and the method returns with the actual buffer data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58cda-137">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="58cda-137">Requirements</span></span>  
 <span data-ttu-id="58cda-138">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58cda-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58cda-139">**Üst bilgi:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="58cda-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="58cda-140">**Kitaplığı:** Bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="58cda-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="58cda-141">.NET framework sürümleri:</span><span class="sxs-lookup"><span data-stu-id="58cda-141">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="58cda-142">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="58cda-142">See also</span></span>

- [<span data-ttu-id="58cda-143">ICLRAssemblyIdentityManager Arabirimi</span><span class="sxs-lookup"><span data-stu-id="58cda-143">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="58cda-144">ICLRAssemblyReferenceList Arabirimi</span><span class="sxs-lookup"><span data-stu-id="58cda-144">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="58cda-145">ICLRHostBindingPolicyManager Arabirimi</span><span class="sxs-lookup"><span data-stu-id="58cda-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
