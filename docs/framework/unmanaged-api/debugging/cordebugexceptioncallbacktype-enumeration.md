---
title: CorDebugExceptionCallbackType Numaralandırması
ms.date: 03/30/2017
api_name:
- CorDebugExceptionCallbackType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionCallbackType
helpviewer_keywords:
- CorDebugExceptionCallbackType enumeration [.NET Framework debugging]
ms.assetid: 4d946ad4-3c19-42cb-bec9-8633325ba769
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91b09be04499396a2229962fd592f29cb8bc8d04
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609038"
---
# <a name="cordebugexceptioncallbacktype-enumeration"></a><span data-ttu-id="e117d-102">CorDebugExceptionCallbackType Numaralandırması</span><span class="sxs-lookup"><span data-stu-id="e117d-102">CorDebugExceptionCallbackType Enumeration</span></span>
<span data-ttu-id="e117d-103">Gelen yapılan bir geri çağırma türünü gösteren bir [Icordebugmanagedcallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) olay.</span><span class="sxs-lookup"><span data-stu-id="e117d-103">Indicates the type of callback that is made from an [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e117d-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="e117d-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionCallbackType {  
    DEBUG_EXCEPTION_FIRST_CHANCE         = 1,  
    DEBUG_EXCEPTION_USER_FIRST_CHANCE    = 2,  
    DEBUG_EXCEPTION_CATCH_HANDLER_FOUND  = 3,  
    DEBUG_EXCEPTION_UNHANDLED            = 4  
} CorDebugExceptionCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="e117d-105">Üyeler</span><span class="sxs-lookup"><span data-stu-id="e117d-105">Members</span></span>  
  
|<span data-ttu-id="e117d-106">Üye</span><span class="sxs-lookup"><span data-stu-id="e117d-106">Member</span></span>|<span data-ttu-id="e117d-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e117d-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="e117d-108">Bir özel durum oluştu.</span><span class="sxs-lookup"><span data-stu-id="e117d-108">An exception was thrown.</span></span>|  
|`DEBUG_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="e117d-109">Özel durum windup işlemi, kullanıcı kodu girildi.</span><span class="sxs-lookup"><span data-stu-id="e117d-109">The exception windup process entered user code.</span></span>|  
|`DEBUG_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="e117d-110">Bulunan özel durum windup işleme bir `catch` kullanıcı kodunda engelleyin.</span><span class="sxs-lookup"><span data-stu-id="e117d-110">The exception windup process found a `catch` block in user code.</span></span>|  
|`DEBUG_EXCEPTION_UNHANDLED`|<span data-ttu-id="e117d-111">Özel durum işlenmedi.</span><span class="sxs-lookup"><span data-stu-id="e117d-111">The exception was not handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e117d-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="e117d-112">Requirements</span></span>  
 <span data-ttu-id="e117d-113">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e117d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e117d-114">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e117d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e117d-115">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e117d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e117d-116">**.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e117d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e117d-117">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="e117d-117">See also</span></span>

- [<span data-ttu-id="e117d-118">Hata Ayıklama Sabit Listeleri</span><span class="sxs-lookup"><span data-stu-id="e117d-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
