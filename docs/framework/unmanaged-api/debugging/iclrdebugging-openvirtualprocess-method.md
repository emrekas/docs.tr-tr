---
title: ICLRDebugging::OpenVirtualProcess Yöntemi
ms.date: 03/30/2017
api_name:
- ICLRDebugging.OpenVirtualProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::OpenVirtualProcess
helpviewer_keywords:
- OpenVirtualProcess method [.NET Framework debugging]
- ICLRDebugging::OpenVirtualProcess method [.NET Framework debugging]
ms.assetid: e8ab7c41-d508-4ed9-8a31-ead072b5a314
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b4ed9526dc38d72b01798215bc602fb8298c2bc3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478030"
---
# <a name="iclrdebuggingopenvirtualprocess-method"></a><span data-ttu-id="548a4-102">ICLRDebugging::OpenVirtualProcess Yöntemi</span><span class="sxs-lookup"><span data-stu-id="548a4-102">ICLRDebugging::OpenVirtualProcess Method</span></span>
<span data-ttu-id="548a4-103">Ortak dil çalışma zamanı (CLR) modül işleme yüklendiğinde karşılık gelen Icordebugprocess arabirimi alır.</span><span class="sxs-lookup"><span data-stu-id="548a4-103">Gets the ICorDebugProcess interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="548a4-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="548a4-104">Syntax</span></span>  
  
