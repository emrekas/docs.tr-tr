---
title: ExecNotificationQueryWmi işlevi (yönetilmeyen API Başvurusu)
description: ExecNotificationQueryWmi işlevi olaylarını almak için bir sorgu yürütür.
ms.date: 11/06/2017
api_name:
- ExecNotificationQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecNotificationQueryWmi
helpviewer_keywords:
- ExecNotificationQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9cac00ff96d0c7007bdd6135282c3f767217385e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352886"
---
# <a name="execnotificationquerywmi-function"></a><span data-ttu-id="6c6a1-103">ExecNotificationQueryWmi işlevi</span><span class="sxs-lookup"><span data-stu-id="6c6a1-103">ExecNotificationQueryWmi function</span></span>

<span data-ttu-id="6c6a1-104">Olayları almak için bir sorgu yürütür.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-104">Executes a query to receive events.</span></span> <span data-ttu-id="6c6a1-105">Çağrı hemen döndürür ve geldikçe çağırana döndürülen Numaralandırıcı olaylar için yoklama.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-105">The call returns immediately, and the caller can poll the returned enumerator for events as they arrive.</span></span> <span data-ttu-id="6c6a1-106">Döndürülen Numaralandırıcı serbest sorguyu iptal eder.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-106">Releasing the returned enumerator cancels the query.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="6c6a1-107">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="6c6a1-107">Syntax</span></span>

```cpp
HRESULT ExecNotificationQueryWmi (
   [in] BSTR                    strQueryLanguage,
   [in] BSTR                    strQuery,
   [in] long                    lFlags,
   [in] IWbemContext*           pCtx,
   [out] IEnumWbemClassObject** ppEnum,
   [in] DWORD                   authLevel,
   [in] DWORD                   impLevel,
   [in] IWbemServices*          pCurrentNamespace,
   [in] BSTR                    strUser,
   [in] BSTR                    strPassword,
   [in] BSTR                    strAuthority
);
```

## <a name="parameters"></a><span data-ttu-id="6c6a1-108">Parametreler</span><span class="sxs-lookup"><span data-stu-id="6c6a1-108">Parameters</span></span>

`strQueryLanguage`\
<span data-ttu-id="6c6a1-109">[in] Windows Management tarafından desteklenen geçerli bir sorgu dili olan bir dize.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-109">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="6c6a1-110">WMI Sorgu Dili kısaltması "WQL" olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-110">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`\
<span data-ttu-id="6c6a1-111">[in] Sorgu metni.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-111">[in] The text of the query.</span></span> <span data-ttu-id="6c6a1-112">Bu parametre olamaz `null`.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-112">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="6c6a1-113">[in] Bu işlevin davranışını etkileyen aşağıdaki iki bayrakların birleşimi.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-113">[in] A combination of the following two flags that affect the behavior of this function.</span></span> <span data-ttu-id="6c6a1-114">Bu değerleri tanımlanan *WbemCli.h* üst bilgi dosyası veya tanımlayabilirsiniz bunları sabitleri kodunuzda.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-114">These values are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>

| <span data-ttu-id="6c6a1-115">Sabit</span><span class="sxs-lookup"><span data-stu-id="6c6a1-115">Constant</span></span> | <span data-ttu-id="6c6a1-116">Değer</span><span class="sxs-lookup"><span data-stu-id="6c6a1-116">Value</span></span>  | <span data-ttu-id="6c6a1-117">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6c6a1-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="6c6a1-118">0x10</span><span class="sxs-lookup"><span data-stu-id="6c6a1-118">0x10</span></span> | <span data-ttu-id="6c6a1-119">Bayrağı yarı zaman uyumsuz bir çağrı neden olur.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-119">The flag causes a semisynchronous call.</span></span> <span data-ttu-id="6c6a1-120">Bu bayrak ayarlanmazsa, çağrı başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-120">If this flag is not set, the call fails.</span></span> <span data-ttu-id="6c6a1-121">Olayları sürekli olarak alınan kullanıcı döndürülen Numaralandırıcı yoklaması gerekir yani olmasıdır.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-121">This is because events are received continuously, which means the user must poll the returned enumerator.</span></span> <span data-ttu-id="6c6a1-122">Bu çağrı süresiz olarak engelleme, mümkün kılar.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-122">Blocking this call indefinitely makes that impossible.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="6c6a1-123">0x20</span><span class="sxs-lookup"><span data-stu-id="6c6a1-123">0x20</span></span> | <span data-ttu-id="6c6a1-124">İşlev yalnızca iletme bir numaralandırıcı döndürür.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="6c6a1-125">Genellikle, yalnızca iletme numaralandırıcılar daha hızlıdır ve geleneksel numaralandırıcılar daha az bellek kullanır, ancak çağrısına izin verme [kopya](clone.md).</span><span class="sxs-lookup"><span data-stu-id="6c6a1-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |

`pCtx`\
<span data-ttu-id="6c6a1-126">[in] Genellikle, bu değer, `null`.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-126">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="6c6a1-127">Aksi takdirde, bir işaretçi olduğu bir [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) istenen olaylar sağlayarak sağlayıcı tarafından kullanılan bir örnek.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-127">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested events.</span></span>

`ppEnum`\
<span data-ttu-id="6c6a1-128">[out] Eğer hiç Hata oluşmazsa, işaretçi örnekleri sorgunun sonuç kümesinde almak çağırıcı veren numaralandırıcıyı alır.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-128">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="6c6a1-129">Bkz: [açıklamalar](#remarks) bölümünde daha fazla bilgi için.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-129">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`\
<span data-ttu-id="6c6a1-130">[in] Yetkilendirme düzeyi.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-130">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="6c6a1-131">[in] Kimliğe bürünme düzeyi.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-131">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="6c6a1-132">[in] Bir işaretçi bir [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) geçerli ad alanını temsil eden nesne.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-132">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="6c6a1-133">[in] Kullanıcı adı.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-133">[in] The user name.</span></span> <span data-ttu-id="6c6a1-134">Bkz: [ConnectServerWmi](connectserverwmi.md) işlevi daha fazla bilgi için.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-134">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="6c6a1-135">[in] Parola.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-135">[in] The password.</span></span> <span data-ttu-id="6c6a1-136">Bkz: [ConnectServerWmi](connectserverwmi.md) işlevi daha fazla bilgi için.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="6c6a1-137">[in] Kullanıcı etki alanı adı.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-137">[in] The domain name of the user.</span></span> <span data-ttu-id="6c6a1-138">Bkz: [ConnectServerWmi](connectserverwmi.md) işlevi daha fazla bilgi için.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="6c6a1-139">Dönüş değeri</span><span class="sxs-lookup"><span data-stu-id="6c6a1-139">Return value</span></span>

