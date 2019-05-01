---
title: INotifySink2::OnSyncCallOut Yöntemi
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallOut
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallOut
helpviewer_keywords:
- INotifySink2::OnSyncCallOut method [.NET Framework debugging]
- OnSyncCallOut method [.NET Framework debugging]
ms.assetid: 97f15656-8677-4079-8553-a1d8603355d6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4cf36b9e09f5e9eeb28930a6adc48426927a60e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940367"
---
# <a name="inotifysink2onsynccallout-method"></a><span data-ttu-id="7d86f-102">INotifySink2::OnSyncCallOut Yöntemi</span><span class="sxs-lookup"><span data-stu-id="7d86f-102">INotifySink2::OnSyncCallOut Method</span></span>
<span data-ttu-id="7d86f-103">Bir çağrı kullanıma olduğunda çağrılır.</span><span class="sxs-lookup"><span data-stu-id="7d86f-103">Gets invoked when a call is out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d86f-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="7d86f-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallOut  
(  
    [in]  CALL_ID  in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*   out_pBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d86f-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="7d86f-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="7d86f-106">[in] Çıkış olan çağrı kimliği. Bkz: [call_ıd yapısı](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="7d86f-106">[in] ID of the call that is out. See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="7d86f-107">[out] Arabellek çağırın.</span><span class="sxs-lookup"><span data-stu-id="7d86f-107">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="7d86f-108">[out] Çağrı arabelleğin bayt cinsinden boyutu.</span><span class="sxs-lookup"><span data-stu-id="7d86f-108">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d86f-109">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="7d86f-109">Return Value</span></span>  
 <span data-ttu-id="7d86f-110">Yöntem başarılı olursa S_OK.</span><span class="sxs-lookup"><span data-stu-id="7d86f-110">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d86f-111">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="7d86f-111">Requirements</span></span>  
 <span data-ttu-id="7d86f-112">**Üst bilgi:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="7d86f-112">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d86f-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="7d86f-113">See also</span></span>

- [<span data-ttu-id="7d86f-114">INotifySink2 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="7d86f-114">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="7d86f-115">INotifySource2 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="7d86f-115">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="7d86f-116">INotifyConnection2 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="7d86f-116">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
