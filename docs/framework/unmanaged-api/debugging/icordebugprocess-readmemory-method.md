---
title: ICorDebugProcess::ReadMemory Yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ReadMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ReadMemory
helpviewer_keywords:
- ReadMemory method [.NET Framework debugging]
- ICorDebugProcess::ReadMemory method [.NET Framework debugging]
ms.assetid: 28e4b2f6-9589-445c-be24-24a3306795e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d74da502492065dbffb5e5499581263760636c7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737071"
---
# <a name="icordebugprocessreadmemory-method"></a>ICorDebugProcess::ReadMemory Yöntemi
Bu işlem için bellek belirtilen bir alan okur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,   
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a>Parametreler  
 `address`  
 [in] A `CORDB_ADDRESS` okumak için bellek taban adresini belirten bir değer.  
  
 `size`  
 [in] Bellekten okunacak bayt sayısı.  
  
 `buffer`  
 [out] Bellek içerikleri alan arabellek.  
  
 `read`  
 [out] Bir işaretçi bayt sayısı belirtilen arabelleğe aktardı.  
  
## <a name="remarks"></a>Açıklamalar  
 `ReadMemory` Yöntemi yönetilmeyen hata ayıklanan bölümü tarafından kullanılmakta olan bellek bölümlerinin incelemek için birlikte çalışma hata ayıklama tarafından kullanılması amaçlanmaktadır. Bu yöntem, Microsoft Ara dil (MSIL) kodu ve JIT olarak derlenmiş yerel kod okumak için de kullanılabilir.  
  
 Yönetilen herhangi bir kesme noktası içerisinde geri dönmemiş ise veri kaldırılacak `buffer` parametresi. Yerel kesme noktaları ayarlayın hiçbir düzeltme yapılan [Icordebugprocess2::setunmanagedbreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).  
  
 Önbelleksizlik işlem bellek gerçekleştirilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
