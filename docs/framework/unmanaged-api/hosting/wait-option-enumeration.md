---
title: WAIT_OPTION Numaralandırması
ms.date: 03/30/2017
api_name:
- WAIT_OPTION
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAIT_OPTION
helpviewer_keywords:
- WAIT_OPTION enumeration [.NET Framework hosting]
ms.assetid: 962fc293-8ded-4b3b-90ce-2c21a4f1b244
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eda866c1a1f1f69f0d042ccfde3dfad293df9b37
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776513"
---
# <a name="waitoption-enumeration"></a>WAIT_OPTION Numaralandırması
Bir konak ortak dil çalışma zamanı (CLR) blok tarafından istenen işlem, eylemde bulunmalısınız gösteren değerleri içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a>Üyeler  
  
|Üye|Açıklama|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|Konak, CLR çağırırsa görev sunucuyu uyandırdı bildirir [Ihosttask::alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) yöntemi.|  
|`WAIT_MSGPUMP`|Ana iş parçacığı engellenmiş duruma gelirse, geçerli işletim sistemi iş parçacığı üzerinde iletileri göndermelidir bildirir. Çalışma zamanı, yalnızca bu değeri belirtir. bir <xref:System.Threading.ApartmentState.STA> iş parçacığı.|  
|`WAIT_NOTINDEADLOCK`|Konak, konak tarafından belirtilen eşitleme isteği ayrıştırılamayan bildirir. Diğer bir deyişle, konak döndüremez `HOST_E_DEADLOCK`.|  
  
## <a name="remarks"></a>Açıklamalar  
 [Ihosttaskmanager::Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) ve [Ihosttaskmanager::switchtotask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) yöntemleri hem bu türde bir parametre alır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** MSCorEE.h  
  
 **Kitaplığı:** MSCorEE.dll  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Barındırma Sabit Listeleri](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
