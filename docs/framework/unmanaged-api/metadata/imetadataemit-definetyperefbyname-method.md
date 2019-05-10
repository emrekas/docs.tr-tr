---
title: IMetaDataEmit::DefineTypeRefByName Yöntemi
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeRefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 82d81be7a9e0843dfe382767de582f93371acb4c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64584485"
---
# <a name="imetadataemitdefinetyperefbyname-method"></a><span data-ttu-id="fa00a-102">IMetaDataEmit::DefineTypeRefByName Yöntemi</span><span class="sxs-lookup"><span data-stu-id="fa00a-102">IMetaDataEmit::DefineTypeRefByName Method</span></span>
<span data-ttu-id="fa00a-103">Bir meta veri geçerli kapsamı dışında olan Belirtilen kapsam içinde tanımlanan bir tür için belirteç alır.</span><span class="sxs-lookup"><span data-stu-id="fa00a-103">Gets a metadata token for a type that is defined in the specified scope, which is outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa00a-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="fa00a-104">Syntax</span></span>  
  
```  
HRESULT DefineTypeRefByName (   
    [in]  mdToken     tkResolutionScope,   
    [in]  LPCWSTR     szName,   
    [out] mdTypeRef   *ptr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa00a-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="fa00a-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="fa00a-106">[in] Çözüm kapsamını belirten belirteç.</span><span class="sxs-lookup"><span data-stu-id="fa00a-106">[in] The token specifying the resolution scope.</span></span> <span data-ttu-id="fa00a-107">Aşağıdaki belirteç türlerini geçerlidir:</span><span class="sxs-lookup"><span data-stu-id="fa00a-107">The following token types are valid:</span></span>  
  
- <span data-ttu-id="fa00a-108">`mdModuleRef`, çağıran tanımlanır aynı bütünleştirilmiş kodda tür tanımlı ise.</span><span class="sxs-lookup"><span data-stu-id="fa00a-108">`mdModuleRef`, if the type is defined in the same assembly in which the caller is defined.</span></span>  
  
- <span data-ttu-id="fa00a-109">`mdAssemblyRef`, bir çağıranın tanımlanır dışındaki bir bütünleştirilmiş kodda tür tanımlı ise.</span><span class="sxs-lookup"><span data-stu-id="fa00a-109">`mdAssemblyRef`, if the type is defined in an assembly other than the one in which the caller is defined.</span></span>  
  
- <span data-ttu-id="fa00a-110">`mdTypeRef`, iç içe türü türü ise.</span><span class="sxs-lookup"><span data-stu-id="fa00a-110">`mdTypeRef`, if the type is a nested type.</span></span>  
  
- <span data-ttu-id="fa00a-111">`mdModule`, türü çağıran tanımlanır aynı modülde tanımlandıysa.</span><span class="sxs-lookup"><span data-stu-id="fa00a-111">`mdModule`, if the type is defined in the same module in which the caller is defined.</span></span>  
  
- <span data-ttu-id="fa00a-112">Türü genel olarak tanımlanmışsa null.</span><span class="sxs-lookup"><span data-stu-id="fa00a-112">Null, if the type is defined globally.</span></span>  
  
 `szName`  
 <span data-ttu-id="fa00a-113">[in] Unicode hedef türünün adı.</span><span class="sxs-lookup"><span data-stu-id="fa00a-113">[in] The name of the target type in Unicode.</span></span>  
  
 `ptr`  
 <span data-ttu-id="fa00a-114">[out] Bir işaretçi `mdTypeRef` türüne atanan belirteci.</span><span class="sxs-lookup"><span data-stu-id="fa00a-114">[out] A pointer to the `mdTypeRef` token that is assigned to the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa00a-115">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="fa00a-115">Requirements</span></span>  
 <span data-ttu-id="fa00a-116">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa00a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa00a-117">**Üst bilgi:** COR.h</span><span class="sxs-lookup"><span data-stu-id="fa00a-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fa00a-118">**Kitaplığı:** Bir kaynak olarak MSCorEE.dll kullanılan</span><span class="sxs-lookup"><span data-stu-id="fa00a-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa00a-119">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa00a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa00a-120">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="fa00a-120">See also</span></span>

- [<span data-ttu-id="fa00a-121">IMetaDataEmit Arabirimi</span><span class="sxs-lookup"><span data-stu-id="fa00a-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="fa00a-122">IMetaDataEmit2 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="fa00a-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
