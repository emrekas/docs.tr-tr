---
title: GetScope2 Metodu
ms.date: 03/30/2017
api_name:
- IALink2.GetScope2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope2
helpviewer_keywords:
- GetScope2 method
ms.assetid: 49435665-6f5a-4acd-9034-8c9244a04a63
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e3c11eeeb4eece495a7ccbe51c7e04d077e497ce
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494577"
---
# <a name="getscope2-method"></a><span data-ttu-id="ee781-102">GetScope2 Metodu</span><span class="sxs-lookup"><span data-stu-id="ee781-102">GetScope2 Method</span></span>
<span data-ttu-id="ee781-103">Bir içeri aktarma kapsamı alır.</span><span class="sxs-lookup"><span data-stu-id="ee781-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee781-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="ee781-104">Syntax</span></span>  
  
```  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="ee781-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="ee781-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ee781-106">Hedef derleme kimliği.</span><span class="sxs-lookup"><span data-stu-id="ee781-106">ID of target assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="ee781-107">Alınacağı dosya kimliği.</span><span class="sxs-lookup"><span data-stu-id="ee781-107">ID of file from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="ee781-108">İçeri aktarmak için sıfır tabanlı kapsam.</span><span class="sxs-lookup"><span data-stu-id="ee781-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="ee781-109">İşaretçi alır [Imetadataımport2 arabirimi](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) Belirtilen kapsam için arabirim.</span><span class="sxs-lookup"><span data-stu-id="ee781-109">Receives pointer to [IMetaDataImport2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interface for indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee781-110">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="ee781-110">Return Value</span></span>  
 <span data-ttu-id="ee781-111">Yöntem başarılı olursa S_OK döndürür.</span><span class="sxs-lookup"><span data-stu-id="ee781-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee781-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="ee781-112">Requirements</span></span>  
 <span data-ttu-id="ee781-113">ALink.h gerektirir.</span><span class="sxs-lookup"><span data-stu-id="ee781-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee781-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="ee781-114">See also</span></span>
- [<span data-ttu-id="ee781-115">IALink2 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="ee781-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="ee781-116">IALink Arabirimi</span><span class="sxs-lookup"><span data-stu-id="ee781-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="ee781-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="ee781-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
