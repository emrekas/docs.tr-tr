---
title: ICorDebugThread::GetID Yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetID
helpviewer_keywords:
- ICorDebugThread::GetID method [.NET Framework debugging]
- GetID method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: f1de4584-92df-42f3-9da4-fca03a1c6821
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8eef616d51febd1b919e0a1936406551f441b98c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987109"
---
# <a name="icordebugthreadgetid-method"></a><span data-ttu-id="aa8c5-102">ICorDebugThread::GetID Yöntemi</span><span class="sxs-lookup"><span data-stu-id="aa8c5-102">ICorDebugThread::GetID Method</span></span>
<span data-ttu-id="aa8c5-103">Bu Icordebugthread etkin parçası geçerli işletim sistemi tanımlayıcısını alır.</span><span class="sxs-lookup"><span data-stu-id="aa8c5-103">Gets the current operating system identifier of the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa8c5-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="aa8c5-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa8c5-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="aa8c5-105">Parameters</span></span>  
 `pdwThreadId`  
 <span data-ttu-id="aa8c5-106">[out] İş parçacığı tanıtıcısı.</span><span class="sxs-lookup"><span data-stu-id="aa8c5-106">[out] The identifier of the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa8c5-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="aa8c5-107">Remarks</span></span>  
 <span data-ttu-id="aa8c5-108">İşletim sistemi tanımlayıcı, bir işlemin yürütülmesi sırasında potansiyel olarak değiştirebilirsiniz ve iş parçacığının farklı bölümleri için farklı bir değer olabilir.</span><span class="sxs-lookup"><span data-stu-id="aa8c5-108">The operating system identifier can potentially change during execution of a process, and can be a different value for different parts of the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa8c5-109">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="aa8c5-109">Requirements</span></span>  
 <span data-ttu-id="aa8c5-110">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa8c5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa8c5-111">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aa8c5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aa8c5-112">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa8c5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa8c5-113">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa8c5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
