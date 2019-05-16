---
title: QualifierSet_GetNames işlevi (yönetilmeyen API Başvurusu)
description: QualifierSet_GetNames işlevi, bir nesneye veya özelliğe niteleyicileri adlarını alır.
ms.date: 11/06/2017
api_name:
- QualifierSet_GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_GetNames
helpviewer_keywords:
- QualifierSet_GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 402d56b44c2b6f53f901e35c6d7b965811a40344
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636597"
---
# <a name="qualifiersetgetnames-function"></a><span data-ttu-id="95518-103">QualifierSet_GetNames function</span><span class="sxs-lookup"><span data-stu-id="95518-103">QualifierSet_GetNames function</span></span>

<span data-ttu-id="95518-104">Tüm niteleyicileri veya geçerli nesne ya da özellik mevcut olan bazı niteleyicileri adlarını alır.</span><span class="sxs-lookup"><span data-stu-id="95518-104">Retrieves the names of all the qualifiers or of certain qualifiers that are available from the current object or property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="95518-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="95518-105">Syntax</span></span>

```cpp
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
);
```

## <a name="parameters"></a><span data-ttu-id="95518-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="95518-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="95518-107">[in] Bu parametre kullanılmaz.</span><span class="sxs-lookup"><span data-stu-id="95518-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="95518-108">[in] Bir işaretçi bir [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) örneği.</span><span class="sxs-lookup"><span data-stu-id="95518-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`\
<span data-ttu-id="95518-109">[in] Aşağıdaki bayrakları veya numaralandırmada dahil etmek için hangi adlarını belirten değerlerinden biri.</span><span class="sxs-lookup"><span data-stu-id="95518-109">[in] One of the following flags or values that specifies which names to include in the enumeration.</span></span>

|<span data-ttu-id="95518-110">Sabit</span><span class="sxs-lookup"><span data-stu-id="95518-110">Constant</span></span>  |<span data-ttu-id="95518-111">Değer</span><span class="sxs-lookup"><span data-stu-id="95518-111">Value</span></span>  |<span data-ttu-id="95518-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="95518-112">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="95518-113">0</span><span class="sxs-lookup"><span data-stu-id="95518-113">0</span></span> | <span data-ttu-id="95518-114">Tüm niteleyicileri adlarını döndürür.</span><span class="sxs-lookup"><span data-stu-id="95518-114">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="95518-115">0x10</span><span class="sxs-lookup"><span data-stu-id="95518-115">0x10</span></span> | <span data-ttu-id="95518-116">Yalnızca niteleyicileri adları belirli için geçerli bir özellik veya nesne döndürür.</span><span class="sxs-lookup"><span data-stu-id="95518-116">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="95518-117">Bir özellik için: Yalnızca (geçersiz kılmaları dahil) özelliğine belirli niteleyicileri ve olmayan sınıf tanımından yayılan niteleyicileri döndürür.</span><span class="sxs-lookup"><span data-stu-id="95518-117">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="95518-118">Bir örneği için: Yalnızca örnek özgü niteleyicisi adlarını döndürür.</span><span class="sxs-lookup"><span data-stu-id="95518-118">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="95518-119">Bir sınıf için: Elde sınıf niteleyicileri yalnızca belirli döndürür.</span><span class="sxs-lookup"><span data-stu-id="95518-119">For a class: Return only qualifiers specific to the class being derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="95518-120">0x20</span><span class="sxs-lookup"><span data-stu-id="95518-120">0x20</span></span> | <span data-ttu-id="95518-121">Başka bir nesnenin dönüş yalnızca niteleyicileri adlarını yayılır.</span><span class="sxs-lookup"><span data-stu-id="95518-121">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="95518-122">Bir özellik için: Bu özellik yalnızca niteleyicileri yayılan dön sınıf tanımı ve özelliğinden olanlar.</span><span class="sxs-lookup"><span data-stu-id="95518-122">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="95518-123">Bir örneği için: Sınıf tanımı dönüş niteleyicileri yalnızca yayılır.</span><span class="sxs-lookup"><span data-stu-id="95518-123">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="95518-124">Bir sınıf için: Return bu niteleyici adları yalnızca üst sınıflardan devralınır.</span><span class="sxs-lookup"><span data-stu-id="95518-124">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

