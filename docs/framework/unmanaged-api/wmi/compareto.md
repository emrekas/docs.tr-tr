---
title: CompareTo işlevi (yönetilmeyen API Başvurusu)
description: CompareTo işlevi bir nesneyi başka bir WMI nesnesini karşılaştırır.
ms.date: 11/06/2017
api_name:
- CompareTo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CompareTo
helpviewer_keywords:
- CompareTo function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3566b9b8a3b4183f936c82c39c38dc5daa3aeae1
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636685"
---
# <a name="compareto-function"></a><span data-ttu-id="018ce-103">CompareTo işlevi</span><span class="sxs-lookup"><span data-stu-id="018ce-103">CompareTo function</span></span>

<span data-ttu-id="018ce-104">Başka bir Windows Yönetim nesnesi için bir nesne ile karşılaştırır.</span><span class="sxs-lookup"><span data-stu-id="018ce-104">Compares an object to another Windows management object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="018ce-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="018ce-105">Syntax</span></span>

```cpp
HRESULT CompareTo (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo
);
```

## <a name="parameters"></a><span data-ttu-id="018ce-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="018ce-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="018ce-107">[in] Bu parametre kullanılmaz.</span><span class="sxs-lookup"><span data-stu-id="018ce-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="018ce-108">[in] Bir işaretçi bir [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) örneği.</span><span class="sxs-lookup"><span data-stu-id="018ce-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`flags`\
<span data-ttu-id="018ce-109">[in] Karşılaştırma için dikkate alınması gereken nesne özellikleri belirten bayraklar Bitsel bir birleşimi.</span><span class="sxs-lookup"><span data-stu-id="018ce-109">[in] A bitwise combination of the flags that specify the object characteristics to consider for the comparison.</span></span> <span data-ttu-id="018ce-110">Bkz: [açıklamalar](#remarks) bölümünde daha fazla bilgi için.</span><span class="sxs-lookup"><span data-stu-id="018ce-110">See the [Remarks](#remarks) section for more information.</span></span>

`pCompareTo`\
<span data-ttu-id="018ce-111">[in] Karşılaştırma için nesne.</span><span class="sxs-lookup"><span data-stu-id="018ce-111">[in] The object for comparison.</span></span> <span data-ttu-id="018ce-112">`pCompareTo` Geçerli bir olmalıdır [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) örnek; olamaz `null`.</span><span class="sxs-lookup"><span data-stu-id="018ce-112">`pCompareTo` must be a valid [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance; it cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="018ce-113">Dönüş değeri</span><span class="sxs-lookup"><span data-stu-id="018ce-113">Return value</span></span>

<span data-ttu-id="018ce-114">Bu işlev tarafından döndürülen aşağıdaki değerleri tanımlanan *WbemCli.h* üst bilgi dosyası veya tanımlayabilirsiniz bunları sabitleri kodunuzda:</span><span class="sxs-lookup"><span data-stu-id="018ce-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="018ce-115">Sabit</span><span class="sxs-lookup"><span data-stu-id="018ce-115">Constant</span></span>  |<span data-ttu-id="018ce-116">Değer</span><span class="sxs-lookup"><span data-stu-id="018ce-116">Value</span></span>  |<span data-ttu-id="018ce-117">Açıklama</span><span class="sxs-lookup"><span data-stu-id="018ce-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="018ce-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="018ce-118">0x80041001</span></span> | <span data-ttu-id="018ce-119">Belirtilmeyen bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="018ce-119">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="018ce-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="018ce-120">0x80041008</span></span> | <span data-ttu-id="018ce-121">Bir parametre geçersiz.</span><span class="sxs-lookup"><span data-stu-id="018ce-121">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="018ce-122">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="018ce-122">0x8004101d</span></span> | <span data-ttu-id="018ce-123">İkinci çağrı `BeginEnumeration` bir çağrı göndermelisiniz olmadan yapılan [ `EndEnumeration` ](endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="018ce-123">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="018ce-124">0</span><span class="sxs-lookup"><span data-stu-id="018ce-124">0</span></span> | <span data-ttu-id="018ce-125">İşlev çağrısı başarılı oldu.</span><span class="sxs-lookup"><span data-stu-id="018ce-125">The function call was successful.</span></span>  |
| `WBEM_S_DIFFERENT` | <span data-ttu-id="018ce-126">0x40003</span><span class="sxs-lookup"><span data-stu-id="018ce-126">0x40003</span></span> | <span data-ttu-id="018ce-127">Nesneler farklı.</span><span class="sxs-lookup"><span data-stu-id="018ce-127">The objects are different.</span></span> |
| `WBEM_S_SAME` | <span data-ttu-id="018ce-128">0</span><span class="sxs-lookup"><span data-stu-id="018ce-128">0</span></span> | <span data-ttu-id="018ce-129">Nesneleri karşılaştırma bayraklarını tabanlı aynıdır.</span><span class="sxs-lookup"><span data-stu-id="018ce-129">The objects are the same based on the comparison flags.</span></span> |

## <a name="remarks"></a><span data-ttu-id="018ce-130">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="018ce-130">Remarks</span></span>

<span data-ttu-id="018ce-131">Bu işlev bir çağrı sarılır [IWbemClassObject::CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="018ce-131">This function wraps a call to the [IWbemClassObject::CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) method.</span></span>

<span data-ttu-id="018ce-132">Olarak geçirilen bayraklar `lEnumFlags` bağımsız değişken tanımlanmış *WbemCli.h* üst bilgi dosyası veya tanımlayabilirsiniz bunları sabitleri kodunuzda.</span><span class="sxs-lookup"><span data-stu-id="018ce-132">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span> <span data-ttu-id="018ce-133">Aşağıdaki bayraklar Bitsel bir birleşimi belirterek Karşılaştırmada dahil bireysel özelliklerini belirtebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="018ce-133">You can specify the individual characteristics involved in the comparison by specifying a bitwise combination of the following flags:</span></span>

|<span data-ttu-id="018ce-134">Sabit</span><span class="sxs-lookup"><span data-stu-id="018ce-134">Constant</span></span>  |<span data-ttu-id="018ce-135">Değer</span><span class="sxs-lookup"><span data-stu-id="018ce-135">Value</span></span>  |<span data-ttu-id="018ce-136">Açıklama</span><span class="sxs-lookup"><span data-stu-id="018ce-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | <span data-ttu-id="018ce-137">2</span><span class="sxs-lookup"><span data-stu-id="018ce-137">2</span></span> | <span data-ttu-id="018ce-138">Kaynak (sunucu ve kaynaklarına ad alanı) yoksayın.</span><span class="sxs-lookup"><span data-stu-id="018ce-138">Ignore the source (the server and the namespace they came from).</span></span> |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | <span data-ttu-id="018ce-139">1.</span><span class="sxs-lookup"><span data-stu-id="018ce-139">1</span></span> | <span data-ttu-id="018ce-140">Tüm niteleyicileri yoksay (dahil olmak üzere **anahtarı** ve **dinamik**)</span><span class="sxs-lookup"><span data-stu-id="018ce-140">Ignore all qualifiers (including **Key** and **Dynamic**)</span></span> |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | <span data-ttu-id="018ce-141">4</span><span class="sxs-lookup"><span data-stu-id="018ce-141">4</span></span> | <span data-ttu-id="018ce-142">Özelliklerin varsayılan değerlerini yoksayın.</span><span class="sxs-lookup"><span data-stu-id="018ce-142">Ignore default values of properties.</span></span> <span data-ttu-id="018ce-143">Bu bayrağı yalnızca sınıfları bir karşılaştırması için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="018ce-143">This flag only applies to comparison of classes.</span></span> |
| `WBEM_FLAG_IGNORE_FLAVOR` | <span data-ttu-id="018ce-144">0x20</span><span class="sxs-lookup"><span data-stu-id="018ce-144">0x20</span></span> | <span data-ttu-id="018ce-145">Niteleyici özelliği yoksayın.</span><span class="sxs-lookup"><span data-stu-id="018ce-145">Ignore qualifier flavors.</span></span> <span data-ttu-id="018ce-146">Bu bayrak hala niteleyicileri, dikkate ancak flavor farklılıklar yayma kuralları gibi yoksayar ve kısıtlamaları geçersiz kılar.</span><span class="sxs-lookup"><span data-stu-id="018ce-146">This flag still takes qualifiers into account, but ignores flavor distinctions such as propagation rules and override restrictions.</span></span> |
| `WBEM_FLAG_IGNORE_CASE` | <span data-ttu-id="018ce-147">0x10</span><span class="sxs-lookup"><span data-stu-id="018ce-147">0x10</span></span> | <span data-ttu-id="018ce-148">Dize değerleri karşılaştırma içinde çalışması yoksayar.</span><span class="sxs-lookup"><span data-stu-id="018ce-148">Ignore case in comparing string values.</span></span> <span data-ttu-id="018ce-149">Bu, hem dizeleri ve niteleyici değeri için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="018ce-149">This applies both to strings and qualifier values.</span></span> <span data-ttu-id="018ce-150">Özellik ve niteleyicisi adlarının karşılaştırma her zaman bu bayrağı ayarlanmış olduğundan bağımsız olarak büyük küçük harfe duyarlıdır.</span><span class="sxs-lookup"><span data-stu-id="018ce-150">The comparison of property and qualifier names is always case-sensitive regardless of whether this flag is set.</span></span> |
| `WBEM_FLAG_IGNORE_CLASS` | <span data-ttu-id="018ce-151">0x8</span><span class="sxs-lookup"><span data-stu-id="018ce-151">0x8</span></span> | <span data-ttu-id="018ce-152">Karşılaştırılan nesnelerin aynı sınıf örnekleri olduğunu varsayar.</span><span class="sxs-lookup"><span data-stu-id="018ce-152">Assume that the objects being compared are instances of the same class.</span></span> <span data-ttu-id="018ce-153">Sonuç olarak, bu bayrağı yalnızca örnekle ilgili bilgi karşılaştırır.</span><span class="sxs-lookup"><span data-stu-id="018ce-153">Consequently, this flag compares instance-related information only.</span></span> <span data-ttu-id="018ce-154">Bu bayrak, performansı iyileştirmek için kullanın.</span><span class="sxs-lookup"><span data-stu-id="018ce-154">Use this flags to optimize performance.</span></span> <span data-ttu-id="018ce-155">Nesneleri aynı sınıfının emin değilseniz, sonuçlar tanımsızdır.</span><span class="sxs-lookup"><span data-stu-id="018ce-155">If the objects are not of the same class, the results are undefined.</span></span> |

<span data-ttu-id="018ce-156">Veya tek bir bileşik bayrağı şu şekilde belirtebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="018ce-156">Or you can specify a single composite flag as follows:</span></span>

|<span data-ttu-id="018ce-157">Sabit</span><span class="sxs-lookup"><span data-stu-id="018ce-157">Constant</span></span>  |<span data-ttu-id="018ce-158">Değer</span><span class="sxs-lookup"><span data-stu-id="018ce-158">Value</span></span>  |<span data-ttu-id="018ce-159">Açıklama</span><span class="sxs-lookup"><span data-stu-id="018ce-159">Description</span></span>  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | <span data-ttu-id="018ce-160">0</span><span class="sxs-lookup"><span data-stu-id="018ce-160">0</span></span> | <span data-ttu-id="018ce-161">Karşılaştırma içindeki tüm özelliklerini göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="018ce-161">Consider all features in the comparison.</span></span> |

## <a name="requirements"></a><span data-ttu-id="018ce-162">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="018ce-162">Requirements</span></span>

<span data-ttu-id="018ce-163">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="018ce-163">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="018ce-164">**Üst bilgi:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="018ce-164">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="018ce-165">**.NET framework sürümleri:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="018ce-165">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="018ce-166">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="018ce-166">See also</span></span>

- [<span data-ttu-id="018ce-167">WMI ve performans sayaçları (yönetilmeyen API Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="018ce-167">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
