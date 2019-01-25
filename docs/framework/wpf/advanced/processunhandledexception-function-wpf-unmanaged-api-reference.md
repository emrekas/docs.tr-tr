---
title: ProcessUnhandledException işlevi (WPF yönetilmeyen API Başvurusu)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: 73480f7cd8be7bcb5296782a8503eb689442a14c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54578646"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="62704-102">ProcessUnhandledException işlevi (WPF yönetilmeyen API Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="62704-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="62704-103">Bu API Windows Presentation Foundation (WPF) altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.</span><span class="sxs-lookup"><span data-stu-id="62704-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="62704-104">Windows Presentation Foundation (WPF) altyapısı tarafından özel durum işleme için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="62704-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62704-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="62704-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="62704-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="62704-106">Parameters</span></span>  
 <span data-ttu-id="62704-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="62704-107">errorMsg</span></span>  
 <span data-ttu-id="62704-108">Hata iletisi.</span><span class="sxs-lookup"><span data-stu-id="62704-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62704-109">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="62704-109">Requirements</span></span>  
 <span data-ttu-id="62704-110">**Platformlar:** Bkz: [.NET Framework sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62704-110">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62704-111">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="62704-111">**DLL:**</span></span>  
  
 <span data-ttu-id="62704-112">.NET Framework 3.0 ve 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="62704-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="62704-113">.NET Framework 4 ve üzeri: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="62704-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="62704-114">**.NET framework sürümü:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62704-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62704-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="62704-115">See also</span></span>
- [<span data-ttu-id="62704-116">WPF Yönetilmeyen API Başvurusu</span><span class="sxs-lookup"><span data-stu-id="62704-116">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
