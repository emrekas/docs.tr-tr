---
title: ICorProfilerThreadEnum::Clone Yöntemi
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Clone method [.NET Framework profiling]
ms.assetid: 5a278bc9-88e2-4c69-b035-9d550dd77081
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 022d0d9c86e4b3b9924b8a486166d8ce3b71e42c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781187"
---
# <a name="icorprofilerthreadenumclone-method"></a>ICorProfilerThreadEnum::Clone Yöntemi
Bu bir kopyasını bir arabirim işaretçisi alır [Icorprofilerthreadenum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `ppEnum`  
 [out] Sırayla bu kopyasını işaret eden bir arabirim işaretçisi için bir işaretçi [Icorprofilerthreadenum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) arabirimi. Numaralandırıcı kopyasını, bu Numaralandırıcının listesinden kendi sıralaması durumu korur. Ancak, kopyanın ilk imleç konumu numaralandırıcıyı Bu geçerli imleç konumundan aynıdır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorProf.idl, CorProf.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Icorprofilerthreadenum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [Profil Oluşturma Arabirimleri](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
