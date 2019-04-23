---
title: IMetaDataTables::GetTableIndex Yöntemi
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableIndex
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableIndex
helpviewer_keywords:
- GetTableIndex method [.NET Framework metadata]
- IMetaDataTables::GetTableIndex method [.NET Framework metadata]
ms.assetid: c6ec3800-e0d9-4387-afb8-ddc0b818114c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eebef02babdca5305deaa4ae11e4bca3bf8bf504
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59154407"
---
# <a name="imetadatatablesgettableindex-method"></a><span data-ttu-id="0d2a6-102">IMetaDataTables::GetTableIndex Yöntemi</span><span class="sxs-lookup"><span data-stu-id="0d2a6-102">IMetaDataTables::GetTableIndex Method</span></span>
<span data-ttu-id="0d2a6-103">Belirtilen belirteç tarafından başvurulan tablo için dizinini alır.</span><span class="sxs-lookup"><span data-stu-id="0d2a6-103">Gets the index for the table referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d2a6-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="0d2a6-104">Syntax</span></span>  
  
```  
HRESULT GetTableIndex (  
    [in]  ULONG   token,  
    [out] ULONG   *pixTbl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d2a6-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="0d2a6-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="0d2a6-106">[in] Tabloya başvuran belirteç.</span><span class="sxs-lookup"><span data-stu-id="0d2a6-106">[in] The token that references the table.</span></span>  
  
 `pixTbl`  
 <span data-ttu-id="0d2a6-107">[out] Başvurulan tablo döndürülen dizini için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="0d2a6-107">[out] A pointer to the returned index for the referenced table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d2a6-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="0d2a6-108">Remarks</span></span>  
 <span data-ttu-id="0d2a6-109">Tutarlı sonuçlar döndürmez çünkü bu yöntem kullanımını önermeyiz.</span><span class="sxs-lookup"><span data-stu-id="0d2a6-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="0d2a6-110">Ortak dil altyapısı (CLI) belgeleri GUID tablosu hakkında daha fazla bilgi için bkz. özellikle "Bölüm II: Meta veri tanımı ve anlamı".</span><span class="sxs-lookup"><span data-stu-id="0d2a6-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="0d2a6-111">Belgeler çevrimiçi olarak kullanılabilir; bkz: [ECMA C# ve ortak dil altyapısı standartları](https://go.microsoft.com/fwlink/?LinkID=99212) MSDN'de ve [standart ECMA-335 - ortak dil altyapısı (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) Ecma uluslararası Web sitesinde.</span><span class="sxs-lookup"><span data-stu-id="0d2a6-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d2a6-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="0d2a6-112">Requirements</span></span>  
 <span data-ttu-id="0d2a6-113">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d2a6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d2a6-114">**Üst bilgi:** COR.h</span><span class="sxs-lookup"><span data-stu-id="0d2a6-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0d2a6-115">**Kitaplığı:** Bir kaynak olarak MsCorEE.dll kullanılan</span><span class="sxs-lookup"><span data-stu-id="0d2a6-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0d2a6-116">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d2a6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d2a6-117">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="0d2a6-117">See also</span></span>

- [<span data-ttu-id="0d2a6-118">IMetaDataTables Arabirimi</span><span class="sxs-lookup"><span data-stu-id="0d2a6-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="0d2a6-119">IMetaDataTables2 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="0d2a6-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
