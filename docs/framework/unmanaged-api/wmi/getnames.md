---
title: GetNames işlevi (yönetilmeyen API Başvurusu)
description: GetNames işlevi, bir nesnenin özellik adlarını alır.
ms.date: 11/06/2017
api_name:
- GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetNames
helpviewer_keywords:
- GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f664edf29e5d2f9ec4e523aa7f7b204cf999e01b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61724089"
---
# <a name="getnames-function"></a><span data-ttu-id="7829e-103">GetNames işlevi</span><span class="sxs-lookup"><span data-stu-id="7829e-103">GetNames function</span></span>
<span data-ttu-id="7829e-104">Bir alt veya tümünü bir nesnenin özellik adlarını alır.</span><span class="sxs-lookup"><span data-stu-id="7829e-104">Retrieves either a subset or all of the names of the properties of an object.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="7829e-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="7829e-105">Syntax</span></span>  
  
```  
HRESULT GetNames (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszQualifierName,
   [in] LONG                lFlags,
   [in] VARIANT*            pQualifierValue,
   [out] SAFEARRAY (BSTR)** pstrNames
); 
```  

## <a name="parameters"></a><span data-ttu-id="7829e-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="7829e-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="7829e-107">[in] Bu parametre kullanılmaz.</span><span class="sxs-lookup"><span data-stu-id="7829e-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="7829e-108">[in] Bir işaretçi bir [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) örneği.</span><span class="sxs-lookup"><span data-stu-id="7829e-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszQualifierName`  
<span data-ttu-id="7829e-109">[in] Geçerli bir işaretçi `LPCWSTR` filtre kapsamında işleyen bir niteleyici adını belirtir.</span><span class="sxs-lookup"><span data-stu-id="7829e-109">[in] A pointer to a valid `LPCWSTR` that specifies a qualifier name that operates as part of a filter.</span></span> <span data-ttu-id="7829e-110">Daha fazla bilgi için [açıklamalar](#remarks) bölümü.</span><span class="sxs-lookup"><span data-stu-id="7829e-110">For more information, see the [Remarks](#remarks) section.</span></span> <span data-ttu-id="7829e-111">Bu parametre olabilir `null`.</span><span class="sxs-lookup"><span data-stu-id="7829e-111">This parameter can be `null`.</span></span> 

`lFlags`  
<span data-ttu-id="7829e-112">[in] Bit alanları bileşimi.</span><span class="sxs-lookup"><span data-stu-id="7829e-112">[in] A combination of bit fields.</span></span> <span data-ttu-id="7829e-113">Daha fazla bilgi için [açıklamalar](#remarks) bölümü.</span><span class="sxs-lookup"><span data-stu-id="7829e-113">For more information, see the [Remarks](#remarks) section.</span></span>

`pQualifierValue`   
<span data-ttu-id="7829e-114">[in] Geçerli bir işaretçi `VARIANT` yapısı için bir filtre değeri başlatıldı.</span><span class="sxs-lookup"><span data-stu-id="7829e-114">[in] A pointer to a valid `VARIANT` structure initialized to a filter value.</span></span> <span data-ttu-id="7829e-115">Bu parametre olabilir `null`.</span><span class="sxs-lookup"><span data-stu-id="7829e-115">This parameter can be `null`.</span></span> 

`pstrNames`  
<span data-ttu-id="7829e-116">[out] A `SAFEARRAY` özellik adları içeren yapısı.</span><span class="sxs-lookup"><span data-stu-id="7829e-116">[out] A `SAFEARRAY` structure that contains property names.</span></span> <span data-ttu-id="7829e-117">Girişte, bu parametre her zaman bir işaretçi olmalıdır `null`.</span><span class="sxs-lookup"><span data-stu-id="7829e-117">On entry, this parameter must always be a pointer to `null`.</span></span> <span data-ttu-id="7829e-118">Bkz: [açıklamalar](#remarks) bölümünde daha fazla bilgi için.</span><span class="sxs-lookup"><span data-stu-id="7829e-118">See the [Remarks](#remarks) section for more information.</span></span> 

## <a name="return-value"></a><span data-ttu-id="7829e-119">Dönüş değeri</span><span class="sxs-lookup"><span data-stu-id="7829e-119">Return value</span></span>

<span data-ttu-id="7829e-120">Bu işlev tarafından döndürülen aşağıdaki değerleri tanımlanan *WbemCli.h* üst bilgi dosyası veya tanımlayabilirsiniz bunları sabitleri kodunuzda:</span><span class="sxs-lookup"><span data-stu-id="7829e-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7829e-121">Sabit</span><span class="sxs-lookup"><span data-stu-id="7829e-121">Constant</span></span>  |<span data-ttu-id="7829e-122">Değer</span><span class="sxs-lookup"><span data-stu-id="7829e-122">Value</span></span>  |<span data-ttu-id="7829e-123">Açıklama</span><span class="sxs-lookup"><span data-stu-id="7829e-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="7829e-124">0x80041001</span><span class="sxs-lookup"><span data-stu-id="7829e-124">0x80041001</span></span> | <span data-ttu-id="7829e-125">Genel bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="7829e-125">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7829e-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7829e-126">0x80041008</span></span> | <span data-ttu-id="7829e-127">Bir veya daha fazla parametre geçerli değil veya yanlış bir birleşimi bayrakları ve parametreleri belirtildi.</span><span class="sxs-lookup"><span data-stu-id="7829e-127">One or more parameters are not valid, or an incorrect combination of flags and parameters was specified.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="7829e-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="7829e-128">0x80041006</span></span> | <span data-ttu-id="7829e-129">İşlemi tamamlamak yeterli bellek yok.</span><span class="sxs-lookup"><span data-stu-id="7829e-129">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="7829e-130">0</span><span class="sxs-lookup"><span data-stu-id="7829e-130">0</span></span> | <span data-ttu-id="7829e-131">İşlev çağrısı başarılı oldu.</span><span class="sxs-lookup"><span data-stu-id="7829e-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="7829e-132">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="7829e-132">Remarks</span></span>

<span data-ttu-id="7829e-133">Bu işlev bir çağrı sarılır [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="7829e-133">This function wraps a call to the [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) method.</span></span>

<span data-ttu-id="7829e-134">Adlandırılmış döndürülen bayrakları ve parametre birleşimi tarafından denetlenir.</span><span class="sxs-lookup"><span data-stu-id="7829e-134">The named returned are controlled by a combination of flags and parameters.</span></span> <span data-ttu-id="7829e-135">Örneğin, işlevi, tüm özelliklerin adları veya yalnızca anahtar özellikler adları döndürebilir.</span><span class="sxs-lookup"><span data-stu-id="7829e-135">For example, the function can return the names of all properties or only the names of the key properties.</span></span>  <span data-ttu-id="7829e-136">Birincil filtre belirtilen `lFlags` parametre ve diğer parametreler, bağlı olarak değişir.</span><span class="sxs-lookup"><span data-stu-id="7829e-136">The primary filter is specified in the `lFlags` parameter, and the other parameters vary depending on it.</span></span>

<span data-ttu-id="7829e-137">Bayrak değeri `lFlags` bit alanları</span><span class="sxs-lookup"><span data-stu-id="7829e-137">The flag values in `lFlags` are bit fields</span></span>

<span data-ttu-id="7829e-138">Olarak geçirilen bayraklar `lEnumFlags` bağımsız değişkeni olan tanımlanan bit alanları *WbemCli.h* üst bilgi dosyası veya tanımlayabilirsiniz bunları sabitleri kodunuzda.</span><span class="sxs-lookup"><span data-stu-id="7829e-138">The flags that can be passed as the `lEnumFlags` argument are bit fields that are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="7829e-139">Herhangi diğer bir grup bayrağı ile her bir gruptan bir bayrak birleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7829e-139">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="7829e-140">Ancak, aynı grup bayrakları birbirini dışlar.</span><span class="sxs-lookup"><span data-stu-id="7829e-140">However, flags from the same group are mutually exclusive.</span></span> 

| <span data-ttu-id="7829e-141">Grup 1 bayrakları</span><span class="sxs-lookup"><span data-stu-id="7829e-141">Group 1 flags</span></span> |<span data-ttu-id="7829e-142">Değer</span><span class="sxs-lookup"><span data-stu-id="7829e-142">Value</span></span>  |<span data-ttu-id="7829e-143">Açıklama</span><span class="sxs-lookup"><span data-stu-id="7829e-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | <span data-ttu-id="7829e-144">0</span><span class="sxs-lookup"><span data-stu-id="7829e-144">0</span></span> | <span data-ttu-id="7829e-145">Tüm özellik adlarını döndürür.</span><span class="sxs-lookup"><span data-stu-id="7829e-145">Return all property names.</span></span> <span data-ttu-id="7829e-146">`strQualifierName` ve `pQualifierVal` kullanılmadı.</span><span class="sxs-lookup"><span data-stu-id="7829e-146">`strQualifierName` and `pQualifierVal` are unused.</span></span> |
| `WBEM_FLAG_ONLY_IF_TRUE` | <span data-ttu-id="7829e-147">1.</span><span class="sxs-lookup"><span data-stu-id="7829e-147">1</span></span> | <span data-ttu-id="7829e-148">Tarafından belirtilen adının niteleyicisi olan özellikler yalnızca dönüş `strQualifierName` parametresi.</span><span class="sxs-lookup"><span data-stu-id="7829e-148">Return only properties that have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="7829e-149">Bu bayrak kullanılırsa belirtmeniz gerekir `strQualifierName`.</span><span class="sxs-lookup"><span data-stu-id="7829e-149">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_FALSE` | <span data-ttu-id="7829e-150">2</span><span class="sxs-lookup"><span data-stu-id="7829e-150">2</span></span> |  <span data-ttu-id="7829e-151">Tarafından belirtilen adının niteleyicisi olmayan özellikler yalnızca dönüş `strQualifierName` parametresi.</span><span class="sxs-lookup"><span data-stu-id="7829e-151">Return only properties that do not have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="7829e-152">Bu bayrak kullanılırsa belirtmeniz gerekir `strQualifierName`.</span><span class="sxs-lookup"><span data-stu-id="7829e-152">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | <span data-ttu-id="7829e-153">3</span><span class="sxs-lookup"><span data-stu-id="7829e-153">3</span></span> | <span data-ttu-id="7829e-154">Yalnızca bir niteleyici tarafından belirtilen adı taşıyan özellikler dönüş `wszQualifierName` parametre ve bir değer tarafından belirtilen aynı de `pQualifierVal` yapısı.</span><span class="sxs-lookup"><span data-stu-id="7829e-154">Return only properties that have a qualifier of the name specified by the `wszQualifierName` parameter and also have a value identical to that specified by the `pQualifierVal` structure.</span></span> <span data-ttu-id="7829e-155">Bu bayrak kullanılırsa, her ikisini de belirtmelisiniz bir `wszQualifierName` ve `pQualifierValue`.</span><span class="sxs-lookup"><span data-stu-id="7829e-155">If this flag is used, you must specify both a `wszQualifierName` and a `pQualifierValue`.</span></span> |

| <span data-ttu-id="7829e-156">Grup 2 bayrakları</span><span class="sxs-lookup"><span data-stu-id="7829e-156">Group 2 flags</span></span> |<span data-ttu-id="7829e-157">Değer</span><span class="sxs-lookup"><span data-stu-id="7829e-157">Value</span></span>  |<span data-ttu-id="7829e-158">Açıklama</span><span class="sxs-lookup"><span data-stu-id="7829e-158">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="7829e-159">0x4</span><span class="sxs-lookup"><span data-stu-id="7829e-159">0x4</span></span> | <span data-ttu-id="7829e-160">Yalnızca anahtarları tanımlayan özellik adlarını döndürür.</span><span class="sxs-lookup"><span data-stu-id="7829e-160">Return only the names of properties that define the keys.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="7829e-161">0x8</span><span class="sxs-lookup"><span data-stu-id="7829e-161">0x8</span></span> | <span data-ttu-id="7829e-162">Nesne başvuruları olan dönüş yalnızca özellik adları.</span><span class="sxs-lookup"><span data-stu-id="7829e-162">Return only property names that are object references.</span></span> |

| <span data-ttu-id="7829e-163">Grup 3 bayrakları</span><span class="sxs-lookup"><span data-stu-id="7829e-163">Group 3 flags</span></span> |<span data-ttu-id="7829e-164">Değer</span><span class="sxs-lookup"><span data-stu-id="7829e-164">Value</span></span>  |<span data-ttu-id="7829e-165">Açıklama</span><span class="sxs-lookup"><span data-stu-id="7829e-165">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="7829e-166">0x10</span><span class="sxs-lookup"><span data-stu-id="7829e-166">0x10</span></span> | <span data-ttu-id="7829e-167">En çok türetilen sınıfa ait özellik adlarını döndürür.</span><span class="sxs-lookup"><span data-stu-id="7829e-167">Return only property names that belong to the most derived class.</span></span> <span data-ttu-id="7829e-168">Özellikleri, üst sınıflardan hariç tutun.</span><span class="sxs-lookup"><span data-stu-id="7829e-168">Exclude properties from the parent classes.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="7829e-169">0x20</span><span class="sxs-lookup"><span data-stu-id="7829e-169">0x20</span></span> | <span data-ttu-id="7829e-170">Ana sınıfa ait özellik adlarını döndürür.</span><span class="sxs-lookup"><span data-stu-id="7829e-170">Return only property names that belong to the parent classes.</span></span> |
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="7829e-171">0x30</span><span class="sxs-lookup"><span data-stu-id="7829e-171">0x30</span></span> | <span data-ttu-id="7829e-172">Yalnızca Sistem özellikleri adlarını döndürür.</span><span class="sxs-lookup"><span data-stu-id="7829e-172">Return only the names of system properties.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="7829e-173">0x40</span><span class="sxs-lookup"><span data-stu-id="7829e-173">0x40</span></span> | <span data-ttu-id="7829e-174">Yalnızca sistem dışı özellik adlarını döndürür.</span><span class="sxs-lookup"><span data-stu-id="7829e-174">Return only the names of non-system properties.</span></span> |

<span data-ttu-id="7829e-175">İşlev her zaman yeni bir ayırır `SAFEARRAY` döndürürse `WBEM_S_NO_ERROR`, ve `pstrNames` her zaman için işaret edecek şekilde ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="7829e-175">The function always allocates a new `SAFEARRAY` if it returns `WBEM_S_NO_ERROR`, and `pstrNames` is always set to point to it.</span></span> <span data-ttu-id="7829e-176">Döndürülen dizi hiçbir özellik belirtilen filtrelerle eşleşen 0 öğeleri olabilir.</span><span class="sxs-lookup"><span data-stu-id="7829e-176">The returned array can have 0 elements if no properties match the specified filters.</span></span> <span data-ttu-id="7829e-177">İşlev dışında bir değer döndürürse `WBM_S_NO_ERROR`, yeni bir `SAFEARRAY` yapısı alınmadı.</span><span class="sxs-lookup"><span data-stu-id="7829e-177">If the function returns an value other than `WBM_S_NO_ERROR`, a new `SAFEARRAY` structure is not returned.</span></span>
 
## <a name="requirements"></a><span data-ttu-id="7829e-178">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="7829e-178">Requirements</span></span>  
 <span data-ttu-id="7829e-179">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7829e-179">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7829e-180">**Üst bilgi:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7829e-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="7829e-181">**.NET framework sürümleri:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7829e-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7829e-182">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="7829e-182">See also</span></span>

- [<span data-ttu-id="7829e-183">WMI ve performans sayaçları (yönetilmeyen API Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="7829e-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
