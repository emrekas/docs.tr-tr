---
title: ICLRDataEnumMemoryRegions::EnumMemoryRegions Yöntemi
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegions.EnumMemoryRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions
helpviewer_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions method [.NET Framework debugging]
- EnumMemoryRegions method [.NET Framework debugging]
ms.assetid: 22d2e339-f174-40b5-a478-0b744501566f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 489ea22e17178398f53e103da04a47e8fe15a936
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738927"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a>ICLRDataEnumMemoryRegions::EnumMemoryRegions Yöntemi
Belirtilen bellek alanları numaralandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `callback`  
 [in] Bir işaretçi bir [Iclrdataenummemoryregionscallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) sonucun hata ayıklayıcı bildirmek için numaralandırılan her bellek bölge için bu yöntem tarafından çağrılan örnek.  
  
 Bile hata geri çağırma gösterir bellek bölümlerinin listelenmeye devam eder.  
  
 `miniDumpFlags`  
 [in] Kullanılmıyor.  
  
 `clrFlags`  
 [in] Değerini [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) sıralanması bellek bölümlerinin belirten sabit listesi.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntemde belirtilen [Iclrdataenummemoryregionscallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) sonuçlarının çağrıyı yapana bunu bildirmesi örneği.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** ClrData.idl, ClrData.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [ICLRDataEnumMemoryRegions Arabirimi](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)
