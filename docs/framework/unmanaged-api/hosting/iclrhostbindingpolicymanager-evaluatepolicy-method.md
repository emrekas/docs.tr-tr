---
title: ICLRHostBindingPolicyManager::EvaluatePolicy Yöntemi
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.EvaluatePolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy method [.NET Framework hosting]
- EvaluatePolicy method [.NET Framework hosting]
ms.assetid: 3a3a9446-7a4e-4836-9b27-5c536c15993d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d23b2371e7cc3c9d1e91af061c19b4fb0dbc69e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779691"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a>ICLRHostBindingPolicyManager::EvaluatePolicy Yöntemi
Bağlama ilkesi, konak adına değerlendirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `pwzReferenceIdentity`  
 [in] İlke değerlendirmesi önce derlemeyi bir başvuru.  
  
 `pbApplicationPolicy`  
 [in] İlke verilerini içeren arabellek için işaretçi.  
  
 `cbAppPolicySize`  
 [in] Boyutu `pbApplicationPolicy` arabellek.  
  
 `pwzPostPolicyReferenceIdentity`  
 [out] Yeni ilke verilerini değerlendirmesi sonra derlemesine bir başvuru.  
  
 `pcchPostPolicyReferenceIdentity`  
 [out içinde] Yeni ilke verilerini değerlendirmesi sonra derleme kimliği başvurusu arabellek boyutu için bir işaretçi.  
  
 `pdwPoliciesApplied`  
 [out] Mantıksal OR birleşimi için bir işaretçi [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) hangi ilkeleri uygulanmış olduğunu belirten değer.  
  
## <a name="return-value"></a>Dönüş Değeri  
  
|HRESULT|Açıklama|  
|-------------|-----------------|  
|S_OK|Değerlendirme başarıyla tamamlandı.|  
|E_INVALIDARG|Ya da `pwzReferenceIdentity` veya `pbApplicationPolicy` bir null başvurudur.|  
|ERROR_INSUFFICIENT_BUFFER|`cbAppPolicySize` çok küçüktür.|  
|HOST_E_CLRNOTAVAILABLE|Ortak dil çalışma zamanı (CLR) işlem içine yüklenmemiş olan veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı şekilde işleme bir durumda değil.|  
|HOST_E_TIMEOUT|Arama zaman aşımına uğradı.|  
|HOST_E_NOT_OWNER|Arayan bir kilide sahip değil.|  
|HOST_E_ABANDONED|Bir olay engellenen bir iş parçacığı iptal edildi veya fiber üzerinde bekleme süresi.|  
|E_FAIL|Bilinmeyen geri dönülemez bir hata oluştu. CLR, artık E_FAIL bir yöntemin dönüşünün ardından, işlem içinde kullanılamaz. Yöntemleri barındırma yapılan sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 `EvaluatePolicy` Yöntemi özel ana bilgisayar bütünleştirilmiş kod korumak için bağlama ilkesi etkilemek için ana sürüm gereksinimleri sağlar. İlke altyapısı CLR içinde kalır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** MSCorEE.h  
  
 **Kitaplığı:** Bir kaynak olarak MSCorEE.dll dahil  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [ICLRHostBindingPolicyManager Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
