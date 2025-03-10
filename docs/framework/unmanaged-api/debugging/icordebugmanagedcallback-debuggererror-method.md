---
title: ICorDebugManagedCallback::DebuggerError Yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.DebuggerError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::DebuggerError
helpviewer_keywords:
- DebuggerError method [.NET Framework debugging]
- ICorDebugManagedCallback::DebuggerError method [.NET Framework debugging]
ms.assetid: 9e983d11-eaf3-4741-b936-29ec456384a3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6abc4893ac99c5ce93a409a8120f090250be57c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759655"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a>ICorDebugManagedCallback::DebuggerError Yöntemi
Ortak dil çalışma zamanı (CLR) bir olaydan işlemeye çalışırken bir hata oluştu, hata ayıklayıcı bildirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `pProcess`  
 [in] Olayın gerçekleştiği işlemini temsil eden bir "ICorDebugProcess" nesneye bir işaretçi.  
  
 `errorHR`  
 [in] Olay işleyicisinden döndürülen HRESULT değerini.  
  
 `errorCode`  
 [in] CLR hata belirten bir tamsayı.  
  
## <a name="remarks"></a>Açıklamalar  
 İşlem hata doğasına bağlı olarak doğrudan modu içine yerleştirilebilir.  
  
 `DebugError` Geri çağırma, hata ayıklayıcıları hata iletisinin kullanıcıya kullanılabilmesini için hata ayıklama Hizmetleri bir hata nedeniyle devre dışı bırakılmış olduğunu gösterir. [Icordebugprocess::GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) çağrısı ancak dahil olmak üzere tüm diğer yöntemler, güvenli olacak [Icordebug::Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), çağrılmamalıdır. Hata ayıklayıcı, işlemleri sonlandırmak için işletim sistemi özelliklerini kullanmanız gerekir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [ICorDebugManagedCallback Arabirimi](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
