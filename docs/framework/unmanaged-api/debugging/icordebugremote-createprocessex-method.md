---
title: ICorDebugRemote::CreateProcessEx Yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.CreateProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::CreateProcessEx
helpviewer_keywords:
- CreateProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
- ICorDebugRemote::CreateProcessEx method [.NET Framework debugging]
ms.assetid: 41af93c7-e448-4251-8d4d-413d38c635f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d05384af8201fae8cf81650d38c99a5c44e6bd16
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744782"
---
# <a name="icordebugremotecreateprocessex-method"></a>ICorDebugRemote::CreateProcessEx Yöntemi
Hata ayıklayıcısı altında uzak bir makinede bir işlem başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT CreateProcessEx (  
    [in]  ICorDebugRemoteTarget*      pRemoteTarget,  
    [in]  LPCWSTR                     lpApplicationName,  
    [in]  LPWSTR                      lpCommandLine,  
    [in]  LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
    [in]  LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
    [in]  BOOL                        bInheritHandles,  
    [in]  DWORD                       dwCreationFlags,  
    [in]  PVOID                       lpEnvironment,  
    [in]  LPCWSTR                     lpCurrentDirectory,  
    [in]  LPSTARTUPINFOW              lpStartupInfo,  
    [in]  LPPROCESS_INFORMATION       lpProcessInformation,  
    [in]  CorDebugCreateProcessFlags  debuggingFlags,  
    [out] ICorDebugProcess**          ppProcess  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `pRemoteTarget`  
 [in] İşaretçi bir [Icordebugremotetarget arabirimi](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md). İşlem başlatılacak uzak makineye belirlemek için kullanılır.  
  
 `lpApplicationName`  
 [in] Başlatılan işlem tarafından yürütülecek modülü belirtiyorsa null ile sonlandırılmış bir dize işaretçisi. Modül çağırma işleminin bağlamında çalıştırılır.  
  
 `lpCommandLine`  
 [in] Başlatılan işlem tarafından yürütülecek komut satırı belirten bir null ile sonlandırılmış dize işaretçisi.  
  
 `lpProcessAttributes`  
 [in] Uzaktan hata ayıklama için kullanılmamaktadır.  
  
 `lpThreadAttributes`  
 [in] Uzaktan hata ayıklama için kullanılmamaktadır.  
  
 `bInheritHandles`  
 [in] Uzaktan hata ayıklama için kullanılmamaktadır.  
  
 `dwCreationFlags`  
 [in] Uzaktan hata ayıklama için kullanılmamaktadır.  
  
 `lpEnvironment`  
 [in] Yeni işlem için bir ortam bloğuna işaretçi.  
  
 `lpCurrentDirectory`  
 [in] İşlem için geçerli dizin tam yolunu belirtir null ile sonlandırılmış bir dize işaretçisi. Bu parametre null ise, yeni işlem çağırma işlemi aynı geçerli sürücü ve dizine sahip.  
  
 `lpStartupInfo`  
 [in] Uzaktan hata ayıklama için kullanılmamaktadır.  
  
 `lpProcessInformation`  
 [in] Uzaktan hata ayıklama için kullanılmamaktadır.  
  
 `debuggingFlags`  
 [in] Uzaktan hata ayıklama için kullanılmamaktadır.  
  
 `ppProcess`  
 [out] İşlemi temsil eden bir "Icordebugprocess arabirimi" nesnesinin adresi için bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 S_OK  
 Hata ayıklama için uzak makineye ve döndürülen bir "Icordebugprocess arabirimi" işlem başarıyla başlatıldı.  
  
 E_FAIL (veya diğer E_ dönüş kodları)  
 Uzak makinede işlemi başlatmak ve hata ayıklama için bir "Icordebugprocess arabirimi" dönüş oluşturulamıyor.  
  
## <a name="remarks"></a>Açıklamalar  
 Silverlight'ta, karma mod hata ayıklaması desteklenmiyor.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorDebug.idl  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** 4.5, 4, 3.5 SP1  
  
## <a name="see-also"></a>Ayrıca bkz.

- [ICorDebugRemote Arabirimi](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [ICorDebug Arabirimi](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [Hata Ayıklama Arabirimleri](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
