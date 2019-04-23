---
title: VerifyClientKey işlevi (yönetilmeyen API Başvurusu)
description: İstemci anahtarı doğru güvenlik sahip VerifyClientKey işlevi sağlar.
ms.date: 11/06/2017
api_name:
- VerifyClientKey
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- VerifyClientKey
helpviewer_keywords:
- VerifyClientKey function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47fee26a0c4c25e4bff5bca94e5e26daaf98cccd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214721"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="75a9d-103">VerifyClientKey işlevi</span><span class="sxs-lookup"><span data-stu-id="75a9d-103">VerifyClientKey function</span></span>
<span data-ttu-id="75a9d-104">İstemci anahtarı doğru güvenlik sahip olmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="75a9d-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="75a9d-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="75a9d-105">Syntax</span></span>  
  
```  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="75a9d-106">Dönüş değeri</span><span class="sxs-lookup"><span data-stu-id="75a9d-106">Return value</span></span>

<span data-ttu-id="75a9d-107">İşlev başarılı olursa, dönüş değeri olduğu `ERROR_SUCCESS` (0).</span><span class="sxs-lookup"><span data-stu-id="75a9d-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="75a9d-108">İşlev başarısız olursa, dönüş değeri tanımlı bir sıfır olmayan hata kodudur *Wınerror*.</span><span class="sxs-lookup"><span data-stu-id="75a9d-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="75a9d-109">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="75a9d-109">Requirements</span></span>  
 <span data-ttu-id="75a9d-110">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75a9d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75a9d-111">**Üst bilgi:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="75a9d-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="75a9d-112">**.NET framework sürümleri:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="75a9d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75a9d-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="75a9d-113">See also</span></span>

- [<span data-ttu-id="75a9d-114">WMI ve performans sayaçları (yönetilmeyen API Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="75a9d-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
