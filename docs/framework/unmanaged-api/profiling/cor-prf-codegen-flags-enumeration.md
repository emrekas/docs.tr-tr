---
title: COR_PRF_CODEGEN_FLAGS Sabit Listesi
ms.date: 03/30/2017
api_name:
- COR_PRF_CODEGEN_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODEGEN_FLAGS
helpviewer_keywords:
- COR_PRF_CODEGEN_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 3e184022-0247-4824-a23d-6b29593d8d01
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 27e2f194d252baa2e2ca185d905c945d26a177a0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590097"
---
# <a name="corprfcodegenflags-enumeration"></a><span data-ttu-id="ce06b-102">COR_PRF_CODEGEN_FLAGS Sabit Listesi</span><span class="sxs-lookup"><span data-stu-id="ce06b-102">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>
<span data-ttu-id="ce06b-103">Ayarlanabilir kod oluşturma bayraklarını tanımlayan [Icorprofilerfunctioncontrol::setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="ce06b-103">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce06b-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="ce06b-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="ce06b-105">Üyeler</span><span class="sxs-lookup"><span data-stu-id="ce06b-105">Members</span></span>  
  
|<span data-ttu-id="ce06b-106">Üye</span><span class="sxs-lookup"><span data-stu-id="ce06b-106">Member</span></span>|<span data-ttu-id="ce06b-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ce06b-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|<span data-ttu-id="ce06b-108">Hiçbir işlev gövdesine bu işlevin satır içine alınmış olacaktır.</span><span class="sxs-lookup"><span data-stu-id="ce06b-108">No functions will be inlined into this function’s body.</span></span> <span data-ttu-id="ce06b-109">Bununla birlikte, işlev çağıranlarını satır içine alınmış olabilir.</span><span class="sxs-lookup"><span data-stu-id="ce06b-109">However, the function itself may be inlined into its callers.</span></span>|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|<span data-ttu-id="ce06b-110">Bu işlev gövdesi için tüm iyileştirmeler devre dışı bırakılır.</span><span class="sxs-lookup"><span data-stu-id="ce06b-110">All optimizations will be disabled for this function’s body.</span></span> <span data-ttu-id="ce06b-111">Bununla birlikte, işlev hala çağıranlarını satır içine alınmış olabilir.</span><span class="sxs-lookup"><span data-stu-id="ce06b-111">However, the function itself may still be inlined into its callers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce06b-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ce06b-112">Remarks</span></span>  
 <span data-ttu-id="ce06b-113">`COR_PRF_CODEGEN_FLAGS` Numaralandırması tarafından kullanılan [Icorprofilerfunctioncontrol::setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) kod oluşturma için JIT yeniden derlenen işlevi denetlemek profil oluşturucuyu etkinleştirme yöntemi.</span><span class="sxs-lookup"><span data-stu-id="ce06b-113">The `COR_PRF_CODEGEN_FLAGS` enumeration is used by the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method to enable the profiler to control the code generation for the JIT-recompiled function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce06b-114">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="ce06b-114">Requirements</span></span>  
 <span data-ttu-id="ce06b-115">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce06b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce06b-116">**Üst bilgi:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ce06b-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ce06b-117">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce06b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce06b-118">**.NET framework sürümleri:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce06b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce06b-119">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="ce06b-119">See also</span></span>
- [<span data-ttu-id="ce06b-120">Profil Oluşturma Sabit Listeleri</span><span class="sxs-lookup"><span data-stu-id="ce06b-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
