---
title: ICorDebugManagedCallback::LogSwitch Yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogSwitch
helpviewer_keywords:
- LogSwitch method [.NET Framework debugging]
- ICorDebugManagedCallback::LogSwitch method [.NET Framework debugging]
ms.assetid: 0ac59d27-783f-4a87-b7a8-baa3ccc54582
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d7432771a7d8eee9cea10f883dd3bd91f5ffb74
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761393"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a>ICorDebugManagedCallback::LogSwitch Yöntemi
Hata ayıklayıcı ortak dil çalışma zamanı (CLR) yönetilen iş parçacığı bir yöntem çağırdı olduğunu bildirir <xref:System.Diagnostics.Switch> sınıfı oluşturmak, değiştirmek veya bir hata ayıklama izleme anahtarı silin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
## <a name="parameters"></a>Parametreler  
 `PAppDomain`  
 [in] Oluşturulan, değiştirilen veya hata ayıklama izleme anahtarı silindi yönetilen iş parçacığı içeren uygulama etki alanını temsil eden bir Icordebugappdomain nesne işaretçisi.  
  
 `pThread`  
 [in] Yönetilen iş parçacığını temsil eden bir Icordebugthread nesne işaretçisi.  
  
 `lLevel`  
 [in] Olay günlüğüne yazılmış açıklayıcı bir ileti önem derecesi belirten bir değer.  
  
 `ulReason`  
 [in] Değerini [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) işlemi belirten numaralandırma hata ayıklama izleme anahtarı gerçekleşen.  
  
 `pLogSwitchName`  
 [in] Hata ayıklama izleme anahtarı adı için bir işaretçi.  
  
 `pParentName`  
 [in] Üst öğesinin hata ayıklama izleme anahtarı adı için bir işaretçi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [ICorDebugManagedCallback Arabirimi](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
