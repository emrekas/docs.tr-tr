---
title: LinkResource Yöntemi
ms.date: 03/30/2017
api_name:
- IALink.LinkResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- LinkResource
helpviewer_keywords:
- LinkResource method
ms.assetid: c404acb3-4c59-4100-9a4c-483cbdb1d736
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 763b7a776007c2ce8dac42c6a5f7f00f6eb58a10
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776948"
---
# <a name="linkresource-method"></a><span data-ttu-id="36903-102">LinkResource Yöntemi</span><span class="sxs-lookup"><span data-stu-id="36903-102">LinkResource Method</span></span>
<span data-ttu-id="36903-103">Bir kaynaktaki bağlantılar.</span><span class="sxs-lookup"><span data-stu-id="36903-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36903-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="36903-104">Syntax</span></span>  
  
```cpp  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="36903-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="36903-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="36903-106">Derlemenin KIMLIĞI.</span><span class="sxs-lookup"><span data-stu-id="36903-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="36903-107">Dosyanın adı.</span><span class="sxs-lookup"><span data-stu-id="36903-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="36903-108">İsteğe bağlı yeni dosya adı.</span><span class="sxs-lookup"><span data-stu-id="36903-108">Optional new file name.</span></span> <span data-ttu-id="36903-109">NULL olmayan bir değer, `pszFileName` pszNewLocation ' a kopyalanacaktır.</span><span class="sxs-lookup"><span data-stu-id="36903-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="36903-110">Kaynağın adı.</span><span class="sxs-lookup"><span data-stu-id="36903-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="36903-111">`mrPublic` Ve`mrPrivate`gibi erişilebilirlik bayrakları.</span><span class="sxs-lookup"><span data-stu-id="36903-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="36903-112">Bu parametre [DefineManifestResource metoduna](../metadata/imetadataassemblyemit-definemanifestresource-method.md)geçirilebilir.</span><span class="sxs-lookup"><span data-stu-id="36903-112">This parameter may be passed to [DefineManifestResource Method](../metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36903-113">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="36903-113">Return Value</span></span>  
 <span data-ttu-id="36903-114">Yöntem başarılı olursa S_OK döndürür.</span><span class="sxs-lookup"><span data-stu-id="36903-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36903-115">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="36903-115">Requirements</span></span>  
 <span data-ttu-id="36903-116">ALink. h gerektirir.</span><span class="sxs-lookup"><span data-stu-id="36903-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36903-117">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="36903-117">See also</span></span>

- [<span data-ttu-id="36903-118">IALink Arabirimi</span><span class="sxs-lookup"><span data-stu-id="36903-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="36903-119">IALink2 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="36903-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="36903-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="36903-120">ALink API</span></span>](index.md)
