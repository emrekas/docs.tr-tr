---
title: ICorDebugThread4::GetBlockingObjects Metodu
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetBlockingObjects Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetBlockingObjects
helpviewer_keywords:
- GetBlockingObjects method [.NET Framework debugging]
- ICorDebugThread4::GetBlockingObjects method [.NET Framework debugging]
ms.assetid: a7e6c54e-7be9-4e52-bbb4-95f52458e8e4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d83f9c0b187ad8b2955bc12ff168e0c4f26b909
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765219"
---
# <a name="icordebugthread4getblockingobjects-method"></a>ICorDebugThread4::GetBlockingObjects Metodu
Sıralı sabit listesi sağlar [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) sağlayan yapıları iş parçacığı engelleme bilgileri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
## <a name="parameters"></a>Parametreler  
 `ppBlockingObjectEnum`  
 [out] Sıralı sabit listesi için bir işaretçi [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) yapıları.  
  
## <a name="remarks"></a>Açıklamalar  
 Döndürülen listedeki ilk öğeyi iş parçacığının engellenmesi ilk yapısına karşılık gelir. İkinci öğe, bir zaman uyumsuz bir yordam çağrısı (APC) ilk ve benzeri engellendiğinde çalıştırılırken karşılaşılan engelleme öğesine karşılık gelir.  
  
 Sabit listesi yalnızca geçerli eşitleme durumunun süresi boyunca geçerlidir.  
  
 Hata ayıklanan eşitlenmiş bir durumda olsa da, bu yöntem çağrılmalıdır.  
  
 Varsa `ppBlockingObjectEnum` geçerli bir işaretçi değil sonuç tanımsızdır.  
  
 Yöntemi, bir iş parçacığı engellenir ve hata belirlenemiyor, hata olduğunu gösteren bir HRESULT döndürür; Aksi takdirde S_OK döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [ICorDebugThread4 Arabirimi](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [Hata Ayıklama Arabirimleri](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Hata Ayıklama](../../../../docs/framework/unmanaged-api/debugging/index.md)
