---
title: ICorDebugProcess6::MarkDebuggerAttached Yöntemi
ms.date: 03/30/2017
ms.assetid: bf94f090-5265-4112-8e57-5b4e20e070d0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c818b196f3252138f2a9c601b04f1d7a6727bc6b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912737"
---
# <a name="icordebugprocess6markdebuggerattached-method"></a><span data-ttu-id="40258-102">ICorDebugProcess6::MarkDebuggerAttached Yöntemi</span><span class="sxs-lookup"><span data-stu-id="40258-102">ICorDebugProcess6::MarkDebuggerAttached Method</span></span>
<span data-ttu-id="40258-103">.NET Framework sınıf kitaplığındaki <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> yöntemin döndürdüğü `true`şekilde, hata ayıklayıcı 'nın iç durumunu değiştirir.</span><span class="sxs-lookup"><span data-stu-id="40258-103">Changes the internal state of the debugee so that the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method in the .NET Framework Class Library returns `true`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40258-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="40258-104">Syntax</span></span>  
  
```cpp  
HRESULT MarkDebuggerAttached(  
    BOOL fIsAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40258-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="40258-105">Parameters</span></span>  
 `fIsAttached`  
 <span data-ttu-id="40258-106">`true`<xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> yöntemin bir hata ayıklayıcının ekli olduğunu belirtmesi gerekiyorsa; `false` Aksi takdirde.</span><span class="sxs-lookup"><span data-stu-id="40258-106">`true` if the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method should indicate that a debugger is attached; `false` otherwise.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40258-107">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="40258-107">Return Value</span></span>  
 <span data-ttu-id="40258-108">Yöntemi aşağıdaki tabloda listelenen değerleri döndürebilir.</span><span class="sxs-lookup"><span data-stu-id="40258-108">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="40258-109">Dönüş değeri</span><span class="sxs-lookup"><span data-stu-id="40258-109">Return value</span></span>|<span data-ttu-id="40258-110">Açıklama</span><span class="sxs-lookup"><span data-stu-id="40258-110">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="40258-111">Hata ayıklanan başarıyla güncelleştirildi.</span><span class="sxs-lookup"><span data-stu-id="40258-111">The debuggee was successfully updated.</span></span>|  
|`CORDBG_E_MODULE_NOT_LOADED`|<span data-ttu-id="40258-112"><xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> Yöntemi içeren derleme yüklü değil veya eksik meta veriler gibi başka bir hata da tanınmasını engellemektedir.</span><span class="sxs-lookup"><span data-stu-id="40258-112">The assembly that contains the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method is not loaded, or some other error, such as missing metadata, is preventing it from being recognized.</span></span><br /><br /> <span data-ttu-id="40258-113">Bu hata yaygın ve zararsız.</span><span class="sxs-lookup"><span data-stu-id="40258-113">This error is common and benign.</span></span> <span data-ttu-id="40258-114">Ek derlemeler yüklenirken yöntemi tekrar çağırmalısınız.</span><span class="sxs-lookup"><span data-stu-id="40258-114">You should call the method again when additional assemblies load.</span></span>|  
|<span data-ttu-id="40258-115">Diğer başarısız `HRESULT` değerler.</span><span class="sxs-lookup"><span data-stu-id="40258-115">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="40258-116">Diğer değerler muhtemelen hatalı hata ayıklayıcı veya derleyici bileşenlerini gösterir.</span><span class="sxs-lookup"><span data-stu-id="40258-116">Other values likely indicate misbehaving debugger or compiler components.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40258-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="40258-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="40258-118">Bu yöntem yalnızca .NET Native kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="40258-118">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40258-119">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="40258-119">Requirements</span></span>  
 <span data-ttu-id="40258-120">**Platform** Bkz. [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40258-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40258-121">**Üst bilgi** CorDebug. IDL, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="40258-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40258-122">**Kitaplığı** Corguid. lib</span><span class="sxs-lookup"><span data-stu-id="40258-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40258-123">**.NET Framework sürümleri:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40258-123">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40258-124">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="40258-124">See also</span></span>

- [<span data-ttu-id="40258-125">ICorDebugProcess6 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="40258-125">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="40258-126">Hata Ayıklama Arabirimleri</span><span class="sxs-lookup"><span data-stu-id="40258-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
