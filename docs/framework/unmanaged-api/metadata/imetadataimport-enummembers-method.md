---
title: IMetaDataImport::EnumMembers Yöntemi
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembers
helpviewer_keywords:
- IMetaDataImport::EnumMembers method [.NET Framework metadata]
- EnumMembers method [.NET Framework metadata]
ms.assetid: 3fb8e178-342b-4c89-9bcf-f7f834e6cb77
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 50035799fcfa4c4b08404d63fe91e7dba85722fa
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758841"
---
# <a name="imetadataimportenummembers-method"></a>IMetaDataImport::EnumMembers Yöntemi
Belirtilen türün üyelerini temsil eden MemberDef belirteçleri numaralandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT EnumMembers (   
   [in, out]  HCORENUM    *phEnum,   
   [in]  mdTypeDef   cl,   
   [out] mdToken     rMembers[],   
   [in]  ULONG       cMax,   
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `phEnum`  
 [out içinde] Numaralandırıcı bir işaretçi.  
  
 `cl`  
 [in] Numaralandırılacak üyeleri olan türü temsil eden bir tür tanımı belirteci.  
  
 `rMembers`  
 [out] Dizi MemberDef belirteçleri tutmak için kullanılır.  
  
 `cMax`  
 [in] En büyük boyutunu `rMembers` dizisi.  
  
 `pcTokens`  
 [out] Döndürülen MemberDef belirteçleri gerçek sayısını `rMembers`.  
  
## <a name="return-value"></a>Dönüş Değeri  
  
|HRESULT|Açıklama|  
|-------------|-----------------|  
|`S_OK`|`EnumMembers` başarıyla döndürüldü.|  
|`S_FALSE`|Numaralandırılacak hiçbir MemberDef belirteçleri vardır. Bu durumda, `pcTokens` sıfırdır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Koleksiyonlar bir sınıfın üyelerinin sıralanırken `EnumMembers` yalnızca üyeleri döndürür (alanlar ve yöntemler, ancak **değil** özellikleri veya olayları) doğrudan sınıf üzerinde tanımlanan. Bile sınıfı, bu devralınan üyeleri için bir uygulama sağlar sınıfını devralan herhangi bir üye döndürmez. Devralınan üyeleri listeleme için arayan açıkça devralma zincirini yol gerekir. Devralma zincirini kurallarını özgün metaverileri gereğince yayılan derleyici ve dil bağlı olarak farklılık gösterebileceğini unutmayın.
 
 Özellikler ve olaylar değil numaralandırılan tarafından `EnumMembers`. Bu listeleme için kullanın [EnumProperties](imetadataimport-enumproperties-method.md) veya [EnumEvents](imetadataimport-enumevents-method.md).
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** COR.h  
  
 **Kitaplığı:** Bir kaynak olarak MsCorEE.dll dahil  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [IMetaDataImport Arabirimi](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 Arabirimi](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
