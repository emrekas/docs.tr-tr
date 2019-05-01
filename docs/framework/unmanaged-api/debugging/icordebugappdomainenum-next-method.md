---
title: ICorDebugAppDomainEnum::Next Yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum::Next method
helpviewer_keywords:
- ICorDebugAppDomainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: b8d1def7-0ebc-4314-a3a2-fd36a75973e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fefc933cc84fede1f3dea16d4b13e09801a96e0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996157"
---
# <a name="icordebugappdomainenumnext-method"></a><span data-ttu-id="7b894-102">ICorDebugAppDomainEnum::Next Yöntemi</span><span class="sxs-lookup"><span data-stu-id="7b894-102">ICorDebugAppDomainEnum::Next Method</span></span>
<span data-ttu-id="7b894-103">Koleksiyondan geçerli imleç konumdan başlayarak belirtilen sayıda uygulama etki alanları alır.</span><span class="sxs-lookup"><span data-stu-id="7b894-103">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b894-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="7b894-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                           ICorDebugAppDomain *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b894-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="7b894-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="7b894-106">[in] Alınacak uygulama etki alanları sayısı.</span><span class="sxs-lookup"><span data-stu-id="7b894-106">[in] The number of application domains to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="7b894-107">[out] Bir dizi işaretçileri, her biri, uygulama etki alanını temsil eden bir Icordebugappdomain nesneye işaret eder.</span><span class="sxs-lookup"><span data-stu-id="7b894-107">[out] An array of pointers, each of which points to an ICorDebugAppDomain object that represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="7b894-108">[out] Gerçekte döndürülen uygulama etki alanı sayısı için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="7b894-108">[out] A pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="7b894-109">Bu değer null olabilir, `celt` biridir.</span><span class="sxs-lookup"><span data-stu-id="7b894-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b894-110">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="7b894-110">Requirements</span></span>  
 <span data-ttu-id="7b894-111">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b894-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b894-112">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b894-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b894-113">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b894-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b894-114">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b894-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
