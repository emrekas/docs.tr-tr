---
title: ICorProfilerInfo4::RequestRevert Yöntemi
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.RequestRevert
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::RequestRevert
helpviewer_keywords:
- RequestRevert method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::RequestRevert method [.NET Framework profiling]
ms.assetid: 70261da5-5933-4e25-9de0-ddf51cba56cc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5e74cb663f968cc9b1b04a912307e3b4a12e86d4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748666"
---
# <a name="icorprofilerinfo4requestrevert-method"></a>ICorProfilerInfo4::RequestRevert Yöntemi
Tüm örneklerinin özgünlüğünü belirtilen işleve döner.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT RequestRevert (  
   [in] ULONG    cFunctions,  
   [in, size_is(cFunctions)]  ModuleID    moduleIds[],  
   [in, size_is(cFunctions)]  mdMethodDef methodIds[],  
   [out, size_is(cFunctions)]  HRESULT status[]);  
```  
  
## <a name="parameters"></a>Parametreler  
 `cFunctions`  
 [in] Geri almak için işlev sayısı.  
  
 `moduleIds`  
 [in] Belirtir `moduleId` kısmı (`module`, `methodDef`) geri döndürülmesi işlevleri tanımlamak çiftleri.  
  
 `methodIds`  
 [in] Belirtir `methodId` kısmı (`module`, `methodDef`) geri döndürülmesi işlevleri tanımlamak çiftleri.  
  
 `status`  
 [out] Bu konunun ilerleyen bölümlerindeki "Durumu HRESULTs" bölümünde listelenen HRESULTs dizisi. Başarı veya başarısızlık paralel dizilerde belirtilen her bir işlevin geri çalışılırken, her HRESULT gösterir `moduleIds` ve `methodIds`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem aşağıdaki özel HRESULT'ları yanı sıra HRESULT döndürür yöntemi hatayı gösteren hatalar.  
  
|HRESULT|Açıklama|  
|-------------|-----------------|  
|S_OK|Tüm istekleri dönmek için girişimde bulunuldu; Ancak, hangi işlevlerin başarıyla geri alındığını belirlemek için döndürülen durum dizisi denetlenmesi gerekir.|  
|CORPROF_E_CALLBACK4_REQUIRED|Profil Oluşturucu uygulamalıdır [Icorprofilercallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) desteklenmesi, bu çağrı için arabirim.|  
|CORPROF_E_REJIT_NOT_ENABLED|JIT yeniden derlemesi etkin değil. Başlatma sırasında JIT yeniden derlemesi kullanarak etkinleştirmelisiniz [Icorprofilerınfo::seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) ayarlanacak yöntemi `COR_PRF_ENABLE_REJIT` bayrağı.|  
|E_INVALIDARG|`cFunctions` 0 ' dır veya `moduleIds` veya `methodIds` olduğu `NULL`.|  
|E_OUTOFMEMORY|CLR, belleği tükendiğinden, isteği tamamlayamadı.|  
  
## <a name="status-hresults"></a>Durum HRESULTS  
  
|Durum dizi HRESULT|Açıklama|  
|--------------------------|-----------------|  
|S_OK|İlgili işlevi başarıyla geri döndürüldü.|  
|E_INVALIDARG|`moduleID` Veya `methodDef` parametresi `NULL`.|  
|CORPROF_E_DATAINCOMPLETE|Modül henüz tam yüklü değil veya yüklenmemiş sürecinde olduğundan.|  
|CORPROF_E_MODULE_IS_DYNAMIC|Belirtilen modül dinamik olarak oluşturulan (örneğin `Reflection.Emit`). Bu nedenle, bu yöntem tarafından desteklenmiyor.|  
|CORPROF_E_ACTIVE_REJIT_REQUEST_NOT_FOUND|CLR, karşılık gelen bir etkin yeniden derleme isteği bulunamadığından belirtilen işlevi döndürülemedi. Yeniden derleme hiçbir zaman istenen ya da işlev zaten döndürüldü.|  
|Diğer|İşletim sistemi CLR denetimin dışında kalan bir hata döndürdü. Örneğin, belleğin bir sayfası erişim korumasını değiştirmek için bir sistem çağrısı başarısız olursa, işletim sistemi hata görüntülenir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Herhangi bir revereted işlevi örnekleri olarak adlandırılır, sonraki açışınızda işlevlerin özgün sürümleri çalıştırılır. Bir işlev zaten çalışıyorsa, çalışmakta olan sürümü yürütme işlemi tamamlanır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorProf.idl, CorProf.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [ICorProfilerInfo4 Arabirimi](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [Profil Oluşturma Arabirimleri](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profil Oluşturma](../../../../docs/framework/unmanaged-api/profiling/index.md)
