---
title: CreateCordbObject İşlevi
ms.date: 03/30/2017
api_name:
- CreateCoredbObject
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f546d7707c40f7f26a46177ae972a988e54e1e45
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487869"
---
# <a name="createcordbobject-function"></a><span data-ttu-id="2e0ec-102">CreateCordbObject İşlevi</span><span class="sxs-lookup"><span data-stu-id="2e0ec-102">CreateCordbObject Function</span></span>
<span data-ttu-id="2e0ec-103">Hata ayıklayıcı arabirim oluşturur ([Icordebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)) uzak bir işlem üzerinde yönetilen hata ayıklama oturumu oluşturmak için işlevsellik sağlar.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-103">Creates a debugger interface ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)) that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e0ec-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="2e0ec-104">Syntax</span></span>  
  
```  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,   
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e0ec-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="2e0ec-105">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="2e0ec-106">[in] Hedef işlemin hata ayıklayıcı sürümü.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-106">[in] Debugger version of the target process.</span></span> <span data-ttu-id="2e0ec-107">Bu parametre, uzaktan hata ayıklama için CorDebugVersion_2_0 olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-107">This parameter must be CorDebugVersion_2_0 for remote debugging.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="2e0ec-108">[out] İçin cast bir nesneye bir işaretçi işaretçisi bir [Icordebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) arabirim ve döndürülür.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-108">[out] Pointer to a pointer to an object that will be cast to an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface and returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2e0ec-109">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="2e0ec-109">Return Value</span></span>  
 <span data-ttu-id="2e0ec-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2e0ec-110">S_OK</span></span>  
 <span data-ttu-id="2e0ec-111">İşlem CLRs sayısında başarıyla belirlendi ve karşılık gelen tanıtıcısı ve yol diziler düzgün doldurulmuş.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-111">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="2e0ec-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2e0ec-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="2e0ec-113">`ppCordb` null ise veya `iDebuggerVersion` CorDebugVersion_2_0 değil.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-113">`ppCordb` is null, or `iDebuggerVersion` is not CorDebugVersion_2_0.</span></span>  
  
 <span data-ttu-id="2e0ec-114">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="2e0ec-114">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="2e0ec-115">Yeterli bellek ayrılamadı `ppCordb`</span><span class="sxs-lookup"><span data-stu-id="2e0ec-115">Unable to allocate enough memory for `ppCordb`</span></span>  
  
 <span data-ttu-id="2e0ec-116">E_FAIL (veya diğer E_ dönüş kodları)</span><span class="sxs-lookup"><span data-stu-id="2e0ec-116">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="2e0ec-117">Diğer hatalar.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-117">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e0ec-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="2e0ec-118">Remarks</span></span>  
 <span data-ttu-id="2e0ec-119">[Icordebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) döndürülür arabirimi `ppCordb` tüm yönetilen hata ayıklama Hizmetleri için en üst düzey hata ayıklama arabirimidir.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-119">The [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface that is returned in `ppCordb` is the top-level debugging interface for all managed debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e0ec-120">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="2e0ec-120">Requirements</span></span>  
 <span data-ttu-id="2e0ec-121">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e0ec-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e0ec-122">**Üst bilgi:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="2e0ec-122">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="2e0ec-123">**Library:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="2e0ec-123">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="2e0ec-124">**.NET framework sürümleri:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="2e0ec-124">**.NET Framework Versions:** 3.5 SP1</span></span>
