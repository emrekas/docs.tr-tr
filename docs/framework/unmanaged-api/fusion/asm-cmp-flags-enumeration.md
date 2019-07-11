---
title: ASM_CMP_FLAGS Numaralandırması
ms.date: 03/30/2017
api_name:
- ASM_CMP_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_CMP_FLAGS
helpviewer_keywords:
- ASM_CMP_FLAGS enumeration [.NET Framework fusion]
ms.assetid: 4d1e6700-d4be-4fbd-8796-bfb4c07abbc8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28157d2ed223d89af4b4314035e7c03d572be7b8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778558"
---
# <a name="asmcmpflags-enumeration"></a><span data-ttu-id="cf82c-102">ASM_CMP_FLAGS Numaralandırması</span><span class="sxs-lookup"><span data-stu-id="cf82c-102">ASM_CMP_FLAGS Enumeration</span></span>
<span data-ttu-id="cf82c-103">Sürüm, yapı, kültür, imza ve tarafından Karşılaştırılacak iki derlemelerin benzeri belirten [Iassemblyname::ısequal](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-isequal-method.md) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="cf82c-103">Indicates the version, build, culture, signature, and so on, of two assemblies to be compared by the [IAssemblyName::IsEqual](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-isequal-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf82c-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="cf82c-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    ASM_CMPF_NAME                   = 0x1,  
    ASM_CMPF_MAJOR_VERSION          = 0x2,  
    ASM_CMPF_MINOR_VERSION          = 0x4,  
    ASM_CMPF_BUILD_NUMBER           = 0x8,  
    ASM_CMPF_REVISION_NUMBER        = 0x10,  
  
    ASM_CMPF_VERSION                =   
                 ASM_CMPF_MAJOR_VERSION |   
                 ASM_CMPF_MINOR_VERSION |   
                 ASM_CMPF_BUILD_NUMBER  |   
                 ASM_CMPF_REVISION_NUMBER,  
  
    ASM_CMPF_PUBLIC_KEY_TOKEN       = 0x20,  
    ASM_CMPF_CULTURE                = 0x40,  
    ASM_CMPF_CUSTOM                 = 0x80,  
    ASM_CMPF_DEFAULT                = 0x100,  
    ASM_CMPF_RETARGET               = 0x200,  
    ASM_CMPF_ARCHITECTURE           = 0x400,  
    ASM_CMPF_CONFIG_MASK            = 0x800,  
    ASM_CMPF_MVID                   = 0x1000,  
    ASM_CMPF_SIGNATURE              = 0x2000,  
  
    ASM_CMPF_IL_ALL                 =   
                 ASM_CMPF_NAME             |   
                 ASM_CMPF_VERSION          |   
                 ASM_CMPF_PUBLIC_KEY_TOKEN |   
                 ASM_CMPF_CULTURE,  
  
    ASM_CMPF_IL_NO_VERSION          =   
                 ASM_CMPF_NAME             |   
                 ASM_CMPF_PUBLIC_KEY_TOKEN |   
                 ASM_CMPF_CULTURE  
  
} ASM_CMP_FLAGS;  
```  
  
## <a name="requirements"></a><span data-ttu-id="cf82c-105">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="cf82c-105">Requirements</span></span>  
 <span data-ttu-id="cf82c-106">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf82c-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf82c-107">**Üst bilgi:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="cf82c-107">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="cf82c-108">**Kitaplığı:** Bir kaynak olarak MsCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="cf82c-108">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cf82c-109">**.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf82c-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf82c-110">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="cf82c-110">See also</span></span>

- [<span data-ttu-id="cf82c-111">IAssemblyName Arabirimi</span><span class="sxs-lookup"><span data-stu-id="cf82c-111">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="cf82c-112">Fusion Sabit Listeleri</span><span class="sxs-lookup"><span data-stu-id="cf82c-112">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
