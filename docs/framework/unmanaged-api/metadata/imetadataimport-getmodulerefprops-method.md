---
title: IMetaDataImport::GetModuleRefProps Metodu
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleRefProps
helpviewer_keywords:
- GetModuleRefProps method [.NET Framework metadata]
- IMetaDataImport::GetModuleRefProps method [.NET Framework metadata]
ms.assetid: b558e766-4c11-4628-ae47-b4e0a1800168
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 501c554f6e2e4ddd8abd21fe81b81d1898ea070b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54583631"
---
# <a name="imetadataimportgetmodulerefprops-method"></a><span data-ttu-id="819c9-102">IMetaDataImport::GetModuleRefProps Metodu</span><span class="sxs-lookup"><span data-stu-id="819c9-102">IMetaDataImport::GetModuleRefProps Method</span></span>
<span data-ttu-id="819c9-103">Belirtilen meta veri belirteci tarafından başvurulan modül adını alır.</span><span class="sxs-lookup"><span data-stu-id="819c9-103">Gets the name of the module referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="819c9-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="819c9-104">Syntax</span></span>  
  
```  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,   
   [in]  ULONG               cchName,   
   [out] ULONG               *pchName   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="819c9-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="819c9-105">Parameters</span></span>  
 `mur`  
 <span data-ttu-id="819c9-106">[in] Meta veri bilgilerini almak için modülüne başvuruyor ModuleRef meta veri belirteci.</span><span class="sxs-lookup"><span data-stu-id="819c9-106">[in] The ModuleRef metadata token that references the module to get metadata information for.</span></span>  
  
 `szName`  
 <span data-ttu-id="819c9-107">[out] Modül adı tutan bir arabellek.</span><span class="sxs-lookup"><span data-stu-id="819c9-107">[out] A buffer to hold the module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="819c9-108">[in] İstenen boyutu `szName` geniş karakter.</span><span class="sxs-lookup"><span data-stu-id="819c9-108">[in] The requested size of `szName` in wide characters.</span></span>  
  
 `pchName`  
 <span data-ttu-id="819c9-109">[out] Döndürülen boyutunu `szName` geniş karakter.</span><span class="sxs-lookup"><span data-stu-id="819c9-109">[out] The returned size of `szName` in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="819c9-110">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="819c9-110">Requirements</span></span>  
 <span data-ttu-id="819c9-111">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="819c9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="819c9-112">**Üst bilgi:** COR.h</span><span class="sxs-lookup"><span data-stu-id="819c9-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="819c9-113">**Kitaplığı:** Bir kaynak olarak MsCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="819c9-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="819c9-114">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="819c9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="819c9-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="819c9-115">See also</span></span>
- [<span data-ttu-id="819c9-116">IMetaDataImport Arabirimi</span><span class="sxs-lookup"><span data-stu-id="819c9-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="819c9-117">IMetaDataImport2 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="819c9-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
