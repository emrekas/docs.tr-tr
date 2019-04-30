---
title: ICorDebugDataTarget::GetThreadContext Metodu
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetThreadContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2db073f6bde3ded27f8e1aa41bfcb87e764745f1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61748948"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a><span data-ttu-id="6d891-102">ICorDebugDataTarget::GetThreadContext Metodu</span><span class="sxs-lookup"><span data-stu-id="6d891-102">ICorDebugDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="6d891-103">Belirtilen iş parçacığı için geçerli iş parçacığı bağlamını döndürür.</span><span class="sxs-lookup"><span data-stu-id="6d891-103">Returns the current thread context for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d891-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="6d891-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d891-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="6d891-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="6d891-106">[in] Alınacak olan bağlamıdır iş parçacığı tanıtıcısı.</span><span class="sxs-lookup"><span data-stu-id="6d891-106">[in] The identifier of the thread whose context is to be retrieved.</span></span> <span data-ttu-id="6d891-107">Tanımlayıcı, işletim sistemi tarafından tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="6d891-107">The identifier is defined by the operating system.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="6d891-108">[in] Bağlamın bölümünü okumalısınız belirtmek platforma bağımlı bayrakları Bitsel bir birleşimi.</span><span class="sxs-lookup"><span data-stu-id="6d891-108">[in] A bitwise combination of platform-dependent flags that indicate which portions of the context should be read.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="6d891-109">[in] Boyutu `pContext`.</span><span class="sxs-lookup"><span data-stu-id="6d891-109">[in] The size of `pContext`.</span></span>  
  
 `pContext`  
 <span data-ttu-id="6d891-110">[out] İş parçacığı bağlamını depolanacağı arabelleği.</span><span class="sxs-lookup"><span data-stu-id="6d891-110">[out] The buffer where the thread context will be stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d891-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="6d891-111">Remarks</span></span>  
 <span data-ttu-id="6d891-112">Windows platformlarında, `pContext` olmalıdır bir `CONTEXT` tarafından belirtilen makine türü için uygun olan (WinNT.h içinde tanımlanmıştır) yapısı [Icordebugdatatarget::getplatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="6d891-112">On Windows platforms, `pContext` must be a `CONTEXT` structure (defined in WinNT.h) that is appropriate for the machine type specified by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="6d891-113">`contextFlags` aynı değerlere sahip olmalıdır `ContextFlags` alanını `CONTEXT` yapısı.</span><span class="sxs-lookup"><span data-stu-id="6d891-113">`contextFlags` must have the same values as the `ContextFlags` field of the `CONTEXT` structure.</span></span> <span data-ttu-id="6d891-114">`CONTEXT` Yapısının olduğundan işlemciye özgü; ayrıntılar için WinNT.h dosyasına bakın.</span><span class="sxs-lookup"><span data-stu-id="6d891-114">The `CONTEXT` structure is processor-specific; refer to the WinNT.h file for details.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d891-115">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="6d891-115">Requirements</span></span>  
 <span data-ttu-id="6d891-116">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d891-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d891-117">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d891-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d891-118">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d891-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d891-119">**.NET framework sürümleri:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d891-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d891-120">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="6d891-120">See also</span></span>

- [<span data-ttu-id="6d891-121">ICorDebugDataTarget Arabirimi</span><span class="sxs-lookup"><span data-stu-id="6d891-121">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="6d891-122">Hata Ayıklama Arabirimleri</span><span class="sxs-lookup"><span data-stu-id="6d891-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="6d891-123">Hata Ayıklama</span><span class="sxs-lookup"><span data-stu-id="6d891-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
