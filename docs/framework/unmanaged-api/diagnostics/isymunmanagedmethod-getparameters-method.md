---
title: ISymUnmanagedMethod::GetParameters Metodu
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetParameters
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetParameters
helpviewer_keywords:
- ISymUnmanagedMethod::GetParameters method [.NET Framework debugging]
- GetParameters method [.NET Framework debugging]
ms.assetid: 3a8074f1-facc-4a3f-bb9b-d6574fc2fc74
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a757e3b28a94c96e28a5bab736a6820a83617a3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101236"
---
# <a name="isymunmanagedmethodgetparameters-method"></a><span data-ttu-id="2ed94-102">ISymUnmanagedMethod::GetParameters Metodu</span><span class="sxs-lookup"><span data-stu-id="2ed94-102">ISymUnmanagedMethod::GetParameters Method</span></span>
<span data-ttu-id="2ed94-103">Bu yöntem için parametreleri alır.</span><span class="sxs-lookup"><span data-stu-id="2ed94-103">Gets the parameters for this method.</span></span> <span data-ttu-id="2ed94-104">Parametre, yöntemin imzası'içinde tanımlanan sırayla döndürülür.</span><span class="sxs-lookup"><span data-stu-id="2ed94-104">The parameters are returned in the order in which they are defined within the method's signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ed94-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="2ed94-105">Syntax</span></span>  
  
```  
HRESULT GetParameters(  
    [in]  ULONG32  cParams,  
    [out] ULONG32  *pcParams,  
    [out, size_is(cParams),  
        length_is(*pcParams)] ISymUnmanagedVariable*  params[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ed94-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="2ed94-106">Parameters</span></span>  
 `cParams`  
 <span data-ttu-id="2ed94-107">[in] Boyutu `params` dizisi.</span><span class="sxs-lookup"><span data-stu-id="2ed94-107">[in] The size of the `params` array.</span></span>  
  
 `pcParams`  
 <span data-ttu-id="2ed94-108">[in] Bir işaretçi bir `ULONG32` parametreleri içermesi için gerekli arabellek boyutunu alır.</span><span class="sxs-lookup"><span data-stu-id="2ed94-108">[in] A pointer to a `ULONG32` that receives the size of the buffer that is required to contain the parameters.</span></span>  
  
 `params`  
 <span data-ttu-id="2ed94-109">[out] Parametreleri alan arabellek için işaretçi.</span><span class="sxs-lookup"><span data-stu-id="2ed94-109">[out] A pointer to the buffer that receives the parameters.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ed94-110">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="2ed94-110">Return Value</span></span>  
 <span data-ttu-id="2ed94-111">Yöntem başarılı olursa S_OK; Aksi takdirde, E_FAIL veya başka bir hata kodu.</span><span class="sxs-lookup"><span data-stu-id="2ed94-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ed94-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="2ed94-112">Requirements</span></span>  
 <span data-ttu-id="2ed94-113">**Üst bilgi:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2ed94-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ed94-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="2ed94-114">See also</span></span>

- [<span data-ttu-id="2ed94-115">ISymUnmanagedMethod Arabirimi</span><span class="sxs-lookup"><span data-stu-id="2ed94-115">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
