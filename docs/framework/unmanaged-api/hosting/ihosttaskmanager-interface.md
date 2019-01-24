---
title: IHostTaskManager Arabirimi
ms.date: 03/30/2017
api_name:
- IHostTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager
helpviewer_keywords:
- IHostTaskManager interface [.NET Framework hosting]
ms.assetid: 4a0b05b9-3ef1-4607-b7c8-bd4dd43647a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d7b85a30a5abd9186f039aa21cbe7790325e4f2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54545653"
---
# <a name="ihosttaskmanager-interface"></a>IHostTaskManager Arabirimi
Ortak dil çalışma zamanı (CLR) görevler için standart işletim sistemi iş parçacığı veya fiber işlevlerini yerine ana bilgisayar üzerinden çalışmak için izin vermek için yöntemler sağlar.  
  
## <a name="methods"></a>Yöntemler  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[BeginDelayAbort Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md)|Yönetilen kod ana bilgisayar, bir süre içinde geçerli görevi iptal gerekir giriyor bildirir.|  
|[BeginThreadAffinity Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)|Yönetilen kod ana bilgisayar, bir süre içinde geçerli görev için başka bir işletim sistemi iş parçacığı taşınmalıdır değil giriyor bildirir.|  
|[CallNeedsHostHook Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)|Ortak dil çalışma zamanı satır içi belirtilen yönetilmeyen bir işlev çağrısı için olup olmadığını belirlemek konak sağlar.|  
|[CreateTask Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)|İstek ana bilgisayar yeni bir görev oluşturun.|  
|[EndDelayAbort Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md)|Yönetilen kod ana bilgisayar çağrısında şu, geçerli görev gerekir değil iptal edilir, dönem çıkıyor bildirir `BeginDelayAbort`.|  
|[EndThreadAffinity Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)|Yönetilen kod ana bilgisayar, dönem içinde geçerli görev gerekir taşınamaz başka bir işletim sistemi iş parçacığı için önceki bir çağrıyı izleyen çıkıyor bildirir `BeginThreadAffinity`.|  
|[EnterRuntime Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)|Konak, yönetilmeyen bir yönteme bir çağrı yöntemi gibi bir platform çağırma CLR yürütme denetimi döndürmektir bildirir.|  
|[GetCurrentTask Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md)|Bu Çağrının yapıldığı işletim sistemi iş parçacığı üzerinde şu anda yürütülmekte olan görev için bir arabirim işaretçisi alır.|  
|[GetStackGuarantee Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getstackguarantee-method.md)|Yığın işlemi tamamlandıktan sonra kullanılabilir olmasını garanti yığın alanı, ancak bir işlemin kapatmadan önce miktarı alır.|  
|[LeaveRuntime Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)|Yönetilen kod ana bilgisayar yönetilmeyen bir işlev çağrısı yapmak üzere olduğunu bildirir.|  
|[ReverseEnterRuntime Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)|Konak, bir çağrı, yönetilmeyen koddan ortak dil çalışma zamanı (CLR) içine yapıldığı bildirir.|  
|[ReverseLeaveRuntime Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)|Konak denetimi CLR bırakarak ve buna karşılık, yönetilen koddan çağrılan yönetilmeyen bir işlev girerek bildirir.|  
|[SetCLRTaskManager Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setclrtaskmanager-method.md)|Bir arabirim işaretçisi ile ana bilgisayarının sağladığı bir [Iclrtaskmanager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) CLR tarafından uygulanan örnek.|  
|[SetLocale Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)|Konak, CLR yerel ayar geçerli görevdeki değiştiğini bildirir.|  
|[SetStackGuarantee Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setstackguarantee-method.md)|Yalnızca iç kullanım için ayrılmıştır.|  
|[SetUILocale Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)|Ana bilgisayar, kullanıcı arabirimi yerel ayar geçerli görevi değiştirildiğini bildirir.|  
|[Sleep Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)|Konak, geçerli görev, uyku durumuna geçiyor bildirir.|  
|[SwitchToTask Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)|Konak, geçerli görevi geçmelisiniz bildirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `IHostTaskManager` sağlar, görevleri oluşturmak ve yönetmek CLR denetimi yönetilmeyen koda ve yönetilen aktarır durumlarda eyleme geçen ve belirli eylemleri belirtmek üzere ana kancaları sağlamak için konak olabilir ve kod yürütme sırasında alamaz.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** MSCorEE.h  
  
 **Kitaplığı:** Bir kaynak olarak MSCorEE.dll dahil  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.
- [ICLRTask Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask Arabirimi](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Barındırma Arabirimleri](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
