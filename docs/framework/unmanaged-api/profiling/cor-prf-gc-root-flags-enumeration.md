---
title: COR_PRF_GC_ROOT_FLAGS Numaralandırması
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_FLAGS
helpviewer_keywords:
- COR_PRF_GC_ROOT_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 4611ee6f-0f05-4d84-91e1-e83d5e7dd7e4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7f179e3b01d6c3b34dfa765565a0fc38d0ba867c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753689"
---
# <a name="corprfgcrootflags-enumeration"></a>COR_PRF_GC_ROOT_FLAGS Numaralandırması
Bir çöp toplama kök özelliğini gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a>Üyeler  
  
|Üye|Açıklama|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|Kök nesnenin taşınmasını çöp toplama engeller.|  
|`COR_PRF_GC_ROOT_WEAKREF`|Kök çöp toplama engellemez.|  
|`COR_PRF_GC_ROOT_INTERIOR`|Kök nesnenin kendisi yerine Nesne bir alana başvuruyor.|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|Kök çöp toplama, nesnenin başvuru sayısının belirli bir değer ise engeller.|  
  
## <a name="remarks"></a>Açıklamalar  
 `COR_PRF_GC_ROOT_FLAGS` Özel kökleri hakkında ek bilgi sağlayan bir bit maskesi olur. Ancak, tüm kökleri özeldir. Örneğin, bazı kökleri zayıf başvurular, sabitlenmiş veya başvuru sayılan iç işaretçiler değildir. Bu tür kökleri iletmek için hiçbir bayrak vardır. Bu nedenle, bu numaralandırma gibi kullandığınız yöntemleri [Icorprofilercallback2::rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) yöntemi, tüm bayraklar belirten bayrak bit maskesi için gönderme 0 kapalıdır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorProf.idl, CorProf.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Profil Oluşturma Sabit Listeleri](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
