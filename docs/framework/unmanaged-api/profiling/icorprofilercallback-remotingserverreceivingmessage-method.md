---
title: ICorProfilerCallback::RemotingServerReceivingMessage Yöntemi
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerReceivingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage method [.NET Framework profiling]
- RemotingServerReceivingMessage method [.NET Framework profiling]
ms.assetid: 5604d21f-e6b7-490e-b469-42122a7568e1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 30015cc6cae935c43cdbfec1a6eeae5c703ef9f2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103213"
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a><span data-ttu-id="ad8ea-102">ICorProfilerCallback::RemotingServerReceivingMessage Yöntemi</span><span class="sxs-lookup"><span data-stu-id="ad8ea-102">ICorProfilerCallback::RemotingServerReceivingMessage Method</span></span>
<span data-ttu-id="ad8ea-103">Profil Oluşturucu işlemin bir uzak yöntem çağırma veya etkinleştirme isteği aldı bildirir.</span><span class="sxs-lookup"><span data-stu-id="ad8ea-103">Notifies the profiler that the process has received a remote method invocation or activation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad8ea-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="ad8ea-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad8ea-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="ad8ea-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="ad8ea-106">[in] Sağlanan değer karşılık gelecek bir değerle [Icorprofilercallback::remotingclientsendingmessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) Bu koşullar altında:</span><span class="sxs-lookup"><span data-stu-id="ad8ea-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="ad8ea-107">Uzaktan iletişim GUID tanımlama bilgilerinin etkin olur.</span><span class="sxs-lookup"><span data-stu-id="ad8ea-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="ad8ea-108">Kanal ileti iletilirken başarılı olur.</span><span class="sxs-lookup"><span data-stu-id="ad8ea-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="ad8ea-109">GUID tanımlama bilgileri istemci tarafı işlemini üzerinde etkindir.</span><span class="sxs-lookup"><span data-stu-id="ad8ea-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="ad8ea-110">Bu, uzak hizmet çağrıları ve bir mantıksal çağrı yığını oluşturulmasını kolay eşlemeye izin verir.</span><span class="sxs-lookup"><span data-stu-id="ad8ea-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="ad8ea-111">[in] Bir değer `true` çağrısı ise, zaman uyumsuz; Aksi takdirde `false`.</span><span class="sxs-lookup"><span data-stu-id="ad8ea-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad8ea-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ad8ea-112">Remarks</span></span>  
 <span data-ttu-id="ad8ea-113">İleti isteği zaman uyumsuz olması durumunda, isteği herhangi bir rastgele iş parçacığı tarafından hizmet verebilir.</span><span class="sxs-lookup"><span data-stu-id="ad8ea-113">If the message request is asynchronous, the request can be serviced by any arbitrary thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad8ea-114">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="ad8ea-114">Requirements</span></span>  
 <span data-ttu-id="ad8ea-115">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad8ea-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad8ea-116">**Üst bilgi:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ad8ea-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ad8ea-117">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad8ea-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ad8ea-118">.NET framework sürümleri:</span><span class="sxs-lookup"><span data-stu-id="ad8ea-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ad8ea-119">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="ad8ea-119">See also</span></span>

- [<span data-ttu-id="ad8ea-120">ICorProfilerCallback Arabirimi</span><span class="sxs-lookup"><span data-stu-id="ad8ea-120">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
