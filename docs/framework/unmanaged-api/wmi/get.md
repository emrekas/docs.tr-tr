---
title: GET işlevi (yönetilmeyen API Başvurusu)
description: GET işlevi belirtilen özellik değerini alır.
ms.date: 11/06/2017
api_name:
- Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Get
helpviewer_keywords:
- Get function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 17304dc8330e4f8571f25b8544f1049dff229f2b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798599"
---
# <a name="get-function"></a>Get işlevi

Varsa belirtilen özellik değerini alır.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sözdizimi

```cpp
HRESULT Get (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
); 
```

## <a name="parameters"></a>Parametreler

`vFunc`\
'ndaki Bu parametre kullanılmıyor.

`ptr`\
'ndaki [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) örneğine yönelik bir işaretçi.

`wszName`\
'ndaki Özelliğin adı.

`lFlags`\
'ndaki Ayrılamadı. Bu parametre 0 olmalıdır.

`pVal`\
dışı İşlev başarıyla döndürürse, `wszName` özelliğinin değerini içerir. `pval` Bağımsız değişkenine, niteleyicisi için doğru tür ve değer atanır.

`pvtType`\
dışı İşlev başarıyla döndürürse, özellik türünü gösteren bir [CIM türü sabiti](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) içerir. Değeri de olabilir `null`. 

`plFlavor`\
dışı İşlev başarıyla döndürürse, özelliğin kaynağı hakkında bilgi alır. Bunun değeri `null`, *wbemcli. h* üstbilgi dosyasında tanımlanan aşağıdaki WBEM_FLAVOR_TYPE sabitlerinden biri olabilir: 

|Sabit  |Değer  |Açıklama  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | Özelliği, standart bir sistem özelliğidir. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | Bir sınıf için: Özelliği üst sınıftan devralınır. <br> Bir örnek için: Üst sınıftan Devralındığı sürece özelliği, örnek tarafından değiştirilmez.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Bir sınıf için: Özelliği türetilmiş sınıfa aittir. <br> Bir örnek için: Özelliği örnek tarafından değiştirilir; diğer bir deyişle, bir değer sağlanmış veya bir niteleyici eklenmiş ya da değiştirilmiş. |

## <a name="return-value"></a>Dönüş değeri

Bu işlev tarafından döndürülen aşağıdaki değerler, *Wbemcli. h* üstbilgi dosyasında tanımlanır veya bunları kodunuzda sabitler olarak tanımlayabilirsiniz:

|Sabit  |Değer  |Açıklama  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Genel bir hata oluştu. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Bir veya daha fazla parametre geçerli değil. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | Belirtilen özellik bulunamadı. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | İşlemi gerçekleştirmek için yeterli bellek yok. |
|`WBEM_S_NO_ERROR` | 0 | İşlev çağrısı başarılı oldu.  |

## <a name="remarks"></a>Açıklamalar

Bu işlev, [IWbemClassObject:: Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) yöntemine bir çağrı kaydırır.

`Get` İşlev sistem özelliklerini de döndürebilir.

Bağımsız değişkenine, niteleyicinin ve com [variantinit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) işlevinin doğru türü ve değeri atanır `pVal`

## <a name="requirements"></a>Gereksinimler

 **Platform** Bkz. [sistem gereksinimleri](../../get-started/system-requirements.md).

 **Üst bilgi** WMINet_Utils. IDL

 **.NET Framework sürümleri:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Ayrıca bkz.

- [WMI ve performans sayaçları (yönetilmeyen API Başvurusu)](index.md)
