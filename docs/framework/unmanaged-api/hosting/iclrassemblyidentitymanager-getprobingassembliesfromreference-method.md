---
title: ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference Yöntemi
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetProbingAssembliesFromReference
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference method [.NET Framework hosting]
- GetProbingAssembliesFromReference method [.NET Framework hosting]
ms.assetid: aec05744-e8d4-44c6-b4a8-e583229ac34e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 55f3bd89f0ca177bcd4edef2e17a7d2256a0042a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773497"
---
# <a name="iclrassemblyidentitymanagergetprobingassembliesfromreference-method"></a>ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference Yöntemi
Alır bir [Iclrprobingassemblyenum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) belirtilen kimlik türü ile derlemesi tarafından başvurulan derleme kimlikleri için Numaralandırıcı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetProbingAssembliesFromReference (  
    [in] DWORD   dwMachineType,  
    [in] DWORD   dwFlags,  
    [in] LPCWSTR pwzReferenceIdentity,  
    [out] ICLRProbingAssemblyEnum **ppProbingAssemblyEnum  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `dwMachineType`  
 [in] İşlemci mimarisi WinNT.h içinde tanımlanan belirtir. geçerli bir değer.  
  
 `dwFlags`  
 [in] Sonra genişletilebilmek için sağlanır. CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT geçerli ortak dil çalışma zamanı (CLR) sürümünü destekleyen tek bir değerdir.  
  
 `pwzReferenceIdentity`  
 [in] Genellikle çağrısından döndürülen bir donuk derleme bağlama kimliği [Iclrassemblyıdentitymanager::getbindingıdentityfromfile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) veya [Iclrassemblyıdentitymanager::getbindingıdentityfromstream](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) yöntemi.  
  
 `ppProbingAssemblyEnum`  
 [out] Bir arabirim işaretçisi için bir `ICLRProbingAssemblyEnum` tarafından tanıtılan derlemenin başvurduğu derlemeleri başvurular içeren bir numaralandırıcı `pwzReferenceIdentity`.  
  
## <a name="return-value"></a>Dönüş Değeri  
  
|HRESULT|Açıklama|  
|-------------|-----------------|  
|S_OK|Yöntemi başarıyla döndürüldü.|  
|HOST_E_CLRNOTAVAILABLE|CLR'yi bir işleme yüklü değil veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı şekilde işleme bir durumda.|  
|HOST_E_TIMEOUT|Arama zaman aşımına uğradı.|  
|HOST_E_NOT_OWNER|Arayan bir kilide sahip değil.|  
|HOST_E_ABANDONED|Bir olay engellenen bir iş parçacığı iptal edildi veya fiber üzerinde bekleme süresi.|  
|E_FAIL|Bilinmeyen geri dönülemez bir hata oluştu. CLR, artık bir yöntem E_FAIL döndürürse, işlem içinde kullanılamaz. Yöntemleri barındırma yapılan sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** MSCorEE.h  
  
 **Kitaplığı:** Bir kaynak olarak MSCorEE.dll dahil  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [ICLRAssemblyIdentityManager Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [ICLRProbingAssemblyEnum Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
