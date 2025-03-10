---
title: ICorDebugAppDomain::GetObject Yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetObject
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetObject
helpviewer_keywords:
- ICorDebugAppDomain::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 78232e6f-ae18-4cfa-a6cd-e79471cf9d76
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1201ac0dca9cbd48c24b2621eba079ae672fd310
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737850"
---
# <a name="icordebugappdomaingetobject-method"></a>ICorDebugAppDomain::GetObject Yöntemi
Ortak dil çalışma zamanı (CLR) uygulama etki alanı için bir arabirim işaretçisi alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `ppObject`  
 [out] CLR uygulama etki alanını temsil eden bir Icordebugvalue arabirimi nesnesinin adresine yönelik işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yönetilen, <xref:System.AppDomain?displayProperty=nameWithType> nesne henüz oluşturulan bu uygulama etki alanı için yöntem döndürür `S_FALSE` ve yerleştirir `NULL` içinde `*ppObject`.  
  
## <a name="remarks"></a>Açıklamalar  
 Her uygulama etki alanında bir işlem yönetilen sahip <xref:System.AppDomain?displayProperty=nameWithType> temsil ettiği çalışma zamanında nesne. Bu işlev yönetilen bu karşılık gelen bir Icordebugvalue arabirimi nesneyi alır <xref:System.AppDomain?displayProperty=nameWithType> nesne.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
