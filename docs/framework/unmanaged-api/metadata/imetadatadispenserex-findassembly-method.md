---
title: IMetaDataDispenserEx::FindAssembly Yöntemi
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssembly
helpviewer_keywords:
- FindAssembly method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssembly method [.NET Framework metadata]
ms.assetid: 3afe7252-5f28-48d9-a74d-1927566c404c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 85ebddf4ef96be2a583e54082e4d4405b30adf46
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777772"
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="b4ebd-102">IMetaDataDispenserEx::FindAssembly Yöntemi</span><span class="sxs-lookup"><span data-stu-id="b4ebd-102">IMetaDataDispenserEx::FindAssembly Method</span></span>
<span data-ttu-id="b4ebd-103">Bu yöntem uygulanmadı.</span><span class="sxs-lookup"><span data-stu-id="b4ebd-103">This method is not implemented.</span></span> <span data-ttu-id="b4ebd-104">Çağrılırsa E_NOTIMPL döndürür.</span><span class="sxs-lookup"><span data-stu-id="b4ebd-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4ebd-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="b4ebd-105">Syntax</span></span>  
  
```cpp  
HRESULT FindAssembly(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4ebd-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="b4ebd-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="b4ebd-107">[in] Kullanılmıyor.</span><span class="sxs-lookup"><span data-stu-id="b4ebd-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="b4ebd-108">[in] Kullanılmıyor.</span><span class="sxs-lookup"><span data-stu-id="b4ebd-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="b4ebd-109">[in] Kullanılmıyor.</span><span class="sxs-lookup"><span data-stu-id="b4ebd-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="b4ebd-110">[in] Bulunacak derleme.</span><span class="sxs-lookup"><span data-stu-id="b4ebd-110">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="b4ebd-111">[out] Derlemenin basit adını.</span><span class="sxs-lookup"><span data-stu-id="b4ebd-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="b4ebd-112">[in] Bayt cinsinden boyutu, `szName`.</span><span class="sxs-lookup"><span data-stu-id="b4ebd-112">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="b4ebd-113">[out] Gerçekte döndürülen karakter sayısını `szName`.</span><span class="sxs-lookup"><span data-stu-id="b4ebd-113">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4ebd-114">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="b4ebd-114">Requirements</span></span>  
 <span data-ttu-id="b4ebd-115">**Platform:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4ebd-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4ebd-116">**Üst bilgi:** COR.h</span><span class="sxs-lookup"><span data-stu-id="b4ebd-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b4ebd-117">**Kitaplığı:** Bir kaynak olarak MsCorEE.dll kullanılan</span><span class="sxs-lookup"><span data-stu-id="b4ebd-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b4ebd-118">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4ebd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4ebd-119">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="b4ebd-119">See also</span></span>

- [<span data-ttu-id="b4ebd-120">IMetaDataDispenserEx Arabirimi</span><span class="sxs-lookup"><span data-stu-id="b4ebd-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="b4ebd-121">IMetaDataDispenser Yöntemi</span><span class="sxs-lookup"><span data-stu-id="b4ebd-121">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
