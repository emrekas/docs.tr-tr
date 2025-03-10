---
title: ICorDebugProcess::ClearCurrentException Yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ClearCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ClearCurrentException
helpviewer_keywords:
- ClearCurrentException method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::ClearCurrentException method [.NET Framework debugging]
ms.assetid: 9e02ee1a-e495-4578-bfb5-b946274bede7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ad7dd3ae0e547933fdf7d579116dccc62ae579c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766150"
---
# <a name="icordebugprocessclearcurrentexception-method"></a>ICorDebugProcess::ClearCurrentException Yöntemi
Verilen iş parçacığı üzerinde geçerli yönetilmeyen özel durum temizler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a>Parametreler  
 `threadID`  
 [in] Geçerli yönetilmeyen özel durum temizlenir iş parçacığı kimliği.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağırmadan önce çağrı [Icordebugcontroller::continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) ne zaman bir iş parçacığı bildirdi bir yönetilmeyen özel durum hata ayıklanan tarafından yoksayılacak. Bu, hem bekleyen bant (IB) hem de verilen iş parçacığı üzerinde bant dışı (OOB) olaylarını temizler. Tüm OOB kesme noktaları ve tek adımlı özel durumları otomatik olarak temizlenir.  
  
 Kullanım [Icordebugthread2::ınterceptcurrentexception](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) geçerli ele alınması için bir iş parçacığında özel durum yönetilen.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
