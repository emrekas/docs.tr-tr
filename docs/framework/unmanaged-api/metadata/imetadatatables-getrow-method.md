---
title: IMetaDataTables::GetRow Yöntemi
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetRow
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetRow
helpviewer_keywords:
- IMetaDataTables::GetRow method [.NET Framework metadata]
- GetRow method [.NET Framework metadata]
ms.assetid: a7408d51-0bce-45a2-b58f-da4660bbc039
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 98fc95c618a7a06f5e6c219d7707af291770c06a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781406"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="0c6d0-102">IMetaDataTables::GetRow Yöntemi</span><span class="sxs-lookup"><span data-stu-id="0c6d0-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="0c6d0-103">Belirtilen tablo dizini altındaki tabloda belirtilen satır dizinindeki bir satır alır.</span><span class="sxs-lookup"><span data-stu-id="0c6d0-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c6d0-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="0c6d0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c6d0-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="0c6d0-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="0c6d0-106">[in] Satır alınır tablosu dizini.</span><span class="sxs-lookup"><span data-stu-id="0c6d0-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="0c6d0-107">[in] Alınacak satırın dizini.</span><span class="sxs-lookup"><span data-stu-id="0c6d0-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="0c6d0-108">[out] Satır için bir işaretçi işaretçisi.</span><span class="sxs-lookup"><span data-stu-id="0c6d0-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c6d0-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="0c6d0-109">Remarks</span></span>  
 <span data-ttu-id="0c6d0-110">Tutarlı sonuçlar döndürmez çünkü bu yöntem kullanımını önermeyiz.</span><span class="sxs-lookup"><span data-stu-id="0c6d0-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="0c6d0-111">Ortak dil altyapısı (CLI) belgeleri GUID tablosu hakkında daha fazla bilgi için bkz. özellikle "Bölüm II: Meta veri tanımı ve anlamı".</span><span class="sxs-lookup"><span data-stu-id="0c6d0-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="0c6d0-112">Belgeler çevrimiçi olarak kullanılabilir; bkz: [ECMA C# ve ortak dil altyapısı standartları](https://go.microsoft.com/fwlink/?LinkID=99212) MSDN'de ve [standart ECMA-335 - ortak dil altyapısı (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) Ecma uluslararası Web sitesinde.</span><span class="sxs-lookup"><span data-stu-id="0c6d0-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c6d0-113">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="0c6d0-113">Requirements</span></span>  
 <span data-ttu-id="0c6d0-114">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c6d0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c6d0-115">**Üst bilgi:** COR.h</span><span class="sxs-lookup"><span data-stu-id="0c6d0-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0c6d0-116">**Kitaplığı:** Bir kaynak olarak MsCorEE.dll kullanılan</span><span class="sxs-lookup"><span data-stu-id="0c6d0-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0c6d0-117">**.NET framework sürümleri**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c6d0-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c6d0-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="0c6d0-118">See also</span></span>

- [<span data-ttu-id="0c6d0-119">IMetaDataTables Arabirimi</span><span class="sxs-lookup"><span data-stu-id="0c6d0-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="0c6d0-120">IMetaDataTables2 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="0c6d0-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
