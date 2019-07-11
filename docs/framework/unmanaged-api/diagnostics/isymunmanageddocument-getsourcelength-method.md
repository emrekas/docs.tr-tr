---
title: ISymUnmanagedDocument::GetSourceLength Yöntemi
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceLength
helpviewer_keywords:
- GetSourceLength method [.NET Framework debugging]
- ISymUnmanagedDocument::GetSourceLength method [.NET Framework debugging]
ms.assetid: e087dbbb-f4fb-4fbe-8292-e4f1a14d0df2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bf79c05b3b16bb61ac59534dd83cb8eb2bb1f823
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776709"
---
# <a name="isymunmanageddocumentgetsourcelength-method"></a><span data-ttu-id="6b20c-102">ISymUnmanagedDocument::GetSourceLength Yöntemi</span><span class="sxs-lookup"><span data-stu-id="6b20c-102">ISymUnmanagedDocument::GetSourceLength Method</span></span>
<span data-ttu-id="6b20c-103">Katıştırılmış kaynak bayt cinsinden uzunluğunu alır.</span><span class="sxs-lookup"><span data-stu-id="6b20c-103">Gets the length, in bytes, of the embedded source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b20c-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="6b20c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceLength(  
    [out, retval]  ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b20c-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="6b20c-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="6b20c-106">[out] Uzunluğu, bayt cinsinden katıştırılmış kaynak gösteren bir değişken için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="6b20c-106">[out] A pointer to a variable that indicates the length, in bytes, of the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6b20c-107">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="6b20c-107">Return Value</span></span>  
 <span data-ttu-id="6b20c-108">Yöntem başarılı olursa S_OK.</span><span class="sxs-lookup"><span data-stu-id="6b20c-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b20c-109">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="6b20c-109">See also</span></span>

- [<span data-ttu-id="6b20c-110">ISymUnmanagedDocument Arabirimi</span><span class="sxs-lookup"><span data-stu-id="6b20c-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
