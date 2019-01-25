---
title: IEnumDefinitionIdentity Arabirimi
ms.date: 03/30/2017
api_name:
- IEnumDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumDefinitionIdentity
helpviewer_keywords:
- IEnumDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: 8263e75d-251b-4abc-8a1a-c62884142232
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a3ff37acd9b4dffe80112f0a0ebe9c9cd86ae66f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668459"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="f4652-102">IEnumDefinitionIdentity Arabirimi</span><span class="sxs-lookup"><span data-stu-id="f4652-102">IEnumDefinitionIdentity Interface</span></span>
<span data-ttu-id="f4652-103">Bir koleksiyonu için bir numaralandırıcı görevi gören `IDefinitionIdentity` nesneleri.</span><span class="sxs-lookup"><span data-stu-id="f4652-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4652-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="f4652-104">Syntax</span></span>  
  
```  
IEnumDefinitionIdentity : IUnknown {  
  
    HRESULT Clone (  
        [out] IEnumDefinitionIdentity **ppIEnumDefinitionIdentity  
    );  
  
    HRESULT Next (  
        [in]  ULONG               celt,  
        [out, length_is(celt), size_is(*pceltWritten)]  
              IDefinitionIdentity *rgpIDefinitionIdentity[],  
        [out] ULONG               *pceltWritten  
    );  
  
    HRESULT Reset ();  
  
    HRESULT Skip (  
        [in] ULONG celt  
    );  
  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f4652-105">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="f4652-105">Methods</span></span>  
  
|<span data-ttu-id="f4652-106">Yöntem</span><span class="sxs-lookup"><span data-stu-id="f4652-106">Method</span></span>|<span data-ttu-id="f4652-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="f4652-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="f4652-108">Yeni bir arabirim işaretçisi alır `IEnumDefinitionIdentity` bu aynı üyeleri içeren nesne `IEnumDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="f4652-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="f4652-109">Belirtilen sayıda alır `IDefinitionIdentity` nesneleri, geçerli konumdan başlayarak.</span><span class="sxs-lookup"><span data-stu-id="f4652-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="f4652-110">Yönerge işaretçisini bu başlangıcına taşır `IEnumDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="f4652-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="f4652-111">Öğe, geçerli konumdan başlayarak belirtilen sayıda yönerge işaretçisini ileriye taşır.</span><span class="sxs-lookup"><span data-stu-id="f4652-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f4652-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="f4652-112">Requirements</span></span>  
 <span data-ttu-id="f4652-113">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4652-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4652-114">**Üst bilgi:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="f4652-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="f4652-115">**.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4652-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4652-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="f4652-116">See also</span></span>
- [<span data-ttu-id="f4652-117">Fusion Arabirimleri</span><span class="sxs-lookup"><span data-stu-id="f4652-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="f4652-118">IDefinitionIdentity Arabirimi</span><span class="sxs-lookup"><span data-stu-id="f4652-118">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
