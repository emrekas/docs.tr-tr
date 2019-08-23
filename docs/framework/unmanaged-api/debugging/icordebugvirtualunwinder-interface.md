---
title: ICorDebugVirtualUnwinder Arabirimi
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f78417d613023bb4fb7325560c0c06abe0874aba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967935"
---
# <a name="icordebugvirtualunwinder-interface"></a><span data-ttu-id="9c7d0-102">ICorDebugVirtualUnwinder Arabirimi</span><span class="sxs-lookup"><span data-stu-id="9c7d0-102">ICorDebugVirtualUnwinder Interface</span></span>
<span data-ttu-id="9c7d0-103">Yığın geri sarma konusunda yardımcı olmak için yöntemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="9c7d0-103">Provides methods to help in stack unwinding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9c7d0-104">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="9c7d0-104">Methods</span></span>  
  
|<span data-ttu-id="9c7d0-105">Yöntem</span><span class="sxs-lookup"><span data-stu-id="9c7d0-105">Method</span></span>|<span data-ttu-id="9c7d0-106">Ad</span><span class="sxs-lookup"><span data-stu-id="9c7d0-106">Name</span></span>|  
|------------|----------|  
|[<span data-ttu-id="9c7d0-107">GetContext Yöntemi</span><span class="sxs-lookup"><span data-stu-id="9c7d0-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-getcontext-method.md)|<span data-ttu-id="9c7d0-108">Bu unwinder 'in geçerli bağlamını alır.</span><span class="sxs-lookup"><span data-stu-id="9c7d0-108">Gets the current context of this unwinder.</span></span>|  
|[<span data-ttu-id="9c7d0-109">Next Yöntemi</span><span class="sxs-lookup"><span data-stu-id="9c7d0-109">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-next-method.md)|<span data-ttu-id="9c7d0-110">Çağıranın bağlamına ilerletir.</span><span class="sxs-lookup"><span data-stu-id="9c7d0-110">Advances to the caller's context.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c7d0-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="9c7d0-111">Remarks</span></span>  
 <span data-ttu-id="9c7d0-112">`ICorDebugVirtualUnwinder` Arabirim üyeleri, yığın geri sarma konusunda yardımcı olmak için hata ayıklayıcı tarafından uygulanır.</span><span class="sxs-lookup"><span data-stu-id="9c7d0-112">The members of the `ICorDebugVirtualUnwinder` interface are implemented by the debugger to help in stack unwinding.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9c7d0-113">Bu arabirim yalnızca .NET Native kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="9c7d0-113">This interface is available with .NET Native only.</span></span> <span data-ttu-id="9c7d0-114">Bu arabirimi .NET Native dışında ICorDebug senaryolarında uygularsanız, ortak dil çalışma zamanı bu arabirimi yoksayar.</span><span class="sxs-lookup"><span data-stu-id="9c7d0-114">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c7d0-115">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="9c7d0-115">Requirements</span></span>  
 <span data-ttu-id="9c7d0-116">**Platform** Bkz. [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c7d0-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c7d0-117">**Üst bilgi** CorDebug. IDL, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="9c7d0-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c7d0-118">**Kitaplığı** Corguid. lib</span><span class="sxs-lookup"><span data-stu-id="9c7d0-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c7d0-119">**.NET Framework sürümleri:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c7d0-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c7d0-120">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="9c7d0-120">See also</span></span>

- [<span data-ttu-id="9c7d0-121">Hata Ayıklama Arabirimleri</span><span class="sxs-lookup"><span data-stu-id="9c7d0-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="9c7d0-122">Hata Ayıklama</span><span class="sxs-lookup"><span data-stu-id="9c7d0-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
