---
title: ICorProfilerInfo::SetILFunctionBody Yöntemi
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerInfo::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method [.NET Framework profiling]
ms.assetid: b159c712-00f4-4fc7-a990-40bf9f642e8f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: abe0a0fc177c9ec89f4621e7defb5330c911034b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778611"
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a>ICorProfilerInfo::SetILFunctionBody Yöntemi
Belirtilen modüldeki belirtilen işlev gövdesinin yerini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a>Parametreler  
 `moduleId`  
 [in] İşlev bulunduğu modül kimliği.  
  
 `methodid`  
 [in] İşlev gövdesi değiştirmek istediğiniz belirteç.  
  
 `pbNewILMethodHeader`  
 [in] İşlev için yeni üstbilgi.  
  
## <a name="remarks"></a>Açıklamalar  
 `SetILFunctionBody` Yöntemi noktaları için yeni işlev gövdesi ve gerektiği gibi iç veri yapılarını ayarlar böylece göreli sanal adres meta verileri işlevin yerini alır.  
  
 `SetILFunctionBody` Yöntemi, üzerinde hiçbir zaman just-in-time (JIT) derleyicisi tarafından derlenen işlevler çağrılabilir.  
  
 Kullanım [Icorprofilerınfo::getılfunctionbodyallocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md) arabellek uyumlu olmasını sağlamak yeni yöntem için alan ayırmak için yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorProf.idl, CorProf.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [ICorProfilerInfo Arabirimi](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
