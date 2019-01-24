---
title: ICorProfilerInfo2::GetClassFromTokenAndTypeArgs Metodu
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
helpviewer_keywords:
- GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: b25c88f0-71b9-443b-8eea-1c94db0a44b9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0651609e6d2597336ee42ceae752df7e561cd252
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54692658"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a>ICorProfilerInfo2::GetClassFromTokenAndTypeArgs Metodu
Alır `ClassID` belirtilen meta veri belirteci kullanarak türü ve `ClassID` herhangi bir değer türü bağımsız değişkenler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `moduleID`  
 [in] Türü bulunduğu modül kimliği.  
  
 `typeDef`  
 [in] Bir `mdTypeDef` türe başvuran meta veri belirteci.  
  
 `cTypeArgs`  
 [in] Verilen tür için tür parametreleri sayısı. Bu değer, genel olmayan türler için sıfır olmalıdır.  
  
 `typeArgs`  
 [in] Bir dizi `ClassID` değerler, her biri olan bir bağımsız değişken türü. Değerini `typeArgs` NULL olabilir `cTypeArgs` sıfır olarak ayarlanır.  
  
 `pClassID`  
 [out] Bir işaretçi `ClassID` belirtilen türe ait.  
  
## <a name="remarks"></a>Açıklamalar  
 Çağırma `GetClassFromTokenAndTypeArgs` yöntemi ile bir `mdTypeRef` yerine bir `mdTypeDef` meta veri belirteci öngörülemeyen sonuçlara sahip olabilir; çağıranlar çözümlemelidir `mdTypeRef` için bir `mdTypeDef` iletmeden olduğunda.  
  
 Türü zaten yüklü değilse, çağırma `GetClassFromTokenAndTypeArgs` birçok bağlamlarda tehlikeli bir işlemi yüklemeyi tetikler. Örneğin, çalışma zamanı, döngüsel olarak şeyler yükleme girişiminde gibi diğer türleri veya modüller yükleme sırasında bu yöntemi çağırmadan sonsuz bir döngüye neden olabilir.  
  
 Genel olarak, kullanım `GetClassFromTokenAndTypeArgs` önerilmez. Profil Oluşturucular, belirli bir tür için olaylar ilgileniyorsanız depolamanız gerekir `ModuleID` ve `mdTypeDef` , türü ve kullanım [Icorprofilerınfo2::getclassıdınfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) denetlemek için olup olmadığını bir verilen `ClassID` budur İstenen türü.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorProf.idl, CorProf.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.
- [ICorProfilerInfo Arabirimi](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 Arabirimi](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
