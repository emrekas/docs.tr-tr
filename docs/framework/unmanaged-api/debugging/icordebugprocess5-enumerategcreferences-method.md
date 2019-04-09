---
title: ICorDebugProcess5::EnumerateGCReferences Yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateGCReferences
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0845165e3200d7a5e14715cbe116ea5255aa021
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178899"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a><span data-ttu-id="3f513-102">ICorDebugProcess5::EnumerateGCReferences Yöntemi</span><span class="sxs-lookup"><span data-stu-id="3f513-102">ICorDebugProcess5::EnumerateGCReferences Method</span></span>
<span data-ttu-id="3f513-103">Bir işlemde atık olarak toplanmış olacak olan tüm nesneler için bir numaralandırıcı alır.</span><span class="sxs-lookup"><span data-stu-id="3f513-103">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f513-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="3f513-104">Syntax</span></span>  
  
```  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,   
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f513-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="3f513-105">Parameters</span></span>  
 `enumerateWeakReferences`  
 <span data-ttu-id="3f513-106">[in] Zayıf başvurular da sıralanması olup olmadığını gösteren bir Boole değeri.</span><span class="sxs-lookup"><span data-stu-id="3f513-106">[in] A Boolean value that indicates whether weak references are also to be enumerated.</span></span> <span data-ttu-id="3f513-107">Varsa `enumerateWeakReferences` olduğu `true`, `ppEnum` Numaralandırıcı güçlü atıflar hem zayıf başvurular içerir.</span><span class="sxs-lookup"><span data-stu-id="3f513-107">If `enumerateWeakReferences` is `true`, the `ppEnum` enumerator includes both strong references and weak references.</span></span> <span data-ttu-id="3f513-108">Varsa `enumerateWeakReferences` olduğu `false`, numaralandırıcı yalnızca tanımlayıcı başvuruları içerir.</span><span class="sxs-lookup"><span data-stu-id="3f513-108">If `enumerateWeakReferences` is `false`, the enumerator includes only strong references.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="3f513-109">[out] Adresine bir işaretçi bir [Icordebuggcreferenceenum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) atık olarak toplanmış için diğer bir deyişle bir numaralandırıcı nesneler için.</span><span class="sxs-lookup"><span data-stu-id="3f513-109">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f513-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="3f513-110">Remarks</span></span>  
 <span data-ttu-id="3f513-111">Bu yöntem, bir işlemdeki yönetilen tüm nesneleri için tam kök zincir belirlemek için bir yol sağlar ve bir nesne neden hala etkin olduğunu belirlemek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="3f513-111">This method provides a way to determine the full rooting chain for any managed object in a process and can be used to determine why an object is still alive.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f513-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="3f513-112">Requirements</span></span>  
 <span data-ttu-id="3f513-113">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f513-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f513-114">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f513-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f513-115">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f513-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3f513-116">.NET framework sürümleri:</span><span class="sxs-lookup"><span data-stu-id="3f513-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3f513-117">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="3f513-117">See also</span></span>

- [<span data-ttu-id="3f513-118">ICorDebugProcess5 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="3f513-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="3f513-119">Hata Ayıklama Arabirimleri</span><span class="sxs-lookup"><span data-stu-id="3f513-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
