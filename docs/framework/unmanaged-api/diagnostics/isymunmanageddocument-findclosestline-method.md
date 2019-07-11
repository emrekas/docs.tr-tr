---
title: ISymUnmanagedDocument::FindClosestLine Yöntemi
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.FindClosestLine
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::FindClosestLine
helpviewer_keywords:
- FindClosestLine method [.NET Framework debugging]
- ISymUnmanagedDocument::FindClosestLine method [.NET Framework debugging]
ms.assetid: 628f2a04-e529-407d-841e-3b3da219a9cb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8d6be64137b59c84dfadbd7f0e4895eac2fb27e4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776792"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="4857e-102">ISymUnmanagedDocument::FindClosestLine Yöntemi</span><span class="sxs-lookup"><span data-stu-id="4857e-102">ISymUnmanagedDocument::FindClosestLine Method</span></span>
<span data-ttu-id="4857e-103">Bir dizi noktası olmayabilir veya bu belgeyi bir satır verilen bir dizi noktası en yakın satır döndürür.</span><span class="sxs-lookup"><span data-stu-id="4857e-103">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4857e-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="4857e-104">Syntax</span></span>  
  
```cpp  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4857e-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="4857e-105">Parameters</span></span>  
 `line`  
 <span data-ttu-id="4857e-106">[in] Bu belgeyi bir satır.</span><span class="sxs-lookup"><span data-stu-id="4857e-106">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="4857e-107">[out] Satırın alan bir değişken için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="4857e-107">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4857e-108">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="4857e-108">Return Value</span></span>  
 <span data-ttu-id="4857e-109">Yöntem başarılı olursa S_OK; Aksi takdirde bir hata kodu.</span><span class="sxs-lookup"><span data-stu-id="4857e-109">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4857e-110">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="4857e-110">See also</span></span>

- [<span data-ttu-id="4857e-111">ISymUnmanagedDocument Arabirimi</span><span class="sxs-lookup"><span data-stu-id="4857e-111">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
