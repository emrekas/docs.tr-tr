---
title: _CorValidateImage İşlevi
ms.date: 03/30/2017
api_name:
- _CorValidateImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorValidateImage
helpviewer_keywords:
- _CorValidateImage function [.NET Framework hosting]
ms.assetid: 0117e080-05f9-4772-885d-e1847230947c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: df9cc0cc86237b1ec439a4ec4fa6a75429c416d9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111182"
---
# <a name="corvalidateimage-function"></a><span data-ttu-id="a7ae6-102">_CorValidateImage İşlevi</span><span class="sxs-lookup"><span data-stu-id="a7ae6-102">_CorValidateImage Function</span></span>
<span data-ttu-id="a7ae6-103">Yönetilen modül görüntüleri doğrular ve bunlar yüklendikten sonra işletim sistemi yükleyicisi bildirir.</span><span class="sxs-lookup"><span data-stu-id="a7ae6-103">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7ae6-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="a7ae6-104">Syntax</span></span>  
  
```  
STDAPI _CorValidateImage (   
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7ae6-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="a7ae6-105">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="a7ae6-106">[in] Yönetilen kod bir işaretçi olarak doğrulamak için görüntüsünün başlangıç konumu.</span><span class="sxs-lookup"><span data-stu-id="a7ae6-106">[in] A pointer to the starting location of the image to validate as managed code.</span></span> <span data-ttu-id="a7ae6-107">Görüntü zaten belleğe yüklenmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="a7ae6-107">The image must already be loaded into memory.</span></span>  
  
 `FileName`  
 <span data-ttu-id="a7ae6-108">[in] Görüntü dosyası adı.</span><span class="sxs-lookup"><span data-stu-id="a7ae6-108">[in] The file name of the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7ae6-109">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="a7ae6-109">Return Value</span></span>  
 <span data-ttu-id="a7ae6-110">Bu işlev, standart değerleri döndürür `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, ve `E_FAIL`, aşağıdaki değerleri yanı sıra.</span><span class="sxs-lookup"><span data-stu-id="a7ae6-110">This function returns the standard values `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, and `E_FAIL`, as well as the following values.</span></span>  
  
|<span data-ttu-id="a7ae6-111">Dönüş değeri</span><span class="sxs-lookup"><span data-stu-id="a7ae6-111">Return value</span></span>|<span data-ttu-id="a7ae6-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="a7ae6-112">Description</span></span>|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|<span data-ttu-id="a7ae6-113">Görüntü geçersiz.</span><span class="sxs-lookup"><span data-stu-id="a7ae6-113">The image is invalid.</span></span> <span data-ttu-id="a7ae6-114">Bu değer, HRESULT 0xC000007BL sahiptir.</span><span class="sxs-lookup"><span data-stu-id="a7ae6-114">This value has the HRESULT 0xC000007BL.</span></span>|  
|`STATUS_SUCCESS`|<span data-ttu-id="a7ae6-115">Görüntü geçerli değil.</span><span class="sxs-lookup"><span data-stu-id="a7ae6-115">The image is valid.</span></span> <span data-ttu-id="a7ae6-116">Bu değer, HRESULT 0x00000000L sahiptir.</span><span class="sxs-lookup"><span data-stu-id="a7ae6-116">This value has the HRESULT 0x00000000L.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7ae6-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a7ae6-117">Remarks</span></span>  
 <span data-ttu-id="a7ae6-118">Windows XP ve sonraki sürümlerinde, işletim sistemi yükleyicisi yönetilen modüller için ortak nesne dosyası biçimi (COFF) üst bilgisindeki COM tanımlayıcısı dizin bit inceleyerek denetler.</span><span class="sxs-lookup"><span data-stu-id="a7ae6-118">In Windows XP and later versions, the operating system loader checks for managed modules by examining the COM Descriptor Directory bit in the common object file format (COFF) header.</span></span> <span data-ttu-id="a7ae6-119">Yönetilen bir modül bit kümesinin gösterir.</span><span class="sxs-lookup"><span data-stu-id="a7ae6-119">A set bit indicates a managed module.</span></span> <span data-ttu-id="a7ae6-120">Yükleyici, yönetilen bir modül algılarsa, MsCorEE.dll ve aramalar yükler `_CorValidateImage`, aşağıdaki eylemleri gerçekleştirir:</span><span class="sxs-lookup"><span data-stu-id="a7ae6-120">If the loader detects a managed module, it loads MsCorEE.dll and calls `_CorValidateImage`, which performs the following actions:</span></span>  
  
-   <span data-ttu-id="a7ae6-121">Görüntünün geçerli yönetilen bir modül olduğunu doğrular.</span><span class="sxs-lookup"><span data-stu-id="a7ae6-121">Confirms that the image is a valid managed module.</span></span>  
  
-   <span data-ttu-id="a7ae6-122">Ortak dil çalışma zamanı (CLR) bir giriş noktası için giriş noktası görüntüde değiştirir.</span><span class="sxs-lookup"><span data-stu-id="a7ae6-122">Changes the entry point in the image to an entry point in the common language runtime (CLR).</span></span>  
  
-   <span data-ttu-id="a7ae6-123">Windows 64-bit sürümleri için bellekte PE32 je typu PE32 + biçimine dönüştürerek görüntü değiştirir.</span><span class="sxs-lookup"><span data-stu-id="a7ae6-123">For 64-bit versions of Windows, modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
-   <span data-ttu-id="a7ae6-124">Yönetilen modül görüntüleri yüklendiğinde yükleyici geri döner.</span><span class="sxs-lookup"><span data-stu-id="a7ae6-124">Returns to the loader when the managed module images are loaded.</span></span>  
  
 <span data-ttu-id="a7ae6-125">Yürütülebilir görüntüler için işletim sistemi yükleyicisi sonra çağıran [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) işlevi, bağımsız yürütülebilir dosya belirtilen giriş noktası olarak.</span><span class="sxs-lookup"><span data-stu-id="a7ae6-125">For executable images, the operating system loader then calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function, regardless of the entry point specified in the executable.</span></span> <span data-ttu-id="a7ae6-126">DLL derleme görüntüler için yükleyici çağırır [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) işlevi.</span><span class="sxs-lookup"><span data-stu-id="a7ae6-126">For DLL assembly images, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function.</span></span>  
  
 <span data-ttu-id="a7ae6-127">`_CorExeMain` veya `_CorDllMain` aşağıdaki eylemleri gerçekleştirir:</span><span class="sxs-lookup"><span data-stu-id="a7ae6-127">`_CorExeMain` or `_CorDllMain` performs the following actions:</span></span>  
  
-   <span data-ttu-id="a7ae6-128">CLR'yi başlatır.</span><span class="sxs-lookup"><span data-stu-id="a7ae6-128">Initializes the CLR.</span></span>  
  
-   <span data-ttu-id="a7ae6-129">Derlemesinin CLR başlığındaki yönetilen giriş noktasını bulur.</span><span class="sxs-lookup"><span data-stu-id="a7ae6-129">Locates the managed entry point from the assembly's CLR header.</span></span>  
  
-   <span data-ttu-id="a7ae6-130">Yürütmeyi başlatır.</span><span class="sxs-lookup"><span data-stu-id="a7ae6-130">Begins execution.</span></span>  
  
 <span data-ttu-id="a7ae6-131">Yükleyici çağrıları [_corımageunloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) işlev yönetilen modül görüntüleri kaldırıldı.</span><span class="sxs-lookup"><span data-stu-id="a7ae6-131">The loader calls the [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) function when managed module images are unloaded.</span></span> <span data-ttu-id="a7ae6-132">Ancak, bu işlev, herhangi bir işlem gerçekleştirmez; hemen döndürür.</span><span class="sxs-lookup"><span data-stu-id="a7ae6-132">However, this function does not perform any action; it just returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7ae6-133">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="a7ae6-133">Requirements</span></span>  
 <span data-ttu-id="a7ae6-134">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7ae6-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7ae6-135">**Üst bilgi:** COR.h</span><span class="sxs-lookup"><span data-stu-id="a7ae6-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a7ae6-136">**Kitaplığı:** Bir kaynak olarak MsCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="a7ae6-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a7ae6-137">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7ae6-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7ae6-138">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="a7ae6-138">See also</span></span>

- [<span data-ttu-id="a7ae6-139">Meta Veri Genel Statik İşlevleri</span><span class="sxs-lookup"><span data-stu-id="a7ae6-139">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
