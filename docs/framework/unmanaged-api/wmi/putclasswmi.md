---
title: PutClassWmi işlevi (yönetilmeyen API Başvurusu)
description: PutClassWmi işlevi, yeni bir sınıf oluşturur veya mevcut olanı güncelleştirir.
ms.date: 11/06/2017
api_name:
- PutClassWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutClassWmi
helpviewer_keywords:
- PutClassWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f9d537f7713233d363f7d408b1cef0485d99d981
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000174"
---
# <a name="putclasswmi-function"></a><span data-ttu-id="979b7-103">PutClassWmi işlevi</span><span class="sxs-lookup"><span data-stu-id="979b7-103">PutClassWmi function</span></span>

<span data-ttu-id="979b7-104">Yeni bir sınıf oluşturur veya mevcut olanı güncelleştirir.</span><span class="sxs-lookup"><span data-stu-id="979b7-104">Creates a new class or updates an existing one.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="979b7-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="979b7-105">Syntax</span></span>

```cpp
HRESULT PutClassWmi (
   [in] IWbemClassObject*    pObject,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a><span data-ttu-id="979b7-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="979b7-106">Parameters</span></span>

`pObject`\
<span data-ttu-id="979b7-107">[in] Geçerli bir sınıf tanımı için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="979b7-107">[in] A pointer to a valid class definition.</span></span> <span data-ttu-id="979b7-108">Tüm gerekli özellik değerleri doğru şekilde yeniden başlatılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="979b7-108">It must be correctly initialized with all the required property values.</span></span>

`lFlags`\
<span data-ttu-id="979b7-109">[in] Bu işlevin davranışını etkileyen bayrakların birleşimi.</span><span class="sxs-lookup"><span data-stu-id="979b7-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="979b7-110">Aşağıdaki değerleri tanımlanan *WbemCli.h* üst bilgi dosyası veya tanımlayabilirsiniz bunları sabitleri kodunuzda:</span><span class="sxs-lookup"><span data-stu-id="979b7-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="979b7-111">Sabit</span><span class="sxs-lookup"><span data-stu-id="979b7-111">Constant</span></span>  |<span data-ttu-id="979b7-112">Değer</span><span class="sxs-lookup"><span data-stu-id="979b7-112">Value</span></span>  |<span data-ttu-id="979b7-113">Açıklama</span><span class="sxs-lookup"><span data-stu-id="979b7-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="979b7-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="979b7-114">0x20000</span></span> | <span data-ttu-id="979b7-115">Tüm niteleyicileri ile değiştirilmiş özellik kümesi, WMI depolamaz</span><span class="sxs-lookup"><span data-stu-id="979b7-115">If set, WMI does not store any qualifiers with the amended flavor.</span></span> <br> <span data-ttu-id="979b7-116">Aksi durumda kümesi, bu nesne yerelleştirilmez ve bu örneği ile depolanan tüm niteleyicileri varsayılır.</span><span class="sxs-lookup"><span data-stu-id="979b7-116">If not set, it is assumed that this object is not localized, and all qualifiers are stored with this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="979b7-117">0</span><span class="sxs-lookup"><span data-stu-id="979b7-117">0</span></span> | <span data-ttu-id="979b7-118">Sınıfı, yok, veya zaten varsa üzerine oluşturun.</span><span class="sxs-lookup"><span data-stu-id="979b7-118">Create the class if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="979b7-119">1.</span><span class="sxs-lookup"><span data-stu-id="979b7-119">1</span></span> | <span data-ttu-id="979b7-120">Sınıf güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="979b7-120">Update the class.</span></span> <span data-ttu-id="979b7-121">Sınıf araması başarılı olması mevcut olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="979b7-121">The class must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="979b7-122">2</span><span class="sxs-lookup"><span data-stu-id="979b7-122">2</span></span> | <span data-ttu-id="979b7-123">Bir sınıf oluşturun.</span><span class="sxs-lookup"><span data-stu-id="979b7-123">Create the class.</span></span> <span data-ttu-id="979b7-124">Sınıf zaten varsa başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="979b7-124">The call fails if the class already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="979b7-125">0x10</span><span class="sxs-lookup"><span data-stu-id="979b7-125">0x10</span></span> | <span data-ttu-id="979b7-126">Bayrağı yarı zaman uyumsuz bir çağrı neden olur.</span><span class="sxs-lookup"><span data-stu-id="979b7-126">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_OWNER_UPDATE` | <span data-ttu-id="979b7-127">0x10000</span><span class="sxs-lookup"><span data-stu-id="979b7-127">0x10000</span></span> | <span data-ttu-id="979b7-128">Anında iletme sağlayıcıları, bu bayrak belirtmelisiniz, çağrılırken `PutClassWmi` Bu sınıf değiştirildiğini göstermek için.</span><span class="sxs-lookup"><span data-stu-id="979b7-128">Push providers must specify this flag when calling `PutClassWmi` to indicate that this class has changed.</span></span> |
| `WBEM_FLAG_UPDATE_COMPATIBLE` | <span data-ttu-id="979b7-129">0</span><span class="sxs-lookup"><span data-stu-id="979b7-129">0</span></span> | <span data-ttu-id="979b7-130">Türetilmiş sınıfları ve bu sınıf örneği varsa güncelleştirilecek bir sınıf sağlar.</span><span class="sxs-lookup"><span data-stu-id="979b7-130">Allows a class to be updated if there are no derived classes and no instances of that class.</span></span> <span data-ttu-id="979b7-131">Değişiklik yalnızca açıklama niteleyicisi gibi önemli niteleyicileri, ayrıca tüm durumlarda güncelleştirmeler sağlar.</span><span class="sxs-lookup"><span data-stu-id="979b7-131">It also allows updates in all cases if the change is just to unimportant qualifiers, such as the Description qualifier.</span></span> <span data-ttu-id="979b7-132">Sınıf örnekleri sahip veya bu değişiklikler için önemli niteleyicileri güncelleştirme başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="979b7-132">If the class has instances or changes are to important qualifiers, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_SAFE_MODE` | <span data-ttu-id="979b7-133">0x20</span><span class="sxs-lookup"><span data-stu-id="979b7-133">0x20</span></span> | <span data-ttu-id="979b7-134">Olsa bile alt sınıfları değişikliği alt sınıflarla çakışmaları neden olmaz sürece sınıflarının güncelleştirmelerine olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="979b7-134">Allows updates of classes even if there are child classes as long as the change does not cause any conflicts with child classes.</span></span> <span data-ttu-id="979b7-135">Örneğin, bu bayrak, herhangi bir alt sınıfı önceden olarak belirtilmeyen temel sınıfa eklenecek yeni bir özellik sağlar.</span><span class="sxs-lookup"><span data-stu-id="979b7-135">For example, this flag allows a new property to be added to the base class that was not previously mentioned in any of the child classes.</span></span> <span data-ttu-id="979b7-136">Sınıf örneği varsa, güncelleştirmeyi başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="979b7-136">If the class has instances, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_FORCE_MODE` | <span data-ttu-id="979b7-137">0x40</span><span class="sxs-lookup"><span data-stu-id="979b7-137">0x40</span></span> | <span data-ttu-id="979b7-138">Çakışan alt sınıflar bulunduğunda sınıflarının güncelleştirmeleri zorlar.</span><span class="sxs-lookup"><span data-stu-id="979b7-138">forces updates of classes when conflicting child classes exist.</span></span> <span data-ttu-id="979b7-139">Örneğin, bu bayrak güncelleştirme sınıf niteleyici bir alt sınıfında tanımlanır ve aynı niteleyicisi eklemek temel sınıf çalışırsa var olan bir çakışan zorlar.</span><span class="sxs-lookup"><span data-stu-id="979b7-139">For example, this flag forces an update if a class qualifier is defined in a child class, and the base class tries to add the same qualifier which conflicts with the existing one.</span></span> <span data-ttu-id="979b7-140">Zorlama modunda, çakışan alt sınıf niteleyicisi silerek TIS çakışma çözülür.</span><span class="sxs-lookup"><span data-stu-id="979b7-140">In force mode, tis conflict is resolved by deleting the conflicting qualifier in the child class.</span></span> |

