---
title: CorRegFlags Numaralandırması
ms.date: 03/30/2017
api_name:
- CorRegFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRegFlags
helpviewer_keywords:
- CorRegFlags enumeration [.NET Framework metadata]
ms.assetid: 8d3080ee-39fe-4c57-8950-51323632d045
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eb6b303fa7569712c854e8dc4e7513d8608e2519
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045363"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="337d2-102">CorRegFlags Numaralandırması</span><span class="sxs-lookup"><span data-stu-id="337d2-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="337d2-103">Bir modül veya bileşik görüntüsü yüklerken kayıt için kullanılan bayrak değerleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="337d2-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="337d2-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="337d2-104">Syntax</span></span>  
  
```  
typedef enum   
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="337d2-105">Üyeler</span><span class="sxs-lookup"><span data-stu-id="337d2-105">Members</span></span>  
  
|<span data-ttu-id="337d2-106">Üye</span><span class="sxs-lookup"><span data-stu-id="337d2-106">Member</span></span>|<span data-ttu-id="337d2-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="337d2-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="337d2-108">Dosyaları hedefe kopyalanmaması gereken olduğunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="337d2-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="337d2-109">Modülün veya bileşik bir yapılandırma olduğunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="337d2-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="337d2-110">Modülün veya bileşik sınıf başvuruları sahip olduğunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="337d2-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="337d2-111">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="337d2-111">Requirements</span></span>  
 <span data-ttu-id="337d2-112">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="337d2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="337d2-113">**Üst bilgi:** COR.h</span><span class="sxs-lookup"><span data-stu-id="337d2-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="337d2-114">**Kitaplığı:** Bir kaynak olarak MsCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="337d2-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="337d2-115">**.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="337d2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="337d2-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="337d2-116">See also</span></span>

- [<span data-ttu-id="337d2-117">Meta Veri Sabit Listeleri</span><span class="sxs-lookup"><span data-stu-id="337d2-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
