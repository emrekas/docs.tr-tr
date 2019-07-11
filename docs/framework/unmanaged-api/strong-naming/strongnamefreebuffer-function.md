---
title: StrongNameFreeBuffer İşlevi
ms.date: 03/30/2017
api_name:
- StrongNameFreeBuffer
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer function [.NET Framework strong naming]
ms.assetid: eda21ecf-4734-4f92-aaba-9f34884385db
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0cdeb446b18adceb4a8ed306a7934d6c905a90f8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778033"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="d9227-102">StrongNameFreeBuffer İşlevi</span><span class="sxs-lookup"><span data-stu-id="d9227-102">StrongNameFreeBuffer Function</span></span>
<span data-ttu-id="d9227-103">Önceki bir tanımlayıcı ad işlev çağrısı ile ayrıldı bellek serbest bırakma [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), veya [StrongNameSignatureGeneration ](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span><span class="sxs-lookup"><span data-stu-id="d9227-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="d9227-104">Bu işlev kullanım dışı bırakıldı.</span><span class="sxs-lookup"><span data-stu-id="d9227-104">This function has been deprecated.</span></span> <span data-ttu-id="d9227-105">Kullanım [Iclrstrongname::strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) yöntemi yerine.</span><span class="sxs-lookup"><span data-stu-id="d9227-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9227-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="d9227-106">Syntax</span></span>  
  
```cpp  
VOID StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9227-107">Parametreler</span><span class="sxs-lookup"><span data-stu-id="d9227-107">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="d9227-108">[in] Belleği boşaltmak için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="d9227-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9227-109">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="d9227-109">Requirements</span></span>  
 <span data-ttu-id="d9227-110">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9227-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9227-111">**Üst bilgi:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="d9227-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d9227-112">**Kitaplığı:** Bir kaynak olarak MsCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="d9227-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d9227-113">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9227-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9227-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="d9227-114">See also</span></span>

- [<span data-ttu-id="d9227-115">StrongNameFreeBuffer Yöntemi</span><span class="sxs-lookup"><span data-stu-id="d9227-115">StrongNameFreeBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="d9227-116">ICLRStrongName Arabirimi</span><span class="sxs-lookup"><span data-stu-id="d9227-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
