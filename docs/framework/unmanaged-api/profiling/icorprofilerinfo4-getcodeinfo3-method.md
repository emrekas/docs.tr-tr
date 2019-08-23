---
title: ICorProfilerInfo4::GetCodeInfo3 Metodu
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetCodeInfo3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetCodeInfo3
helpviewer_keywords:
- GetCodeInfo3 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetCodeInfo3 method [.NET Framework profiling]
ms.assetid: bb8c105e-4d9a-4684-8c05-ed6909cc1b8c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 084007bd7ab20449c28d2c5e6125cbacfa280526
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912709"
---
# <a name="icorprofilerinfo4getcodeinfo3-method"></a><span data-ttu-id="fc6cd-102">ICorProfilerInfo4::GetCodeInfo3 Metodu</span><span class="sxs-lookup"><span data-stu-id="fc6cd-102">ICorProfilerInfo4::GetCodeInfo3 Method</span></span>
<span data-ttu-id="fc6cd-103">Belirtilen işlevin JıT yeniden derlenmesi sürümü ile ilişkili yerel kod kapsamlarını alır.</span><span class="sxs-lookup"><span data-stu-id="fc6cd-103">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc6cd-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="fc6cd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeInfo3(  
    [in]  FunctionID functionID,  
    [in]  ReJITID reJitId,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc6cd-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="fc6cd-105">Parameters</span></span>  
 `functionID`  
 <span data-ttu-id="fc6cd-106">'ndaki Yerel kodun ilişkilendirildiği işlevin KIMLIĞI.</span><span class="sxs-lookup"><span data-stu-id="fc6cd-106">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `reJitId`  
 <span data-ttu-id="fc6cd-107">'ndaki JıT-yeniden derleme işlevinin kimliği.</span><span class="sxs-lookup"><span data-stu-id="fc6cd-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `cCodeInfos`  
 <span data-ttu-id="fc6cd-108">'ndaki `codeInfos` Dizinin boyutu.</span><span class="sxs-lookup"><span data-stu-id="fc6cd-108">[in] The size of the `codeInfos` array.</span></span>  
  
 `pcCodeInfos`  
 <span data-ttu-id="fc6cd-109">dışı Kullanılabilir toplam [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) yapısı sayısına yönelik bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="fc6cd-109">[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.</span></span>  
  
 `codeInfos`  
 <span data-ttu-id="fc6cd-110">dışı Arayan tarafından sağlanmış arabellek.</span><span class="sxs-lookup"><span data-stu-id="fc6cd-110">[out] A caller-provided buffer.</span></span> <span data-ttu-id="fc6cd-111">Yöntem çağrıldıktan sonra, her biri yerel kod bloğunu açıklayan `COR_PRF_CODE_INFO` bir yapı dizisi içerir.</span><span class="sxs-lookup"><span data-stu-id="fc6cd-111">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc6cd-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="fc6cd-112">Remarks</span></span>  
 <span data-ttu-id="fc6cd-113">Yöntemi, GetCodeInfo2 ile benzerdir, ancak belirtilen IP adresini içeren işlevin JIT yeniden derlenmesi kimliğini alır. [](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) `GetCodeInfo3`</span><span class="sxs-lookup"><span data-stu-id="fc6cd-113">The `GetCodeInfo3` method is similar to [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md), except that it will get the JIT-recompiled ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fc6cd-114">`GetCodeInfo3`bir çöp toplama tetiklenebilir, ancak [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) olmayacaktır.</span><span class="sxs-lookup"><span data-stu-id="fc6cd-114">`GetCodeInfo3` can trigger a garbage collection, whereas [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) will not.</span></span> <span data-ttu-id="fc6cd-115">Daha fazla bilgi için bkz. [corprof_e_unsupported_call_sequence](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md) HRESULT.</span><span class="sxs-lookup"><span data-stu-id="fc6cd-115">For more information, see the [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md) HRESULT.</span></span>  
  
 <span data-ttu-id="fc6cd-116">Kapsamlar, artan ortak ara dil (CıL) kaydırmasının sırasına göre sıralanır.</span><span class="sxs-lookup"><span data-stu-id="fc6cd-116">The extents are sorted in order of increasing Common Intermediate Language (CIL) offset.</span></span>  
  
 <span data-ttu-id="fc6cd-117">Geri döndüğünde, `codeInfos` arabelleğin tüm COR_PRF_CODE_INFO yapılarını içerecek kadar büyük olduğunu doğrulamanız gerekir. [](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) `GetCodeInfo3`</span><span class="sxs-lookup"><span data-stu-id="fc6cd-117">After `GetCodeInfo3` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures.</span></span> <span data-ttu-id="fc6cd-118">Bunu yapmak için değerini `cCodeInfos` `cchName` parametresinin değeriyle karşılaştırın.</span><span class="sxs-lookup"><span data-stu-id="fc6cd-118">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="fc6cd-119">`codeInfos` `cCodeInfos` `GetCodeInfo3` [](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) BirCOR_PRF_CODE_INFO`pcCodeInfos`yapısının boyutuna göre ayrılmışsa,dahaküçükbirarabellekayırarak,yeni,dahabüyükboyutlagüncelleştirin`cCodeInfos` ve yeniden çağırın.</span><span class="sxs-lookup"><span data-stu-id="fc6cd-119">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo3` again.</span></span>  
  
 <span data-ttu-id="fc6cd-120">Alternatif olarak, doğru arabellek boyutunu `GetCodeInfo3` elde etmek için ilk olarak `codeInfos` sıfır uzunluklu bir arabellek ile çağrı yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fc6cd-120">Alternatively, you can first call `GetCodeInfo3` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="fc6cd-121">Daha sonra `codeInfos` arabellek boyutunu ' de `pcCodeInfos`döndürülen değere ayarlayabilir, bir COR_PRF_CODE_INFO yapısının boyutuyla çarpılır ve yeniden çağırabilirsiniz. [](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) `GetCodeInfo3`</span><span class="sxs-lookup"><span data-stu-id="fc6cd-121">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure, and call `GetCodeInfo3` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc6cd-122">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="fc6cd-122">Requirements</span></span>  
 <span data-ttu-id="fc6cd-123">**Platform** Bkz. [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc6cd-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc6cd-124">**Üst bilgi** CorProf. IDL, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="fc6cd-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fc6cd-125">**Kitaplığı** Corguid. lib</span><span class="sxs-lookup"><span data-stu-id="fc6cd-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc6cd-126">**.NET Framework sürümleri:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc6cd-126">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc6cd-127">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="fc6cd-127">See also</span></span>

- [<span data-ttu-id="fc6cd-128">GetCodeInfo2 Yöntemi</span><span class="sxs-lookup"><span data-stu-id="fc6cd-128">GetCodeInfo2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)
- [<span data-ttu-id="fc6cd-129">ICorProfilerInfo4 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="fc6cd-129">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="fc6cd-130">Profil Oluşturma Arabirimleri</span><span class="sxs-lookup"><span data-stu-id="fc6cd-130">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="fc6cd-131">Profil Oluşturma</span><span class="sxs-lookup"><span data-stu-id="fc6cd-131">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
