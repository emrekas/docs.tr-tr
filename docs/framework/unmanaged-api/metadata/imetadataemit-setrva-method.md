---
title: IMetaDataEmit::SetRVA Yöntemi
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetRVA
helpviewer_keywords:
- IMetaDataEmit::SetRVA method [.NET Framework metadata]
- SetRVA method [.NET Framework metadata]
ms.assetid: 4d69fb6d-ee35-4318-8224-5eea2bd16818
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 89475ebc5ef04c8693adb7a83bd1dd07f5774fb9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544704"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="cb83e-102">IMetaDataEmit::SetRVA Yöntemi</span><span class="sxs-lookup"><span data-stu-id="cb83e-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="cb83e-103">Belirtilen yöntemin göreli sanal adres ayarlar.</span><span class="sxs-lookup"><span data-stu-id="cb83e-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb83e-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="cb83e-104">Syntax</span></span>  
  
```  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,   
    [in]  ULONG        ulRVA   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cb83e-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="cb83e-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="cb83e-106">[in] Hedef yöntem veya yöntem uygulaması için belirteci.</span><span class="sxs-lookup"><span data-stu-id="cb83e-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="cb83e-107">[in] Kod veya veri alanı adresi.</span><span class="sxs-lookup"><span data-stu-id="cb83e-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb83e-108">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="cb83e-108">Requirements</span></span>  
 <span data-ttu-id="cb83e-109">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb83e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb83e-110">**Üst bilgi:** COR.h</span><span class="sxs-lookup"><span data-stu-id="cb83e-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cb83e-111">**Kitaplığı:** Bir kaynak olarak MSCorEE.dll kullanılan</span><span class="sxs-lookup"><span data-stu-id="cb83e-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cb83e-112">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb83e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb83e-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="cb83e-113">See also</span></span>
- [<span data-ttu-id="cb83e-114">IMetaDataEmit Arabirimi</span><span class="sxs-lookup"><span data-stu-id="cb83e-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="cb83e-115">IMetaDataEmit2 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="cb83e-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
