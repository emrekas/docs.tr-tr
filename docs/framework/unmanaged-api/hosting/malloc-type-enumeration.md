---
title: MALLOC_TYPE Numaralandırması
ms.date: 03/30/2017
api_name:
- MALLOC_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MALLOC_TYPE
helpviewer_keywords:
- MALLOC_TYPE Enumeration
ms.assetid: c02476f9-23a2-4af7-9282-aa9c42c7429b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 695f69c8d9c3a295a705971743733339cf8aab13
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765225"
---
# <a name="malloctype-enumeration"></a><span data-ttu-id="6f913-102">MALLOC_TYPE Numaralandırması</span><span class="sxs-lookup"><span data-stu-id="6f913-102">MALLOC_TYPE Enumeration</span></span>
<span data-ttu-id="6f913-103">Ayrılan bellek özelliklerini belirten değerleri içerir.</span><span class="sxs-lookup"><span data-stu-id="6f913-103">Contains values that specify the characteristics of the memory that is being allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f913-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="6f913-104">Syntax</span></span>  
  
```  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="6f913-105">Üyeler</span><span class="sxs-lookup"><span data-stu-id="6f913-105">Members</span></span>  
  
|<span data-ttu-id="6f913-106">Üye</span><span class="sxs-lookup"><span data-stu-id="6f913-106">Member</span></span>|<span data-ttu-id="6f913-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6f913-107">Description</span></span>|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|<span data-ttu-id="6f913-108">Ayrılan bellek bir yürütülebilir dosya içerebilir.</span><span class="sxs-lookup"><span data-stu-id="6f913-108">The allocated memory can contain an executable file.</span></span>|  
|`MALLOC_THREADSAFE`|<span data-ttu-id="6f913-109">Ayrılan bellek, iş parçacığı açısından güvenlidir.</span><span class="sxs-lookup"><span data-stu-id="6f913-109">The allocated memory is thread-safe.</span></span> <span data-ttu-id="6f913-110">Diğer bir deyişle, bellek, herhangi bir eşitleme olmadan birden çok iş parçacığı tarafından erişilebilir.</span><span class="sxs-lookup"><span data-stu-id="6f913-110">That is, the memory can be accessed by multiple threads without any synchronization.</span></span><br /><br /> <span data-ttu-id="6f913-111">Bu bayrak ayarlanmazsa çağrıları nesnede seri hale getirilmelidir.</span><span class="sxs-lookup"><span data-stu-id="6f913-111">If this flag is not set, calls on the object must be serialized.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6f913-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="6f913-112">Requirements</span></span>  
 <span data-ttu-id="6f913-113">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f913-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f913-114">**Üst bilgi:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6f913-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6f913-115">**Kitaplığı:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6f913-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6f913-116">**.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f913-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f913-117">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="6f913-117">See also</span></span>

- [<span data-ttu-id="6f913-118">Barındırma Sabit Listeleri</span><span class="sxs-lookup"><span data-stu-id="6f913-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
