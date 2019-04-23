---
title: ICorPublishProcessEnum Arabirimi
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum
helpviewer_keywords:
- ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: aac8fcf9-ac09-437c-bd5c-2fda14ae1007
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5186df61eb82b29fcfa9776408498b748068e122
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173660"
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="1705d-102">ICorPublishProcessEnum Arabirimi</span><span class="sxs-lookup"><span data-stu-id="1705d-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="1705d-103">Öğesinin [Icorpublishenum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) koleksiyonunu geçirmek için yöntemler sağlar arabirimi [Icorpublishprocess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) nesneleri.</span><span class="sxs-lookup"><span data-stu-id="1705d-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1705d-104">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="1705d-104">Methods</span></span>  
  
|<span data-ttu-id="1705d-105">Yöntem</span><span class="sxs-lookup"><span data-stu-id="1705d-105">Method</span></span>|<span data-ttu-id="1705d-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="1705d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1705d-107">Next Yöntemi</span><span class="sxs-lookup"><span data-stu-id="1705d-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-next-method.md)|<span data-ttu-id="1705d-108">Belirtilen sayıda alır `ICorPublishProcess` geçerli konumunda başlayan koleksiyondan örnekleri.</span><span class="sxs-lookup"><span data-stu-id="1705d-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1705d-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="1705d-109">Remarks</span></span>  
 <span data-ttu-id="1705d-110">`ICorPublishProcessEnum` Arabirimi soyut arabirimin yöntemlerini uygulayan [Icorpublishenum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="1705d-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="1705d-111">Bir `ICorPublishProcessEnum` örneği tarafından oluşturulan [Icorpublish::enumprocesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="1705d-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="1705d-112">Koleksiyonu geçişi `ICorPublishProcess` nesneleri zaman verilen filtre ölçütünü temel `ICorPublishProcessEnum` örneği oluşturuldu.</span><span class="sxs-lookup"><span data-stu-id="1705d-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1705d-113">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="1705d-113">Requirements</span></span>  
 <span data-ttu-id="1705d-114">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1705d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1705d-115">**Üst bilgi:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="1705d-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="1705d-116">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1705d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1705d-117">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1705d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1705d-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="1705d-118">See also</span></span>

- [<span data-ttu-id="1705d-119">Hata Ayıklama Arabirimleri</span><span class="sxs-lookup"><span data-stu-id="1705d-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="1705d-120">CorpubPublish Coclass</span><span class="sxs-lookup"><span data-stu-id="1705d-120">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
