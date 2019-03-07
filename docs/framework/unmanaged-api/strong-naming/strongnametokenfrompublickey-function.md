---
title: StrongNameTokenFromPublicKey İşlevi
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- StrongNameTokenFromPublicKey
helpviewer_keywords:
- StrongNameTokenFromPublicKey function [.NET Framework strong naming]
ms.assetid: 997e9e57-abb2-4217-bf20-1df621a75add
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b095d999f1e7e37c068c800e66f56c293422127
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490404"
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="aa2d5-102">StrongNameTokenFromPublicKey İşlevi</span><span class="sxs-lookup"><span data-stu-id="aa2d5-102">StrongNameTokenFromPublicKey Function</span></span>
<span data-ttu-id="aa2d5-103">Bir ortak anahtar temsil eden bir belirteç alır.</span><span class="sxs-lookup"><span data-stu-id="aa2d5-103">Gets a token representing a public key.</span></span> <span data-ttu-id="aa2d5-104">Genel anahtar kısaltılmış bir tanımlayıcı ad belirtecidir.</span><span class="sxs-lookup"><span data-stu-id="aa2d5-104">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="aa2d5-105">Bu işlev kullanım dışı bırakıldı.</span><span class="sxs-lookup"><span data-stu-id="aa2d5-105">This function has been deprecated.</span></span> <span data-ttu-id="aa2d5-106">Kullanım [Iclrstrongname::strongnametokenfrompublickey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md) yöntemi yerine.</span><span class="sxs-lookup"><span data-stu-id="aa2d5-106">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa2d5-107">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="aa2d5-107">Syntax</span></span>  
  
```  
BOOLEANStrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa2d5-108">Parametreler</span><span class="sxs-lookup"><span data-stu-id="aa2d5-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="aa2d5-109">[in] Türünden bir yapıyı [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) tanımlayıcı ad imzası oluşturmak için kullanılan anahtar çiftinden ortak kısmını içerir.</span><span class="sxs-lookup"><span data-stu-id="aa2d5-109">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="aa2d5-110">[in] Bayt cinsinden boyutu, `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="aa2d5-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="aa2d5-111">[out] Anahtarına karşılık gelen tanımlayıcı ad belirteç geçirilen `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="aa2d5-111">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="aa2d5-112">Ortak dil çalışma zamanı, bir belirteç döndürecek şekilde bellek ayırır.</span><span class="sxs-lookup"><span data-stu-id="aa2d5-112">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="aa2d5-113">Çağıranın bu bellek kullanarak ücretsiz gerekir [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) işlevi.</span><span class="sxs-lookup"><span data-stu-id="aa2d5-113">The caller must free this memory by using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="aa2d5-114">[out] Döndürülen tanımlayıcı ad belirtecinin bayt cinsinden boyutu.</span><span class="sxs-lookup"><span data-stu-id="aa2d5-114">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa2d5-115">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="aa2d5-115">Return Value</span></span>  
 <span data-ttu-id="aa2d5-116">`true` başarıyla tamamlandığında; Aksi takdirde, `false`.</span><span class="sxs-lookup"><span data-stu-id="aa2d5-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa2d5-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="aa2d5-117">Remarks</span></span>  
 <span data-ttu-id="aa2d5-118">Tanımlayıcı ad anahtar bilgilerini meta verileri depolarken alanından tasarruf etmek için kullanılan genel anahtar kısaltılmış belirtecidir.</span><span class="sxs-lookup"><span data-stu-id="aa2d5-118">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="aa2d5-119">Özellikle, tanımlayıcı ad belirteçleri, derleme başvurularını bağımlı derlemeye başvurmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="aa2d5-119">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="aa2d5-120">Varsa `StrongNameTokenFromPublicKey` işlevi değil başarıyla tamamlanması, çağrı [Strongnameerrorınfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) oluşturulan son hatayı alması için işlevi.</span><span class="sxs-lookup"><span data-stu-id="aa2d5-120">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa2d5-121">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="aa2d5-121">Requirements</span></span>  
 <span data-ttu-id="aa2d5-122">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa2d5-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa2d5-123">**Üst bilgi:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="aa2d5-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="aa2d5-124">**Kitaplığı:** Bir kaynak olarak mscoree.dll dahil</span><span class="sxs-lookup"><span data-stu-id="aa2d5-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="aa2d5-125">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa2d5-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa2d5-126">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="aa2d5-126">See also</span></span>
- [<span data-ttu-id="aa2d5-127">StrongNameTokenFromPublicKey Yöntemi</span><span class="sxs-lookup"><span data-stu-id="aa2d5-127">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="aa2d5-128">StrongNameGetPublicKey Yöntemi</span><span class="sxs-lookup"><span data-stu-id="aa2d5-128">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="aa2d5-129">PublicKeyBlob Yapısı</span><span class="sxs-lookup"><span data-stu-id="aa2d5-129">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