```  
HRESULT OpenVirtualProcess(  
    [in] ULONG64 moduleBaseAddress,  
    [in] IUnknown * pDataTarget,  
    [in] ICLRDebuggingLibraryProvider * pLibraryProvider,  
    [in] CLR_DEBUGGING_VERSION * pMaxDebuggerSupportedVersion,  
    [in] REFIID riidProcess,  
    [out, iid_is(riidProcess)] IUnknown ** ppProcess,  
    [in, out] CLR_DEBUGGING_VERSION * pVersion,  
    [out] CLR_DEBUGGING_PROCESS_FLAGS * pdwFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="548a4-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="548a4-105">Parameters</span></span>  
 `moduleBaseAddress`  
 <span data-ttu-id="548a4-106">[in] Hedef işlemde bir modülün temel adres.</span><span class="sxs-lookup"><span data-stu-id="548a4-106">[in] The base address of a module in the target process.</span></span> <span data-ttu-id="548a4-107">Belirtilen modül bir CLR modülünü değilse COR_E_NOT_CLR döndürülür.</span><span class="sxs-lookup"><span data-stu-id="548a4-107">COR_E_NOT_CLR will be returned if the specified module is not a CLR module.</span></span>  
  
 `pDataTarget`  
 <span data-ttu-id="548a4-108">[in] İşlem durumu denetlemek yönetilen hata ayıklayıcı sağlayan veri hedef özeti.</span><span class="sxs-lookup"><span data-stu-id="548a4-108">[in] A data target abstraction that allows the managed debugger to inspect process state.</span></span> <span data-ttu-id="548a4-109">Hata ayıklayıcı uygulamalıdır [Icordebugdatatarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) arabirimi.</span><span class="sxs-lookup"><span data-stu-id="548a4-109">The debugger must implement the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="548a4-110">Uygulamalıdır [Iclrdebugginglibraryprovider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) ayıklanmakta olan CLR yüklü olmayan yerel bilgisayarda senaryoları desteklemek için arabirim.</span><span class="sxs-lookup"><span data-stu-id="548a4-110">You should implement the [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface to support scenarios where the CLR that is being debugged is not installed locally on the computer.</span></span>  
  
 `pLibraryProvider`  
 <span data-ttu-id="548a4-111">[in] Ve yüklenecek üzerine yerleştirilecek sürümüne özel hata ayıklama kitaplıklarına izin veren bir kitaplık sağlayıcı geri arama arabirimi.</span><span class="sxs-lookup"><span data-stu-id="548a4-111">[in] A library provider callback interface that allows version-specific debugging libraries to be located and loaded on demand.</span></span> <span data-ttu-id="548a4-112">Bu parametre yalnızca gereklidir `ppProcess` veya `pFlags` değil `null`.</span><span class="sxs-lookup"><span data-stu-id="548a4-112">This parameter is required only if `ppProcess` or `pFlags` is not `null`.</span></span>  
  
 `pMaxDebuggerSupportedVersion`  
 <span data-ttu-id="548a4-113">[in] Bu hata ayıklayıcı hata ayıklaması yapabilirsiniz CLR en yüksek sürümü.</span><span class="sxs-lookup"><span data-stu-id="548a4-113">[in] The highest version of the CLR that this debugger can debug.</span></span> <span data-ttu-id="548a4-114">Ana, alt, belirtin ve bu hata ayıklayıcı destekleyen en son CLR sürümü sürümlerinden yapı ve düzeltme numarası 65535 hizmet sürümlerini gelecekteki yerinde CLR uyum sağlayacak şekilde ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="548a4-114">You should specify the major, minor, and build versions from the latest CLR version this debugger supports, and set the revision number to 65535 to accommodate future in-place CLR servicing releases.</span></span>  
  
 `riidProcess`  
 <span data-ttu-id="548a4-115">[in] Alınacak Icordebugprocess arabirimi kimliği.</span><span class="sxs-lookup"><span data-stu-id="548a4-115">[in] The ID of the ICorDebugProcess interface to retrieve.</span></span> <span data-ttu-id="548a4-116">Şu anda, kabul edilen değerler yalnızca IID_CORDEBUGPROCESS3 IID_CORDEBUGPROCESS2 ve IID_CORDEBUGPROCESS ' dir.</span><span class="sxs-lookup"><span data-stu-id="548a4-116">Currently, the only accepted values are IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2, and IID_CORDEBUGPROCESS.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="548a4-117">[out] Bir işaretçi tarafından tanımlanan COM arabirimi `riidProcess`.</span><span class="sxs-lookup"><span data-stu-id="548a4-117">[out] A pointer to the COM interface that is identified by `riidProcess`.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="548a4-118">[out içinde] CLR sürümü.</span><span class="sxs-lookup"><span data-stu-id="548a4-118">[in, out] The version of the CLR.</span></span> <span data-ttu-id="548a4-119">Bu değer, giriş olabilir `null`.</span><span class="sxs-lookup"><span data-stu-id="548a4-119">On input, this value can be `null`.</span></span> <span data-ttu-id="548a4-120">Bu da işaret edebilir bir [clr_debuggıng_versıon](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) yapısı, bu durumda yapısı `wStructVersion` alan 0 (sıfır) başlatılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="548a4-120">It can also point to a [CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) structure, in which case the structure's `wStructVersion` field must be initialized to 0 (zero).</span></span>  
  
 <span data-ttu-id="548a4-121">Çıktıda, döndürülen `CLR_DEBUGGING_VERSION` yapısı, CLR sürüm bilgilerini oturum doldurulur.</span><span class="sxs-lookup"><span data-stu-id="548a4-121">On output, the returned `CLR_DEBUGGING_VERSION` structure will be filled in with the version information for the CLR.</span></span>  
  
 `pdwFlags`  
 <span data-ttu-id="548a4-122">[out] Belirtilen çalışma zamanı hakkında bilgi bayrakları.</span><span class="sxs-lookup"><span data-stu-id="548a4-122">[out] Informational flags about the specified runtime.</span></span> <span data-ttu-id="548a4-123">Bkz: [clr_debuggıng_process_flags](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md) konu bayrakları açıklaması.</span><span class="sxs-lookup"><span data-stu-id="548a4-123">See the [CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md) topic for a description of the flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="548a4-124">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="548a4-124">Return Value</span></span>  
 <span data-ttu-id="548a4-125">Bu yöntem aşağıdaki özel HRESULT'ları yanı sıra HRESULT döndürür yöntemi hatayı gösteren hatalar.</span><span class="sxs-lookup"><span data-stu-id="548a4-125">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="548a4-126">HRESULT</span><span class="sxs-lookup"><span data-stu-id="548a4-126">HRESULT</span></span>|<span data-ttu-id="548a4-127">Açıklama</span><span class="sxs-lookup"><span data-stu-id="548a4-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="548a4-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="548a4-128">S_OK</span></span>|<span data-ttu-id="548a4-129">Yöntem başarıyla tamamlandı.</span><span class="sxs-lookup"><span data-stu-id="548a4-129">The method completed successfully.</span></span>|  
|<span data-ttu-id="548a4-130">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="548a4-130">E_POINTER</span></span>|<span data-ttu-id="548a4-131">`pDataTarget` olan `null`.</span><span class="sxs-lookup"><span data-stu-id="548a4-131">`pDataTarget` is `null`.</span></span>|  
|<span data-ttu-id="548a4-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span><span class="sxs-lookup"><span data-stu-id="548a4-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span></span>|<span data-ttu-id="548a4-133">[Iclrdebugginglibraryprovider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) geri çağırma bir hata döndürür veya geçerli bir tanıtıcı sağlamaz.</span><span class="sxs-lookup"><span data-stu-id="548a4-133">The [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) callback returns an error or does not provide a valid handle.</span></span>|  
|<span data-ttu-id="548a4-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="548a4-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span></span>|<span data-ttu-id="548a4-135">`pDataTarget` çalışma zamanının bu sürümü için gerekli verileri hedef arabirimi uygulamıyor.</span><span class="sxs-lookup"><span data-stu-id="548a4-135">`pDataTarget` does not implement the required data target interfaces for this version of the runtime.</span></span>|  
|<span data-ttu-id="548a4-136">CORDBG_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="548a4-136">CORDBG_E_NOT_CLR</span></span>|<span data-ttu-id="548a4-137">Belirtilen modül bir CLR modülünü değil.</span><span class="sxs-lookup"><span data-stu-id="548a4-137">The indicated module is not a CLR module.</span></span> <span data-ttu-id="548a4-138">Bir CLR modül bellek bozulmuş, modül kullanılabilir olmadığı veya CLR sürümünün dolgu sürümden daha sonraki algılanamıyor olduğunda bu HRESULT da döndürülür.</span><span class="sxs-lookup"><span data-stu-id="548a4-138">This HRESULT is also returned when a CLR module cannot be detected because memory has been corrupted, the module is not available, or the CLR version is later than the shim version.</span></span>|  
|<span data-ttu-id="548a4-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span><span class="sxs-lookup"><span data-stu-id="548a4-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span></span>|<span data-ttu-id="548a4-140">Bu çalışma zamanı sürümü, bu hata ayıklama modelini desteklemiyor.</span><span class="sxs-lookup"><span data-stu-id="548a4-140">This runtime version does not support this debugging model.</span></span> <span data-ttu-id="548a4-141">Şu anda, hata ayıklama modeli önce CLR sürümleri tarafından desteklenmeyen [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="548a4-141">Currently, the debugging model is not supported by CLR versions before the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="548a4-142">`pwszVersion` Çıkış parametresi doğru değer yine de bu hatadan sonra ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="548a4-142">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="548a4-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span><span class="sxs-lookup"><span data-stu-id="548a4-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span></span>|<span data-ttu-id="548a4-144">Bu hata ayıklayıcı desteği iddia sürümünden büyük CLR sürümüdür.</span><span class="sxs-lookup"><span data-stu-id="548a4-144">The version of the CLR is greater than the version this debugger claims to support.</span></span> <span data-ttu-id="548a4-145">`pwszVersion` Çıkış parametresi doğru değer yine de bu hatadan sonra ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="548a4-145">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="548a4-146">E_NO_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="548a4-146">E_NO_INTERFACE</span></span>|<span data-ttu-id="548a4-147">`riidProcess` Arabirimi kullanılabilir değil.</span><span class="sxs-lookup"><span data-stu-id="548a4-147">The `riidProcess` interface is not available.</span></span>|  
|<span data-ttu-id="548a4-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span><span class="sxs-lookup"><span data-stu-id="548a4-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span></span>|<span data-ttu-id="548a4-149">`CLR_DEBUGGING_VERSION` Yapısı için tanınan bir değer yok `wStructVersion`.</span><span class="sxs-lookup"><span data-stu-id="548a4-149">The `CLR_DEBUGGING_VERSION` structure does not have a recognized value for `wStructVersion`.</span></span> <span data-ttu-id="548a4-150">Şu anda yalnızca kabul edilen değeri 0'dır.</span><span class="sxs-lookup"><span data-stu-id="548a4-150">The only accepted value at this time is 0.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="548a4-151">Özel Durumlar</span><span class="sxs-lookup"><span data-stu-id="548a4-151">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="548a4-152">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="548a4-152">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="548a4-153">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="548a4-153">Requirements</span></span>  
 <span data-ttu-id="548a4-154">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="548a4-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="548a4-155">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="548a4-155">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="548a4-156">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="548a4-156">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="548a4-157">**.NET framework sürümleri:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="548a4-157">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="548a4-158">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="548a4-158">See also</span></span>
- [<span data-ttu-id="548a4-159">Hata Ayıklama Arabirimleri</span><span class="sxs-lookup"><span data-stu-id="548a4-159">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="548a4-160">Hata Ayıklama</span><span class="sxs-lookup"><span data-stu-id="548a4-160">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
