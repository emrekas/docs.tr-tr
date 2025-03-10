---
title: ICorDebugProcess5::GetTypeFields Metodu
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeFields
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeFields
helpviewer_keywords:
- GetTypeFields method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeFields method [.NET Framework debugging]
ms.assetid: 6a0ad3ee-dacb-47e9-abae-4536bcc4804b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d413b17da0b6f241f9078bfeb3bd035d4d07a81
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767632"
---
# <a name="icordebugprocess5gettypefields-method"></a>ICorDebugProcess5::GetTypeFields Metodu
Bir türe ait alanları hakkında bilgi sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],   
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `id`  
 [in] Alan bilgilerini alınan tür tanımlayıcısı.  
  
 `celt`  
 [in] Sayısını [cor_fıeld](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) olan alan bilgilerdir alınacak nesne.  
  
 `fields`  
 [out] Bir dizi [cor_fıeld](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) türe ait alanları hakkında bilgi sağlayan nesneleri.  
  
 `pceltNeeded`  
 [out] Bir işaretçi sayısına [cor_fıeld](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) bulunan nesneleri `fields`.  
  
## <a name="remarks"></a>Açıklamalar  
 `celt` Alan bilgilerini doldurmak için yöntemi kullanan alanların sayısını belirten bir parametre `fields`, değerine karşılık gelmelidir `COR_TYPE_LAYOUT::numFields` alan.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [ICorDebugProcess5 Arabirimi](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Hata Ayıklama Arabirimleri](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
