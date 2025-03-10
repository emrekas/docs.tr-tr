---
title: ICLRRuntimeInfo::GetDefaultStartupFlags Metodu
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aeb4c9935d5e9e4063497dd56276edfe6e62752a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765591"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a>ICLRRuntimeInfo::GetDefaultStartupFlags Metodu
Başlangıç bayrakları ve çalışma zamanı'nı başlatmak için kullanılacak ana bilgisayar yapılandırma dosyası alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
## <a name="parameters"></a>Parametreler  
 `pdwStartupFlags`  
 [out] Şu anda ayarlanmış ana başlangıç bayrakları için bir işaretçi.  
  
 `pwzHostConfigFile`  
 [out] Dizin yolu geçerli ana bilgisayar yapılandırma dosyasının bir işaretçi.  
  
 `pcchHostConfigFile`  
 [out içinde] Giriş üzerinde boyutunu `pwzHostConfigFile`, arabellek taşması önlemek için. Varsa `pwzHostConfigFile` olduğu null yöntem gerekli boyutunu döndürür `pwzHostConfigFile` ön ayırması için.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem aşağıdaki özel HRESULT döndürür yöntemi hatayı belirtmek HRESULT hata yanı sıra.  
  
|HRESULT|Açıklama|  
|-------------|-----------------|  
|S_OK|Yöntem başarıyla tamamlandı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem varsayılan bayrak değerleri döndürür (`STARTUP_CONCURRENT_GC` ve `NULL`), veya önceki bir çağrı tarafından sağlanan değerleri [Iclrruntimeınfo::setdefaultstartupflags yöntemi](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), veya herhangi biri tarafından ayarlanan değerlerle `CorBind*` Bu çalışma zamanına bağlıysa yöntemleri.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** MetaHost.h  
  
 **Kitaplığı:** Bir kaynak olarak MSCorEE.dll dahil  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [ICLRRuntimeInfo Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [Barındırma Arabirimleri](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Barındırma](../../../../docs/framework/unmanaged-api/hosting/index.md)
