---
title: ISymUnmanagedScope::GetParent Metodu
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetParent
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetParent
helpviewer_keywords:
- GetParent method [.NET Framework debugging]
- ISymUnmanagedScope::GetParent method [.NET Framework debugging]
ms.assetid: c7963c87-6ec5-49b3-a5cd-e0fe0c43f9b4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 606b9b496380a00ab9615ab7fe7febdc749b3ee2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663537"
---
# <a name="isymunmanagedscopegetparent-method"></a><span data-ttu-id="0ed14-102">ISymUnmanagedScope::GetParent Metodu</span><span class="sxs-lookup"><span data-stu-id="0ed14-102">ISymUnmanagedScope::GetParent Method</span></span>
<span data-ttu-id="0ed14-103">Bu kapsam üst kapsamı alır.</span><span class="sxs-lookup"><span data-stu-id="0ed14-103">Gets the parent scope of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ed14-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="0ed14-104">Syntax</span></span>  
  
```  
HRESULT GetParent(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ed14-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="0ed14-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="0ed14-106">[out] Döndürülen işaretçi [Isymunmanagedscope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) arabirimi.</span><span class="sxs-lookup"><span data-stu-id="0ed14-106">[out] A pointer to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ed14-107">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="0ed14-107">Return Value</span></span>  
 <span data-ttu-id="0ed14-108">Yöntem başarılı olursa S_OK; Aksi takdirde, E_FAIL veya başka bir hata kodu.</span><span class="sxs-lookup"><span data-stu-id="0ed14-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ed14-109">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="0ed14-109">Requirements</span></span>  
 <span data-ttu-id="0ed14-110">**Üst bilgi:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0ed14-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ed14-111">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="0ed14-111">See also</span></span>
- [<span data-ttu-id="0ed14-112">ISymUnmanagedScope Arabirimi</span><span class="sxs-lookup"><span data-stu-id="0ed14-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="0ed14-113">GetChildren Yöntemi</span><span class="sxs-lookup"><span data-stu-id="0ed14-113">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)
