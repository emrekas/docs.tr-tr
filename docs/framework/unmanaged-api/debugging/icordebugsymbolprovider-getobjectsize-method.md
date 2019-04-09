---
title: ICorDebugSymbolProvider::GetObjectSize yöntemi
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbcdb5541fdd49944f462321dc24131a32a42391
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107295"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="3dca9-102">ICorDebugSymbolProvider::GetObjectSize yöntemi</span><span class="sxs-lookup"><span data-stu-id="3dca9-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="3dca9-103">Kendi TypeSpec'te imzasına bağlı bir nesne için nesne boyutu döndürür.</span><span class="sxs-lookup"><span data-stu-id="3dca9-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dca9-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="3dca9-104">Syntax</span></span>  
  
```  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3dca9-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="3dca9-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="3dca9-106">[in] TypeSpec'te imza bayt sayısı.</span><span class="sxs-lookup"><span data-stu-id="3dca9-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="3dca9-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="3dca9-107">typeSig</span></span>  
 <span data-ttu-id="3dca9-108">[in] TypeSpec'te imzası.</span><span class="sxs-lookup"><span data-stu-id="3dca9-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="3dca9-109">[out] Nesnenin boyutu için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="3dca9-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3dca9-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="3dca9-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3dca9-111">Bu yöntem yalnızca .NET Native ile kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="3dca9-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3dca9-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="3dca9-112">Requirements</span></span>  
 <span data-ttu-id="3dca9-113">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3dca9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3dca9-114">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3dca9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3dca9-115">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3dca9-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3dca9-116">.NET framework sürümleri:</span><span class="sxs-lookup"><span data-stu-id="3dca9-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3dca9-117">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="3dca9-117">See also</span></span>

- [<span data-ttu-id="3dca9-118">ICorDebugSymbolProvider Arabirimi</span><span class="sxs-lookup"><span data-stu-id="3dca9-118">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="3dca9-119">Hata Ayıklama Arabirimleri</span><span class="sxs-lookup"><span data-stu-id="3dca9-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
