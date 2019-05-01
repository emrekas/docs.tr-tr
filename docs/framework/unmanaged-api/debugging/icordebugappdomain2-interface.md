---
title: ICorDebugAppDomain2 Arabirimi
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2
helpviewer_keywords:
- ICorDebugAppDomain2 interface [.NET Framework debugging]
ms.assetid: 314d29f3-feb0-4a92-9530-b569c280cc31
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c6ef901f43cd6568f17657ed8e58bc2cc2cc0a1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922271"
---
# <a name="icordebugappdomain2-interface"></a><span data-ttu-id="04622-102">ICorDebugAppDomain2 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="04622-102">ICorDebugAppDomain2 Interface</span></span>

<span data-ttu-id="04622-103">Diziler, işaretçiler, işlev işaretçileri ve başvuru türleri ile çalışmak için yöntemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="04622-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="04622-104">Bu arabirim, Icordebugappdomain arabiriminin bir uzantısıdır.</span><span class="sxs-lookup"><span data-stu-id="04622-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="04622-105">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="04622-105">Methods</span></span>  
  
|<span data-ttu-id="04622-106">Yöntem</span><span class="sxs-lookup"><span data-stu-id="04622-106">Method</span></span>|<span data-ttu-id="04622-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="04622-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="04622-108">GetArrayOrPointerType Yöntemi</span><span class="sxs-lookup"><span data-stu-id="04622-108">GetArrayOrPointerType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="04622-109">Belirtilen tür veya işaretçi veya başvuru belirtilen türe dizisini alır.</span><span class="sxs-lookup"><span data-stu-id="04622-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="04622-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="04622-110">GetFunctionPointerType</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="04622-111">Belirli bir imzaya sahip bir işlev için bir işaretçi alır.</span><span class="sxs-lookup"><span data-stu-id="04622-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04622-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="04622-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04622-113">Bu arabirim makineler arası veya çapraz işlem uzaktan çağrılan desteklemez.</span><span class="sxs-lookup"><span data-stu-id="04622-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04622-114">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="04622-114">Requirements</span></span>  
 <span data-ttu-id="04622-115">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04622-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04622-116">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="04622-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="04622-117">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04622-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04622-118">**.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04622-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04622-119">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="04622-119">See also</span></span>

- [<span data-ttu-id="04622-120">Hata Ayıklama Arabirimleri</span><span class="sxs-lookup"><span data-stu-id="04622-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
