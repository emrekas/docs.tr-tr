---
title: IMetaDataEmit::DefineField Yöntemi
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dfe888f74face85179306c982f7b5a888752987e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54742805"
---
# <a name="imetadataemitdefinefield-method"></a>IMetaDataEmit::DefineField Yöntemi
Belirtilen meta verileri imza ile bir alan için bir tanım oluşturur ve bu alan tanımı için bir belirteç alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT DefineField (   
    [in]  mdTypeDef   td,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwFieldFlags,   
    [in]  PCCOR_SIGNATURE pvSigBlob,   
    [in]  ULONG       cbSigBlob,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue,   
    [out] mdFieldDef  *pmd   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `td`  
 [in] `mdTypeDef` Kapsayan sınıf veya arabirim için belirteç.  
  
 `szName`  
 [in] Unicode alan adı.  
  
 `dwFieldFlags`  
 [in] Alan öznitelikleri. Bu, bir bit maskesi, `CorFieldAttr` değerleri.  
  
 `pvSigBlob`  
 [in] Bir BLOB olarak alan imzası.  
  
 `cbSigBlob`  
 [in] Bayt sayısı `pvSigBlob`.  
  
 `dwCPlusTypeFlag`  
 [in] `ELEMENT_TYPE_` *\** Sabit değer. Bu bir `CorElementType` değeri. Alan için sabit bir değer tanımlamayarak kullanırsanız `ELEMENT_TYPE_END`.  
  
 `pValue`  
 [in] Alan için sabit bir değer.  
  
 `cchValue`  
 [in] \(Unicode) karakter cinsinden boyutu `pValue`.  
  
 `pmd`  
 [out] `mdFieldDef` Atanan simgesi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** COR.h  
  
 **Kitaplığı:** Bir kaynak olarak MSCorEE.dll kullanılan  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.
- [IMetaDataEmit Arabirimi](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 Arabirimi](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
