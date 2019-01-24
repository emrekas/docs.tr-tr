---
title: ICorProfilerFunctionControl Arabirimi
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl
helpviewer_keywords:
- ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 4e3d3141-4662-4166-8f05-bc857c1b4216
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 37e0c9dcbd8975338e7c64dbd9c44dd54508b4d6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649719"
---
# <a name="icorprofilerfunctioncontrol-interface"></a><span data-ttu-id="68063-102">ICorProfilerFunctionControl Arabirimi</span><span class="sxs-lookup"><span data-stu-id="68063-102">ICorProfilerFunctionControl Interface</span></span>
<span data-ttu-id="68063-103">Bir kod profil oluşturucu nasıl JIT Derleyici kodu belirli bir yöntem yeniden derlemeden oluşturmasını denetlemek için (CLR) ortak dil çalışma zamanıyla iletişim kurmasına izin vermek için yöntemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="68063-103">Provides methods that allow a code profiler to communicate with the common language runtime (CLR) to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="68063-104">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="68063-104">Methods</span></span>  
  
|<span data-ttu-id="68063-105">Yöntem</span><span class="sxs-lookup"><span data-stu-id="68063-105">Method</span></span>|<span data-ttu-id="68063-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="68063-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="68063-107">SetCodegenFlags Yöntemi</span><span class="sxs-lookup"><span data-stu-id="68063-107">SetCodegenFlags Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md)|<span data-ttu-id="68063-108">Bir veya daha fazla bayraklarını ayarlar [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) numaralandırması için bir tam zamanında (JIT) denetimi kod oluşturma için yeniden derlenen işlevi.</span><span class="sxs-lookup"><span data-stu-id="68063-108">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>|  
|[<span data-ttu-id="68063-109">SetILFunctionBody Yöntemi</span><span class="sxs-lookup"><span data-stu-id="68063-109">SetILFunctionBody Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilfunctionbody-method.md)|<span data-ttu-id="68063-110">Ortak Ara Dili (CIL) yönteminin gövdesinin yerini alır.</span><span class="sxs-lookup"><span data-stu-id="68063-110">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>|  
|[<span data-ttu-id="68063-111">SetILInstrumentedCodeMap Yöntemi</span><span class="sxs-lookup"><span data-stu-id="68063-111">SetILInstrumentedCodeMap Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)|<span data-ttu-id="68063-112">Belirtilen işlev için kod haritası, belirtilen ortak Ara dil (CIL) map girişlerini kullanarak ayarlar.</span><span class="sxs-lookup"><span data-stu-id="68063-112">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68063-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="68063-113">Remarks</span></span>  
 <span data-ttu-id="68063-114">`ICorProfilerFunctionControl` Arabirimi kod oluşturma için tek bir znovu işlevi denetlemek için yöntemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="68063-114">The `ICorProfilerFunctionControl` interface provides methods for controlling code generation for a single recompiled function.</span></span> <span data-ttu-id="68063-115">Profil Oluşturucu bu arabirimi üzerinden bir örneğini alır [Icorprofilercallback4::getrejıtparameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) geri çağırma.</span><span class="sxs-lookup"><span data-stu-id="68063-115">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="68063-116">Her bir örneği `ICorProfilerFunctionControl` bir işlevin tüm örneklerini denetler.</span><span class="sxs-lookup"><span data-stu-id="68063-116">Each instance of `ICorProfilerFunctionControl` controls all instances of one function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68063-117">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="68063-117">Requirements</span></span>  
 <span data-ttu-id="68063-118">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68063-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68063-119">**Üst bilgi:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="68063-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="68063-120">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68063-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68063-121">**.NET framework sürümleri:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68063-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68063-122">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="68063-122">See also</span></span>
- [<span data-ttu-id="68063-123">ICorProfilerInfo4 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="68063-123">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="68063-124">Profil Oluşturma Arabirimleri</span><span class="sxs-lookup"><span data-stu-id="68063-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="68063-125">EnumJITedFunctions2 Yöntemi</span><span class="sxs-lookup"><span data-stu-id="68063-125">EnumJITedFunctions2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)
