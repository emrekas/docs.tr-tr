---
title: ICorDebugFunction::GetCurrentVersionNumber Metodu
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetCurrentVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetCurrentVersionNumber
helpviewer_keywords:
- GetCurrentVersionNumber method [.NET Framework debugging]
- ICorDebugFunction::GetCurrentVersionNumber method [.NET Framework debugging]
ms.assetid: c3af1575-cbe6-457a-bc08-c53460edcbc8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea615eacb30fd4e7a0fd7d730094c2ab4f9dc285
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988734"
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a><span data-ttu-id="30fb3-102">ICorDebugFunction::GetCurrentVersionNumber Metodu</span><span class="sxs-lookup"><span data-stu-id="30fb3-102">ICorDebugFunction::GetCurrentVersionNumber Method</span></span>
<span data-ttu-id="30fb3-103">Bu ICorDebugFunction nesnesiyle temsil edilen işlevine yapılan en son düzenleme sürüm numarasını alır.</span><span class="sxs-lookup"><span data-stu-id="30fb3-103">Gets the version number of the latest edit made to the function represented by this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30fb3-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="30fb3-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30fb3-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="30fb3-105">Parameters</span></span>  
 `pnCurrentVersion`  
 <span data-ttu-id="30fb3-106">[out] Bu işleve yapılan en son düzenleme sürüm sayısı bir tamsayı değeri için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="30fb3-106">[out] A pointer to an integer value that is the version number of the latest edit made to this function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30fb3-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="30fb3-107">Remarks</span></span>  
 <span data-ttu-id="30fb3-108">Bu işleve yapılan en son düzenleme sürüm numarasını işlevi sürüm numarasından daha büyük olabilir.</span><span class="sxs-lookup"><span data-stu-id="30fb3-108">The version number of the latest edit made to this function may be greater than the version number of the function itself.</span></span> <span data-ttu-id="30fb3-109">Hangisini [Icordebugfunction2::getversionnumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) yöntemi veya [Icordebugcode::getversionnumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) işlevi sürüm numarasını almak için yöntemi.</span><span class="sxs-lookup"><span data-stu-id="30fb3-109">Use either the [ICorDebugFunction2::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) method or the [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method to retrieve the version number of the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30fb3-110">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="30fb3-110">Requirements</span></span>  
 <span data-ttu-id="30fb3-111">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30fb3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30fb3-112">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30fb3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30fb3-113">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30fb3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30fb3-114">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30fb3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
