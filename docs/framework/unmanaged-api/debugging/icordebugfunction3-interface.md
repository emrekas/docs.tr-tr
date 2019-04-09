---
title: ICorDebugFunction3 Arabirimi
ms.date: 03/30/2017
api_name:
- ICorDebugFunction3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c29d631f84ce2dd7532e32951e71d6597218ebb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59088866"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="4bb78-102">ICorDebugFunction3 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="4bb78-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="4bb78-103">[.NET Framework 4.5.2 ve sonraki sürümlerinde desteklenen]</span><span class="sxs-lookup"><span data-stu-id="4bb78-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="4bb78-104">ICorDebugFunction arabirimi ReJIT istekten koda erişim sağlamak için mantıksal olarak genişletir.</span><span class="sxs-lookup"><span data-stu-id="4bb78-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4bb78-105">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="4bb78-105">Methods</span></span>  
  
|<span data-ttu-id="4bb78-106">Yöntem</span><span class="sxs-lookup"><span data-stu-id="4bb78-106">Method</span></span>|<span data-ttu-id="4bb78-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="4bb78-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4bb78-108">GetActiveReJitRequestILCode Yöntemi</span><span class="sxs-lookup"><span data-stu-id="4bb78-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="4bb78-109">Bir arabirim işaretçisi alır bir [Icordebugılcode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) , etkin bir ReJIT istek IL içerir.</span><span class="sxs-lookup"><span data-stu-id="4bb78-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4bb78-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="4bb78-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bb78-111">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="4bb78-111">Requirements</span></span>  
 <span data-ttu-id="4bb78-112">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bb78-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bb78-113">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4bb78-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4bb78-114">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4bb78-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4bb78-115">.NET framework sürümleri:</span><span class="sxs-lookup"><span data-stu-id="4bb78-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4bb78-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="4bb78-116">See also</span></span>

- [<span data-ttu-id="4bb78-117">Hata Ayıklama Arabirimleri</span><span class="sxs-lookup"><span data-stu-id="4bb78-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="4bb78-118">Hata Ayıklama</span><span class="sxs-lookup"><span data-stu-id="4bb78-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="4bb78-119">ReJIT: Nasıl yapılır Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="4bb78-119">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
