---
title: CorDebugBlockingObject Yapısı
ms.date: 03/30/2017
api_name:
- CorDebugBlockingObject Structure
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingObject
helpviewer_keywords:
- CorDebugBlockingObject structure [.NET Framework debugging]
ms.assetid: 5944edd1-0914-4efa-aba0-d5a277c38b1a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83dac3b9b2ac396cdef19695fcce0f7e20485a50
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740398"
---
# <a name="cordebugblockingobject-structure"></a>CorDebugBlockingObject Yapısı
Bir iş parçacığı ve iş parçacığı engellenir belirli bir nedenle engelleyen bir nesneyi tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a>Üyeler  
  
|Üye|Açıklama|  
|------------|-----------------|  
|`pBlockingObject`|Nesne üzerinde iş parçacığını engelliyor. Bu nesne yalnızca geçerli eşitleme durumunun süresi boyunca geçerlidir. İki iş parçacığı aynı eşitlenmiş durum içinde'aynı nesne üzerinde engelliyorsanız bekleyebilir [Icordebugvalue::getaddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) aynı değeri döndürmek için yöntemi. Ancak, arabirimler olabilir veya eşdeğer bir işaretçi olabilir.|  
|`dwTimeout`|Engelleme işleminden önce milisaniye sayısını, zaman aşımı veya onu olacağı zaman aşımına gösteren SONSUZ değer olur. Zaman aşımı değerini durdurma işlemi, yine de kalan saat için toplam süreyi belirtir.|  
|`blockingReason`|Neden iş parçacığı bu nesne üzerinde engellenir.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorDebug.idl  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Hata Ayıklama Yapıları](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Hata Ayıklama](../../../../docs/framework/unmanaged-api/debugging/index.md)
