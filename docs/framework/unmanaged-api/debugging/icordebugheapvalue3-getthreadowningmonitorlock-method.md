---
title: ICorDebugHeapValue3::GetThreadOwningMonitorLock Metodu
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetThreadOwningMonitorLock
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetThreadOwningMonitorLock
helpviewer_keywords:
- GetThreadOwningMonitorLock method [.NET Framework debugging]
- ICorDebugHeapValue3::GetThreadOwningMonitorLock method [.NET Framework debugging]
ms.assetid: e06fc19d-2cf4-4cad-81a3-137a68af8969
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4322a7e23c7085dadb3b2df6c1f72125aa685cef
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756611"
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a>ICorDebugHeapValue3::GetThreadOwningMonitorLock Metodu
Bu nesne izleme kilidi sahibi yönetilen iş parçacığı döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `ppThread`  
 [out] Bu nesne izleme kilidi sahibi yönetilen iş parçacığı.  
  
 `pAcquisitionCount`  
 [out] Bu iş parçacığı sahipsiz için döndürmeden önce kilidi zorunda sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem aşağıdaki özel HRESULT'ları yanı sıra HRESULT döndürür yöntemi hatayı gösteren hatalar.  
  
|HRESULT|Açıklama|  
|-------------|-----------------|  
|S_OK|Yöntem başarıyla tamamlandı.|  
|S_FALSE|Yönetilen iş parçacığı bu nesne izleme kilidi sahibi.|  
  
## <a name="exceptions"></a>Özel Durumlar  
  
## <a name="remarks"></a>Açıklamalar  
 Yönetilen iş parçacığı bu nesne izleme kilidi sahipse:  
  
- Yöntem S_OK döndürür.  
  
- İş parçacığı çıkana kadar iş parçacığı nesne geçerli değil.  
  
 Yönetilen iş parçacığı bu nesne izleme kilidi sahipse `ppThread` ve `pAcquisitionCount` aynıdır, ve yöntem S_FALSE döndürür.  
  
 Varsa `ppThread` veya `pAcquisitionCount` geçerli bir işaretçi değil sonuç tanımsızdır.  
  
 Yöntemi, varsa, iş parçacığı bu nesne izleme kilidi sahibi olan belirlenemiyor, bir hata oluşursa hata olduğunu gösteren bir HRESULT döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Hata Ayıklama Arabirimleri](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Hata Ayıklama](../../../../docs/framework/unmanaged-api/debugging/index.md)
