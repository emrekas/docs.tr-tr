---
title: ICorProfilerInfo2::GetThreadStaticAddress Yöntemi
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetThreadStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetThreadStaticAddress
helpviewer_keywords:
- GetThreadStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetThreadStaticAddress method [.NET Framework profiling]
ms.assetid: 8e7dbf14-98a2-4384-a950-58a7640e59df
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: de0e46f4703479daeb96cb83276ec14150125e7f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64587439"
---
# <a name="icorprofilerinfo2getthreadstaticaddress-method"></a><span data-ttu-id="a3025-102">ICorProfilerInfo2::GetThreadStaticAddress Yöntemi</span><span class="sxs-lookup"><span data-stu-id="a3025-102">ICorProfilerInfo2::GetThreadStaticAddress Method</span></span>
<span data-ttu-id="a3025-103">Belirtilen iş parçacığı kapsamında belirtilen statik iş parçacığı alanı adresini alır.</span><span class="sxs-lookup"><span data-stu-id="a3025-103">Gets the address of the specified thread-static field that is in the scope of the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3025-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="a3025-104">Syntax</span></span>  
  
```  
HRESULT GetThreadStaticAddress(  
    [in] ClassID     classId,  
    [in] mdFieldDef  fieldToken,  
    [in] ThreadID    threadId,  
    [out] void       **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3025-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="a3025-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="a3025-106">[in] İstenen iş parçacığı statik alanı içeren sınıf kimliği.</span><span class="sxs-lookup"><span data-stu-id="a3025-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="a3025-107">[in] İstenen iş parçacığı statik alan için meta veri belirteci.</span><span class="sxs-lookup"><span data-stu-id="a3025-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `threadId`  
 <span data-ttu-id="a3025-108">[in] Kapsamı istenen statik alan için iş parçacığı kimliği.</span><span class="sxs-lookup"><span data-stu-id="a3025-108">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="a3025-109">[out] Belirtilen iş parçacığı içinde statik alanı adresi için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="a3025-109">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3025-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a3025-110">Remarks</span></span>  
 <span data-ttu-id="a3025-111">`GetThreadStaticAddress` Yöntemi aşağıdakilerden birini döndürebilir:</span><span class="sxs-lookup"><span data-stu-id="a3025-111">The `GetThreadStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="a3025-112">Bir CORPROF_E_DATAINCOMPLETE belirtilen statik alanı belirtilen bağlam bir adres değil atandıysa HRESULT.</span><span class="sxs-lookup"><span data-stu-id="a3025-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="a3025-113">Adresleri nesnelerin çöp koleksiyonu yığınında olabilir.</span><span class="sxs-lookup"><span data-stu-id="a3025-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="a3025-114">Çöp toplamanın ardından bu adresler geçersiz hale gelebilir bunu sonra atık toplama profil oluşturucular geçerli olduğunu varsayın değil.</span><span class="sxs-lookup"><span data-stu-id="a3025-114">These addresses may become invalid after garbage collection, so after garbage collection profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="a3025-115">Bir sınıfın sınıf oluşturucusu tamamlanmadan önce `GetThreadStaticAddress` bazı statik alanlar zaten başlatılmış olabilir ancak tüm kendi statik alanları için CORPROF_E_DATAINCOMPLETE döndürür ve çöp toplama nesneleri kök dizini değiştirme.</span><span class="sxs-lookup"><span data-stu-id="a3025-115">Before a class’s class constructor is completed, `GetThreadStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3025-116">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="a3025-116">Requirements</span></span>  
 <span data-ttu-id="a3025-117">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3025-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3025-118">**Üst bilgi:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a3025-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a3025-119">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3025-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3025-120">**.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3025-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3025-121">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="a3025-121">See also</span></span>

- [<span data-ttu-id="a3025-122">ICorProfilerInfo Arabirimi</span><span class="sxs-lookup"><span data-stu-id="a3025-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="a3025-123">ICorProfilerInfo2 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="a3025-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
