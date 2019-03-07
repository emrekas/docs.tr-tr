---
title: IMetaDataEmit::SetFieldProps Yöntemi
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldProps
helpviewer_keywords:
- IMetaDataEmit::SetFieldProps method [.NET Framework metadata]
- SetFieldProps method [.NET Framework metadata]
ms.assetid: 47132dda-fa92-4bd1-ae4b-24cd9a60665a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ace278e0031d3e673418f50356f173c473a4832d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494330"
---
# <a name="imetadataemitsetfieldprops-method"></a>IMetaDataEmit::SetFieldProps Yöntemi
Belirtilen alan belirteci tarafından başvurulan alan için varsayılan değer güncelleştirir veya ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,   
    [in]  DWORD       dwFieldFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `fd`  
 [in] Hedef alan belirteci.  
  
 `dwFieldFlags`  
 [in] Alan öznitelikleri. Bu, bir bit maskesi, `CorFieldAttr` değerleri.  
  
 `dwCPlusTypeFlag`  
 [in] `ELEMENT_TYPE_` *\** Sabit değer. Bu bir `CorElementType` değeri. Bir sabit tanımlı değilse, bu değeri ayarlamak `ELEMENT_TYPE_END`.  
  
 `pValue`  
 [in] Alan için sabit bir değer.  
  
 `cchValue`  
 [in] Unicode karakter cinsinden boyutu, `pValue`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** COR.h  
  
 **Kitaplığı:** Bir kaynak olarak MSCorEE.dll kullanılan  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.
- [IMetaDataEmit Arabirimi](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 Arabirimi](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
