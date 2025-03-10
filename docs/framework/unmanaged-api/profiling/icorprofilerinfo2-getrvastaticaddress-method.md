---
title: ICorProfilerInfo2::GetRVAStaticAddress Metodu
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetRVAStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetRVAStaticAddress
helpviewer_keywords:
- GetRVAStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetRVAStaticAddress method [.NET Framework profiling]
ms.assetid: a25a8f8b-5cfa-440d-9376-a1a1c3a9fc11
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fc7b6d1a27faf7bde46305f9c98d98351e6261b6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782268"
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a>ICorProfilerInfo2::GetRVAStaticAddress Metodu
Belirtilen göreli sanal adres (RVA) statik alan adresini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a>Parametreler  
 `classId`  
 [in] İstenen RVA statik alanı içeren sınıf kimliği.  
  
 `fieldToken`  
 [in] İstenen RVA statik alan için meta veri belirteci.  
  
 `ppAddress`  
 [out] Bir işaretçi adresine RVA statik alan.  
  
## <a name="remarks"></a>Açıklamalar  
 `GetRVAStaticAddress` Yöntemi aşağıdakilerden birini döndürebilir:  
  
- Bir CORPROF_E_DATAINCOMPLETE belirtilen statik alanı belirtilen bağlam bir adres değil atandıysa HRESULT.  
  
- Adresleri nesnelerin çöp koleksiyonu yığınında olabilir. Çöp toplamanın ardından, profil oluşturucular geçerli olduğunu varsayın değil için bu adresleri çöp toplamanın ardından geçersiz hale gelebilir.  
  
 Bir sınıfın sınıf oluşturucusu tamamlanmadan önce `GetRVAStaticAddress` bazı statik alanlar zaten başlatıldı ve çöp toplama nesneleri kök dizini değiştirme ancak CORPROF_E_DATAINCOMPLETE tüm kendi statik alanları için döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorProf.idl, CorProf.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [ICorProfilerInfo Arabirimi](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 Arabirimi](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
