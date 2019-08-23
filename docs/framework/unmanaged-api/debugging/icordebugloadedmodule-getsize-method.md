---
title: ICorDebugLoadedModule::GetSize Metodu
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3067cdee1d3a5df0ad5594bce581139431fd1846
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936869"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="f1547-102">ICorDebugLoadedModule::GetSize Metodu</span><span class="sxs-lookup"><span data-stu-id="f1547-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="f1547-103">Yüklenen modülün bayt cinsinden boyutunu alır.</span><span class="sxs-lookup"><span data-stu-id="f1547-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1547-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="f1547-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1547-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="f1547-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="f1547-106">dışı Yüklenen modüldeki bayt sayısına yönelik bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="f1547-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1547-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="f1547-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1547-108">Bu yöntem yalnızca .NET Native kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="f1547-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1547-109">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="f1547-109">Requirements</span></span>  
 <span data-ttu-id="f1547-110">**Platform** Bkz. [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1547-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1547-111">**Üst bilgi** CorDebug. IDL, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="f1547-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1547-112">**Kitaplığı** Corguid. lib</span><span class="sxs-lookup"><span data-stu-id="f1547-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1547-113">**.NET Framework sürümleri:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1547-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1547-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="f1547-114">See also</span></span>

- [<span data-ttu-id="f1547-115">ICorDebugLoadedModule Arabirimi</span><span class="sxs-lookup"><span data-stu-id="f1547-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="f1547-116">Hata Ayıklama Arabirimleri</span><span class="sxs-lookup"><span data-stu-id="f1547-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
