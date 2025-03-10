---
title: ICorProfilerInfo::SetEnterLeaveFunctionHooks Yöntemi
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEnterLeaveFunctionHooks
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEnterLeaveFunctionHooks
helpviewer_keywords:
- SetEnterLeaveFunctionHooks method [.NET Framework profiling]
- ICorProfilerInfo::SetEnterLeaveFunctionHooks method [.NET Framework profiling]
ms.assetid: 72399636-c219-4ffd-8ac8-39432c9d4641
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1b6f53d5747eca00b898b2cde66d75764ca490cf
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772098"
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a>ICorProfilerInfo::SetEnterLeaveFunctionHooks Yöntemi
Profil Oluşturucu uygulanan işlevleri "enter", "Ayrıl" ve "tailcall" hooks yönetilen işlevlerin çağrılmasına belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
## <a name="parameters"></a>Parametreler  
 `pFuncEnter`  
 [in] Bir işaretçi olarak kullanılmak üzere uygulamaya [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) geri çağırma.  
  
 `pFuncLeave`  
 [in] Bir işaretçi olarak kullanılmak üzere uygulamaya [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) geri çağırma.  
  
 `pFuncTailcall`  
 [in] Bir işaretçi olarak kullanılmak üzere uygulamaya [FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) geri çağırma.  
  
## <a name="remarks"></a>Açıklamalar  
 .NET Framework sürüm 1.0, her işlev işaretçisi, karşılık gelen bir geri çağırma devre dışı bırakmak için null olabilir.  
  
 Bir kerede yalnızca bir dizi geri çağırmaları etkin olabilir. Bu nedenle, her ikisi de bir profil oluşturucu çağırırsa `SetEnterLeaveFunctionHooks` ve [Icorprofilerınfo2::setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), ardından `SetEnterLeaveFunctionHooks2` önceliklidir.  
  
 `SetEnterLeaveFunctionHooks` Yöntemi yalnızca profil oluşturucu çağrılabilir [Icorprofilercallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) geri çağırma.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorProf.idl, CorProf.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [ICorProfilerInfo Arabirimi](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
