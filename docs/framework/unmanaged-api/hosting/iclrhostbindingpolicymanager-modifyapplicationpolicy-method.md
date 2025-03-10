---
title: ICLRHostBindingPolicyManager::ModifyApplicationPolicy Yöntemi
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.ModifyApplicationPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy method [.NET Framework hosting]
- ModifyApplicationPolicy method [.NET Framework hosting]
ms.assetid: d82d633e-cce6-427c-8b02-8227e34e12ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a9e438e6dd436303cd6f7aa60c779179b5d3c04
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779665"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a>ICLRHostBindingPolicyManager::ModifyApplicationPolicy Yöntemi
Belirtilen derleme için bağlama ilkesi değiştirir ve ilke yeni bir sürümünü oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT  ModifyApplicationPolicy (  
    [in] LPCWSTR     pwzSourceAssemblyIdentity,   
    [in] LPCWSTR     pwzTargetAssemblyIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [in] DWORD       dwPolicyModifyFlags,  
    [out, size_is(*pcbNewAppPolicySize)] BYTE *pbNewApplicationPolicy,   
    [in, out] DWORD *pcbNewAppPolicySize  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `pwzSourceAssemblyIdentity`  
 [in] Değiştirilecek derleme kimliği.  
  
 `pwzTargetAssemblyIdentity`  
 [in] Değiştirilen derlemenin yeni kimliği.  
  
 `pbApplicationPolicy`  
 [in] Değiştirilecek derleme için bağlama ilkesi verileri içeren arabellek için işaretçi.  
  
 `cbAppPolicySize`  
 [in] Değiştirilecek bağlama ilkesi boyutu.  
  
 `dwPolicyModifyFlags`  
 [in] Bir mantıksal OR kombinasyonudur [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) yeniden yönlendirme denetimini gösteren değer.  
  
 `pbNewApplicationPolicy`  
 [out] Yeni veri bağlama ilkesi içeren arabellek için işaretçi.  
  
 `pcbNewAppPolicySize`  
 [out içinde] Yeni bağlama ilkesi arabellek boyutu için bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
  
|HRESULT|Açıklama|  
|-------------|-----------------|  
|S_OK|İlke başarıyla değiştirildi.|  
|E_INVALIDARG|`pwzSourceAssemblyIdentity` veya `pwzTargetAssemblyIdentity` null başvuru oluştu.|  
|ERROR_INSUFFICIENT_BUFFER|`pbNewApplicationPolicy` çok küçüktür.|  
|HOST_E_CLRNOTAVAILABLE|Ortak dil çalışma zamanı (CLR) işlem içine yüklenmemiş olan veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı şekilde işleme bir durumda değil.|  
|HOST_E_TIMEOUT|Arama zaman aşımına uğradı.|  
|HOST_E_NOT_OWNER|Arayan bir kilide sahip değil.|  
|HOST_E_ABANDONED|Bir olay engellenen bir iş parçacığı iptal edildi veya fiber üzerinde bekleme süresi.|  
|E_FAIL|Bilinmeyen geri dönülemez bir hata oluştu. CLR, artık E_FAIL bir yöntemin dönüşünün ardından, işlem içinde kullanılamaz. Yöntemleri barındırma yapılan sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 `ModifyApplicationPolicy` Yöntemi iki kez çağrılabilir. İlk çağrı için bir null değer sağlamanız `pbNewApplicationPolicy` parametresi. Bu çağrı için gerekli olan değerle döndüreceği `pcbNewAppPolicySize`. Bu değer için yapılan ikinci çağrı sunmalıdır `pcbNewAppPolicySize`ve bu boyut için bir arabellek işaret `pbNewApplicationPolicy`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** MSCorEE.h  
  
 **Kitaplığı:** Bir kaynak olarak MSCorEE.dll dahil  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [ICLRHostBindingPolicyManager Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
