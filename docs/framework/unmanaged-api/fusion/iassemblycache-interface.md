---
title: IAssemblyCache Arabirimi
ms.date: 03/30/2017
api_name:
- IAssemblyCache
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache
helpviewer_keywords:
- IAssemblyCache interface [.NET Framework fusion]
ms.assetid: 71ea170f-872d-4fc5-81b6-27da1dec9b19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6dab5fe941fce3c23ba718906b29c80c6d257c2f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796774"
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="ca3fc-102">IAssemblyCache Arabirimi</span><span class="sxs-lookup"><span data-stu-id="ca3fc-102">IAssemblyCache Interface</span></span>
<span data-ttu-id="ca3fc-103">Fusion teknolojisinin kullanması için genel derleme önbelleğini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="ca3fc-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ca3fc-104">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="ca3fc-104">Methods</span></span>  
  
|<span data-ttu-id="ca3fc-105">Yöntem</span><span class="sxs-lookup"><span data-stu-id="ca3fc-105">Method</span></span>|<span data-ttu-id="ca3fc-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ca3fc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ca3fc-107">CreateAssemblyCacheItem Yöntemi</span><span class="sxs-lookup"><span data-stu-id="ca3fc-107">CreateAssemblyCacheItem Method</span></span>](iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="ca3fc-108">Yeni bir [IAssemblyCacheItem](iassemblycacheitem-interface.md)öğesine bir başvuru alır.</span><span class="sxs-lookup"><span data-stu-id="ca3fc-108">Gets a reference to a new [IAssemblyCacheItem](iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="ca3fc-109">CreateAssemblyScavenger Yöntemi</span><span class="sxs-lookup"><span data-stu-id="ca3fc-109">CreateAssemblyScavenger Method</span></span>](iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="ca3fc-110">Fusion teknolojisinin iç kullanımı için ayrılmıştır.</span><span class="sxs-lookup"><span data-stu-id="ca3fc-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="ca3fc-111">InstallAssembly Yöntemi</span><span class="sxs-lookup"><span data-stu-id="ca3fc-111">InstallAssembly Method</span></span>](iassemblycache-installassembly-method.md)|<span data-ttu-id="ca3fc-112">Belirtilen derlemeyi genel derleme önbelleğine yüklenir.</span><span class="sxs-lookup"><span data-stu-id="ca3fc-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="ca3fc-113">QueryAssemblyInfo Yöntemi</span><span class="sxs-lookup"><span data-stu-id="ca3fc-113">QueryAssemblyInfo Method</span></span>](iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="ca3fc-114">Belirtilen derleme hakkında istenen verileri alır.</span><span class="sxs-lookup"><span data-stu-id="ca3fc-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="ca3fc-115">UninstallAssembly Yöntemi</span><span class="sxs-lookup"><span data-stu-id="ca3fc-115">UninstallAssembly Method</span></span>](iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="ca3fc-116">Belirtilen derlemeyi genel bütünleştirilmiş kod önbelleğinden kaldırır.</span><span class="sxs-lookup"><span data-stu-id="ca3fc-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ca3fc-117">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="ca3fc-117">Requirements</span></span>  
 <span data-ttu-id="ca3fc-118">**Platform** Bkz. [sistem gereksinimleri](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca3fc-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca3fc-119">**Üst bilgi** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="ca3fc-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ca3fc-120">**.NET Framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca3fc-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca3fc-121">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="ca3fc-121">See also</span></span>

- [<span data-ttu-id="ca3fc-122">Fusion Arabirimleri</span><span class="sxs-lookup"><span data-stu-id="ca3fc-122">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="ca3fc-123">Genel Derleme Önbelleği</span><span class="sxs-lookup"><span data-stu-id="ca3fc-123">Global Assembly Cache</span></span>](../../app-domains/gac.md)
