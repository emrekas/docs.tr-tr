---
title: ICorDebugEval2::CallParameterizedFunction Yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CallParameterizedFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CallParameterizedFunction
helpviewer_keywords:
- ICorDebugEval2::CallParameterizedFunction method [.NET Framework debugging]
- CallParameterizedFunction method [.NET Framework debugging]
ms.assetid: 72f54a45-dbe6-4bb4-8c99-e879a27368e5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cba4eb2b76d7057a5ed66a35342a79615cb8539f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487736"
---
# <a name="icordebugeval2callparameterizedfunction-method"></a><span data-ttu-id="48ed8-102">ICorDebugEval2::CallParameterizedFunction Yöntemi</span><span class="sxs-lookup"><span data-stu-id="48ed8-102">ICorDebugEval2::CallParameterizedFunction Method</span></span>
<span data-ttu-id="48ed8-103">Bir çağrı, Oluşturucusu götüren bir sınıf içinde iç içe belirtilen ICorDebugFunction ayarlar <xref:System.Type> parametreleri veya can'ın kendisi <xref:System.Type> parametreleri.</span><span class="sxs-lookup"><span data-stu-id="48ed8-103">Sets up a call to the specified ICorDebugFunction, which can be nested inside a class whose constructor takes <xref:System.Type> parameters, or can itself take <xref:System.Type> parameters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48ed8-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="48ed8-104">Syntax</span></span>  
  
```  
HRESULT CallParameterizedFunction (  
    [in] ICorDebugFunction     *pFunction,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48ed8-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="48ed8-105">Parameters</span></span>  
 `pFunction`  
 <span data-ttu-id="48ed8-106">[in] Bir işaretçi bir `ICorDebugFunction` çağrılacak işlev temsil eden nesne.</span><span class="sxs-lookup"><span data-stu-id="48ed8-106">[in] A pointer to an `ICorDebugFunction` object that represents the function to be called.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="48ed8-107">[in] Alan işlev bağımsız değişken sayısı.</span><span class="sxs-lookup"><span data-stu-id="48ed8-107">[in] The number of arguments that the function takes.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="48ed8-108">[in] Bir dizi işaretçileri, her biri bir işlev bağımsız değişkeni temsil eden bir Icordebugtype nesneye işaret eder.</span><span class="sxs-lookup"><span data-stu-id="48ed8-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a function argument.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="48ed8-109">[in] Değerlerin sayısını işleve geçirildi.</span><span class="sxs-lookup"><span data-stu-id="48ed8-109">[in] The number of values passed in the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="48ed8-110">[in] Her biri bir değeri temsil eden bir Icordebugvalue nesneye işaret eden bir işaretçiler dizisi, bir işlev bağımsız değişkeni geçirildi.</span><span class="sxs-lookup"><span data-stu-id="48ed8-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents a value passed in a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48ed8-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="48ed8-111">Remarks</span></span>  
 <span data-ttu-id="48ed8-112">`CallParameterizedFunction` benzer [Icordebugeval::CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md) işlevi tür parametreleri ile bir sınıf içinde olabilir dışında kendi tür parametreleri veya her ikisi de alabilir.</span><span class="sxs-lookup"><span data-stu-id="48ed8-112">`CallParameterizedFunction` is like [ICorDebugEval::CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md) except that the function may be inside a class with type parameters, may itself take type parameters, or both.</span></span> <span data-ttu-id="48ed8-113">Tür bağımsız değişkeni, ilk sınıf ve işlev için verilmelidir.</span><span class="sxs-lookup"><span data-stu-id="48ed8-113">The type arguments should be given first for the class, and then for the function.</span></span>  
  
 <span data-ttu-id="48ed8-114">İşlev, farklı uygulama etki alanında ise, bir geçiş meydana gelir.</span><span class="sxs-lookup"><span data-stu-id="48ed8-114">If the function is in a different application domain, a transition will occur.</span></span> <span data-ttu-id="48ed8-115">Ancak, tüm türü ve değeri bağımsız değişkenleri hedef uygulama etki alanında olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="48ed8-115">However, all type and value arguments must be in the target application domain.</span></span>  
  
 <span data-ttu-id="48ed8-116">İşlev değerlendirmesi yalnızca sınırlı sayıda senaryoda gerçekleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="48ed8-116">Function evaluation can be performed only in limited scenarios.</span></span> <span data-ttu-id="48ed8-117">Varsa `CallParameterizedFunction` veya `ICorDebugEval::CallFunction` başarısız olursa, döndürülen HRESULT hata olası en genel nedenlerinden gösterecektir.</span><span class="sxs-lookup"><span data-stu-id="48ed8-117">If `CallParameterizedFunction` or `ICorDebugEval::CallFunction` fails, the returned HRESULT will indicate the most general possible reason for failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48ed8-118">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="48ed8-118">Requirements</span></span>  
 <span data-ttu-id="48ed8-119">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48ed8-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48ed8-120">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48ed8-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48ed8-121">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48ed8-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48ed8-122">**.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48ed8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
