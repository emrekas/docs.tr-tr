---
title: ISymUnmanagedReader::GetMethodVersion Metodu
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 45aaceb2c39703cb1369941ce801c9cff1935ad6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555849"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="4897f-102">ISymUnmanagedReader::GetMethodVersion Metodu</span><span class="sxs-lookup"><span data-stu-id="4897f-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="4897f-103">Yöntem sürümünü alır.</span><span class="sxs-lookup"><span data-stu-id="4897f-103">Gets the method version.</span></span> <span data-ttu-id="4897f-104">Yöntemi sürüm 1 ile başlayan ve yöntem yeniden derlenen her zaman artırılır.</span><span class="sxs-lookup"><span data-stu-id="4897f-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="4897f-105">Yeniden derleme değişikliğe gerek kalmadan yönteme oluşabilir.</span><span class="sxs-lookup"><span data-stu-id="4897f-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4897f-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="4897f-106">Syntax</span></span>  
  
```  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4897f-107">Parametreler</span><span class="sxs-lookup"><span data-stu-id="4897f-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="4897f-108">[in] Hangi sürümü almak yöntem.</span><span class="sxs-lookup"><span data-stu-id="4897f-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="4897f-109">[out] Bir işaretçi bir değişkene yöntemi sürümünü alır.</span><span class="sxs-lookup"><span data-stu-id="4897f-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4897f-110">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="4897f-110">Return Value</span></span>  
 <span data-ttu-id="4897f-111">Yöntem başarılı olursa S_OK; Aksi takdirde, E_FAIL veya başka bir hata kodu.</span><span class="sxs-lookup"><span data-stu-id="4897f-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4897f-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="4897f-112">Requirements</span></span>  
 <span data-ttu-id="4897f-113">**Üst bilgi:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4897f-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4897f-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="4897f-114">See also</span></span>
- [<span data-ttu-id="4897f-115">ISymUnmanagedReader Arabirimi</span><span class="sxs-lookup"><span data-stu-id="4897f-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
