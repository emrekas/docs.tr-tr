---
title: ICorDebugCode::GetCode Metodu
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetCode
helpviewer_keywords:
- ICorDebugCode::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7137e3d1-1dad-48d8-8c37-16ac816534d3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e18097dd380ee354e5652886544d40da074f1230
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747629"
---
# <a name="icordebugcodegetcode-method"></a>ICorDebugCode::GetCode Metodu
Ayrıştırma için biçimlendirilmiş belirtilen işlevi tüm kod alır. Bu yöntem .NET Framework 2.0 sürümünde kullanım dışı bırakıldı. Kullanım [Icordebugcode2::getcodechunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) yerine.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetCode (  
    [in] ULONG32     startOffset,   
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `startOffset`  
 [in] İşlevin başlangıcına uzaklık.  
  
 `endOffset`  
 [in] İşlevin sonuna uzaklığı.  
  
 `cBufferAlloc`  
 [in] Boyutu `buffer` dizi kod, döndürülecek içine.  
  
 `buffer`  
 [out] Dizi içine kod döndürülür.  
  
 `pcBufferSize`  
 [out] Döndürülen bayt sayısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Birden çok öbeklere işlevin kodunu bölünmüş, bunlar, yerel uzaklık artan sırada bitiştirilir. Yönerge sınırları denetlenmez.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** 1.1, 1.0  
  
## <a name="see-also"></a>Ayrıca bkz.

- [GetCodeChunks Yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)
