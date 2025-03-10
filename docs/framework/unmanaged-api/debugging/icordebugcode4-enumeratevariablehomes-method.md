---
title: ICorDebugCode4::EnumerateVariableHomes yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugCode4.EnumerateVariableHomes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0e6acdf6996f437c85b629b0af886287b1aef03
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748564"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a>ICorDebugCode4::EnumerateVariableHomes yöntemi
Bir numaralandırıcı bir işlevde yerel değişkenleri ve bağımsız değişkenleri alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `ppEnum`  
 Adresine bir işaretçi bir [Icordebugvariablehomeenum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) arabirimi nesnesi yerel değişkenleri ve bir işlevde bağımsız değişken için bir numaralandırıcı.  
  
## <a name="remarks"></a>Açıklamalar  
 [Icordebugvariablehomeenum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) arabirimi nesnedir listeleme olanak tanıyan "ICorDebugEnum" arabirimden türetilmiş standart bir numaralandırıcı [Icordebugvariablehome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) nesneleri. Birden çok koleksiyon bulunabilir [Icordebugvariablehome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) işlevi farklı noktalarda farklı havaalanlarından oluşturulduysa nesneleri aynı yuva veya bağımsız değişkenin dizini.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [ICorDebugCode4 Arabirimi](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)
- [Hata Ayıklama Arabirimleri](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
