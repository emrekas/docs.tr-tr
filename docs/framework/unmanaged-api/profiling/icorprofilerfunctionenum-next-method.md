---
title: ICorProfilerFunctionEnum::Next Yöntemi
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Next Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Next
helpviewer_keywords:
- ICorProfilerFunctionEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 5ed4aa83-ce56-4b9f-9237-5da7587787fe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d51f26e6d3fa2c37e1588d255f04578dce5bc24
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780296"
---
# <a name="icorprofilerfunctionenumnext-method"></a>ICorProfilerFunctionEnum::Next Yöntemi
Belirtilen bitişik işlev sayısı dizideki geçerli konum Numaralandırıcının başlayan İşlevler, sıralı bir koleksiyonunu alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    COR_PRF_FUNCTION ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
## <a name="parameters"></a>Parametreler  
 `celt`  
 [in] Alınacak işlev sayısı.  
  
 `ids`  
 [out] Bir dizi `COR_PRF_FUNCTION` değerler, her biri alınan bir işlevi temsil eder.  
  
 `pceltFetched`  
 [out] Gerçekte döndürülen işlev sayısı için bir işaretçi `ids` dizisi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem aşağıdaki özel HRESULT'ları yanı sıra HRESULT döndürür yöntemi hatayı gösteren hatalar.  
  
|HRESULT|Açıklama|  
|-------------|-----------------|  
|S_OK|`celt` öğeleri döndürülmedi.|  
|S_FALSE|Az `celt` öğeleri döndürüldü, numaralandırma tamamlandığını gösterir.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorProf.idl, CorProf.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [ICorProfilerFunctionEnum Arabirimi](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [Profil Oluşturma Arabirimleri](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
