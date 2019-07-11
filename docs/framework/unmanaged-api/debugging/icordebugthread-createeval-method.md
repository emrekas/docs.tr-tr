---
title: ICorDebugThread::CreateEval Yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateEval
helpviewer_keywords:
- CreateEval method [.NET Framework debugging]
- ICorDebugThread::CreateEval method [.NET Framework debugging]
ms.assetid: 36605067-33d3-4579-9c72-fb0e551ab0f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 41bd4c0bb4e84b6d6f267e24808baafa57f71882
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771111"
---
# <a name="icordebugthreadcreateeval-method"></a>ICorDebugThread::CreateEval Yöntemi
Toplar ve bu Icordebugthread işlevselliğini kullanıma sunan bir Icordebugeval nesnesi oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `ppEval`  
 [out] Adresine bir işaretçi bir `ICorDebugEval` nesnesini toplar ve bu iş parçacığı işlevini gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 Değerlendirme nesne yeni zinciri kendi hesaplama gerçekleştirmeden önce iş parçacığı üzerinde bildirim yapar. Bu değerlendirme tamamlanana kadar iş parçacığı üzerinde şu anda gerçekleştirilmekte olan hesaplamayı kesintiye uğratır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
