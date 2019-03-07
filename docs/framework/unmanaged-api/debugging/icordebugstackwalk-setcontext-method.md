---
title: ICorDebugStackWalk::SetContext Yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.SetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::SetContext
helpviewer_keywords:
- SetContext method [.NET Framework debugging]
- ICorDebugStackWalk::SetContext method [.NET Framework debugging]
ms.assetid: bac0b156-31a3-4e7f-be4d-ab21789c81f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3bbd215b2fefc662da4867a0a8700ca130c4e14c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470198"
---
# <a name="icordebugstackwalksetcontext-method"></a><span data-ttu-id="17fbc-102">ICorDebugStackWalk::SetContext Yöntemi</span><span class="sxs-lookup"><span data-stu-id="17fbc-102">ICorDebugStackWalk::SetContext Method</span></span>
<span data-ttu-id="17fbc-103">Kümeleri [Icordebugstackwalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) iş parçacığı için geçerli bir bağlamı için geçerli bağlam nesnesi.</span><span class="sxs-lookup"><span data-stu-id="17fbc-103">Sets the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object’s current context to a valid context for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17fbc-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="17fbc-104">Syntax</span></span>  
  
```  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17fbc-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="17fbc-105">Parameters</span></span>  
 `flag`  
 <span data-ttu-id="17fbc-106">[in] A [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) yığında etkin çerçeveye bağlamı dandır veya bir bağlamı elde yığın geriye doğru izleme olup olmadığını gösteren bayrak.</span><span class="sxs-lookup"><span data-stu-id="17fbc-106">[in] A [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) flag that indicates whether the context is from the active frame on the stack, or a context obtained by unwinding the stack.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="17fbc-107">[in] Ayrılmış boyutunu `CONTEXT` arabellek.</span><span class="sxs-lookup"><span data-stu-id="17fbc-107">[in] The allocated size of the `CONTEXT` buffer.</span></span>  
  
 `context`  
 <span data-ttu-id="17fbc-108">[in] `CONTEXT` Arabellek.</span><span class="sxs-lookup"><span data-stu-id="17fbc-108">[in] The `CONTEXT` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="17fbc-109">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="17fbc-109">Return Value</span></span>  
 <span data-ttu-id="17fbc-110">Bu yöntem aşağıdaki özel HRESULT'ları yanı sıra HRESULT döndürür yöntemi hatayı gösteren hatalar.</span><span class="sxs-lookup"><span data-stu-id="17fbc-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="17fbc-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="17fbc-111">HRESULT</span></span>|<span data-ttu-id="17fbc-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="17fbc-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="17fbc-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="17fbc-113">S_OK</span></span>|<span data-ttu-id="17fbc-114">`ICorDebugStackWalk` Nesnenin bağlam başarıyla ayarlandı.</span><span class="sxs-lookup"><span data-stu-id="17fbc-114">The `ICorDebugStackWalk` object's context was successfully set.</span></span>|  
|<span data-ttu-id="17fbc-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="17fbc-115">E_FAIL</span></span>|<span data-ttu-id="17fbc-116">`ICorDebugStackWalk` Nesnenin bağlam ayarlanmamış.</span><span class="sxs-lookup"><span data-stu-id="17fbc-116">The `ICorDebugStackWalk` object's context was not set.</span></span>|  
|<span data-ttu-id="17fbc-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="17fbc-117">E_INVALIDARG</span></span>|<span data-ttu-id="17fbc-118">Bağlam null olur.</span><span class="sxs-lookup"><span data-stu-id="17fbc-118">The context is null.</span></span>|  
|<span data-ttu-id="17fbc-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="17fbc-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="17fbc-120">Bağlam arabellek çok küçük.</span><span class="sxs-lookup"><span data-stu-id="17fbc-120">The context buffer is too small.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="17fbc-121">Özel Durumlar</span><span class="sxs-lookup"><span data-stu-id="17fbc-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17fbc-122">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="17fbc-122">Remarks</span></span>  
 <span data-ttu-id="17fbc-123">Bu yöntem, geçerli iş parçacığının bağlamında değiştirmez.</span><span class="sxs-lookup"><span data-stu-id="17fbc-123">This method does not alter the current context of the thread.</span></span>  
  
 <span data-ttu-id="17fbc-124">Geçerli bağlam için geçersiz bir bağlam ayarlama yığın yürüyüşçüsü öngörülemeyen sonuçlara neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="17fbc-124">Setting the current context to an invalid context may cause unpredictable results from the stack walker.</span></span>  
  
 <span data-ttu-id="17fbc-125">Bu bağlamın tam bir bit düzeyinde kopyalama hemen çağırarak alabilirsiniz [Icordebugstackwalk::getcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="17fbc-125">You can retrieve an exact bitwise copy of this context by immediately calling the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17fbc-126">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="17fbc-126">Requirements</span></span>  
 <span data-ttu-id="17fbc-127">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17fbc-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17fbc-128">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17fbc-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17fbc-129">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17fbc-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17fbc-130">**.NET framework sürümleri:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17fbc-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17fbc-131">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="17fbc-131">See also</span></span>
- [<span data-ttu-id="17fbc-132">Hata Ayıklama Arabirimleri</span><span class="sxs-lookup"><span data-stu-id="17fbc-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="17fbc-133">Hata Ayıklama</span><span class="sxs-lookup"><span data-stu-id="17fbc-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
