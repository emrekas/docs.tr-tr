---
title: ICorDebugModule2::SetJMCStatus Yöntemi
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJMCStatus
helpviewer_keywords:
- SetJMCStatus method, ICorDebugModule2 interface [.NET Framework debugging]
- ICorDebugModule2::SetJMCStatus method [.NET Framework debugging]
ms.assetid: 8c6d2089-4dbb-4715-b9e9-2a4491c8c9ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d438123dcefb901098954845596c210e5b76cea6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764107"
---
# <a name="icordebugmodule2setjmcstatus-method"></a>ICorDebugModule2::SetJMCStatus Yöntemi
Tüm sınıfların tüm yöntemleri yalnızca benim kodum (JMC) durumunu bu Icordebugmodule2 hariç belirtilen değere ayarlar `pTokens` dizisi karşı değer olarak ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `bIsJustMycode`  
 [in] Kümesine `true` kod hata ayıklaması; tersi durumda ise, kümesine `false`.  
  
 `cTokens`  
 [in] Boyutu `pTokens` dizisi.  
  
 `pTokens`  
 [in] Bir dizi `mdToken` değerler, her biri JMC durumunu kümesine sahip olan bir yönteme başvuran!`bIsJustMycode`.  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtilen her yöntemin JMC durumunu `pTokens` dizi tersini için ayarlanmış `bIsJustMycode` değeri. Bu modüldeki tüm diğer yöntemler durumunu ayarlamak `bIsJustMycode` değeri.  
  
 `SetJMCStatus` Yöntemi bu modüldeki tüm önceki JMC ayarları siler.  
  
 `SetJMCStatus` Yöntemi, tüm işlevler başarıyla belirlenmişse bir S_OK HRESULT döndürür. CORDBG_E_FUNCTION_NOT_DEBUGGABLE bazı işlevler, HRESULT işaretlenir döndürür `true` hata ayıklanabilir değildir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
