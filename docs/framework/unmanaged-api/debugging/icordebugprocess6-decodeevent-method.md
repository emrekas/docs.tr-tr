---
title: ICorDebugProcess6::DecodeEvent Yöntemi
ms.date: 03/30/2017
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a392e236f180771a9b05526a0db569f27f6f7d8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230752"
---
# <a name="icordebugprocess6decodeevent-method"></a><span data-ttu-id="439be-102">ICorDebugProcess6::DecodeEvent Yöntemi</span><span class="sxs-lookup"><span data-stu-id="439be-102">ICorDebugProcess6::DecodeEvent Method</span></span>
<span data-ttu-id="439be-103">Özel olarak hazırlanmış yerel özel durum hata ayıklama olaylarını yükteki kapsüllenmiş yönetilen hata ayıklama olaylarını kodunu çözer.</span><span class="sxs-lookup"><span data-stu-id="439be-103">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="439be-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="439be-104">Syntax</span></span>  
  
```  
HRESULT DecodeEvent(  
        [in, length_is(countBytes), size_is(countBytes)]  const BYTE pRecord[],  
        [in] DWORD countBytes,  
        [in] CorDebugRecordFormat format,  
        [in] DWORD dwFlags,   
        [in] DWORD dwThreadId,   
        [out] ICorDebugDebugEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="439be-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="439be-105">Parameters</span></span>  
 `pRecord`  
 <span data-ttu-id="439be-106">[in] Bir bayt dizisine bir işaretçi yerel özel durum hata ayıklama olayından yönetilen hata ayıklama olay hakkında bilgiler içerir.</span><span class="sxs-lookup"><span data-stu-id="439be-106">[in] A pointer to a byte array from a native exception debug event that includes information about a managed debug event.</span></span>  
  
 `countBytes`  
 <span data-ttu-id="439be-107">[in] İçindeki öğelerin sayısını `pRecord` bayt dizisi.</span><span class="sxs-lookup"><span data-stu-id="439be-107">[in] The number of elements in the `pRecord` byte array.</span></span>  
  
 `format`  
 <span data-ttu-id="439be-108">[in] A [CorDebugRecordFormat](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md) yönetilmeyen hata ayıklama olayı biçimini belirten numaralandırma üyesi.</span><span class="sxs-lookup"><span data-stu-id="439be-108">[in] A [CorDebugRecordFormat](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md) enumeration member that specifies the format of the unmanaged debug event.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="439be-109">[in] Hedef mimarisine bağlıdır ve hata ayıklama olay hakkında ek bilgi belirten bir bit alanı.</span><span class="sxs-lookup"><span data-stu-id="439be-109">[in] A bit field that depends on the target architecture and that specifies additional information about the debug event.</span></span> <span data-ttu-id="439be-110">Windows sistemleri için bir üyesi olabilir [CorDebugDecodeEventFlagsWindows](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md) sabit listesi.</span><span class="sxs-lookup"><span data-stu-id="439be-110">For Windows systems, it can be a member of the [CorDebugDecodeEventFlagsWindows](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md) enumeration.</span></span>  
  
 `dwThreadId`  
 <span data-ttu-id="439be-111">[in] Özel durumun oluştuğu iş parçacığı işletim sistemi tanımlayıcısı.</span><span class="sxs-lookup"><span data-stu-id="439be-111">[in] The operating system identifier of the thread on which the exception was thrown.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="439be-112">[out] Adresine bir işaretçi bir [Icordebugdebugevent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) kodu çözülmüş yönetilen hata ayıklama olayı temsil eden nesne.</span><span class="sxs-lookup"><span data-stu-id="439be-112">[out] A pointer to the address of an [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) object that represents a decoded managed debug event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="439be-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="439be-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="439be-114">Bu yöntem yalnızca .NET Native ile kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="439be-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="439be-115">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="439be-115">Requirements</span></span>  
 <span data-ttu-id="439be-116">**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="439be-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="439be-117">**Üst bilgi:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="439be-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="439be-118">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="439be-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="439be-119">.NET framework sürümleri:</span><span class="sxs-lookup"><span data-stu-id="439be-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="439be-120">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="439be-120">See also</span></span>

- [<span data-ttu-id="439be-121">ICorDebugProcess6 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="439be-121">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="439be-122">Hata Ayıklama Arabirimleri</span><span class="sxs-lookup"><span data-stu-id="439be-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
