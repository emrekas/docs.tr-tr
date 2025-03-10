---
title: ICorDebugClass::GetStaticFieldValue Yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 56e718b4-fabd-418b-a5b3-3cc33c745683
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7649d91ca2b654952d1d5ab0d45f7903d3c46a32
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745546"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a>ICorDebugClass::GetStaticFieldValue Yöntemi
Belirtilen statik alan değerini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `fieldDef`  
 [in] Bir alan `Def` alınacak alana başvuran bir belirteç.  
  
 `pFrame`  
 [in] İş parçacığı, içerik ve uygulama etki alanı statikler arasında ayırt etmek için kullanılacak çerçeveyi temsil eden bir Icordebugframe nesne işaretçisi.  
  
 Statik alan bir iş parçacığı, bir bağlam veya bir uygulama etki alanına göre çerçeve uygun değeri belirler.  
  
 `ppValue`  
 [out] Statik alan değerini temsil eden bir Icordebugvalue nesnenin adresi için bir işaretçi.  
  
## <a name="remarks"></a>Açıklamalar  
 Parametreli türler için belirli bir örneğini oluşturmada göreli statik alan değerdir. Bu nedenle, sınıf oluşturucusu tür parametrelerinin uzun sürerse <xref:System.Type>, çağrı [Icordebugtype::getstaticfieldvalue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) yerine `ICorDebugClass::GetStaticFieldValue`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
