---
title: NOTIFY_FILTER Numaralandırması
ms.date: 03/30/2017
api_name:
- NOTIFY_FILTER
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- NOTIFY_FILTER
helpviewer_keywords:
- NOTIFY_FILTER enumeration [.NET Framework debugging]
ms.assetid: 4789d08f-8683-45d3-ac30-73d48c61e470
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 09c36dd65c8a4202f13d362668f74cd9a362e35a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744361"
---
# <a name="notifyfilter-enumeration"></a>NOTIFY_FILTER Numaralandırması
Hata ayıklayıcı işlevleri için geri çağırmaları tanımlar. Daha fazla bilgi için [Inotifysource2::setnotifyfilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) yöntemi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum tagNOTIFY_FILTER  
{  
    NOTIFY_FILTER_ONSYNCCALLOUT    = 0x1,  
    NOTIFY_FILTER_ONSYNCCALLENTER  = 0x2,  
    NOTIFY_FILTER_ONSYNCCALLEXIT   = 0x4,  
    NOTIFY_FILTER_ONSYNCCALLRETURN = 0x8,  
    NOTIFY_FILTER_ALLSYNC = NOTIFY_FILTER_ONSYNCCALLOUT | NOTIFY_FILTER_ONSYNCCALLENTER | NOTIFY_FILTER_ONSYNCCALLEXIT | NOTIFY_FILTER_ONSYNCCALLRETURN,  
    NOTIFY_FILTER_ALL              = 0xffffffff,  
    NOTIFY_FILTER_NONE             = 0  
};  
```  
  
## <a name="members"></a>Üyeler  
  
|Üye|Açıklama|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|Bildiren [Inotifysink2::onsynccallout](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) yöntemi çağrılacak.|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|Bildiren [Inotifysink2::onsynccallenter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) yöntemi çağrılacak.|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|Bildiren [Inotifysink2::onsynccallexit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) yöntemi çağrılacak.|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|Bildiren [Inotifysink2::onsynccallreturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) yöntemi çağrılacak.|  
|`NOTIFY_FILTER_ALLSYNC`|Bildiren tüm [Inotifysink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) yöntemleri çağrılacak.|  
|`NOTIFY_FILTER_ALL`|Tüm mevcut ve gelecekteki bildirimleri etkinleştirir.|  
|`NOTIFY_FILTER_NONE`|Hiçbir bildirim yöntemi çağrılmalıdır gösterir.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Üst bilgi:** ProtocolNotify2.idl  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Tanılama Simge Deposu Sabit Listeleri](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
