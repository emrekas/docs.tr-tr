---
title: ICorDebugMergedAssemblyRecord::GetVersion yöntemi
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 762ac20c376f4161aa9c053f6e5213ba24c792ba
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499789"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="a54db-102">ICorDebugMergedAssemblyRecord::GetVersion yöntemi</span><span class="sxs-lookup"><span data-stu-id="a54db-102">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>
<span data-ttu-id="a54db-103">Derlemenin sürüm bilgilerini alır.</span><span class="sxs-lookup"><span data-stu-id="a54db-103">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a54db-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="a54db-104">Syntax</span></span>  
  
```  
HRESULT GetVersion(  
   [out] USHORT *pMajor,   
   [out] USHORT *pMinor,   
   [out] USHORT *pBuild,   
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a54db-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="a54db-105">Parameters</span></span>  
 `pMajor`  
 <span data-ttu-id="a54db-106">[out] Ana sürüm numarası bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="a54db-106">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="a54db-107">[out] Alt sürüm numarasını bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="a54db-107">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="a54db-108">[out] Yapı numarası bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="a54db-108">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="a54db-109">[out] Düzeltme numarası için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="a54db-109">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a54db-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a54db-110">Remarks</span></span>  
 <span data-ttu-id="a54db-111">Derleme sürüm numaraları hakkında daha fazla bilgi için bkz: <xref:System.Version> sınıf konusuna.</span><span class="sxs-lookup"><span data-stu-id="a54db-111">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a54db-112">Bu yöntem yalnızca .NET Native ile kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="a54db-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a54db-113">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="a54db-113">Requirements</span></span>  
 <span data-ttu-id="a54db-114">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a54db-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a54db-115">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a54db-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a54db-116">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a54db-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a54db-117">**.NET framework sürümleri:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a54db-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a54db-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="a54db-118">See also</span></span>
- [<span data-ttu-id="a54db-119">ICorDebugMergedAssemblyRecord Arabirimi</span><span class="sxs-lookup"><span data-stu-id="a54db-119">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="a54db-120">Hata Ayıklama Arabirimleri</span><span class="sxs-lookup"><span data-stu-id="a54db-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
