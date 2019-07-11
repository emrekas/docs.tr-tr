---
title: ISymUnmanagedVariable::GetSignature Metodu
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetSignature method [.NET Framework debugging]
ms.assetid: 78c1ba28-a410-4360-805c-23a95408964a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: abd4bb00f5c1e703740462f1709407616ac8a8e8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778232"
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="ced30-102">ISymUnmanagedVariable::GetSignature Metodu</span><span class="sxs-lookup"><span data-stu-id="ced30-102">ISymUnmanagedVariable::GetSignature Method</span></span>
<span data-ttu-id="ced30-103">Bu değişken imzasını alır.</span><span class="sxs-lookup"><span data-stu-id="ced30-103">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ced30-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="ced30-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ced30-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="ced30-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="ced30-106">[in] Arabellek uzunluğu tarafından işaret edilen `sig` parametresi.</span><span class="sxs-lookup"><span data-stu-id="ced30-106">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="ced30-107">[out] Bir işaretçi bir `ULONG32` karakter imza içerecek şekilde gerekli arabellek boyutunu alır.</span><span class="sxs-lookup"><span data-stu-id="ced30-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="ced30-108">[out] İmza depolayan arabellek.</span><span class="sxs-lookup"><span data-stu-id="ced30-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ced30-109">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="ced30-109">Return Value</span></span>  
 <span data-ttu-id="ced30-110">Yöntem başarılı olursa S_OK; Aksi takdirde, E_FAIL veya başka bir hata kodu.</span><span class="sxs-lookup"><span data-stu-id="ced30-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ced30-111">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="ced30-111">Requirements</span></span>  
 <span data-ttu-id="ced30-112">**Üst bilgi:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ced30-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ced30-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="ced30-113">See also</span></span>

- [<span data-ttu-id="ced30-114">ISymUnmanagedVariable Arabirimi</span><span class="sxs-lookup"><span data-stu-id="ced30-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
