---
title: StrongNameSignatureVerificationEx2 Yöntemi
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameSignatureVerificationEx2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameSignatureVerificationEx2
helpviewer_keywords:
- StrongNameSignatureVerificationEx2 method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameSignatureVerificationEx2 method [.NET Framework hosting]
ms.assetid: dfd4133f-a074-4db3-a7ee-4f250fe9ad3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aab3b697a0bb2f58258816ce4f8133009b26f54a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220597"
---
# <a name="strongnamesignatureverificationex2-method"></a>StrongNameSignatureVerificationEx2 Yöntemi
Kesin adlandırılmış derlemenin imzayı doğrular ve ECMA anahtarından bir eşleme için gerçek bir anahtar sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `wszFilePath`  
 [in] Taşınabilir yürütülebilir (.exe veya .dll) dosyası doğrulanması derleme yolu.  
  
 `fForceVerification`  
 [in] `true` , olsa bile gerekli kayıt defteri ayarlarını geçersiz kılmak; Aksi takdirde, doğrulamanın `false`.  
  
 `pbEcmaPublicKey`  
 [in] Eşleme için bir işaretçi gerçek anahtarı ECMA ortak anahtarından doğrulama için kullanılır.  
  
 `cbEcmaPublicKey`  
 [in] Gerçek ECMA ortak anahtarın uzunluğu.  
  
 `pfWasVerified`  
 [out] `true` tanımlayıcı ad imzası, doğrulanmış; Aksi takdirde `false`. Bu parametre aynı zamanda kümesine `false` kayıt defteri ayarları nedeniyle doğrulama başarılı olursa.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `S_OK` doğrulama başarılı olduysa; Aksi takdirde hata olduğunu gösteren HRESULT değerini (bkz [ortak HRESULT değerlerini](https://go.microsoft.com/fwlink/?LinkId=213878) bir listesi için).  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** MetaHost.h  
  
 **Kitaplığı:** Bir kaynak olarak MSCorEE.dll dahil  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [StrongNameSignatureVerification Yöntemi](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [StrongNameSignatureVerificationEx Yöntemi](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [ICLRStrongName Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
