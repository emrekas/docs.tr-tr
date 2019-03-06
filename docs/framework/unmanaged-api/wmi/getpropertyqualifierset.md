---
title: GetPropertyQualifierSet işlevi (yönetilmeyen API Başvurusu)
description: GetPropertyQualifierSet işlevi için bir özelliği ayarlamak niteleyicisi alır.
ms.date: 11/06/2017
api_name:
- GetPropertyQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyQualifierSet
helpviewer_keywords:
- GetPropertyQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cdb9f748279e4e74c0dbd1ced1f48e3a24b9904d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358424"
---
# <a name="getpropertyqualifierset-function"></a><span data-ttu-id="82dda-103">GetPropertyQualifierSet işlevi</span><span class="sxs-lookup"><span data-stu-id="82dda-103">GetPropertyQualifierSet function</span></span>

<span data-ttu-id="82dda-104">Belirli bir özellik için ayarlanmış niteleyicisi alır.</span><span class="sxs-lookup"><span data-stu-id="82dda-104">Retrieves the qualifier set for a particular property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="82dda-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="82dda-105">Syntax</span></span>

```cpp
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
);
```

## <a name="parameters"></a><span data-ttu-id="82dda-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="82dda-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="82dda-107">[in] Bu parametre kullanılmaz.</span><span class="sxs-lookup"><span data-stu-id="82dda-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="82dda-108">[in] Bir işaretçi bir [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) örneği.</span><span class="sxs-lookup"><span data-stu-id="82dda-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethod`\
<span data-ttu-id="82dda-109">[in] Özellik adı.</span><span class="sxs-lookup"><span data-stu-id="82dda-109">[in] The property  name.</span></span> <span data-ttu-id="82dda-110">`wszProperty` Geçerli bir işaret etmelidir `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="82dda-110">`wszProperty` must point to a valid `LPCWSTR`.</span></span>

`ppQualSet`\
<span data-ttu-id="82dda-111">[out] Özellik niteleyicileri erişmesini sağlayan bir arabirim işaretçisi alır.</span><span class="sxs-lookup"><span data-stu-id="82dda-111">[out] Receives the interface pointer that allows access to the qualifiers of the property.</span></span> <span data-ttu-id="82dda-112">`ppQualSet` olamaz `null`.</span><span class="sxs-lookup"><span data-stu-id="82dda-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="82dda-113">Bir hata meydana gelir yeni bir nesne değil döndürülür ve işaretçi, işaret edecek şekilde ayarlanır `null`.</span><span class="sxs-lookup"><span data-stu-id="82dda-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="82dda-114">Dönüş değeri</span><span class="sxs-lookup"><span data-stu-id="82dda-114">Return value</span></span>

<span data-ttu-id="82dda-115">Bu işlev tarafından döndürülen aşağıdaki değerleri tanımlanan *WbemCli.h* üst bilgi dosyası veya tanımlayabilirsiniz bunları sabitleri kodunuzda:</span><span class="sxs-lookup"><span data-stu-id="82dda-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="82dda-116">Sabit</span><span class="sxs-lookup"><span data-stu-id="82dda-116">Constant</span></span>  |<span data-ttu-id="82dda-117">Değer</span><span class="sxs-lookup"><span data-stu-id="82dda-117">Value</span></span>  |<span data-ttu-id="82dda-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="82dda-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="82dda-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="82dda-119">0x80041001</span></span> | <span data-ttu-id="82dda-120">Genel bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="82dda-120">There has been a general failure.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="82dda-121">0x80041002</span><span class="sxs-lookup"><span data-stu-id="82dda-121">0x80041002</span></span> | <span data-ttu-id="82dda-122">Belirtilen yöntem yok.</span><span class="sxs-lookup"><span data-stu-id="82dda-122">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="82dda-123">0x80041006</span><span class="sxs-lookup"><span data-stu-id="82dda-123">0x80041006</span></span> | <span data-ttu-id="82dda-124">İşlemi tamamlamak yeterli bellek yok.</span><span class="sxs-lookup"><span data-stu-id="82dda-124">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="82dda-125">0x80041008</span><span class="sxs-lookup"><span data-stu-id="82dda-125">0x80041008</span></span> | <span data-ttu-id="82dda-126">Bir parametre `null`.</span><span class="sxs-lookup"><span data-stu-id="82dda-126">A parameter is `null`.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | <span data-ttu-id="82dda-127">0x80041030</span><span class="sxs-lookup"><span data-stu-id="82dda-127">0x80041030</span></span> | <span data-ttu-id="82dda-128">İşlevi, bir sistem özellik niteleyicileri almayı dener.</span><span class="sxs-lookup"><span data-stu-id="82dda-128">The function attempts to get qualifiers of a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="82dda-129">0</span><span class="sxs-lookup"><span data-stu-id="82dda-129">0</span></span> | <span data-ttu-id="82dda-130">İşlev çağrısı başarılı oldu.</span><span class="sxs-lookup"><span data-stu-id="82dda-130">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="82dda-131">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="82dda-131">Remarks</span></span>

<span data-ttu-id="82dda-132">Bu işlev bir çağrı sarılır [IWbemClassObject::GetPropertyQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="82dda-132">This function wraps a call to the [IWbemClassObject::GetPropertyQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset) method.</span></span>

<span data-ttu-id="82dda-133">Bu işlev çağrısı, yalnızca geçerli nesneye bir CIM sınıf tanımı ise desteklenir.</span><span class="sxs-lookup"><span data-stu-id="82dda-133">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="82dda-134">Yöntem işleme için kullanılabilir değil [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) CIM örneklerine işaret eden işaretçilerin.</span><span class="sxs-lookup"><span data-stu-id="82dda-134">Method manipulation is not available for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="82dda-135">Her yöntem kendi niteleyicileri olabileceğinden [IWbemQualifierSet işaretçi](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) eklemek, düzenlemek veya bu niteleyiciler silme çağıran olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="82dda-135">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span>

<span data-ttu-id="82dda-136">Sistem özellikleri hiçbir niteleyicileri içerdiğinden, işlev döndürür `WBEM_E_SYSTEM_PROPERTY` elde denerseniz bir [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) bir sistem özelliği için işaretçi.</span><span class="sxs-lookup"><span data-stu-id="82dda-136">Because system properties have no qualifiers, the function returns `WBEM_E_SYSTEM_PROPERTY` if you attempt to obtain a [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) pointer for a system property.</span></span>

## <a name="requirements"></a><span data-ttu-id="82dda-137">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="82dda-137">Requirements</span></span>

<span data-ttu-id="82dda-138">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82dda-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="82dda-139">**Üst bilgi:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="82dda-139">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="82dda-140">**.NET framework sürümleri:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="82dda-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="82dda-141">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="82dda-141">See also</span></span>

- [<span data-ttu-id="82dda-142">WMI ve performans sayaçları (yönetilmeyen API Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="82dda-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)