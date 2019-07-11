---
title: ISymUnmanagedReader::GetVariables Yöntemi
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetVariables
helpviewer_keywords:
- ISymUnmanagedReader::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 16dc49cb-2c60-4ac8-9c35-020e9afba3f8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d1db08dfcd2adf1247dd717d6c826bce4726b8a1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777042"
---
# <a name="isymunmanagedreadergetvariables-method"></a><span data-ttu-id="a456c-102">ISymUnmanagedReader::GetVariables Yöntemi</span><span class="sxs-lookup"><span data-stu-id="a456c-102">ISymUnmanagedReader::GetVariables Method</span></span>
<span data-ttu-id="a456c-103">Kendi üst adı verilen bir yerel olmayan Değişken döndürür.</span><span class="sxs-lookup"><span data-stu-id="a456c-103">Returns a non-local variable, given its parent and name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a456c-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="a456c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVariables (  
    [in]  mdToken  parent,  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is (cVars),  
        length_is (*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a456c-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="a456c-105">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="a456c-106">[in] Değişken üst.</span><span class="sxs-lookup"><span data-stu-id="a456c-106">[in] The parent of the variable.</span></span>  
  
 `cVars`  
 <span data-ttu-id="a456c-107">[in] Boyutu `pVars` dizisi.</span><span class="sxs-lookup"><span data-stu-id="a456c-107">[in] The size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="a456c-108">[out] Döndürülen değişken sayısı alan değişken işaretçisi `pVars`.</span><span class="sxs-lookup"><span data-stu-id="a456c-108">[out] A pointer to the variable that receives the number of variables returned in `pVars`.</span></span>  
  
 `pVars`  
 <span data-ttu-id="a456c-109">[out] Bir işaretçi değişkenine değişkenleri alır.</span><span class="sxs-lookup"><span data-stu-id="a456c-109">[out] A pointer to the variable that receives the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a456c-110">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="a456c-110">Return Value</span></span>  
 <span data-ttu-id="a456c-111">Yöntem başarılı olursa S_OK; Aksi takdirde, E_FAIL veya başka bir hata kodu.</span><span class="sxs-lookup"><span data-stu-id="a456c-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a456c-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="a456c-112">Requirements</span></span>  
 <span data-ttu-id="a456c-113">**Üst bilgi:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a456c-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a456c-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="a456c-114">See also</span></span>

- [<span data-ttu-id="a456c-115">ISymUnmanagedReader Arabirimi</span><span class="sxs-lookup"><span data-stu-id="a456c-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
