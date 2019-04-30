---
title: ICLRStrongName::GetHashFromHandle Metodu
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromHandle
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromHandle method [.NET Framework hosting]
ms.assetid: 3bedbb7d-3cdd-4175-b370-10ae734062db
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d11c71498053844792cd902959dee642877c46b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771520"
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="52448-102">ICLRStrongName::GetHashFromHandle Metodu</span><span class="sxs-lookup"><span data-stu-id="52448-102">ICLRStrongName::GetHashFromHandle Method</span></span>
<span data-ttu-id="52448-103">Belirtilen karma algoritması kullanılarak belirtilen tanıtıcıya sahip bir dosya içeriğini bir karma oluşturur.</span><span class="sxs-lookup"><span data-stu-id="52448-103">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52448-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="52448-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52448-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="52448-105">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="52448-106">[in] Karma hale getirilecek dosya tanıtıcısı.</span><span class="sxs-lookup"><span data-stu-id="52448-106">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="52448-107">[out içinde] Sabit karma algoritmasını belirtir.</span><span class="sxs-lookup"><span data-stu-id="52448-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="52448-108">Sıfır varsayılan algoritma için kullanın.</span><span class="sxs-lookup"><span data-stu-id="52448-108">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="52448-109">[out] Döndürülen karma arabellek.</span><span class="sxs-lookup"><span data-stu-id="52448-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="52448-110">[in] İstenen en büyük boyutunu `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="52448-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="52448-111">[out] Döndürülen bayt cinsinden boyutu `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="52448-111">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52448-112">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="52448-112">Return Value</span></span>  
 <span data-ttu-id="52448-113">`S_OK` yöntemi başarıyla tamamlandı Aksi takdirde hata olduğunu gösteren HRESULT değerini (bkz [ortak HRESULT değerlerini](https://go.microsoft.com/fwlink/?LinkId=213878) bir listesi için).</span><span class="sxs-lookup"><span data-stu-id="52448-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52448-114">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="52448-114">Requirements</span></span>  
 <span data-ttu-id="52448-115">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52448-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52448-116">**Üst bilgi:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="52448-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="52448-117">**Kitaplığı:** Bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="52448-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="52448-118">**.NET framework sürümleri:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52448-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52448-119">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="52448-119">See also</span></span>

- [<span data-ttu-id="52448-120">ICLRStrongName Arabirimi</span><span class="sxs-lookup"><span data-stu-id="52448-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
