---
title: IAssemblyCache::CreateAssemblyCacheItem Yöntemi
ms.date: 03/30/2017
api_name:
- IAssemblyCache.CreateAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::CreateAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCache::CreateAssemblyCacheItem method [.NET Framework fusion]
- CreateAssemblyCacheItem method [.NET Framework fusion]
ms.assetid: 017a7ba5-aaaf-44e2-9cbe-ceebef259df0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 648b641cbd2ec97305674451df06ce5be6a93a49
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183696"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="1fd7f-102">IAssemblyCache::CreateAssemblyCacheItem Yöntemi</span><span class="sxs-lookup"><span data-stu-id="1fd7f-102">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>
<span data-ttu-id="1fd7f-103">Yeni bir başvuru alır [Iassemblycacheıtem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) nesne.</span><span class="sxs-lookup"><span data-stu-id="1fd7f-103">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fd7f-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="1fd7f-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fd7f-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="1fd7f-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="1fd7f-106">[in] Fusion.idl içinde tanımlanan bayraklar.</span><span class="sxs-lookup"><span data-stu-id="1fd7f-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="1fd7f-107">Aşağıdaki değerleri desteklenir:</span><span class="sxs-lookup"><span data-stu-id="1fd7f-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="1fd7f-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0X00000001)</span><span class="sxs-lookup"><span data-stu-id="1fd7f-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
-   <span data-ttu-id="1fd7f-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0X00000002)</span><span class="sxs-lookup"><span data-stu-id="1fd7f-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="1fd7f-110">[in] Sonra genişletilebilmek için ayrılmış.</span><span class="sxs-lookup"><span data-stu-id="1fd7f-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="1fd7f-111">`pvReserved` null bir başvuru olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="1fd7f-111">`pvReserved` must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="1fd7f-112">[out] Döndürülen `IAssemblyCacheItem` işaretçi.</span><span class="sxs-lookup"><span data-stu-id="1fd7f-112">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="1fd7f-113">[, isteğe bağlı] Uncanonicalized, virgülle ayrılmış `name=value` çiftleri.</span><span class="sxs-lookup"><span data-stu-id="1fd7f-113">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fd7f-114">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="1fd7f-114">Requirements</span></span>  
 <span data-ttu-id="1fd7f-115">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fd7f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fd7f-116">**Üst bilgi:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="1fd7f-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="1fd7f-117">**.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fd7f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fd7f-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="1fd7f-118">See also</span></span>

- [<span data-ttu-id="1fd7f-119">IAssemblyCache Arabirimi</span><span class="sxs-lookup"><span data-stu-id="1fd7f-119">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="1fd7f-120">IAssemblyCacheItem Arabirimi</span><span class="sxs-lookup"><span data-stu-id="1fd7f-120">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
