---
title: ICorDebugEval::NewArray Yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewArray
helpviewer_keywords:
- NewArray method [.NET Framework debugging]
- ICorDebugEval::NewArray method [.NET Framework debugging]
ms.assetid: cc79a67d-5368-434d-a943-209db90491b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9597d05e46c2d41ab1f24a073c028561e944fb59
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753033"
---
# <a name="icordebugevalnewarray-method"></a>ICorDebugEval::NewArray Yöntemi
Belirtilen öğe türü ve boyut yeni bir dizi ayırır.  
  
 Bu yöntem .NET Framework 2.0 sürümünde artık kullanılmıyor. Kullanım [Icordebugeval2::newparameterizedarray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) yerine.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `elementType`  
 [in] Dizinin öğe türü belirtir CorElementType sabit listesi değeri.  
  
 `pElementClass`  
 [in] Öğe sınıfı belirten Icordebugclass nesnesine bir işaretçi. Bu değer, öğe türü basit bir tür ise null olabilir.  
  
 `rank`  
 [in] Dizinin boyut sayısı. .NET Framework 2.0 sürümünde, bu değeri 1 olmalı.  
  
 `dims`  
 [in] Dizinin her boyutunun bayt cinsinden boyutu.  
  
 `lowBounds`  
 [in] İsteğe bağlı. Dizinin her boyutunun alt sınırı. Bu değer belirtilmezse, her boyut için alt sınırı sıfır varsayılır.  
  
## <a name="remarks"></a>Açıklamalar  
 Dizinin her zaman iş parçacığı gerçekleştirmektedir uygulama etki alanında oluşturulur.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** 1.1, 1.0
