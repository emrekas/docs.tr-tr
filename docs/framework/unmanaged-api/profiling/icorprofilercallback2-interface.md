---
title: ICorProfilerCallback2 Arabirimi
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2
helpviewer_keywords:
- ICorProfilerCallback2 interface [.NET Framework profiling]
ms.assetid: 4a261dba-450d-4f1f-8d98-865b58bfc992
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d36d8ef3bfdbd6a1acf787a91003e2ff3139a4d9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963962"
---
# <a name="icorprofilercallback2-interface"></a>ICorProfilerCallback2 Arabirimi
Profil oluşturucunun abone olduğu olaylar gerçekleştiğinde, bir kod Profilcisi bildirmek için ortak dil çalışma zamanı (CLR) tarafından kullanılan yöntemleri sağlar. Arabirim, [ICorProfilerCallback arabiriminin bir uzantısıdır.](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) `ICorProfilerCallback2` Diğer bir deyişle, .NET Framework sürüm 2,0 ' de tanıtılan yeni geri çağrılar sağlar.  
  
> [!NOTE]
> Her yöntem uygulamasının hata durumunda Success veya E_FAıL değeri için S_OK değerine sahip bir HRESULT döndürmesi gerekir. Şu anda CLR [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)hariç her geri çağırma tarafından döndürülen HRESULT 'yi yoksayar.  
  
## <a name="methods"></a>Yöntemler  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[FinalizeableObjectQueued Yöntemi](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md)|Kod Profilcisi, sonlandırıcısı olan bir nesnenin, `Finalize` yönteminin yürütülmesi için Sonlandırıcı iş parçacığına sıraya alınmış olduğunu bildirir.|  
|[GarbageCollectionFinished Yöntemi](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)|Profiler öğesine bir çöp toplamanın tamamlandığını ve tüm çöp toplama geri çağırmaları için verildiğini bildirir.|  
|[GarbageCollectionStarted Yöntemi](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)|Kod Profilcisi bir çöp toplamanın başlatıldığını bildirir.|  
|[HandleCreated Yöntemi](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md)|Kod Profilcisi bir çöp toplama tutamacının oluşturulduğunu bildirir.|  
|[HandleDestroyed Yöntemi](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md)|Kod Profilcisi bir çöp toplama tanıtıcısının yok edildiğini bildirir.|  
|[RootReferences2 Yöntemi](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)|Çöp toplama gerçekleştirildikten sonra profil oluşturucuyu kök başvuruları hakkında bilgilendirir. Bu yöntem [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) yönteminin bir uzantısıdır.|  
|[SurvivingReferences Yöntemi](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md)|Bir atık toplamayı daha fazla kullanan nesne başvuruları hakkında profil oluşturucuyu bilgilendirir.|  
|[ThreadNameChanged Yöntemi](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-threadnamechanged-method.md)|Kod Profilcisi bir iş parçacığı adının değiştiğini bildirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 CLR, profil oluşturucunun abone olduğu bir `ICorProfilerCallback` olay olduğunda `ICorProfilerCallback2`profil oluşturucuyu bilgilendirmek için (veya) arabirimindeki bir yöntemi çağırır. Bu, CLR 'nin kod Profilcisi ile iletişim kurduğu birincil geri çağırma arabirimidir.  
  
 Bir kod profil oluşturucu `ICorProfilerCallback` arabirimin yöntemlerini uygulamalıdır. .NET Framework 2,0 ve sonraki sürümlerinde, profil oluşturucunun de `ICorProfilerCallback2` yöntemleri uygulaması gerekir. Her yöntem uygulamasının hata durumunda Success veya E_FAıL değeri için S_OK değerine sahip bir HRESULT döndürmesi gerekir. Şu anda CLR [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)hariç her geri çağırma tarafından döndürülen HRESULT 'yi yoksayar.  
  
 Bir kod Profilcisi, `ICorProfilerCallback` ve `ICorProfilerCallback2` arabirimlerini uygulayan com nesnesine Microsoft Windows kayıt defteri 'ne kaydolmalıdır. Bir kod profil oluşturucu, [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)çağırarak bildirim almak istediği olaylara abone olur. Bu genellikle profil oluşturucunun [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)uygulamasında yapılır. Profil Oluşturucu daha sonra bir olay gerçekleşmekte olduğu veya yürütülmekte olan bir çalışma zamanı işleminde gerçekleştiyse çalışma zamanından bildirim alabilir.  
  
> [!NOTE]
> Profil Oluşturucu tek bir COM nesnesi kaydeder. Profiler .NET Framework sürüm 1,0 veya 1,1 ' i hedefliyorsanız, bu COM nesnesi yalnızca ' nin `ICorProfilerCallback`yöntemlerini uygular. .NET Framework sürüm 2,0 ve üzeri hedefleniyorsa, COM nesnesinin yöntemlerini `ICorProfilerCallback2`de uygulaması gerekir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platform** Bkz. [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi** CorProf. IDL, CorProf. h  
  
 **Kitaplığı** Corguid. lib  
  
 **.NET Framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Profil Oluşturma Arabirimleri](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [ICorProfilerCallback Arabirimi](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ICorProfilerCallback3 Arabirimi](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)
- [ICorProfilerCallback4 Arabirimi](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
