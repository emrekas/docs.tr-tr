---
title: CertFreeAuthenticodeSignerInfo İşlevi
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeSignerInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4282be8e57c965e14398a9284002b1191c5169fa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708044"
---
# <a name="certfreeauthenticodesignerinfo-function"></a>CertFreeAuthenticodeSignerInfo İşlevi
İçin ayrılan kaynakları serbest bırakan [axl_authentıcode_sıgner_ınfo](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) yapısı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pSignerInfo`  
 [out içinde] Yayımlanacak imzalayan bilgileri. Bkz: [axl_authentıcode_sıgner_ınfo](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) yapısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `S_OK` işlev başarılı olursa. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca bkz.
- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