<span data-ttu-id="6c6a1-140">Bu işlev tarafından döndürülen aşağıdaki değerleri tanımlanan *WbemCli.h* üst bilgi dosyası veya tanımlayabilirsiniz bunları sabitleri kodunuzda:</span><span class="sxs-lookup"><span data-stu-id="6c6a1-140">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="6c6a1-141">Sabit</span><span class="sxs-lookup"><span data-stu-id="6c6a1-141">Constant</span></span>  |<span data-ttu-id="6c6a1-142">Değer</span><span class="sxs-lookup"><span data-stu-id="6c6a1-142">Value</span></span>  |<span data-ttu-id="6c6a1-143">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6c6a1-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="6c6a1-144">0x80041003</span><span class="sxs-lookup"><span data-stu-id="6c6a1-144">0x80041003</span></span> | <span data-ttu-id="6c6a1-145">Kullanıcı, bir veya daha fazla işlev döndürebilir sınıfları görüntüleme izni yok.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-145">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="6c6a1-146">0x80041001</span><span class="sxs-lookup"><span data-stu-id="6c6a1-146">0x80041001</span></span> | <span data-ttu-id="6c6a1-147">Belirtilmeyen bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-147">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="6c6a1-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="6c6a1-148">0x80041008</span></span> | <span data-ttu-id="6c6a1-149">Bir parametre geçerli değil.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-149">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="6c6a1-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="6c6a1-150">0x80041010</span></span> | <span data-ttu-id="6c6a1-151">Sorgu var olmayan bir sınıfı belirtiyor.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-151">The query specifies a class that does not exist.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | <span data-ttu-id="6c6a1-152">0x80042002</span><span class="sxs-lookup"><span data-stu-id="6c6a1-152">0x80042002</span></span> | <span data-ttu-id="6c6a1-153">Çok fazla olay teslimini kesinlik istendi.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-153">Too much precision in delivery of events has been requested.</span></span> <span data-ttu-id="6c6a1-154">Daha büyük bir yoklama toleransı belirtilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-154">A larger polling tolerance must be specified.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | <span data-ttu-id="6c6a1-155">0x80042001</span><span class="sxs-lookup"><span data-stu-id="6c6a1-155">0x80042001</span></span> | <span data-ttu-id="6c6a1-156">Sorgu, Windows Yönetim sunabileceğinden daha fazla bilgi ister.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-156">The query requests more information than Windows Management can provide.</span></span> <span data-ttu-id="6c6a1-157">Bu `HRESULT` isteğinde bir ad alanındaki tüm nesneler yoklamak üzere Olay sorgusu sonuçları döndürülür.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-157">This `HRESULT` is returned when an event query results in a request to poll all objects in a namespace.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="6c6a1-158">0x80041017</span><span class="sxs-lookup"><span data-stu-id="6c6a1-158">0x80041017</span></span> | <span data-ttu-id="6c6a1-159">Sorgu söz dizimi hatası vardı.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-159">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="6c6a1-160">0x80041018</span><span class="sxs-lookup"><span data-stu-id="6c6a1-160">0x80041018</span></span> | <span data-ttu-id="6c6a1-161">İstenen sorgu dili desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-161">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="6c6a1-162">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="6c6a1-162">0x8004106c</span></span> | <span data-ttu-id="6c6a1-163">Sorgu çok daha karmaşıktır.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-163">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="6c6a1-164">0x80041006</span><span class="sxs-lookup"><span data-stu-id="6c6a1-164">0x80041006</span></span> | <span data-ttu-id="6c6a1-165">İşlemi tamamlamak yeterli bellek yok.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-165">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="6c6a1-166">0x80041033</span><span class="sxs-lookup"><span data-stu-id="6c6a1-166">0x80041033</span></span> | <span data-ttu-id="6c6a1-167">WMI, büyük olasılıkla durdu ve yeniden başlatılıyor.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-167">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="6c6a1-168">Çağrı [ConnectServerWmi](connectserverwmi.md) yeniden.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-168">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="6c6a1-169">0x80041015</span><span class="sxs-lookup"><span data-stu-id="6c6a1-169">0x80041015</span></span> | <span data-ttu-id="6c6a1-170">Geçerli işlem WMI arasındaki uzak yordam çağrısı (RPC) bağlantı başarısız oldu.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-170">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_UNPARSABLE_QUERY` | <span data-ttu-id="6c6a1-171">0x80041058</span><span class="sxs-lookup"><span data-stu-id="6c6a1-171">0x80041058</span></span> | <span data-ttu-id="6c6a1-172">Sorgu nelze analyzovat.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-172">The query cannot be parsed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="6c6a1-173">0</span><span class="sxs-lookup"><span data-stu-id="6c6a1-173">0</span></span> | <span data-ttu-id="6c6a1-174">İşlev çağrısı başarılı oldu.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-174">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="6c6a1-175">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="6c6a1-175">Remarks</span></span>

