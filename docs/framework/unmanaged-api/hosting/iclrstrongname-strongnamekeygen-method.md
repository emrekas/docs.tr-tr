---
title: ICLRStrongName::StrongNameKeyGen Yöntemi
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyGen method [.NET Framework hosting]
ms.assetid: ac5c1245-9acf-4271-9c08-3d9b7c670df3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c535d3d73b6d3d0165ea2d744ef625a16bd76cd4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747836"
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a>ICLRStrongName::StrongNameKeyGen Yöntemi
Tanımlayıcı ad kullanmak için yeni bir ortak/özel anahtar çifti oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `wszKeyContainer`  
 [in] İstenen anahtar kapsayıcısı adı. `wszKeyContainer` ya da boş dize veya geçici bir ad oluşturmak için null olmalıdır.  
  
 `dwFlags`  
 [in] Kaydedilen anahtar bırakın belirten bir değer. Aşağıdaki değerleri desteklenir:  
  
- kullanılan 0x00000000 - `wszKeyContainer` geçici bir anahtar kapsayıcısı adını oluşturmak için null.  
  
- 0x00000001 (`SN_LEAVE_KEY`)-anahtar sol kaydedilmesi gerektiğini belirtir.  
  
 `ppbKeyBlob`  
 [out] Döndürülen ortak/özel anahtar çifti.  
  
 `pcbKeyBlob`  
 [out] Bayt cinsinden boyutu, `ppbKeyBlob`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `S_OK` yöntemi başarıyla tamamlandı Aksi takdirde hata olduğunu gösteren HRESULT değerini (bkz [ortak HRESULT değerlerini](https://go.microsoft.com/fwlink/?LinkId=213878) bir listesi için).  
  
## <a name="remarks"></a>Açıklamalar  
 [Iclrstrongname::strongnamekeygen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) yöntemi 1024 bit anahtar oluşturur. Anahtarı aldıktan sonra çağırmalıdır [Iclrstrongname::strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) ayrılan belleği serbest bırakmak için yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** MetaHost.h  
  
 **Kitaplığı:** Bir kaynak olarak MSCorEE.dll dahil  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [StrongNameKeyGenEx Yöntemi](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [ICLRStrongName Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
