---
title: IMetaDataImport::GetClassLayout Metodu
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetClassLayout
helpviewer_keywords:
- IMetaDataImport::GetClassLayout method [.NET Framework metadata]
- GetClassLayout method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 8f35414d-f40b-4b99-8768-9adb675c622a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6094bbedcc5386d3f5c0400960e47ac91defe2a1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782455"
---
# <a name="imetadataimportgetclasslayout-method"></a><span data-ttu-id="f4f70-102">IMetaDataImport::GetClassLayout Metodu</span><span class="sxs-lookup"><span data-stu-id="f4f70-102">IMetaDataImport::GetClassLayout Method</span></span>
<span data-ttu-id="f4f70-103">Belirtilen tür tanımı tarafından başvurulan sınıfın düzen bilgilerini belirtecini alır.</span><span class="sxs-lookup"><span data-stu-id="f4f70-103">Gets layout information for the class referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4f70-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="f4f70-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassLayout  (   
   [in]  mdTypeDef          td,   
   [out] DWORD              *pdwPackSize,  
   [out] COR_FIELD_OFFSET   rFieldOffset[],  
   [in]  ULONG              cMax,  
   [out] ULONG              *pcFieldOffset,  
   [out] ULONG              *pulClassSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4f70-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="f4f70-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="f4f70-106">[in] Döndürülecek düzeni ile sınıf için TypeDef simgesi.</span><span class="sxs-lookup"><span data-stu-id="f4f70-106">[in] The TypeDef token for the class with the layout to return.</span></span>  
  
 `pdwPackSize`  
 <span data-ttu-id="f4f70-107">[out] 1, 2, 4, 8 veya 16, sınıf paketi boyutunu temsil eden değerlerinden biri.</span><span class="sxs-lookup"><span data-stu-id="f4f70-107">[out] One of the values 1, 2, 4, 8, or 16, representing the pack size of the class.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="f4f70-108">[out] Bir dizi [cor_fıeld_offset](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) değerleri.</span><span class="sxs-lookup"><span data-stu-id="f4f70-108">[out] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) values.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f4f70-109">[in] En büyük boyutunu `rFieldOffset` dizisi.</span><span class="sxs-lookup"><span data-stu-id="f4f70-109">[in] The maximum size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="f4f70-110">[out] Döndürülen öğe sayısını `rFieldOffset`.</span><span class="sxs-lookup"><span data-stu-id="f4f70-110">[out] The number of elements returned in `rFieldOffset`.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="f4f70-111">[out] Tarafından temsil edilen sınıf bayt cinsinden boyut `td`.</span><span class="sxs-lookup"><span data-stu-id="f4f70-111">[out] The size in bytes of the class represented by `td`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4f70-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="f4f70-112">Requirements</span></span>  
 <span data-ttu-id="f4f70-113">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4f70-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4f70-114">**Üst bilgi:** COR.h</span><span class="sxs-lookup"><span data-stu-id="f4f70-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f4f70-115">**Kitaplığı:** Bir kaynak olarak MsCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="f4f70-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f4f70-116">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4f70-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4f70-117">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="f4f70-117">See also</span></span>

- [<span data-ttu-id="f4f70-118">IMetaDataImport Arabirimi</span><span class="sxs-lookup"><span data-stu-id="f4f70-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f4f70-119">IMetaDataImport2 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="f4f70-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
