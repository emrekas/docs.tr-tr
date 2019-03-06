---
title: GetPropertyHandle işlevi (yönetilmeyen API Başvurusu)
description: GetPropertyHandle işlevi bir özelliği tanımlayan benzersiz bir tanıtıcı döndürür.
ms.date: 11/06/2017
api_name:
- GetPropertyHandle
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyHandle
helpviewer_keywords:
- GetPropertyHandle function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92d48caf7de873850135c7410a5e4b5861131212
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366380"
---
# <a name="getpropertyhandle-function"></a><span data-ttu-id="977ab-103">GetPropertyHandle işlevi</span><span class="sxs-lookup"><span data-stu-id="977ab-103">GetPropertyHandle function</span></span>

<span data-ttu-id="977ab-104">Bir özelliği tanımlayan benzersiz bir tanıtıcı döndürür.</span><span class="sxs-lookup"><span data-stu-id="977ab-104">Returns a unique handle that identifies a property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="977ab-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="977ab-105">Syntax</span></span>

```cpp
HRESULT GetPropertyHandle (
   [in] int                  vFunc,
   [in] IWbemObjectAccess*   ptr,
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
);
```

## <a name="parameters"></a><span data-ttu-id="977ab-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="977ab-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="977ab-107">[in] Bu parametre kullanılmaz.</span><span class="sxs-lookup"><span data-stu-id="977ab-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="977ab-108">[in] Bir işaretçi bir [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) örneği.</span><span class="sxs-lookup"><span data-stu-id="977ab-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`wszPropertyName`\
<span data-ttu-id="977ab-109">[in] Özellik adını içeren bir null ile sonlandırılmış dize UTF16 kodlanmış karakter.</span><span class="sxs-lookup"><span data-stu-id="977ab-109">[in] A null-terminated string of UTF16-encoded characters that contains the property name.</span></span>

`pType`\
<span data-ttu-id="977ab-110">[out] Bir işaretçi bir [ `CIMTYPE` ](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) özelliği CIM türünü temsil eden numaralandırma üyesi.</span><span class="sxs-lookup"><span data-stu-id="977ab-110">[out] A pointer to a [`CIMTYPE`](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) enumeration member that represents the CIM type of the property.</span></span>

`pHandle`\
<span data-ttu-id="977ab-111">[out] Özellik işleyicisi içeren bir tamsayı işaretçisi.</span><span class="sxs-lookup"><span data-stu-id="977ab-111">[out] A pointer to an integer that contains the property handle.</span></span>

## <a name="return-value"></a><span data-ttu-id="977ab-112">Dönüş değeri</span><span class="sxs-lookup"><span data-stu-id="977ab-112">Return value</span></span>

<span data-ttu-id="977ab-113">Bu işlev tarafından döndürülen aşağıdaki değerleri tanımlanan *WbemCli.h* üst bilgi dosyası veya tanımlayabilirsiniz bunları sabitleri kodunuzda:</span><span class="sxs-lookup"><span data-stu-id="977ab-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="977ab-114">Sabit</span><span class="sxs-lookup"><span data-stu-id="977ab-114">Constant</span></span>  |<span data-ttu-id="977ab-115">Değer</span><span class="sxs-lookup"><span data-stu-id="977ab-115">Value</span></span>  |<span data-ttu-id="977ab-116">Açıklama</span><span class="sxs-lookup"><span data-stu-id="977ab-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="977ab-117">0x80041002</span><span class="sxs-lookup"><span data-stu-id="977ab-117">0x80041002</span></span> | <span data-ttu-id="977ab-118">Belirtilen özellik adı bulunamadı.</span><span class="sxs-lookup"><span data-stu-id="977ab-118">The specified property name was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="977ab-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="977ab-119">0x80041008</span></span> | <span data-ttu-id="977ab-120">Bir parametre geçerli değil.</span><span class="sxs-lookup"><span data-stu-id="977ab-120">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_SUPPORTED` | <span data-ttu-id="977ab-121">0x8004100c</span><span class="sxs-lookup"><span data-stu-id="977ab-121">0x8004100c</span></span> | <span data-ttu-id="977ab-122">İstenen özellik türünde olan `CIM_OBJECT` veya `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="977ab-122">The requested property is of type are `CIM_OBJECT` or `CIM_ARRAY`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="977ab-123">0</span><span class="sxs-lookup"><span data-stu-id="977ab-123">0</span></span> | <span data-ttu-id="977ab-124">İşlev çağrısı başarılı oldu.</span><span class="sxs-lookup"><span data-stu-id="977ab-124">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="977ab-125">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="977ab-125">Remarks</span></span>

<span data-ttu-id="977ab-126">Bu işlev bir çağrı sarılır [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="977ab-126">This function wraps a call to the [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) method.</span></span>

<span data-ttu-id="977ab-127">Kullanırken özellikleri tanımlamak için bu tutamacı kullan [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) özellik değerlerini okumak veya yazmak için yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="977ab-127">You can use this handle to identify properties when using  [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) methods to read or write property values.</span></span>

<span data-ttu-id="977ab-128">Tanıtıcıları alınabilir özellikleri için tüm veri türleri dışındaki `CIM_OBJECT` ve `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="977ab-128">Handles can be retrieved for properties of all data types other than `CIM_OBJECT` and `CIM_ARRAY`.</span></span> <span data-ttu-id="977ab-129">Bir sınıfın tüm örnekleri arasında tanıtıcıları iş döndürdü.</span><span class="sxs-lookup"><span data-stu-id="977ab-129">Returned handles work across all instances of a class.</span></span>

## <a name="requirements"></a><span data-ttu-id="977ab-130">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="977ab-130">Requirements</span></span>

<span data-ttu-id="977ab-131">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="977ab-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="977ab-132">**Üst bilgi:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="977ab-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="977ab-133">**.NET framework sürümleri:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="977ab-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="977ab-134">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="977ab-134">See also</span></span>

- [<span data-ttu-id="977ab-135">WMI ve performans sayaçları (yönetilmeyen API Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="977ab-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)