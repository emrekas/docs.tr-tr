---
title: ICorProfilerInfo4 Arabirimi
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4
helpviewer_keywords:
- ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 80a5308e-c22f-4201-ba89-31cc8562515b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 34c358a3405262787ed495bf9d8d75462d97a71f
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/30/2019
ms.locfileid: "66380339"
---
# <a name="icorprofilerinfo4-interface"></a><span data-ttu-id="3561b-102">ICorProfilerInfo4 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="3561b-102">ICorProfilerInfo4 Interface</span></span>
<span data-ttu-id="3561b-103">İstek bilgilerini ve ortak dil çalışma zamanı olayı izlemeyi denetlemek için (CLR) ile iletişim kurmak için kod profil oluşturucuları kullanmak için yöntemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="3561b-103">Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information.</span></span> <span data-ttu-id="3561b-104">biçimindeki telefon numarasıdır.</span><span class="sxs-lookup"><span data-stu-id="3561b-104">.</span></span> <span data-ttu-id="3561b-105">`ICorProfilerInfo4` Arabirimidir diğer uzantı `ICorProfilerInfo` arabirimleri.</span><span class="sxs-lookup"><span data-stu-id="3561b-105">The `ICorProfilerInfo4` interface is an extension of the other `ICorProfilerInfo` interfaces.</span></span> <span data-ttu-id="3561b-106">Bu, just-ın-time (JIT) yeniden derleme, .NET Framework 4. 5 ' eklenen desteklemek için yeni yöntemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="3561b-106">It provides new methods to support just-in-time (JIT) recompilation, added in the .NET Framework 4.5.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3561b-107">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="3561b-107">Methods</span></span>  
  
