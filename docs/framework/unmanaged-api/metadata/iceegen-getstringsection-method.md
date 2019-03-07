---
title: ICeeGen::GetStringSection Yöntemi
ms.date: 03/30/2017
api_name:
- ICeeGen.GetStringSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetStringSection
helpviewer_keywords:
- ICeeGen::GetStringSection method [.NET Framework metadata]
- GetStringSection method [.NET Framework metadata]
ms.assetid: a2267d39-69d1-4de1-bf37-f752cafacc71
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0e306ccc824910226e522bc664f8f87f828a0d52
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477055"
---
# <a name="iceegengetstringsection-method"></a><span data-ttu-id="e975d-102">ICeeGen::GetStringSection Yöntemi</span><span class="sxs-lookup"><span data-stu-id="e975d-102">ICeeGen::GetStringSection Method</span></span>
<span data-ttu-id="e975d-103">Belirtilen tanıtıcı tarafından başvurulan kod bölümünde dize gösterimini alır.</span><span class="sxs-lookup"><span data-stu-id="e975d-103">Gets a string representation of the code section referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="e975d-104">Bu yöntem artık kullanılmıyor ve kullanılmamalıdır.</span><span class="sxs-lookup"><span data-stu-id="e975d-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e975d-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="e975d-105">Syntax</span></span>  
  
```  
HRESULT GetStringSection (  
    [in, out] HCEESECTION     *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e975d-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="e975d-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="e975d-107">[out içinde] Kod bölümüne tanıtıcısı.</span><span class="sxs-lookup"><span data-stu-id="e975d-107">[in, out] The handle to the code section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e975d-108">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="e975d-108">Requirements</span></span>  
 <span data-ttu-id="e975d-109">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e975d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e975d-110">**Üst bilgi:** COR.h</span><span class="sxs-lookup"><span data-stu-id="e975d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e975d-111">**Kitaplığı:** Bir kaynak olarak MsCorEE.dll kullanılan</span><span class="sxs-lookup"><span data-stu-id="e975d-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e975d-112">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e975d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e975d-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="e975d-113">See also</span></span>
- [<span data-ttu-id="e975d-114">ICeeGen Arabirimi</span><span class="sxs-lookup"><span data-stu-id="e975d-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
