---
title: ICorDebugController::HasQueuedCallbacks Yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugController.HasQueuedCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::HasQueuedCallbacks
helpviewer_keywords:
- HasQueuedCallbacks method [.NET Framework debugging]
- ICorDebugController::HasQueuedCallbacks method [.NET Framework debugging]
ms.assetid: 0d6a1cd9-370b-4462-adbf-e3980e897ea7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d17f51867b64780fca9b21c5f48c88db36343af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748778"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a>ICorDebugController::HasQueuedCallbacks Yöntemi
Tüm yönetilen geri çağırmaları belirtilen iş parçacığı için sıraya alınmış olup olmadığını gösteren bir değer alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `pThread`  
 [in] İş parçacığını temsil eden bir "ICorDebugThread" nesne işaretçisi.  
  
 `pbQueued`  
 [out] Bir değer için bir işaretçi `true` tüm yönetilen geri çağırmaları şu anda, belirtilen iş parçacığı için kuyruğa alınan; Aksi takdirde `false`.  
  
 Null için belirtilirse `pThread` parametresi `HasQueuedCallbacks` döndürür `true` şu anda yönetilen geri çağırmaları herhangi bir iş parçacığı için kuyruğa alındı.  
  
## <a name="remarks"></a>Açıklamalar  
 Geri çağırmaları gönderilen birer birer, her zaman olacaktır [Icordebugcontroller::continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) çağrılır. Aynı anda birden çok hata ayıklama olayları bildirmek istiyorsa, hata ayıklayıcı bu bayrağı kontrol edebilirsiniz.  
  
 Hata ayıklama olaylarını sıralandığında, hata ayıklayıcı hata ayıklanan durumunu emin olmak için tüm kuyruk boşaltma gerekir böylece bunlar zaten, oluştu. (Çağrı `ICorDebugController::Continue` boşaltma kuyruğu için.) Örneğin, sıranın iş parçacığı üzerinde iki hata ayıklama olaylarını içeriyorsa *X*, ve hata ayıklayıcı iş parçacığını askıya alır *X* ilk hata ayıklama olayı ve ardından aramaları `ICorDebugController::Continue`, ikinci hata ayıklama olayı için iş parçacığı *X* iş parçacığını askıya alındı ancak gönderilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.
