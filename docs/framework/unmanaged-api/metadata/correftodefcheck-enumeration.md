---
title: CorRefToDefCheck Numaralandırması
ms.date: 03/30/2017
api_name:
- CorRefToDefCheck
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRefToDefCheck
helpviewer_keywords:
- CorRefToDefCheck enumeration [.NET Framework metadata]
ms.assetid: f9a80f1a-55af-4459-b095-8441aae16119
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 82abeb0ce3db075d794787bb1fcd5bc18321bef2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906184"
---
# <a name="correftodefcheck-enumeration"></a><span data-ttu-id="c9bab-102">CorRefToDefCheck Numaralandırması</span><span class="sxs-lookup"><span data-stu-id="c9bab-102">CorRefToDefCheck Enumeration</span></span>
<span data-ttu-id="c9bab-103">Başvurulan öğeleri kod iyileştirmek için tanımları için dönüştürülür denetim bayrakları belirtir.</span><span class="sxs-lookup"><span data-stu-id="c9bab-103">Specifies flags to control which referenced items are converted to their definitions in order to optimize the code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9bab-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="c9bab-104">Syntax</span></span>  
  
```  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a><span data-ttu-id="c9bab-105">Üyeler</span><span class="sxs-lookup"><span data-stu-id="c9bab-105">Members</span></span>  
  
|<span data-ttu-id="c9bab-106">Üye</span><span class="sxs-lookup"><span data-stu-id="c9bab-106">Member</span></span>|<span data-ttu-id="c9bab-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="c9bab-107">Description</span></span>|  
|------------|-----------------|  
|`MDRefToDefDefault`|<span data-ttu-id="c9bab-108">Tür başvurularını ve üye başvuruları tanımlara dönüştürülüp dönüştürülmeyeceğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="c9bab-108">Specifies that type references and member references should be converted to definitions.</span></span> <span data-ttu-id="c9bab-109">Varsayılan değer budur (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span><span class="sxs-lookup"><span data-stu-id="c9bab-109">This is the default value (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span></span>|  
|`MDRefToDefAll`|<span data-ttu-id="c9bab-110">Tüm başvurulan öğelerin tanımlarını dönüştürülmesi gerektiğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="c9bab-110">Specifies that all referenced items should be converted to definitions.</span></span>|  
|`MDRefToDefNone`|<span data-ttu-id="c9bab-111">Başvurulan öğe tanımlarını dönüştürülmesi gerektiğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="c9bab-111">Specifies that no referenced items should be converted to definitions.</span></span>|  
|`MDTypeRefToDef`|<span data-ttu-id="c9bab-112">Yalnızca tür başvurularını tür tanımlarına dönüştürülmesi gerektiğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="c9bab-112">Specifies that only type references should be converted to type definitions.</span></span>|  
|`MDMemberRefToDef`|<span data-ttu-id="c9bab-113">Yalnızca üye başvuruları tanımlara dönüştürülmesi gerektiğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="c9bab-113">Specifies that only member references should be converted to definitions.</span></span> <span data-ttu-id="c9bab-114">Diğer bir deyişle, üye başvuruları yöntemi tanımları veya alan tanımları dönüştürülmelidir.</span><span class="sxs-lookup"><span data-stu-id="c9bab-114">That is, member references should be converted to either method definitions or field definitions.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c9bab-115">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="c9bab-115">Requirements</span></span>  
 <span data-ttu-id="c9bab-116">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9bab-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9bab-117">**Üst bilgi:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="c9bab-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c9bab-118">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9bab-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9bab-119">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="c9bab-119">See also</span></span>

- [<span data-ttu-id="c9bab-120">Meta Veri Sabit Listeleri</span><span class="sxs-lookup"><span data-stu-id="c9bab-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
