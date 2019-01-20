---
title: IXCLRDataProcess::StartEnumModules yöntemi
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumModules Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumModules Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumModules Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: a81da147c1483e7649612050f4aba29a2cc63b49
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416210"
---
# <a name="ixclrdataprocessstartenummodules-method"></a><span data-ttu-id="9ddf5-102">IXCLRDataProcess::StartEnumModules yöntemi</span><span class="sxs-lookup"><span data-stu-id="9ddf5-102">IXCLRDataProcess::StartEnumModules Method</span></span>

<span data-ttu-id="9ddf5-103">Bir işlemin modülleri listelemek için bir tanıtıcı sağlar.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-103">Provides a handle to enumerate the modules of a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9ddf5-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="9ddf5-104">Syntax</span></span>

```
HRESULT StartEnumModules(
    [out] CLRDATA_ENUM *handle
);
```

### <a name="parameters"></a><span data-ttu-id="9ddf5-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="9ddf5-105">Parameters</span></span>

<span data-ttu-id="9ddf5-106">`handle` [out] Modülleri numaralandırma tanıtıcısı.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-106">`handle` [out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="9ddf5-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="9ddf5-107">Remarks</span></span>

<span data-ttu-id="9ddf5-108">Sağlanan yöntem parçasıdır `IXCLRDataProcess` arabirim ve sanal yöntem tablosunu 24 yuvaya karşılık gelir.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 24th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="9ddf5-109">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="9ddf5-109">Requirements</span></span>

<span data-ttu-id="9ddf5-110">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ddf5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9ddf5-111">**Üst bilgi:** Hiçbiri</span><span class="sxs-lookup"><span data-stu-id="9ddf5-111">**Header:** None</span></span>  
<span data-ttu-id="9ddf5-112">**Kitaplığı:** Hiçbiri</span><span class="sxs-lookup"><span data-stu-id="9ddf5-112">**Library:** None</span></span>  
<span data-ttu-id="9ddf5-113">**.NET framework sürümleri:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9ddf5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9ddf5-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9ddf5-114">See Also</span></span>

- [<span data-ttu-id="9ddf5-115">CLRDataSourceType numaralandırması</span><span class="sxs-lookup"><span data-stu-id="9ddf5-115">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="9ddf5-116">Hata Ayıklama</span><span class="sxs-lookup"><span data-stu-id="9ddf5-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="9ddf5-117">IXCLRDataProcess arabirimi</span><span class="sxs-lookup"><span data-stu-id="9ddf5-117">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
