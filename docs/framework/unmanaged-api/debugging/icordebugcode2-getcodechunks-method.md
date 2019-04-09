---
title: ICorDebugCode2::GetCodeChunks Yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCodeChunks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1428fc245d4f6993050c2753321684afee488c0e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116787"
---
# <a name="icordebugcode2getcodechunks-method"></a><span data-ttu-id="b6f54-102">ICorDebugCode2::GetCodeChunks Yöntemi</span><span class="sxs-lookup"><span data-stu-id="b6f54-102">ICorDebugCode2::GetCodeChunks Method</span></span>
<span data-ttu-id="b6f54-103">Bu kod nesnesi oluşan kod öbekleriyle alır.</span><span class="sxs-lookup"><span data-stu-id="b6f54-103">Gets the chunks of code that this code object is composed of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6f54-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="b6f54-104">Syntax</span></span>  
  
```  
HRESULT GetCodeChunks (  
    [in]  ULONG32     cbufSize,  
    [out] ULONG32     *pcnumChunks,  
    [out, size_is(cbufSize), length_is(*pcnumChunks)]   
        CodeChunkInfo chunks[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6f54-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="b6f54-105">Parameters</span></span>  
 `cbufSize`  
 <span data-ttu-id="b6f54-106">[in] Boyutu `chunks` dizisi.</span><span class="sxs-lookup"><span data-stu-id="b6f54-106">[in] Size of the `chunks` array.</span></span>  
  
 `pcnumChunks`  
 <span data-ttu-id="b6f54-107">[out] Döndürülen öbeği sayısı `chunks` dizisi.</span><span class="sxs-lookup"><span data-stu-id="b6f54-107">[out] The number of chunks returned in the `chunks` array.</span></span>  
  
 `chunks`  
 <span data-ttu-id="b6f54-108">[out] Her biri tek bir öbek kodunu temsil eden bir dizi "Codechunkınfo" yapıları.</span><span class="sxs-lookup"><span data-stu-id="b6f54-108">[out] An array of "CodeChunkInfo" structures, each of which represents a single chunk of code.</span></span> <span data-ttu-id="b6f54-109">Varsa değerini `cbufSize` 0'dır, bu parametre null olabilir.</span><span class="sxs-lookup"><span data-stu-id="b6f54-109">If the value of `cbufSize` is 0, this parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6f54-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="b6f54-110">Remarks</span></span>  
 <span data-ttu-id="b6f54-111">Kod öbekleri hiçbir zaman çakışır ve bunlar, bunlar birleştirilmiş tarafından sırasını takip [Icordebugcode::getcode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md).</span><span class="sxs-lookup"><span data-stu-id="b6f54-111">The code chunks will never overlap, and they will follow the order in which they would have been concatenated by [ICorDebugCode::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md).</span></span> <span data-ttu-id="b6f54-112">.NET Framework sürüm 2.0 Microsoft Ara dili (MSIL) kodu nesnesinde tek kod öbek oluşur.</span><span class="sxs-lookup"><span data-stu-id="b6f54-112">A Microsoft intermediate language (MSIL) code object in the .NET Framework version 2.0 will comprise a single code chunk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6f54-113">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="b6f54-113">Requirements</span></span>  
 <span data-ttu-id="b6f54-114">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6f54-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6f54-115">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6f54-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6f54-116">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6f54-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b6f54-117">.NET framework sürümleri:</span><span class="sxs-lookup"><span data-stu-id="b6f54-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b6f54-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="b6f54-118">See also</span></span>
