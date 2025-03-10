---
title: CorBindToRuntimeByCfg İşlevi
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeByCfg
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeByCfg
helpviewer_keywords:
- CorBindToRuntimeByCfg function [.NET Framework hosting]
ms.assetid: ded1e492-a782-4185-9c66-709e421c1782
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8f5e9a909a752dd8dc70bfc1c683b4611715f31
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767968"
---
# <a name="corbindtoruntimebycfg-function"></a>CorBindToRuntimeByCfg İşlevi
Ortak dil çalışma zamanı (CLR), bir XML dosyasından okunan sürüm bilgilerini kullanarak bir işlem içine yükler.  
  
 Bu işlev .NET Framework 4'te kullanım dışıdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT CorBindToRuntimeByCfg (  
    [in]  IStream     *pCfgStream,  
    [in]  DWORD        reserved,  
    [in]  DWORD        startupFlags,  
    [in]  REFCLSID     rclsid,  
    [in]  REFIID       riid,   
    [out] LPVOID FAR*  ppv  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `pCfgStream`  
 [in] Bir işaretçi bir `IStream` XML dosyasını okuyan bir nesne.  
  
 `reserved`  
 [in] Gelecekte kullanılmak üzere ayrılmış. Değeri olarak 0 (sıfır) kullanın.  
  
 `startupFlags`  
 [in] Değerini [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) CLR başlangıç davranışını belirten sabit listesi.  
  
 `rclsid`  
 [in] `CLSID` Ya da uygulayan yardımcı sınıf, [Icorruntimehost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) veya [Iclrruntimehost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) arabirimi. Desteklenen değerler: clsıd_corruntimehost veya clsıd_clrruntimehost şunlardır.  
  
 `riid`  
 [in] `IID` Herhangi birinin `ICorRuntimeHost` veya `ICLRRuntimeHost` arabirimi. Desteklenen değerler: ııd_ıcorruntimehost veya ııd_ıclrruntimehost şunlardır.  
  
 `ppv`  
 [out] Döndürülen arabirim adresi için bir işaretçi.  
  
## <a name="remarks"></a>Açıklamalar  
 XML dosyasının biçimi sonra standart uygulama yapılandırma dosyasına modellenir. XML dosyaları hakkında daha fazla bilgi için bkz. [yapılandırma dosyası şeması](../../../../docs/framework/configure-apps/file-schema/index.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** MSCorEE.h  
  
 **Kitaplığı:** MSCorEE.dll  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [CorBindToCurrentRuntime İşlevi](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [CorBindToRuntime İşlevi](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [CorBindToRuntimeEx İşlevi](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [CorBindToRuntimeHost İşlevi](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [ICorRuntimeHost Arabirimi](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Kullanım Dışı CLR Barındırma İşlevleri](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