<span data-ttu-id="6c6a1-176">Bu işlev bir çağrı sarılır [IWbemServices::ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-176">This function wraps a call to the [IWbemServices::ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) method.</span></span>

<span data-ttu-id="6c6a1-177">Çağıran düzenli aralıklarla işlev döndürdükten sonra döndürülen geçirir. `ppEnum` nesnesini [sonraki](next.md) meydana gelen olayları kullanılabilir olup olmadığını görmek için işlev.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-177">After the function returns, the caller periodically passes the returned `ppEnum` object to the [Next](next.md) function to see if any events are available.</span></span>

<span data-ttu-id="6c6a1-178">Bununla ilgili sınırlamalar sayısını `AND` ve `OR` WQL sorguları kullanılabilir anahtar sözcükler.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-178">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="6c6a1-179">Çok sayıda karmaşık bir sorguda kullanılan WQL anahtar sözcükleri döndürmek WMI neden olabilecek `WBEM_E_QUOTA_VIOLATION` (veya 0x8004106c) hata kodunu bir `HRESULT` değeri.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-179">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="6c6a1-180">WQL anahtar sözcük sınırını nasıl karmaşık sorgu olduğuna bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-180">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="6c6a1-181">İşlev çağrısı başarısız olursa, ek hata bilgileri çağırarak elde edebileceğiniz [Geterrorınfo](geterrorinfo.md) işlevi.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-181">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="6c6a1-182">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="6c6a1-182">Requirements</span></span>

<span data-ttu-id="6c6a1-183">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c6a1-183">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="6c6a1-184">**Üst bilgi:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="6c6a1-184">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="6c6a1-185">**.NET framework sürümleri:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6c6a1-185">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6c6a1-186">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="6c6a1-186">See also</span></span>

- [<span data-ttu-id="6c6a1-187">WMI ve performans sayaçları (yönetilmeyen API Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="6c6a1-187">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)