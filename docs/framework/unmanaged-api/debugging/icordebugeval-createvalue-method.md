---
title: ICorDebugEval::CreateValue Yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CreateValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CreateValue
helpviewer_keywords:
- ICorDebugEval::CreateValue method [.NET Framework debugging]
- CreateValue method [.NET Framework debugging]
ms.assetid: 9a1c0b47-6f10-4fcb-844a-4ab2d7990140
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ada3a06a2beb8f21c3e24665c0f1f8e7c48515f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752948"
---
# <a name="icordebugevalcreatevalue-method"></a>ICorDebugEval::CreateValue Yöntemi
Belirtilen türde bir değer sıfır ya da null bir başlangıç değeriyle birlikte oluşturur.  
  
 Bu yöntem .NET Framework 2.0 sürümünde artık kullanılmıyor. Kullanım [Icordebugeval2::createvaluefortype](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) yerine.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `elementType`  
 [in] Değerini [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) değerin türünü belirten sabit listesi.  
  
 `pElementClass`  
 [in] İşaretçi bir [Icordebugclass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) değerinin sınıf türü bir basit türü değilse belirten nesne.  
  
 `ppValue`  
 [out] İşaretçi adresine "ICorDebugValue" nesnenin değerini temsil eder.  
  
## <a name="remarks"></a>Açıklamalar  
 `CreateValue` oluşturur bir `ICorDebugValue` bir işlev değerlendirmesini kullanarak verilen tür için tek amacı, nesne. Bu değer nesnesi kullanıcı sabitleri parametre olarak geçirmek için kullanılabilir.  
  
 Değerin türü bir basit türü ise, ilk değeri sıfırdır veya null. Kullanım [Icordebuggenericvalue::SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) türü basit tür değeri ayarlamak için.  
  
 Varsa değerini `elementType` ELEMENT_TYPE_CLASS, olan "ICorDebugReferenceValue" Al (döndürdü `ppValue`) temsil eden null Nesne başvurusu. Bu nesne, nesne başvuru parametreleri olan bir işlev değerlendirmesi için null değeri geçirmeye izin kullanabilirsiniz. Ayarlayamazsınız `ICorDebugValue` şey; bu her zaman boş kalır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** 1.1, 1.0  
  
## <a name="see-also"></a>Ayrıca bkz.

- [CreateValueForType Yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)
- [Icordebugeval arabirimi](icordebugeval-interface.md)
