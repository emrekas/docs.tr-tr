---
title: ICLRStrongName::StrongNameKeyGenEx Yöntemi
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGenEx
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyGenEx method [.NET Framework hosting]
- StrongNameKeyGenEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 1f8b59d0-5b72-45b8-ab74-c2b43ffc806e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f97e6f16029b9a273a68d52b830939819bfa5380
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083563"
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a><span data-ttu-id="036c2-102">ICLRStrongName::StrongNameKeyGenEx Yöntemi</span><span class="sxs-lookup"><span data-stu-id="036c2-102">ICLRStrongName::StrongNameKeyGenEx Method</span></span>
<span data-ttu-id="036c2-103">Tanımlayıcı ad kullanmak için belirtilen anahtar boyutu ile yeni bir ortak/özel anahtar çifti oluşturur.</span><span class="sxs-lookup"><span data-stu-id="036c2-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="036c2-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="036c2-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="036c2-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="036c2-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="036c2-106">[in] İstenen anahtar kapsayıcısı adı.</span><span class="sxs-lookup"><span data-stu-id="036c2-106">[in] The requested key container name.</span></span> <span data-ttu-id="036c2-107">`wszKeyContainer` ya da boş dize veya geçici bir ad oluşturmak için null olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="036c2-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="036c2-108">[in] Kaydedilen anahtar bırakın belirten bir değer.</span><span class="sxs-lookup"><span data-stu-id="036c2-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="036c2-109">Aşağıdaki değerleri desteklenir:</span><span class="sxs-lookup"><span data-stu-id="036c2-109">The following values are supported:</span></span>  
  
-   <span data-ttu-id="036c2-110">kullanılan 0x00000000 - `wszKeyContainer` geçici bir anahtar kapsayıcısı adını oluşturmak için null.</span><span class="sxs-lookup"><span data-stu-id="036c2-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="036c2-111">0x00000001 (`SN_LEAVE_KEY`)-anahtar sol kaydedilmesi gerektiğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="036c2-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="036c2-112">[in] İstenen bit cinsinden anahtar boyutunu.</span><span class="sxs-lookup"><span data-stu-id="036c2-112">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="036c2-113">[out] Döndürülen ortak/özel anahtar çifti.</span><span class="sxs-lookup"><span data-stu-id="036c2-113">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="036c2-114">[out] Bayt cinsinden boyutu, `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="036c2-114">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="036c2-115">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="036c2-115">Return Value</span></span>  
 <span data-ttu-id="036c2-116">`S_OK` yöntemi başarıyla tamamlandı Aksi takdirde hata olduğunu gösteren HRESULT değerini (bkz [ortak HRESULT değerlerini](https://go.microsoft.com/fwlink/?LinkId=213878) bir listesi için).</span><span class="sxs-lookup"><span data-stu-id="036c2-116">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="036c2-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="036c2-117">Remarks</span></span>  
 <span data-ttu-id="036c2-118">.NET Framework sürümleri 1.0 ve 1.1 gerektiren bir `dwKeySize` derlemeyi bir katı adla imzalamak için 1024 bit 2048 bit anahtar için desteklenen sürüm 2.0 ekler.</span><span class="sxs-lookup"><span data-stu-id="036c2-118">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="036c2-119">Anahtarı aldıktan sonra çağırmalıdır [Iclrstrongname::strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) ayrılan belleği serbest bırakmak için yöntemi.</span><span class="sxs-lookup"><span data-stu-id="036c2-119">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="036c2-120">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="036c2-120">Requirements</span></span>  
 <span data-ttu-id="036c2-121">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="036c2-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="036c2-122">**Üst bilgi:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="036c2-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="036c2-123">**Kitaplığı:** Bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="036c2-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="036c2-124">**.NET framework sürümleri:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="036c2-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="036c2-125">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="036c2-125">See also</span></span>

- [<span data-ttu-id="036c2-126">StrongNameKeyGen Yöntemi</span><span class="sxs-lookup"><span data-stu-id="036c2-126">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="036c2-127">ICLRStrongName Arabirimi</span><span class="sxs-lookup"><span data-stu-id="036c2-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
