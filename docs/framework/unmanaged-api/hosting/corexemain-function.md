---
title: _CorExeMain İşlevi
ms.date: 03/30/2017
api_name:
- _CorExeMain
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain
helpviewer_keywords:
- _CorExeMain function [.NET Framework hosting]
ms.assetid: 898f76e2-16f4-4a63-b7d9-dad2d3824d8a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7407db297a827004c851b904b2da8652778cb08
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756422"
---
# <a name="corexemain-function"></a><span data-ttu-id="3bf77-102">_CorExeMain İşlevi</span><span class="sxs-lookup"><span data-stu-id="3bf77-102">_CorExeMain Function</span></span>
<span data-ttu-id="3bf77-103">Ortak dil çalışma zamanı (CLR) başlatır, derlemesinin CLR başlığındaki yönetilen giriş noktasını bulur ve yürütmeyi başlatır.</span><span class="sxs-lookup"><span data-stu-id="3bf77-103">Initializes the common language runtime (CLR), locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bf77-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="3bf77-104">Syntax</span></span>  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="3bf77-105">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="3bf77-105">Remarks</span></span>  
 <span data-ttu-id="3bf77-106">Bu işlev, yürütülebilir yönetilen derlemelerden oluşturan işlemlerde yükleyicisi tarafından çağrılır.</span><span class="sxs-lookup"><span data-stu-id="3bf77-106">This function is called by the loader in processes created from managed executable assemblies.</span></span> <span data-ttu-id="3bf77-107">DLL derlemeler için yükleyici çağırır [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) işlevini.</span><span class="sxs-lookup"><span data-stu-id="3bf77-107">For DLL assemblies, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="3bf77-108">İşletim sistemi yükleyicisi görüntü dosyasında belirtilen giriş noktası bakılmaksızın bu yöntemi çağırır.</span><span class="sxs-lookup"><span data-stu-id="3bf77-108">The operating system loader calls this method regardless of the entry point specified in the image file.</span></span>  
  
 <span data-ttu-id="3bf77-109">Windows 98, Windows ME, Windows NT, Windows 2000'de, `_CorExeMain` çağrıldığında dolaylı olarak işletim sistemi yükleyicisi'nde bir düzeltme aracılığıyla.</span><span class="sxs-lookup"><span data-stu-id="3bf77-109">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorExeMain` function is called indirectly through a fixup in the operating system loader.</span></span> <span data-ttu-id="3bf77-110">Tüm diğer Windows sürümlerinde, doğrudan işletim sistemi yükleyicisi tarafından çağrılır.</span><span class="sxs-lookup"><span data-stu-id="3bf77-110">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="3bf77-111">Ek bilgi için bkz açıklamalar bölümünde [_corvalidateımage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) konu.</span><span class="sxs-lookup"><span data-stu-id="3bf77-111">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bf77-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="3bf77-112">Requirements</span></span>  
 <span data-ttu-id="3bf77-113">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bf77-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bf77-114">**Üst bilgi:** COR.h</span><span class="sxs-lookup"><span data-stu-id="3bf77-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3bf77-115">**Kitaplığı:** Bir kaynak olarak MsCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="3bf77-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3bf77-116">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bf77-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bf77-117">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="3bf77-117">See also</span></span>

- [<span data-ttu-id="3bf77-118">Meta Veri Genel Statik İşlevleri</span><span class="sxs-lookup"><span data-stu-id="3bf77-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
