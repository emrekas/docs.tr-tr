---
title: COR_HEAPINFO Yapısı
ms.date: 03/30/2017
api_name:
- COR_HEAPINFO
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPINFO
helpviewer_keywords:
- COR_HEAPINFO structure [.NET Framework debugging]
ms.assetid: bfb2cd39-3e0b-4d51-ba0c-f009755c1456
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3dd233643bd18b60b7d6176c34ee57e4061daf7c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740660"
---
# <a name="corheapinfo-structure"></a>COR_HEAPINFO Yapısı
Numaralandırılabilir olup olmadığı dahil çöp toplama yığınındaki hakkında genel bilgiler sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;   
    DWORD pointerSize;   
    DWORD numHeaps;  
    BOOL concurrent;   
    CorDebugGCType gcType;   
} COR_HEAPINFO;  
```  
  
## <a name="members"></a>Üyeler  
  
|Üye|Açıklama|  
|------------|-----------------|  
|`areGCStructuresValid`|`true` Çöp toplama yapıları geçerli ve yığın numaralandırılabilir; Aksi takdirde, `false`.|  
|`pointerSize`|Hedef mimari işaretçilerde bayt cinsinden boyutu.|  
|`numHeaps`|Mantıksal çöp toplama işleminde yığınlardaki sayısı.|  
|`concurrent`|`TRUE` eş zamanlı varsa (arka plan) çöp toplama etkin; Aksi takdirde, `FALSE`.|  
|`gcType`|Üye [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md) atık toplayıcı bir iş istasyonunda veya sunucuda çalışıp çalışmadığını gösteren sabit listesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Örneği `COR_HEAPINFO` yapısı çağırarak döndürülür [Icordebugprocess5::getgcheapınformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) yöntemi.  
  
 Her zaman işaretlemeniz gerekir çöp toplama yığını üzerindeki nesneler numaralandırılırken önce `areGCStructuresValid` alanı yığın numaralandırılabilir bir durumda olduğundan emin olun. Daha fazla bilgi için [Icordebugprocess5::getgcheapınformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Hata Ayıklama Yapıları](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Hata Ayıklama](../../../../docs/framework/unmanaged-api/debugging/index.md)
