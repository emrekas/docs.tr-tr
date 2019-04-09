---
title: ISymUnmanagedReader::GetMethodByVersion Metodu
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodByVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodByVersion
helpviewer_keywords:
- ISymUnmanagedReader::GetMethodByVersion method [.NET Framework debugging]
- GetMethodByVersion method [.NET Framework debugging]
ms.assetid: 6ddb0631-4569-41b3-93e4-50fdfaa486dc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d4bc763d908156f3bbf8998c13073820686903f6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132762"
---
# <a name="isymunmanagedreadergetmethodbyversion-method"></a><span data-ttu-id="b73d5-102">ISymUnmanagedReader::GetMethodByVersion Metodu</span><span class="sxs-lookup"><span data-stu-id="b73d5-102">ISymUnmanagedReader::GetMethodByVersion Method</span></span>
<span data-ttu-id="b73d5-103">Bir sembol okuyucu yöntemi verilen token metody ve bir düzenleme ve kopyalama sürüm numarasını alır.</span><span class="sxs-lookup"><span data-stu-id="b73d5-103">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span> <span data-ttu-id="b73d5-104">Sürüm numaraları 1'den başlar ve bir düzenleme ve kopyalama işlemi sonucunda yöntemi her değiştirildiğinde artırılır.</span><span class="sxs-lookup"><span data-stu-id="b73d5-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b73d5-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="b73d5-105">Syntax</span></span>  
  
```  
HRESULT GetMethodByVersion (  
    [in]  mdMethodDef  token,  
    [in]  int  version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b73d5-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="b73d5-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="b73d5-107">[in] Token metody</span><span class="sxs-lookup"><span data-stu-id="b73d5-107">[in] The method token.</span></span>  
  
 `version`  
 <span data-ttu-id="b73d5-108">[in] Yöntemi sürümü.</span><span class="sxs-lookup"><span data-stu-id="b73d5-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="b73d5-109">[out] Döndürülen arabirim işaretçisi.</span><span class="sxs-lookup"><span data-stu-id="b73d5-109">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b73d5-110">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="b73d5-110">Return Value</span></span>  
 <span data-ttu-id="b73d5-111">Yöntem başarılı olursa S_OK; Aksi takdirde, E_FAIL veya başka bir hata kodu.</span><span class="sxs-lookup"><span data-stu-id="b73d5-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b73d5-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="b73d5-112">Requirements</span></span>  
 <span data-ttu-id="b73d5-113">**Üst bilgi:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b73d5-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b73d5-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="b73d5-114">See also</span></span>

- [<span data-ttu-id="b73d5-115">ISymUnmanagedReader Arabirimi</span><span class="sxs-lookup"><span data-stu-id="b73d5-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
