---
title: ICorProfilerCallback::RemotingClientInvocationStarted Yöntemi
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationStarted
helpviewer_keywords:
- RemotingClientInvocationStarted method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationStarted method [.NET Framework profiling]
ms.assetid: 796b63f3-c809-47f1-89cc-b23ad8eb5e79
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b452cbfc5564d98b3770c2ed97f8453296f0fc13
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157696"
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a><span data-ttu-id="d62e1-102">ICorProfilerCallback::RemotingClientInvocationStarted Yöntemi</span><span class="sxs-lookup"><span data-stu-id="d62e1-102">ICorProfilerCallback::RemotingClientInvocationStarted Method</span></span>
<span data-ttu-id="d62e1-103">Profil Oluşturucu bir çağrının sürebileceği başlatıldığını bildirir.</span><span class="sxs-lookup"><span data-stu-id="d62e1-103">Notifies the profiler that a remoting call has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d62e1-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="d62e1-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="d62e1-105">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d62e1-105">Remarks</span></span>  
 <span data-ttu-id="d62e1-106">Bu olay, zaman uyumlu ve zaman uyumsuz çağrılar için aynıdır.</span><span class="sxs-lookup"><span data-stu-id="d62e1-106">This event is the same for synchronous and asynchronous calls.</span></span>  
  
 <span data-ttu-id="d62e1-107">Her biri aşağıdaki geri çağırmalar çiftleri aynı iş parçacığında ortaya çıkar:</span><span class="sxs-lookup"><span data-stu-id="d62e1-107">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
-   `RemotingClientInvocationStarted` <span data-ttu-id="d62e1-108">ve [Icorprofilercallback::remotingclientsendingmessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="d62e1-108">and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
-   <span data-ttu-id="d62e1-109">[Icorprofilercallback::remotingclientreceivingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) ve [Icorprofilercallback::remotingclientınvocationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="d62e1-109">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
-   <span data-ttu-id="d62e1-110">[Icorprofilercallback::remotingserverınvocationreturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) ve [Icorprofilercallback::remotingserversendingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="d62e1-110">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="d62e1-111">Uzaktan iletişimini geri çağırmaları ile ilgili aşağıdaki sorunları farkında olmalıdır:</span><span class="sxs-lookup"><span data-stu-id="d62e1-111">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
-   <span data-ttu-id="d62e1-112">İstemciden çağrılan ve sunucu üzerinde yürütülen işlevler için bildirimler düzgün alınmadı şekilde profil oluşturucu API, uzak bir işlevin yürütülmesini yansıtılmaz.</span><span class="sxs-lookup"><span data-stu-id="d62e1-112">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="d62e1-113">Gerçek çağrısını bir proxy nesnesi olur; Profil Oluşturucu için bazı işlevlerini JIT olarak derlenmiş ancak hiçbir zaman kullanılan görünür.</span><span class="sxs-lookup"><span data-stu-id="d62e1-113">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
-   <span data-ttu-id="d62e1-114">Profil Oluşturucu, zaman uyumsuz uzaktan iletişim olayları için doğru bildirimleri almaz.</span><span class="sxs-lookup"><span data-stu-id="d62e1-114">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d62e1-115">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="d62e1-115">Requirements</span></span>  
 <span data-ttu-id="d62e1-116">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d62e1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d62e1-117">**Üst bilgi:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d62e1-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d62e1-118">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d62e1-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d62e1-119">.NET framework sürümleri:</span><span class="sxs-lookup"><span data-stu-id="d62e1-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d62e1-120">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d62e1-120">See also</span></span>

- [<span data-ttu-id="d62e1-121">ICorProfilerCallback Arabirimi</span><span class="sxs-lookup"><span data-stu-id="d62e1-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
