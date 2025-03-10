---
title: ICorProfilerInfo2::GetStaticFieldInfo Yöntemi
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStaticFieldInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo method [.NET Framework profiling]
- GetStaticFieldInfo method [.NET Framework profiling]
ms.assetid: fc663e76-e23f-49a8-bdd5-52cdf1a3b2b3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 36cb8d5865cdc4c1c8e34671010ede25d531bacf
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782251"
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a>ICorProfilerInfo2::GetStaticFieldInfo Yöntemi
Belirtilen alan için geçerli bir statik türünü belirten bir değer alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
## <a name="parameters"></a>Parametreler  
 `classId`  
 [in] Statik alan tanımlandığı sınıfın Kimliğidir.  
  
 `fieldToken`  
 [in] Statik alan için meta veri belirteci.  
  
 `pFieldInfo`  
 [out] Bir işaretçi değerini [cor_prf_statıc_type](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) numaralandırma belirten belirtilen alan statik olmasına ve bu nedenle, statik tür, alan için geçerli olup olmadığını.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu bilgiler, hangi işlevin adresi statik alanı alma çağrısı belirlemek için kullanılabilir.  
  
 Profil Oluşturucu kodu yine de, aslında bir adresi olduğundan emin olmak statik bir alan için meta verileri denetlemeniz gerekir. Statik değişmez değerler (diğer bir deyişle, sabitler) yalnızca meta verilerde mevcut ve bir adresi yok.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorProf.idl, CorProf.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [ICorProfilerInfo Arabirimi](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 Arabirimi](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
