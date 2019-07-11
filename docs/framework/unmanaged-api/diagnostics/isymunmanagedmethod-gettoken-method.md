---
title: ISymUnmanagedMethod::GetToken Yöntemi
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetToken
helpviewer_keywords:
- ISymUnmanagedMethod::GetToken method [.NET Framework debugging]
- GetToken method, ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: 4effbe95-c36e-4a45-8b2a-ee21339415fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1bb9a444d8e8b674d1f173214d8bac427f24e408
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759397"
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="83303-102">ISymUnmanagedMethod::GetToken Yöntemi</span><span class="sxs-lookup"><span data-stu-id="83303-102">ISymUnmanagedMethod::GetToken Method</span></span>
<span data-ttu-id="83303-103">Bu yöntem için meta veri belirteci döndürür.</span><span class="sxs-lookup"><span data-stu-id="83303-103">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83303-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="83303-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83303-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="83303-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="83303-106">[out] Bir işaretçi bir `mdMethodDef` karakter meta veri içermesini gerekli arabellek boyutunu alır.</span><span class="sxs-lookup"><span data-stu-id="83303-106">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83303-107">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="83303-107">Return Value</span></span>  
 <span data-ttu-id="83303-108">Yöntem başarılı olursa S_OK; Aksi takdirde, E_FAIL veya başka bir hata kodu.</span><span class="sxs-lookup"><span data-stu-id="83303-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83303-109">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="83303-109">Requirements</span></span>  
 <span data-ttu-id="83303-110">**Üst bilgi:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="83303-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83303-111">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="83303-111">See also</span></span>

- [<span data-ttu-id="83303-112">ISymUnmanagedMethod Yöntemi</span><span class="sxs-lookup"><span data-stu-id="83303-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
