---
title: CorDebugUserState Numaralandırması
ms.date: 03/30/2017
api_name:
- CorDebugUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUserState
helpviewer_keywords:
- CorDebugUserState enumeration [.NET Framework debugging]
ms.assetid: 5f6c2bcd-8102-4e3b-abc5-86ab0bd62def
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1ee5044c2223d3ff90cf10b53cad4e1b353d87c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726522"
---
# <a name="cordebuguserstate-enumeration"></a><span data-ttu-id="85923-102">CorDebugUserState Numaralandırması</span><span class="sxs-lookup"><span data-stu-id="85923-102">CorDebugUserState Enumeration</span></span>
<span data-ttu-id="85923-103">Kullanıcı durumunu bir iş parçacığının gösterir.</span><span class="sxs-lookup"><span data-stu-id="85923-103">Indicates the user state of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85923-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="85923-104">Syntax</span></span>  
  
```  
typedef enum CorDebugUserState {  
    USER_STOP_REQUESTED     =  0x01,  
    USER_SUSPEND_REQUESTED  =  0x02,  
    USER_BACKGROUND         =  0x04,  
    USER_UNSTARTED          =  0x08,  
    USER_STOPPED            =  0x10,  
    USER_WAIT_SLEEP_JOIN    =  0x20,  
    USER_SUSPENDED          =  0x40,  
    USER_UNSAFE_POINT       =  0x80,  
    USER_THREADPOOL         = 0x100  
} CorDebugUserState;  
```  
  
## <a name="members"></a><span data-ttu-id="85923-105">Üyeler</span><span class="sxs-lookup"><span data-stu-id="85923-105">Members</span></span>  
  
|<span data-ttu-id="85923-106">Değer</span><span class="sxs-lookup"><span data-stu-id="85923-106">Value</span></span>|<span data-ttu-id="85923-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="85923-107">Description</span></span>|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|<span data-ttu-id="85923-108">İş parçacığının sonlandırılması istendi.</span><span class="sxs-lookup"><span data-stu-id="85923-108">A termination of the thread has been requested.</span></span>|  
|`USER_SUSPEND_REQUESTED`|<span data-ttu-id="85923-109">İş parçacığının bir askıya alma isteğinde bulundu.</span><span class="sxs-lookup"><span data-stu-id="85923-109">A suspension of the thread has been requested.</span></span>|  
|`USER_BACKGROUND`|<span data-ttu-id="85923-110">İş parçacığı arka planda çalışıyor.</span><span class="sxs-lookup"><span data-stu-id="85923-110">The thread is running in the background.</span></span>|  
|`USER_UNSTARTED`|<span data-ttu-id="85923-111">Yürütme iş parçacığı başlatılmadı.</span><span class="sxs-lookup"><span data-stu-id="85923-111">The thread has not started executing.</span></span>|  
|`USER_STOPPED`|<span data-ttu-id="85923-112">İş parçacığı sonlandırıldı.</span><span class="sxs-lookup"><span data-stu-id="85923-112">The thread has been terminated.</span></span>|  
|`USER_WAIT_SLEEP_JOIN`|<span data-ttu-id="85923-113">İş parçacığı bir görevi tamamlamak başka bir iş parçacığı için bekliyor.</span><span class="sxs-lookup"><span data-stu-id="85923-113">The thread is waiting for another thread to complete a task.</span></span>|  
|`USER_SUSPENDED`|<span data-ttu-id="85923-114">İş parçacığını askıya alındı.</span><span class="sxs-lookup"><span data-stu-id="85923-114">The thread has been suspended.</span></span>|  
|`USER_UNSAFE_POINT`|<span data-ttu-id="85923-115">İş parçacığı güvenli olmayan bir noktada ' dir.</span><span class="sxs-lookup"><span data-stu-id="85923-115">The thread is at an unsafe point.</span></span> <span data-ttu-id="85923-116">Diğer bir deyişle, yürütme noktasında bir çöp toplama burada engelleyebilir iş parçacığıdır.</span><span class="sxs-lookup"><span data-stu-id="85923-116">That is, the thread is at a point in execution where it may block garbage collection.</span></span><br /><br /> <span data-ttu-id="85923-117">Hata ayıklama olaylarını güvenli olmayan noktalarından gönderilir, ancak güvenli olmayan bir noktada bir iş parçacığını askıya büyük olasılıkla neden olacak bir kilitlenme iş parçacığı sürdürülene kadar.</span><span class="sxs-lookup"><span data-stu-id="85923-117">Debug events may be dispatched from unsafe points, but suspending a thread at an unsafe point  will very likely cause a deadlock until the thread is resumed.</span></span> <span data-ttu-id="85923-118">Güvenli ve güvenli olmayan noktaları, just-in-time (JIT) ve çöp toplama uygulama tarafından belirlenir.</span><span class="sxs-lookup"><span data-stu-id="85923-118">The safe and unsafe points are determined by the just-in-time (JIT) and garbage collection implementation.</span></span>|  
|`USER_THREADPOOL`|<span data-ttu-id="85923-119">İş parçacığı havuzu iş parçacığıdır.</span><span class="sxs-lookup"><span data-stu-id="85923-119">The thread is from the thread pool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85923-120">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="85923-120">Remarks</span></span>  
 <span data-ttu-id="85923-121">Kullanıcı durumunu bir iş parçacığının iş parçacığı hata ayıklayıcısı incelerken olan durumudur.</span><span class="sxs-lookup"><span data-stu-id="85923-121">The user state of a thread is the state that the thread has when the debugger examines it.</span></span> <span data-ttu-id="85923-122">Bir iş parçacığı, kullanıcı durumlarını bir birleşimi olabilir.</span><span class="sxs-lookup"><span data-stu-id="85923-122">A thread may have a combination of user states.</span></span>  
  
 <span data-ttu-id="85923-123">Kullanım [Icordebugthread::getuserstate](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) bir iş parçacığının kullanıcı durumunu almak için yöntemi.</span><span class="sxs-lookup"><span data-stu-id="85923-123">Use the [ICorDebugThread::GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) method to retrieve a thread's user state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85923-124">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="85923-124">Requirements</span></span>  
 <span data-ttu-id="85923-125">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85923-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85923-126">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85923-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85923-127">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85923-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85923-128">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85923-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85923-129">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="85923-129">See also</span></span>
- [<span data-ttu-id="85923-130">Hata Ayıklama Sabit Listeleri</span><span class="sxs-lookup"><span data-stu-id="85923-130">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
