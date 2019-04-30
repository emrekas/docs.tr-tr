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
ms.openlocfilehash: 846ff76fb1073394cc27597c9a2015148581cc70
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670007"
---
# <a name="isymunmanagedreadergetvariables-method"></a><span data-ttu-id="529ea-102">ISymUnmanagedReader::GetVariables Yöntemi</span><span class="sxs-lookup"><span data-stu-id="529ea-102">ISymUnmanagedReader::GetVariables Method</span></span>
<span data-ttu-id="529ea-103">Kendi üst adı verilen bir yerel olmayan Değişken döndürür.</span><span class="sxs-lookup"><span data-stu-id="529ea-103">Returns a non-local variable, given its parent and name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="529ea-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="529ea-104">Syntax</span></span>  
  
```  
HRESULT GetVariables (  
    [in]  mdToken  parent,  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is (cVars),  
        length_is (*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="529ea-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="529ea-105">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="529ea-106">[in] Değişken üst.</span><span class="sxs-lookup"><span data-stu-id="529ea-106">[in] The parent of the variable.</span></span>  
  
 `cVars`  
 <span data-ttu-id="529ea-107">[in] Boyutu `pVars` dizisi.</span><span class="sxs-lookup"><span data-stu-id="529ea-107">[in] The size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="529ea-108">[out] Döndürülen değişken sayısı alan değişken işaretçisi `pVars`.</span><span class="sxs-lookup"><span data-stu-id="529ea-108">[out] A pointer to the variable that receives the number of variables returned in `pVars`.</span></span>  
  
 `pVars`  
 <span data-ttu-id="529ea-109">[out] Bir işaretçi değişkenine değişkenleri alır.</span><span class="sxs-lookup"><span data-stu-id="529ea-109">[out] A pointer to the variable that receives the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="529ea-110">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="529ea-110">Return Value</span></span>  
 <span data-ttu-id="529ea-111">Yöntem başarılı olursa S_OK; Aksi takdirde, E_FAIL veya başka bir hata kodu.</span><span class="sxs-lookup"><span data-stu-id="529ea-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="529ea-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="529ea-112">Requirements</span></span>  
 <span data-ttu-id="529ea-113">**Üst bilgi:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="529ea-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="529ea-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="529ea-114">See also</span></span>

- [<span data-ttu-id="529ea-115">ISymUnmanagedReader Arabirimi</span><span class="sxs-lookup"><span data-stu-id="529ea-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
