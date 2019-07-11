---
title: DeleteMethod işlevi (yönetilmeyen API Başvurusu)
description: DeleteMethod işlevi, belirtilen yöntem bir CIM sınıfı tanımını siler.
ms.date: 11/06/2017
api_name:
- DeleteMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- DeleteMethod
helpviewer_keywords:
- DeleteMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 291d5d0461da8d130d41f9a0eca67ea3be42b4bc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746815"
---
# <a name="deletemethod-function"></a><span data-ttu-id="8b6e2-103">DeleteMethod işlevi</span><span class="sxs-lookup"><span data-stu-id="8b6e2-103">DeleteMethod function</span></span>
<span data-ttu-id="8b6e2-104">Belirtilen yöntemde bir CIM sınıfı tanımını siler.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-104">Deletes the specified method from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="8b6e2-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="8b6e2-105">Syntax</span></span>  
  
```cpp  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="8b6e2-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="8b6e2-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="8b6e2-107">[in] Bu parametre kullanılmaz.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="8b6e2-108">[in] Bir işaretçi bir [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) örneği.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="8b6e2-109">[in] Sınıf tablodan kaldırmak için yöntemin adı.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-109">[in] The name of the method to remove from the class table.</span></span> <span data-ttu-id="8b6e2-110">`wszName` Geçerli bir işaretçi olmalıdır `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="8b6e2-111">Dönüş değeri</span><span class="sxs-lookup"><span data-stu-id="8b6e2-111">Return value</span></span>

<span data-ttu-id="8b6e2-112">Bu işlev tarafından döndürülen aşağıdaki değerleri tanımlanan *WbemCli.h* üst bilgi dosyası veya tanımlayabilirsiniz bunları sabitleri kodunuzda:</span><span class="sxs-lookup"><span data-stu-id="8b6e2-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="8b6e2-113">Sabit</span><span class="sxs-lookup"><span data-stu-id="8b6e2-113">Constant</span></span>  |<span data-ttu-id="8b6e2-114">Değer</span><span class="sxs-lookup"><span data-stu-id="8b6e2-114">Value</span></span>  |<span data-ttu-id="8b6e2-115">Açıklama</span><span class="sxs-lookup"><span data-stu-id="8b6e2-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="8b6e2-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="8b6e2-116">0x80041002</span></span> | <span data-ttu-id="8b6e2-117">Belirtilen yöntem yok.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-117">The specified method does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="8b6e2-118">0x80041006</span><span class="sxs-lookup"><span data-stu-id="8b6e2-118">0x80041006</span></span> | <span data-ttu-id="8b6e2-119">İşlemi tamamlamak için yeterli bellek yok.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-119">There is not enough memory to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="8b6e2-120">0</span><span class="sxs-lookup"><span data-stu-id="8b6e2-120">0</span></span> | <span data-ttu-id="8b6e2-121">İşlev çağrısı başarılı oldu.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-121">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="8b6e2-122">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="8b6e2-122">Remarks</span></span>

<span data-ttu-id="8b6e2-123">Bu işlev bir çağrı sarılır [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-123">This function wraps a call to the [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) method.</span></span>

<span data-ttu-id="8b6e2-124">Yöntem silme için desteklenmediğinden [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) CIM örneklerine işaret eden işaretçilerin.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-124">Method deletion is not supported for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

## <a name="requirements"></a><span data-ttu-id="8b6e2-125">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="8b6e2-125">Requirements</span></span>  
 <span data-ttu-id="8b6e2-126">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b6e2-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b6e2-127">**Üst bilgi:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="8b6e2-127">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="8b6e2-128">**.NET framework sürümleri:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8b6e2-128">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b6e2-129">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="8b6e2-129">See also</span></span>

- [<span data-ttu-id="8b6e2-130">WMI ve performans sayaçları (yönetilmeyen API Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="8b6e2-130">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
