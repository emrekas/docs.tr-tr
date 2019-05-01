---
title: INotifySink2::OnSyncCallReturn Yöntemi
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallReturn
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallReturn
helpviewer_keywords:
- OnSyncCallReturn method [.NET Framework debugging]
- INotifySink2::OnSyncCallReturn method [.NET Framework debugging]
ms.assetid: c1bda761-6292-4750-a14b-7d5db8f33456
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0adc6ec1db3f12d1850bb6ff9a01d5b6cc5f90c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940354"
---
# <a name="inotifysink2onsynccallreturn-method"></a><span data-ttu-id="78297-102">INotifySink2::OnSyncCallReturn Yöntemi</span><span class="sxs-lookup"><span data-stu-id="78297-102">INotifySink2::OnSyncCallReturn Method</span></span>
<span data-ttu-id="78297-103">Çağrısı döndürüldüğünde çağrılan.</span><span class="sxs-lookup"><span data-stu-id="78297-103">Gets invoked when a call returns.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78297-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="78297-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallReturn  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78297-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="78297-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="78297-106">[in] Parametresinden döndürülen aramanın kimliği.</span><span class="sxs-lookup"><span data-stu-id="78297-106">[in] ID of the call being returned from.</span></span> <span data-ttu-id="78297-107">Bkz: [call_ıd yapısı](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="78297-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="78297-108">[in] Arabellek çağırın.</span><span class="sxs-lookup"><span data-stu-id="78297-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="78297-109">[in] Çağrı arabelleğin bayt cinsinden boyutu.</span><span class="sxs-lookup"><span data-stu-id="78297-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78297-110">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="78297-110">Return Value</span></span>  
 <span data-ttu-id="78297-111">Yöntem başarılı olursa S_OK.</span><span class="sxs-lookup"><span data-stu-id="78297-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78297-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="78297-112">Requirements</span></span>  
 <span data-ttu-id="78297-113">**Üst bilgi:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="78297-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78297-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="78297-114">See also</span></span>

- [<span data-ttu-id="78297-115">INotifySink2 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="78297-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="78297-116">INotifySource2 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="78297-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="78297-117">INotifyConnection2 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="78297-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
