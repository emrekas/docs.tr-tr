---
title: ICorDebugInternalFrame2::IsCloserToLeaf Yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.IsCloserToLeaf Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf
helpviewer_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf method [.NET Framework debugging]
- IsCloserToLeaf method [.NET Framework debugging]
ms.assetid: c1d3d1eb-8370-4f25-8297-3bd262b4740a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0e72d15ab4ca9b4468efb2a671022f30bfb3cc6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759948"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a>ICorDebugInternalFrame2::IsCloserToLeaf Yöntemi
Denetler olmadığını `this` iç çerçeve belirtilen Icordebugframe nesneden yaprağa yakın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a>Parametreler  
 `pFrameToCompare`  
 [in] Karşılaştırma için bir işaretçi `ICorDebugFrame` nesne.  
  
 `pIsCloser`  
 [out] `true` varsa `this` iç çerçeve yaprağa tarafından belirtilen çerçeve daha yakından `pFrameToCompare`; Aksi takdirde `false`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem aşağıdaki özel HRESULT'ları yanı sıra HRESULT döndürür yöntemi hatayı gösteren hatalar.  
  
|HRESULT|Açıklama|  
|-------------|-----------------|  
|S_OK|Karşılaştırma başarıyla gerçekleştirildi.|  
|E_FAIL|Karşılaştırma gerçekleştirilemedi.|  
|E_INVALIDARG|`pFrameToCompare` veya `pIsCloser` null.|  
  
## <a name="remarks"></a>Açıklamalar  
 `IsCloserToLeaf` İç çerçeveler yığında diğer çerçevelerle Interleaving ilkesini uygulamak için kullanılabilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [ICorDebugInternalFrame2 Arabirimi](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [Hata Ayıklama Arabirimleri](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Hata Ayıklama](../../../../docs/framework/unmanaged-api/debugging/index.md)
