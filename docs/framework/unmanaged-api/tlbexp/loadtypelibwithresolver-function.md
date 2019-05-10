---
title: LoadTypeLibWithResolver İşlevi
ms.date: 03/30/2017
api_name:
- LoadTypeLibWithResolver
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- LoadTypeLibWithResolver
helpviewer_keywords:
- LoadTypeLibWithResolver function [.NET Framework]
ms.assetid: 7123a89b-eb9b-463a-a552-a081e33b0a3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51d7cd273aa7a8799a1aac90d828ec81a7670906
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64603275"
---
# <a name="loadtypelibwithresolver-function"></a><span data-ttu-id="91675-102">LoadTypeLibWithResolver İşlevi</span><span class="sxs-lookup"><span data-stu-id="91675-102">LoadTypeLibWithResolver Function</span></span>
<span data-ttu-id="91675-103">Bir tür kitaplığı yükler ve sağlanan kullanan [Itypelibresolver arabirimi](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) tüm dahili olarak başvurulan tür kitaplıkları çözümlenecek.</span><span class="sxs-lookup"><span data-stu-id="91675-103">Loads a type library and uses the supplied [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any internally referenced type libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91675-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="91675-104">Syntax</span></span>  
  
```  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91675-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="91675-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="91675-106">[in] Tür kitaplığı dosyasının yolu.</span><span class="sxs-lookup"><span data-stu-id="91675-106">[in] The file path of the type library.</span></span>  
  
 `regkind`  
 <span data-ttu-id="91675-107">[in] A [REGKIND numaralandırma](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/ne-oleauto-tagregkind) nasıl bir tür kitaplığı kaydedilmemiş denetleyen bayrak.</span><span class="sxs-lookup"><span data-stu-id="91675-107">[in] A [REGKIND enumeration](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/ne-oleauto-tagregkind) flag that controls how the type library is registered.</span></span> <span data-ttu-id="91675-108">Olası değerleri şunlardır:</span><span class="sxs-lookup"><span data-stu-id="91675-108">Its possible values are:</span></span>  
  
- <span data-ttu-id="91675-109">`REGKIND_DEFAULT`: Varsayılan kayıt davranışı kullanın.</span><span class="sxs-lookup"><span data-stu-id="91675-109">`REGKIND_DEFAULT`: Use default registration behavior.</span></span>  
  
- <span data-ttu-id="91675-110">`REGKIND_REGISTER`: Bu tür kitaplığına kaydedin.</span><span class="sxs-lookup"><span data-stu-id="91675-110">`REGKIND_REGISTER`: Register this type library.</span></span>  
  
- <span data-ttu-id="91675-111">`REGKIND_NONE`: Bu tür kitaplığı kaydetmeyin.</span><span class="sxs-lookup"><span data-stu-id="91675-111">`REGKIND_NONE`: Do not register this type library.</span></span>  
  
 `pTlbResolver`  
 <span data-ttu-id="91675-112">[in] Uygulanmasına yönelik bir işaretçi [Itypelibresolver arabirimi](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).</span><span class="sxs-lookup"><span data-stu-id="91675-112">[in] A pointer to the implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).</span></span>  
  
 `pptlib`  
 <span data-ttu-id="91675-113">[out] Yüklenmekte tür kitaplığına bir başvuru.</span><span class="sxs-lookup"><span data-stu-id="91675-113">[out] A reference to the type library that is being loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91675-114">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="91675-114">Return Value</span></span>  
 <span data-ttu-id="91675-115">Aşağıdaki tabloda listelenen HRESULT değerlerinden biri.</span><span class="sxs-lookup"><span data-stu-id="91675-115">One of the HRESULT values listed in the following table.</span></span>  
  
|<span data-ttu-id="91675-116">Dönüş değeri</span><span class="sxs-lookup"><span data-stu-id="91675-116">Return value</span></span>|<span data-ttu-id="91675-117">Açıklama</span><span class="sxs-lookup"><span data-stu-id="91675-117">Meaning</span></span>|  
|------------------|-------------|  
|`S_OK`|<span data-ttu-id="91675-118">Başarılı.</span><span class="sxs-lookup"><span data-stu-id="91675-118">Success.</span></span>|  
|`E_OUTOFMEMORY`|<span data-ttu-id="91675-119">Bellek yetersiz.</span><span class="sxs-lookup"><span data-stu-id="91675-119">Out of memory.</span></span>|  
|`E_POINTER`|<span data-ttu-id="91675-120">Bir veya daha fazla işaretçileri geçersizdir.</span><span class="sxs-lookup"><span data-stu-id="91675-120">One or more of the pointers are invalid.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="91675-121">Bir veya daha fazla bağımsız değişken geçersiz.</span><span class="sxs-lookup"><span data-stu-id="91675-121">One or more of the arguments are invalid.</span></span>|  
|`TYPE_E_IOERROR`|<span data-ttu-id="91675-122">İşlevi, dosyaya yazılamadı.</span><span class="sxs-lookup"><span data-stu-id="91675-122">The function could not write to the file.</span></span>|  
|`TYPE_E_REGISTRYACCESS`|<span data-ttu-id="91675-123">Sistem kayıt veritabanı açılamadı.</span><span class="sxs-lookup"><span data-stu-id="91675-123">The system registration database could not be opened.</span></span>|  
|`TYPE_E_INVALIDSTATE`|<span data-ttu-id="91675-124">Tür kitaplığı dosyası açılamadı.</span><span class="sxs-lookup"><span data-stu-id="91675-124">The type library could not be opened.</span></span>|  
|`TYPE_E_CANTLOADLIBRARY`|<span data-ttu-id="91675-125">Tür kitaplığı veya DLL yüklenemedi.</span><span class="sxs-lookup"><span data-stu-id="91675-125">The type library or DLL could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91675-126">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="91675-126">Remarks</span></span>  
 <span data-ttu-id="91675-127">[Tlbexp.exe (tür kitaplığı dışarı Aktarıcı)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) çağrıları `LoadTypeLibWithResolver` derleme için tür kitaplığını dönüştürme işlemi sırasında işlevi.</span><span class="sxs-lookup"><span data-stu-id="91675-127">The [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) calls the `LoadTypeLibWithResolver` function during the assembly-to-type-library conversion process.</span></span>  
  
 <span data-ttu-id="91675-128">Bu işlev, belirtilen tür kitaplığı ile en az düzeyde erişim kayıt defterine yükler.</span><span class="sxs-lookup"><span data-stu-id="91675-128">This function loads the specified type library with minimal access to the registry.</span></span> <span data-ttu-id="91675-129">İşlev, her biri gerekir yüklenebilir ve üst tür kitaplığına eklenen dahili olarak başvurulan tür kitaplıkları için tür kitaplığı ardından inceler.</span><span class="sxs-lookup"><span data-stu-id="91675-129">The function then examines the type library for internally referenced type libraries, each of which must be loaded and added to the parent type library.</span></span>  
  
 <span data-ttu-id="91675-130">Başvurulan tür kitaplığının yüklenmeden önce bir tam dosya yolu başvurusu dosya yoluna çözümlenmelidir.</span><span class="sxs-lookup"><span data-stu-id="91675-130">Before a referenced type library can be loaded, its reference file path must be resolved to a full file path.</span></span> <span data-ttu-id="91675-131">Bu aracılığıyla gerçekleştirilir [ResolveTypeLib yöntemi](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) tarafından sağlanan [Itypelibresolver arabirimi](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), içinde geçirilen `pTlbResolver` parametresi.</span><span class="sxs-lookup"><span data-stu-id="91675-131">This is accomplished through the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) that is provided by the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), which is passed in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="91675-132">Başvurulan tür kitaplığının tam dosya yolunu bilindiğinde `LoadTypeLibWithResolver` işlevi yükler ve başvurulan tür kitaplığının bir birleşik asıl tür kütüphanesi oluşturuluyor üst türü, ekler.</span><span class="sxs-lookup"><span data-stu-id="91675-132">When the full file path of the referenced type library is known, the `LoadTypeLibWithResolver` function loads and adds the referenced type library to the parent type library, creating a combined master type library.</span></span>  
  
 <span data-ttu-id="91675-133">İşlevi, çözümler ve tüm dahili olarak başvurulan tür kitaplıklarını yükler sonra ana çözümlenen tür kitaplığına bir başvuru döndürür. `pptlib` parametresi.</span><span class="sxs-lookup"><span data-stu-id="91675-133">After the function resolves and loads all internally referenced type libraries, it returns a reference to the master resolved type library in the `pptlib` parameter.</span></span>  
  
 <span data-ttu-id="91675-134">`LoadTypeLibWithResolver` İşlev çağrılan genellikle [Tlbexp.exe (tür kitaplığı dışarı Aktarıcı)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), kendi iç sağladığı [Itypelibresolver arabirimi](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) uygulamasında `pTlbResolver` parametre.</span><span class="sxs-lookup"><span data-stu-id="91675-134">The `LoadTypeLibWithResolver` function is generally called by the [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), which supplies its own internal [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementation in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="91675-135">Eğer `LoadTypeLibWithResolver` doğrudan, kendi sağlamalısınız [Itypelibresolver arabirimi](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) uygulaması.</span><span class="sxs-lookup"><span data-stu-id="91675-135">If you call `LoadTypeLibWithResolver` directly, you must supply your own [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91675-136">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="91675-136">Requirements</span></span>  
 <span data-ttu-id="91675-137">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91675-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91675-138">**Üst bilgi:** TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="91675-138">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="91675-139">**Kitaplığı:** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="91675-139">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="91675-140">**.NET framework sürümü:** 3.5, 3.0, 2.0</span><span class="sxs-lookup"><span data-stu-id="91675-140">**.NET Framework Version:** 3.5, 3.0, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91675-141">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="91675-141">See also</span></span>

- [<span data-ttu-id="91675-142">Tlbexp Yardımcı İşlevleri</span><span class="sxs-lookup"><span data-stu-id="91675-142">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [<span data-ttu-id="91675-143">LoadTypeLibEx işlevi</span><span class="sxs-lookup"><span data-stu-id="91675-143">LoadTypeLibEx Function</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
