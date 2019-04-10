---
title: IValidator::FormatEventInfo Yöntemi
ms.date: 03/30/2017
api_name:
- IValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FormatEventInfo
helpviewer_keywords:
- IValidator::FormatEventInfo method [.NET Framework hosting]
- FormatEventInfo method, IValidator interface [.NET Framework hosting]
ms.assetid: 4c0c7477-05ba-461b-b21b-cbfba95f1db1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ecbecec86d81357000679ab50e12f06d91c9f50d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217087"
---
# <a name="ivalidatorformateventinfo-method"></a><span data-ttu-id="14168-102">IValidator::FormatEventInfo Yöntemi</span><span class="sxs-lookup"><span data-stu-id="14168-102">IValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="14168-103">Belirtilen doğrulama hatası için karşılık gelen hata iletisini alır.</span><span class="sxs-lookup"><span data-stu-id="14168-103">Gets the error message corresponding to the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14168-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="14168-104">Syntax</span></span>  
  
```  
HRESULT FormatEventInfo(  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14168-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="14168-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="14168-106">[in] Doğrulama hata işleyicisine geçirilen HRESULT değerini.</span><span class="sxs-lookup"><span data-stu-id="14168-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="14168-107">[in] A `VEContext` doğrulama hatası ile ilgili bağlam bilgilerini içeren bir örneği.</span><span class="sxs-lookup"><span data-stu-id="14168-107">[in] A `VEContext` instance that contains context information about the validation error.</span></span>  
  
 `msg`  
 <span data-ttu-id="14168-108">[out içinde] Döndürülen hata iletisi içeren bir dize.</span><span class="sxs-lookup"><span data-stu-id="14168-108">[in, out] A string that contains the returned error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="14168-109">[in] Hata iletisi en fazla uzunluğu.</span><span class="sxs-lookup"><span data-stu-id="14168-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="14168-110">[in] Hatayı açıklayan ek parametreler içeren güvenli bir dizi.</span><span class="sxs-lookup"><span data-stu-id="14168-110">[in] A safe array that contains additional parameters describing the error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14168-111">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="14168-111">Requirements</span></span>  
 <span data-ttu-id="14168-112">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14168-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14168-113">**Üst bilgi:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="14168-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="14168-114">**Kitaplığı:** Bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="14168-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="14168-115">.NET framework sürümleri:</span><span class="sxs-lookup"><span data-stu-id="14168-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
