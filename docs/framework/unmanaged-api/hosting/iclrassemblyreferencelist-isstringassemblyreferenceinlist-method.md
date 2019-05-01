---
title: ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Yöntemi
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList.IsStringAssemblyReferenceInList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList method [.NET Framework hosting]
- IsStringAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: e6121cc3-2f11-42c7-bdae-47808581ff71
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de17a91b5093372579a4d9435532a95406addd0a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969916"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="a72bb-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Yöntemi</span><span class="sxs-lookup"><span data-stu-id="a72bb-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="a72bb-103">Sağlanan ad listesinde bir derlemenin adı ile eşleşip eşleşmediğini gösteren bir değer alır.</span><span class="sxs-lookup"><span data-stu-id="a72bb-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a72bb-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="a72bb-104">Syntax</span></span>  
  
```  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a72bb-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="a72bb-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="a72bb-106">[in] Aramak istediğiniz bütünleştirilmiş kod adı.</span><span class="sxs-lookup"><span data-stu-id="a72bb-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a72bb-107">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="a72bb-107">Return Value</span></span>  
  
|<span data-ttu-id="a72bb-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a72bb-108">HRESULT</span></span>|<span data-ttu-id="a72bb-109">Açıklama</span><span class="sxs-lookup"><span data-stu-id="a72bb-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a72bb-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a72bb-110">S_OK</span></span>|<span data-ttu-id="a72bb-111">Dize listesinde görünür.</span><span class="sxs-lookup"><span data-stu-id="a72bb-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="a72bb-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a72bb-112">S_FALSE</span></span>|<span data-ttu-id="a72bb-113">Dize, listede görünmez.</span><span class="sxs-lookup"><span data-stu-id="a72bb-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="a72bb-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a72bb-114">E_FAIL</span></span>|<span data-ttu-id="a72bb-115">Bilinmeyen geri dönülemez bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="a72bb-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a72bb-116">Ortak dil çalışma zamanı, artık E_FAIL bir yöntemin dönüşünün ardından, işlem içinde kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="a72bb-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="a72bb-117">Yöntemleri barındırma yapılan sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.</span><span class="sxs-lookup"><span data-stu-id="a72bb-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a72bb-118">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="a72bb-118">Requirements</span></span>  
 <span data-ttu-id="a72bb-119">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a72bb-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a72bb-120">**Üst bilgi:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a72bb-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a72bb-121">**Kitaplığı:** Bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="a72bb-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a72bb-122">**.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a72bb-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a72bb-123">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="a72bb-123">See also</span></span>

- [<span data-ttu-id="a72bb-124">ICLRAssemblyIdentityManager Arabirimi</span><span class="sxs-lookup"><span data-stu-id="a72bb-124">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="a72bb-125">ICLRAssemblyReferenceList Arabirimi</span><span class="sxs-lookup"><span data-stu-id="a72bb-125">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="a72bb-126">IHostAssemblyManager Arabirimi</span><span class="sxs-lookup"><span data-stu-id="a72bb-126">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="a72bb-127">IHostAssemblyStore Arabirimi</span><span class="sxs-lookup"><span data-stu-id="a72bb-127">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
