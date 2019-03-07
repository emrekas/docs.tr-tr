---
title: IMetaDataEmit::SetHandler Yöntemi
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetHandler
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetHandler
helpviewer_keywords:
- IMetaDataEmit::SetHandler method [.NET Framework metadata]
- SetHandler method [.NET Framework metadata]
ms.assetid: c6c1aaaf-e2cd-407c-b73e-fbe6ffd83bb3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ada84df2a08b992aa178c2fb63c713b05a8937a2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503222"
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="69642-102">IMetaDataEmit::SetHandler Yöntemi</span><span class="sxs-lookup"><span data-stu-id="69642-102">IMetaDataEmit::SetHandler Method</span></span>
<span data-ttu-id="69642-103">Belirtilen tarafından başvurulan ayarlar `IUnknown` bir bildirim geri çağırması için belirteci yeniden eşleme olarak işaretçi.</span><span class="sxs-lookup"><span data-stu-id="69642-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69642-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="69642-104">Syntax</span></span>  
  
```  
HRESULT SetHandler (   
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69642-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="69642-105">Parameters</span></span>  
 `pUnk`  
 <span data-ttu-id="69642-106">[in] Kaydetmek için işleyici.</span><span class="sxs-lookup"><span data-stu-id="69642-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69642-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="69642-107">Remarks</span></span>  
 <span data-ttu-id="69642-108">Meta veri altyapısı tarafından sağlanan yöntemini kullanarak bildirim gönderir. `SetHandler`, derleyiciler, oluşturmaz kayıtları en iyi duruma getirilmiş bir yolla ve kaydedilmiş kayıtları en iyi hale getirmek istediğiniz için.</span><span class="sxs-lookup"><span data-stu-id="69642-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="69642-109">Geri çağırma yöntemi aracılığıyla sağlanmazsa `SetHandler`, hiçbir iyileştirme gerçekleştirilecek üzerinde kaydetme burada birkaç alma dışında kapsamları kullanarak birleştirildiğini `IMapToken` üzerinde her kapsam için birleştirme.</span><span class="sxs-lookup"><span data-stu-id="69642-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69642-110">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="69642-110">Requirements</span></span>  
 <span data-ttu-id="69642-111">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69642-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69642-112">**Üst bilgi:** COR.h</span><span class="sxs-lookup"><span data-stu-id="69642-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="69642-113">**Kitaplığı:** Bir kaynak olarak MSCorEE.dll kullanılan</span><span class="sxs-lookup"><span data-stu-id="69642-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="69642-114">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69642-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69642-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="69642-115">See also</span></span>
- [<span data-ttu-id="69642-116">IMetaDataEmit Arabirimi</span><span class="sxs-lookup"><span data-stu-id="69642-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="69642-117">IMetaDataEmit2 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="69642-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