`pCtx`\
<span data-ttu-id="979b7-141">[in] Genellikle, bu değer, `null`.</span><span class="sxs-lookup"><span data-stu-id="979b7-141">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="979b7-142">Aksi takdirde, bir işaretçi olduğu bir [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) istenen sınıfları sağlayan sağlayıcı tarafından kullanılan bir örnek.</span><span class="sxs-lookup"><span data-stu-id="979b7-142">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppCallResult`\
<span data-ttu-id="979b7-143">[out] Varsa `null`, bu parametre kullanılmaz.</span><span class="sxs-lookup"><span data-stu-id="979b7-143">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="979b7-144">Varsa `lFlags` içeren `WBEM_FLAG_RETURN_IMMEDIATELY`, işlev ile hemen döndürür. `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="979b7-144">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="979b7-145">`ppCallResult` Parametre bir işaretçi yeni bir alan [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) nesne.</span><span class="sxs-lookup"><span data-stu-id="979b7-145">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="979b7-146">Dönüş değeri</span><span class="sxs-lookup"><span data-stu-id="979b7-146">Return value</span></span>

<span data-ttu-id="979b7-147">Bu işlev tarafından döndürülen aşağıdaki değerleri tanımlanan *WbemCli.h* üst bilgi dosyası veya tanımlayabilirsiniz bunları sabitleri kodunuzda:</span><span class="sxs-lookup"><span data-stu-id="979b7-147">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="979b7-148">Sabit</span><span class="sxs-lookup"><span data-stu-id="979b7-148">Constant</span></span>  |<span data-ttu-id="979b7-149">Değer</span><span class="sxs-lookup"><span data-stu-id="979b7-149">Value</span></span>  |<span data-ttu-id="979b7-150">Açıklama</span><span class="sxs-lookup"><span data-stu-id="979b7-150">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="979b7-151">0x80041003</span><span class="sxs-lookup"><span data-stu-id="979b7-151">0x80041003</span></span> | <span data-ttu-id="979b7-152">Kullanıcı oluşturma veya sınıflar değiştirme izni yok.</span><span class="sxs-lookup"><span data-stu-id="979b7-152">The user does not have permission to create or modify classes.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="979b7-153">0x80041001</span><span class="sxs-lookup"><span data-stu-id="979b7-153">0x80041001</span></span> | <span data-ttu-id="979b7-154">Belirtilmeyen bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="979b7-154">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="979b7-155">0x80041010</span><span class="sxs-lookup"><span data-stu-id="979b7-155">0x80041010</span></span> | <span data-ttu-id="979b7-156">Belirtilen sınıf geçerli değil.</span><span class="sxs-lookup"><span data-stu-id="979b7-156">The specified class is not valid.</span></span> <span data-ttu-id="979b7-157">Genellikle, gösterir `pObject` örneği nesnesini belirtir.</span><span class="sxs-lookup"><span data-stu-id="979b7-157">Typically, this indicates that `pObject` specifies an instance object.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="979b7-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="979b7-158">0x80041008</span></span> | <span data-ttu-id="979b7-159">Bir parametre geçerli değil.</span><span class="sxs-lookup"><span data-stu-id="979b7-159">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID OPERATION` | <span data-ttu-id="979b7-160">0x80041016</span><span class="sxs-lookup"><span data-stu-id="979b7-160">0x80041016</span></span> | <span data-ttu-id="979b7-161">Belirtilen sınıf adı geçerli değil.</span><span class="sxs-lookup"><span data-stu-id="979b7-161">The specified class name is not valid.</span></span> |
| `WBEM_E_CLASS_HAS_CHILDREN` | <span data-ttu-id="979b7-162">0x80041025</span><span class="sxs-lookup"><span data-stu-id="979b7-162">0x80041025</span></span> | <span data-ttu-id="979b7-163">Bir alt kılacak bir değişiklik yapmak için girişimde bulunuldu.</span><span class="sxs-lookup"><span data-stu-id="979b7-163">An attempt was made to make a change that would invalidate a subclass.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="979b7-164">0x80041019</span><span class="sxs-lookup"><span data-stu-id="979b7-164">0x80041019</span></span> | <span data-ttu-id="979b7-165">`WBEM_FLAG_CREATE_ONLY` Bayrağı belirtildi, ancak sınıf zaten mevcut.</span><span class="sxs-lookup"><span data-stu-id="979b7-165">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the class already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="979b7-166">0x80041002</span><span class="sxs-lookup"><span data-stu-id="979b7-166">0x80041002</span></span> | <span data-ttu-id="979b7-167">`WBEM_FLAG_UPDATE_ONLY` Belirtilen `lFlags`, ve sınıfı bulunamadı.</span><span class="sxs-lookup"><span data-stu-id="979b7-167">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, and the class was not found.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="979b7-168">0x80041020</span><span class="sxs-lookup"><span data-stu-id="979b7-168">0x80041020</span></span> | <span data-ttu-id="979b7-169">Tüm sınıflar için gerekli özellikleri ayarlanmadı.</span><span class="sxs-lookup"><span data-stu-id="979b7-169">The required properties for classes have not all been set.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="979b7-170">0x80041006</span><span class="sxs-lookup"><span data-stu-id="979b7-170">0x80041006</span></span> | <span data-ttu-id="979b7-171">İşlemi tamamlamak yeterli bellek yok.</span><span class="sxs-lookup"><span data-stu-id="979b7-171">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="979b7-172">0x80041033</span><span class="sxs-lookup"><span data-stu-id="979b7-172">0x80041033</span></span> | <span data-ttu-id="979b7-173">WMI, büyük olasılıkla durdu ve yeniden başlatılıyor.</span><span class="sxs-lookup"><span data-stu-id="979b7-173">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="979b7-174">Çağrı [ConnectServerWmi](connectserverwmi.md) yeniden.</span><span class="sxs-lookup"><span data-stu-id="979b7-174">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="979b7-175">0x80041015</span><span class="sxs-lookup"><span data-stu-id="979b7-175">0x80041015</span></span> | <span data-ttu-id="979b7-176">Geçerli işlem WMI arasındaki uzak yordam çağrısı (RPC) bağlantı başarısız oldu.</span><span class="sxs-lookup"><span data-stu-id="979b7-176">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="979b7-177">0</span><span class="sxs-lookup"><span data-stu-id="979b7-177">0</span></span> | <span data-ttu-id="979b7-178">İşlev çağrısı başarılı oldu.</span><span class="sxs-lookup"><span data-stu-id="979b7-178">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="979b7-179">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="979b7-179">Remarks</span></span>

<span data-ttu-id="979b7-180">Bu işlev bir çağrı sarılır [IWbemServices::PutClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="979b7-180">This function wraps a call to the [IWbemServices::PutClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) method.</span></span>

<span data-ttu-id="979b7-181">Kullanıcı sınıfları ile başlayamaz veya alt çizgi karakteriyle bitemez adları oluşturamazsınız.</span><span class="sxs-lookup"><span data-stu-id="979b7-181">The user may not create classes with names that begin or end with an underscore character.</span></span>

<span data-ttu-id="979b7-182">İşlev çağrısı başarısız olursa, ek hata bilgileri çağırarak elde edebileceğiniz [Geterrorınfo](geterrorinfo.md) işlevi.</span><span class="sxs-lookup"><span data-stu-id="979b7-182">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="979b7-183">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="979b7-183">Requirements</span></span>

<span data-ttu-id="979b7-184">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="979b7-184">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="979b7-185">**Üst bilgi:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="979b7-185">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="979b7-186">**.NET framework sürümleri:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="979b7-186">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="979b7-187">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="979b7-187">See also</span></span>

- [<span data-ttu-id="979b7-188">WMI ve performans sayaçları (yönetilmeyen API Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="979b7-188">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)