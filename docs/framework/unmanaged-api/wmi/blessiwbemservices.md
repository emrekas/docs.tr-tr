---
title: Blessıwbemservices işlevi (yönetilmeyen API Başvurusu)
description: Blessıwbemservices işlevi, kullanıcı kimlik bilgilerini IWbemServices sınıfı erişime olup olmadığını gösterir.
ms.date: 11/06/2017
api_name:
- BlessIWbemServices
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServices
helpviewer_keywords:
- BlessIWbemServices function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 23b72856015d028e50c1e3bfd4a12e0f220291c3
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354615"
---
# <a name="blessiwbemservices-function"></a>Blessıwbemservices işlevi
Kullanıcı kimlik bilgilerini belirtilen erişim izni olup olmadığını gösteren [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) sınıfı.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT BlessIWbemServices (
   [in] IWbemServices* pIWbemServices,
   [in] BSTR strUser, 
   [in] BSTR strPassword, 
   [in] BSTR strAuthority, 
   [in] DWORD impLevel, 
   [in] DWORD authnLevel
);
```  

## <a name="parameters"></a>Parametreler

`pIWbemServices`\
[in] Bir işaretçi [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) nesnesi için izinleri gereklidir.

`strUser`\
[in] Kullanıcı adı.

`strPassword`\
[in] İlişkili parolayı `strUser`.

`strAuthority`\
[in] Kullanıcı etki alanı adı. Bkz: [ConnectServerWmi](connectserverwmi.md) işlevi daha fazla bilgi için.

`impLevel`\
[in] Kimliğe bürünme düzeyi.

`authnLevel`\
[in] Yetkilendirme düzeyi.

## <a name="return-value"></a>Dönüş değeri

Bu işlev tarafından döndürülen aşağıdaki değerleri tanımlanan *Wınerror* üst bilgi dosyası veya tanımlayabilirsiniz bunları sabitleri kodunuzda:

|Sabit  |Değer  |Açıklama  |
|---------|---------|---------|
| `E_INVALIDARG` | 0x80070057 | Bir veya daha fazla bağımsız değişken geçersiz. |
| `E_POINTER` | 0x80004003 | `pIWbemServices` olan `null`. | 
| `E_FAIL` | 0x80000008 | Belirtilmeyen bir hata oluştu. |
| `E_OUTOFMEMORY` | 0x80000002 | İşlemi gerçekleştirmek yeterli bellek yok. | 
| `S_OK` | 0 | İşlev çağrısı başarılı oldu. | 

## <a name="requirements"></a>Gereksinimler  

 **Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Üst bilgi:** WMINet_Utils.idl  
  
 **.NET framework sürümleri:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [WMI ve performans sayaçları (yönetilmeyen API Başvurusu)](index.md)