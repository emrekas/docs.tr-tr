---
title: ICorProfilerInfo::GetFunctionFromIP Yöntemi
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionFromIP
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionFromIP
helpviewer_keywords:
- GetFunctionFromIP method [.NET Framework profiling]
- ICorProfilerInfo::GetFunctionFromIP method [.NET Framework profiling]
ms.assetid: f069802a-198f-46dd-9f09-4f77adffc9ba
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 23fb9c58f2eac904b63294434654f3caf1ba9f41
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107971"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a>ICorProfilerInfo::GetFunctionFromIP Yöntemi
Yönetilen kod yönerge işaretçisi eşleyen bir `FunctionID`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="parameters"></a>Parametreler  
 `ip`  
 [in] Yönetilen kodda yönerge işaretçisi.  
  
 `pFunctionId`  
 [out] Döndürülen işlevin kimliği.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorProf.idl, CorProf.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [ICorProfilerInfo Arabirimi](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
