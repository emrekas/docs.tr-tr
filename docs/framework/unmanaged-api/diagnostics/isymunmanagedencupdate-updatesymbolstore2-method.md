---
title: ISymUnmanagedENCUpdate::UpdateSymbolStore2 Yöntemi
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateSymbolStore2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2
helpviewer_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2 method [.NET Framework debugging]
- UpdateSymbolStore2 method [.NET Framework debugging]
ms.assetid: 35588317-6184-485c-ab41-4b15fc1765d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 82f2f335299cfd3041dcecc7d176cb77ce54ae96
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59172139"
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a><span data-ttu-id="701b6-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 Yöntemi</span><span class="sxs-lookup"><span data-stu-id="701b6-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 Method</span></span>
<span data-ttu-id="701b6-103">Satır bilgilerini gereksinimlerini karşılayan program veritabanı (PDB) akışından değiştirilmiş işlevleri atlamak bir derleyici sağlar.</span><span class="sxs-lookup"><span data-stu-id="701b6-103">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided the line information meets the requirements.</span></span> <span data-ttu-id="701b6-104">Doğru satır bilgilerini eski PDB satır bilgileri ve tüm satırları işlevi için bir delta ile belirlenebilir.</span><span class="sxs-lookup"><span data-stu-id="701b6-104">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="701b6-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="701b6-105">Syntax</span></span>  
  
```  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
## <a name="parameters"></a><span data-ttu-id="701b6-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="701b6-106">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="701b6-107">[in] Bir işaretçi bir [IStream](/windows/desktop/api/objidl/nn-objidl-istream) , satır bilgileri içerir.</span><span class="sxs-lookup"><span data-stu-id="701b6-107">[in] A pointer to an [IStream](/windows/desktop/api/objidl/nn-objidl-istream) that contains the line information.</span></span>  
  
 `pDeltaLines`  
 <span data-ttu-id="701b6-108">[in] Bir işaretçi bir [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) değiştirilen satırları içeren yapısı.</span><span class="sxs-lookup"><span data-stu-id="701b6-108">[in] A pointer to a [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) structure that contains the lines that have changed.</span></span>  
  
 `cDeltaLines`  
 <span data-ttu-id="701b6-109">[in] A `ULONG` değişmiş olan satır sayısını temsil eder.</span><span class="sxs-lookup"><span data-stu-id="701b6-109">[in] A `ULONG` that represents the number of lines that have changed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="701b6-110">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="701b6-110">Return Value</span></span>  
 <span data-ttu-id="701b6-111">Yöntem başarılı olursa S_OK; Aksi takdirde, E_FAIL veya başka bir hata kodu.</span><span class="sxs-lookup"><span data-stu-id="701b6-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="701b6-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="701b6-112">Requirements</span></span>  
 <span data-ttu-id="701b6-113">**Üst bilgi:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="701b6-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="701b6-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="701b6-114">See also</span></span>

- [<span data-ttu-id="701b6-115">ISymUnmanagedENCUpdate Arabirimi</span><span class="sxs-lookup"><span data-stu-id="701b6-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
