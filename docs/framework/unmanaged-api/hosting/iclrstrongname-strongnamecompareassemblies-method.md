---
title: ICLRStrongName::StrongNameCompareAssemblies Yöntemi
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameCompareAssemblies
helpviewer_keywords:
- ICLRStrongName::StrongNameCompareAssemblies method [.NET Framework hosting]
- StrongNameCompareAssemblies method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: b1fb356c-72cf-4aa4-8376-f291a6d97c01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 266e2d92ea3c21a9df28bda18a5d0f32e5a32090
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748095"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a>ICLRStrongName::StrongNameCompareAssemblies Yöntemi
İki derlemenin yalnızca tanımlayıcı ad imzaları tarafından farklı olup olmadığını belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `wszAssembly1`  
 [in] İlk bütünleştirilmiş kod yolu.  
  
 `wszAssembly2`  
 [in] İkinci bütünleştirilmiş kod yolu.  
  
 `pdwResult`  
 [out] Aşağıdaki değerlerden biri:  
  
- `SN_CMP_DIFFERENT` (0) - derlemeleri farklı veri içerdiğini belirtir.  
  
- `SN_CMP_IDENTICAL` (1) - derlemeleri tam olarak aynı kendi imzaları ve sağlama toplamı dahil olmak üzere olduğunu belirtir.  
  
- `SN_CMP_SIGONLY` (2) - derlemeler yalnızca imza ve sağlama toplamı farklı olduğunu belirtir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `S_OK` yöntemi başarıyla tamamlandı Aksi takdirde hata olduğunu gösteren HRESULT değerini (bkz [ortak HRESULT değerlerini](https://go.microsoft.com/fwlink/?LinkId=213878) bir listesi için).  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** MetaHost.h  
  
 **Kitaplığı:** Bir kaynak olarak MSCorEE.dll dahil  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="remarks"></a>Açıklamalar  
 Bir derlemenin tanımlayıcı ad imzası, derlemenin metin adı, sürüm, kültür ve ortak anahtar belirteci oluşur.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [ICLRStrongName Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