|<span data-ttu-id="3561b-108">Yöntem</span><span class="sxs-lookup"><span data-stu-id="3561b-108">Method</span></span>|<span data-ttu-id="3561b-109">Açıklama</span><span class="sxs-lookup"><span data-stu-id="3561b-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3561b-110">EnumJITedFunctions2 Yöntemi</span><span class="sxs-lookup"><span data-stu-id="3561b-110">EnumJITedFunctions2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)|<span data-ttu-id="3561b-111">Daha önce JIT olarak derlenmiş ve JIT yeniden derlenen tüm işlevler için bir numaralandırıcı döndürür.</span><span class="sxs-lookup"><span data-stu-id="3561b-111">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span>|  
|[<span data-ttu-id="3561b-112">EnumThreads Yöntemi</span><span class="sxs-lookup"><span data-stu-id="3561b-112">EnumThreads Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumthreads-method.md)|<span data-ttu-id="3561b-113">Profili oluşturulan işlemdeki tüm yönetilen iş parçacıkları koleksiyonu sırayla yinelemek için yöntemler sağlayan bir numaralandırıcıyı alır.</span><span class="sxs-lookup"><span data-stu-id="3561b-113">Gets an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>|  
|[<span data-ttu-id="3561b-114">GetCodeInfo3 Yöntemi</span><span class="sxs-lookup"><span data-stu-id="3561b-114">GetCodeInfo3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)|<span data-ttu-id="3561b-115">Belirtilen işlev JIT yeniden derlenen sürümü ile ilişkili yerel kod kapsam alır.</span><span class="sxs-lookup"><span data-stu-id="3561b-115">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>|  
|[<span data-ttu-id="3561b-116">GetFunctionFromIP2 Yöntemi</span><span class="sxs-lookup"><span data-stu-id="3561b-116">GetFunctionFromIP2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getfunctionfromip2-method.md)|<span data-ttu-id="3561b-117">Yönetilen kod yönerge işaretçisini belirtilen işlevi yeniden JIT derlenen sürümüne eşler.</span><span class="sxs-lookup"><span data-stu-id="3561b-117">Maps a managed code instruction pointer to the JIT-recompiled version of a specified function.</span></span>|  
|[<span data-ttu-id="3561b-118">GetILToNativeMapping2 Yöntemi</span><span class="sxs-lookup"><span data-stu-id="3561b-118">GetILToNativeMapping2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)|<span data-ttu-id="3561b-119">Harita, Microsoft Ara dil (MSIL) için belirtilen işlev JIT yeniden derlenen sürümünde yer alan kodun yerel uzaklıklar uzaklıkları alır.</span><span class="sxs-lookup"><span data-stu-id="3561b-119">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function .</span></span>|  
|[<span data-ttu-id="3561b-120">GetObjectSize2 Yöntemi</span><span class="sxs-lookup"><span data-stu-id="3561b-120">GetObjectSize2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md)|<span data-ttu-id="3561b-121">Belirtilen nesnenin boyutunu döndürür.</span><span class="sxs-lookup"><span data-stu-id="3561b-121">Returns the size of a specified object.</span></span>|  
|[<span data-ttu-id="3561b-122">GetReJITIDs Yöntemi</span><span class="sxs-lookup"><span data-stu-id="3561b-122">GetReJITIDs Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getrejitids-method.md)|<span data-ttu-id="3561b-123">Yine de atanan tüm JIT yeniden derlenen sürümlerini belirtilen işlev tanımlamak kimlikleri dizisi döndürür.</span><span class="sxs-lookup"><span data-stu-id="3561b-123">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span>|  
|[<span data-ttu-id="3561b-124">InitializeCurrentThread Yöntemi</span><span class="sxs-lookup"><span data-stu-id="3561b-124">InitializeCurrentThread Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-initializecurrentthread-method.md)|<span data-ttu-id="3561b-125">Geçerli iş parçacığı sonraki profil oluşturucu bu kilitlenme önlenebilir şekilde aynı iş parçacığında API çağrılarının tarifelerindeki başlatır.</span><span class="sxs-lookup"><span data-stu-id="3561b-125">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>|  
|[<span data-ttu-id="3561b-126">RequestReJIT Yöntemi</span><span class="sxs-lookup"><span data-stu-id="3561b-126">RequestReJIT Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md)|<span data-ttu-id="3561b-127">Belirtilen işlevler tüm örneklerinin bir JIT yeniden derlemesi ister.</span><span class="sxs-lookup"><span data-stu-id="3561b-127">Requests a JIT recompilation of all instances of the specified functions.</span></span>|  
|[<span data-ttu-id="3561b-128">RequestRevert Yöntemi</span><span class="sxs-lookup"><span data-stu-id="3561b-128">RequestRevert Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)|<span data-ttu-id="3561b-129">Tüm örneklerinin özgünlüğünü belirtilen işleve döner.</span><span class="sxs-lookup"><span data-stu-id="3561b-129">Reverts all instances of the specified functions to their original versions.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3561b-130">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="3561b-130">Remarks</span></span>  
 <span data-ttu-id="3561b-131">CLR yöntemlerini uygulayan `ICorProfilerInfo4` ücretsiz iş parçacıklı model kullanarak arabirimi.</span><span class="sxs-lookup"><span data-stu-id="3561b-131">The CLR implements the methods of the `ICorProfilerInfo4` interface by using the free-threaded model.</span></span> <span data-ttu-id="3561b-132">Her yöntem başarısı veya başarısızlığı göstermek için HRESULT döndürür.</span><span class="sxs-lookup"><span data-stu-id="3561b-132">Each method returns an HRESULT to indicate success or failure.</span></span> <span data-ttu-id="3561b-133">Olası dönüş kodları listesi için CorError.h dosyasına bakın.</span><span class="sxs-lookup"><span data-stu-id="3561b-133">For a list of possible return codes, see the CorError.h file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3561b-134">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="3561b-134">Requirements</span></span>  
 <span data-ttu-id="3561b-135">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3561b-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3561b-136">**Üst bilgi:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3561b-136">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3561b-137">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3561b-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3561b-138">**.NET framework sürümleri:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3561b-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3561b-139">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="3561b-139">See also</span></span>

- [<span data-ttu-id="3561b-140">Profil Oluşturma Arabirimleri</span><span class="sxs-lookup"><span data-stu-id="3561b-140">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="3561b-141">ICorProfilerInfo Arabirimi</span><span class="sxs-lookup"><span data-stu-id="3561b-141">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
