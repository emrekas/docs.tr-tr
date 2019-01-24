---
title: ICorDebugCode::GetILToNativeMapping Metodu
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetILToNativeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetILToNativeMapping method [.NET Framework debugging]
ms.assetid: a8ecd8c8-9627-4356-9c6f-bd05e24637c0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8614dd612fff2886c4e44a977d05a575fce74eec
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648949"
---
# <a name="icordebugcodegetiltonativemapping-method"></a><span data-ttu-id="10533-102">ICorDebugCode::GetILToNativeMapping Metodu</span><span class="sxs-lookup"><span data-stu-id="10533-102">ICorDebugCode::GetILToNativeMapping Method</span></span>
<span data-ttu-id="10533-103">Eşlemeleri için yerel uzaklıklar Microsoft Ara dili (MSIL) kaydırır temsil eden "Cor_debug_ıl_to_natıve_map" örneklerinin bir dizisini alır.</span><span class="sxs-lookup"><span data-stu-id="10533-103">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from Microsoft intermediate language (MSIL) offsets to native offsets.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10533-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="10533-104">Syntax</span></span>  
  
```  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10533-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="10533-105">Parameters</span></span>  
 `cMap`  
 <span data-ttu-id="10533-106">[in] Boyutu `map` dizisi.</span><span class="sxs-lookup"><span data-stu-id="10533-106">[in] The size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="10533-107">[out] Gerçek döndürülen öğe sayısına bir işaretçi `map` dizisi.</span><span class="sxs-lookup"><span data-stu-id="10533-107">[out] A pointer to the actual number of elements returned in the `map` array.</span></span>  
  
 `map`  
 <span data-ttu-id="10533-108">[out] Bir dizi `COR_DEBUG_IL_TO_NATIVE_MAP` stuctures, her biri bir MSIL uzaklık bir eşleme yerel uzaklık temsil eder.</span><span class="sxs-lookup"><span data-stu-id="10533-108">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` stuctures, each of which represents a mapping from an MSIL offset to a native offset.</span></span>  
  
 <span data-ttu-id="10533-109">Sıralama yok döndürülen öğe dizisi yok.</span><span class="sxs-lookup"><span data-stu-id="10533-109">There is no ordering to the array of elements returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10533-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="10533-110">Remarks</span></span>  
 <span data-ttu-id="10533-111">`GetILToNativeMapping` Yöntemi yalnızca bu "ICorDebugCode" örneği, yalnızca derlenmiş MSIL kodunu zamanında (JIT) yerel kod temsil ediyorsa anlamlı sonuçlar döndürür.</span><span class="sxs-lookup"><span data-stu-id="10533-111">The `GetILToNativeMapping` method returns meaningful results only if this "ICorDebugCode" instance represents native code that was just-in-time (JIT) compiled from MSIL code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10533-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="10533-112">Requirements</span></span>  
 <span data-ttu-id="10533-113">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10533-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10533-114">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10533-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10533-115">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10533-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10533-116">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10533-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10533-117">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="10533-117">See also</span></span>
- [<span data-ttu-id="10533-118">ICorDebugCode Arabirimi1</span><span class="sxs-lookup"><span data-stu-id="10533-118">ICorDebugCode Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)