`pstrNames`\
<span data-ttu-id="95518-125">[out] Yeni bir `SAFEARRAY` , istenen adlarını içerir.</span><span class="sxs-lookup"><span data-stu-id="95518-125">[out] A new `SAFEARRAY` that contains the requested names.</span></span> <span data-ttu-id="95518-126">Dizi öğeleri 0 olabilir.</span><span class="sxs-lookup"><span data-stu-id="95518-126">The array can have 0 elements.</span></span> <span data-ttu-id="95518-127">Bir hata oluşursa, yeni bir `SAFEARRAY` döndürülmez.</span><span class="sxs-lookup"><span data-stu-id="95518-127">If an error occurs, a new `SAFEARRAY` is not returned.</span></span>

## <a name="return-value"></a><span data-ttu-id="95518-128">Dönüş değeri</span><span class="sxs-lookup"><span data-stu-id="95518-128">Return value</span></span>

<span data-ttu-id="95518-129">Bu işlev tarafından döndürülen aşağıdaki değerleri tanımlanan *WbemCli.h* üst bilgi dosyası veya tanımlayabilirsiniz bunları sabitleri kodunuzda:</span><span class="sxs-lookup"><span data-stu-id="95518-129">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="95518-130">Sabit</span><span class="sxs-lookup"><span data-stu-id="95518-130">Constant</span></span>  |<span data-ttu-id="95518-131">Değer</span><span class="sxs-lookup"><span data-stu-id="95518-131">Value</span></span>  |<span data-ttu-id="95518-132">Açıklama</span><span class="sxs-lookup"><span data-stu-id="95518-132">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="95518-133">0x80041008</span><span class="sxs-lookup"><span data-stu-id="95518-133">0x80041008</span></span> | <span data-ttu-id="95518-134">Bir parametre geçerli değil.</span><span class="sxs-lookup"><span data-stu-id="95518-134">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="95518-135">0x80041006</span><span class="sxs-lookup"><span data-stu-id="95518-135">0x80041006</span></span> | <span data-ttu-id="95518-136">Yeni bir numaralandırma başlatmak yeterli bellek yok.</span><span class="sxs-lookup"><span data-stu-id="95518-136">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="95518-137">0</span><span class="sxs-lookup"><span data-stu-id="95518-137">0</span></span> | <span data-ttu-id="95518-138">İşlev çağrısı başarılı oldu.</span><span class="sxs-lookup"><span data-stu-id="95518-138">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="95518-139">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="95518-139">Remarks</span></span>

<span data-ttu-id="95518-140">Bu işlev bir çağrı sarılır [IWbemQualifierSet::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="95518-140">This function wraps a call to the [IWbemQualifierSet::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) method.</span></span>

<span data-ttu-id="95518-141">Siz niteleyicisi adları aldıktan sonra her niteleyicisi adına göre çağırarak erişebilirsiniz [QualifierSet_Get](qualifierset-get.md) işlevi.</span><span class="sxs-lookup"><span data-stu-id="95518-141">Once you've retrieved the qualifier names, you can access each qualifier by name by calling the [QualifierSet_Get](qualifierset-get.md) function.</span></span>

<span data-ttu-id="95518-142">Sıfır niteleyicileri olması belirli bir nesne için bir hata değil dizelerde sayısını `pstrNames` işlevi döndürür olsa bile getirisini 0 olabilir `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="95518-142">It is not an error for a given object to have zero qualifiers, so the number of strings in `pstrNames` on return can be 0, even though the function returns `WBEM_S_NO_ERROR`.</span></span>

## <a name="requirements"></a><span data-ttu-id="95518-143">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="95518-143">Requirements</span></span>

<span data-ttu-id="95518-144">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95518-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="95518-145">**Üst bilgi:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="95518-145">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="95518-146">**.NET framework sürümleri:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="95518-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="95518-147">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="95518-147">See also</span></span>

- [<span data-ttu-id="95518-148">WMI ve performans sayaçları (yönetilmeyen API Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="95518-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
