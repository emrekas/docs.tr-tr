---
title: FUSION_INSTALL_REFERENCE Yapısı
ms.date: 03/30/2017
api_name:
- FUSION_INSTALL_REFERENCE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- FUSION_INSTALL_REFERENCE
helpviewer_keywords:
- FUSION_INSTALL_REFERENCE structure [.NET Framework fusion]
ms.assetid: ae181ec8-36bf-4ed1-9a02-ca27d417c80b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e81fb7c99b9fd03a69456a84f2191770f40121d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795339"
---
# <a name="fusion_install_reference-structure"></a><span data-ttu-id="da1cb-102">FUSION_INSTALL_REFERENCE Yapısı</span><span class="sxs-lookup"><span data-stu-id="da1cb-102">FUSION_INSTALL_REFERENCE Structure</span></span>
<span data-ttu-id="da1cb-103">Uygulamanın, uygulamanın genel derleme önbelleğinde yüklediği bir derlemeye yaptığı bir başvuruyu temsil eder.</span><span class="sxs-lookup"><span data-stu-id="da1cb-103">Represents a reference that an application makes to an assembly that the application has installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da1cb-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="da1cb-104">Syntax</span></span>  
  
```cpp  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="da1cb-105">Üyeler</span><span class="sxs-lookup"><span data-stu-id="da1cb-105">Members</span></span>  
  
|<span data-ttu-id="da1cb-106">Üye</span><span class="sxs-lookup"><span data-stu-id="da1cb-106">Member</span></span>|<span data-ttu-id="da1cb-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="da1cb-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="da1cb-108">Yapının bayt cinsinden boyutu.</span><span class="sxs-lookup"><span data-stu-id="da1cb-108">The size of the structure in bytes.</span></span>|  
|`dwFlags`|<span data-ttu-id="da1cb-109">Gelecekteki genişletilebilirlik için ayrılmıştır.</span><span class="sxs-lookup"><span data-stu-id="da1cb-109">Reserved for future extensibility.</span></span> <span data-ttu-id="da1cb-110">Bu değer 0 (sıfır) olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="da1cb-110">This value must be 0 (zero).</span></span>|  
|`guidScheme`|<span data-ttu-id="da1cb-111">Başvuruyu ekleyen varlık.</span><span class="sxs-lookup"><span data-stu-id="da1cb-111">The entity that adds the reference.</span></span> <span data-ttu-id="da1cb-112">Bu alan aşağıdaki değerlerden birine sahip olabilir:</span><span class="sxs-lookup"><span data-stu-id="da1cb-112">This field can have one of the following values:</span></span><br /><br /> <span data-ttu-id="da1cb-113">- FUSION_REFCOUNT_MSI_GUID: Derlemeye, Microsoft Windows Installer kullanılarak yüklenen bir uygulama tarafından başvurulur.</span><span class="sxs-lookup"><span data-stu-id="da1cb-113">-   FUSION_REFCOUNT_MSI_GUID: The assembly is referenced by an application that was installed using the Microsoft Windows Installer.</span></span> <span data-ttu-id="da1cb-114">Alanı olarak `MSI`ayarlanır ve`szNonCanonicalData` alan olarak`Windows Installer`ayarlanır. `szIdentifier`</span><span class="sxs-lookup"><span data-stu-id="da1cb-114">The `szIdentifier` field is set to `MSI`, and the `szNonCanonicalData` field is set to `Windows Installer`.</span></span> <span data-ttu-id="da1cb-115">Bu düzen Windows yan yana derlemeler için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="da1cb-115">This scheme is used for Windows side-by-side assemblies.</span></span><br /><span data-ttu-id="da1cb-116">- FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: Derlemeye **Program Ekle/Kaldır** arabiriminde görünen bir uygulama tarafından başvurulur.</span><span class="sxs-lookup"><span data-stu-id="da1cb-116">-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: The assembly is referenced by an application that appears in the **Add/Remove Programs** interface.</span></span> <span data-ttu-id="da1cb-117">Alan, uygulamayı **Program Ekle/Kaldır** arabirimiyle kaydeden belirteci sağlar. `szIdentifier`</span><span class="sxs-lookup"><span data-stu-id="da1cb-117">The `szIdentifier` field provides the token that registers the application with the **Add/Remove Programs** interface.</span></span><br /><span data-ttu-id="da1cb-118">- FUSION_REFCOUNT_FILEPATH_GUID: Derlemeye, dosya sistemindeki bir dosya tarafından temsil edilen bir uygulama tarafından başvurulur.</span><span class="sxs-lookup"><span data-stu-id="da1cb-118">-   FUSION_REFCOUNT_FILEPATH_GUID: The assembly is referenced by an application that is represented by a file in the file system.</span></span> <span data-ttu-id="da1cb-119">`szIdentifier` Alan, bu dosyanın yolunu sağlar.</span><span class="sxs-lookup"><span data-stu-id="da1cb-119">The `szIdentifier` field provides the path to this file.</span></span><br /><span data-ttu-id="da1cb-120">- FUSION_REFCOUNT_OPAQUE_STRING_GUID: Derlemeye yalnızca donuk bir dize tarafından temsil edilen bir uygulama tarafından başvuruluyor.</span><span class="sxs-lookup"><span data-stu-id="da1cb-120">-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: The assembly is referenced by an application that is represented only by an opaque string.</span></span> <span data-ttu-id="da1cb-121">`szIdentifier` Alan bu donuk dize sağlar.</span><span class="sxs-lookup"><span data-stu-id="da1cb-121">The `szIdentifier` field provides this opaque string.</span></span> <span data-ttu-id="da1cb-122">Genel bütünleştirilmiş kod önbelleği, bu değeri kaldırdığınızda donuk başvuruların varlığını denetlemez.</span><span class="sxs-lookup"><span data-stu-id="da1cb-122">The global assembly cache does not check for the existence of opaque references when you remove this value.</span></span><br /><span data-ttu-id="da1cb-123">- FUSION_REFCOUNT_OSINSTALL_GUID: Bu değer ayrılmıştır.</span><span class="sxs-lookup"><span data-stu-id="da1cb-123">-   FUSION_REFCOUNT_OSINSTALL_GUID: This value is reserved.</span></span>|  
|`szIdentifier`|<span data-ttu-id="da1cb-124">Derlemeyi genel derleme önbelleğine yükleyen uygulamayı tanımlayan benzersiz bir dize.</span><span class="sxs-lookup"><span data-stu-id="da1cb-124">A unique string that identifies the application that installed the assembly in the global assembly cache.</span></span> <span data-ttu-id="da1cb-125">Değeri `guidScheme` alanın değerine bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="da1cb-125">Its value depends upon the value of the `guidScheme` field.</span></span>|  
|`szNonCanonicalData`|<span data-ttu-id="da1cb-126">Yalnızca başvuruyu ekleyen varlık tarafından anlaşılan bir dize.</span><span class="sxs-lookup"><span data-stu-id="da1cb-126">A string that is understood only by the entity that adds the reference.</span></span> <span data-ttu-id="da1cb-127">Genel bütünleştirilmiş kod önbelleği bu dizeyi depolar, ancak kullanmaz.</span><span class="sxs-lookup"><span data-stu-id="da1cb-127">The global assembly cache stores this string, but does not use it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="da1cb-128">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="da1cb-128">Requirements</span></span>  
 <span data-ttu-id="da1cb-129">**Platform** Bkz. [sistem gereksinimleri](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da1cb-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da1cb-130">**Üst bilgi** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="da1cb-130">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="da1cb-131">**.NET Framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da1cb-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da1cb-132">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="da1cb-132">See also</span></span>

- [<span data-ttu-id="da1cb-133">Fusion Yapıları</span><span class="sxs-lookup"><span data-stu-id="da1cb-133">Fusion Structures</span></span>](fusion-structures.md)
- [<span data-ttu-id="da1cb-134">Genel Derleme Önbelleği</span><span class="sxs-lookup"><span data-stu-id="da1cb-134">Global Assembly Cache</span></span>](../../app-domains/gac.md)
