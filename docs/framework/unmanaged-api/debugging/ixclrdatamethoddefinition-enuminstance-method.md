---
title: IXCLRDataMethodDefinition::EnumInstance yöntemi
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EnumInstance Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 420acda89858713f12ea87a8c8d3909682a3f5e3
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416213"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a><span data-ttu-id="a3b1a-102">IXCLRDataMethodDefinition::EnumInstance yöntemi</span><span class="sxs-lookup"><span data-stu-id="a3b1a-102">IXCLRDataMethodDefinition::EnumInstance Method</span></span>

<span data-ttu-id="a3b1a-103">Bu yöntem tanımını örneklerini sıralar.</span><span class="sxs-lookup"><span data-stu-id="a3b1a-103">Enumerates the instances of this method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="a3b1a-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="a3b1a-104">Syntax</span></span>

```
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

### <a name="parameters"></a><span data-ttu-id="a3b1a-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="a3b1a-105">Parameters</span></span>

<span data-ttu-id="a3b1a-106">`handle` [out içinde] Örnekleri numaralandırma tanıtıcısı.</span><span class="sxs-lookup"><span data-stu-id="a3b1a-106">`handle` [in, out] A handle for enumerating the instances.</span></span>

<span data-ttu-id="a3b1a-107">`instance` [out] Numaralandırılmış örneği.</span><span class="sxs-lookup"><span data-stu-id="a3b1a-107">`instance` [out] The enumerated instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="a3b1a-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a3b1a-108">Remarks</span></span>

<span data-ttu-id="a3b1a-109">Sağlanan yöntem parçasıdır `IXCLRDataMethodDefinition` arabirim ve sanal yöntem tablosunun dördüncü yuvaya karşılık gelir.</span><span class="sxs-lookup"><span data-stu-id="a3b1a-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="a3b1a-110">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="a3b1a-110">Requirements</span></span>

<span data-ttu-id="a3b1a-111">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3b1a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="a3b1a-112">**Üst bilgi:** Hiçbiri</span><span class="sxs-lookup"><span data-stu-id="a3b1a-112">**Header:** None</span></span>  
<span data-ttu-id="a3b1a-113">**Kitaplığı:** Hiçbiri</span><span class="sxs-lookup"><span data-stu-id="a3b1a-113">**Library:** None</span></span>  
<span data-ttu-id="a3b1a-114">**.NET framework sürümleri:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a3b1a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="a3b1a-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a3b1a-115">See Also</span></span>

- [<span data-ttu-id="a3b1a-116">CLRDataSourceType numaralandırması</span><span class="sxs-lookup"><span data-stu-id="a3b1a-116">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="a3b1a-117">Hata Ayıklama</span><span class="sxs-lookup"><span data-stu-id="a3b1a-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="a3b1a-118">IXCLRDataMethodDefinition arabirimi</span><span class="sxs-lookup"><span data-stu-id="a3b1a-118">IXCLRDataMethodDefinition Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
- [<span data-ttu-id="a3b1a-119">IXCLRDataMethodInstance arabirimi</span><span class="sxs-lookup"><span data-stu-id="a3b1a-119">IXCLRDataMethodInstance Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-interface.md)
