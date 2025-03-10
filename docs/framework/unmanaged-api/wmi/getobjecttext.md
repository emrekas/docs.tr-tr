---
title: GetObjectText işlevi (yönetilmeyen API Başvurusu)
description: GetObjectText işlevi, MOF sözdiziminde bir nesnenin metinsel işlemesini döndürür.
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d47fcd59204a4d114fc9f0dc5bc4550ba1681f33
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798499"
---
# <a name="getobjecttext-function"></a>GetObjectText işlevi
Yönetilen Nesne Biçimi (MOF) sözdiziminde nesnenin metinsel işlemesini döndürür.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a>Parametreler

`vFunc`  
'ndaki Bu parametre kullanılmıyor.

`ptr`  
'ndaki [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) örneğine yönelik bir işaretçi.

`lFlags`  
'ndaki Normalde 0. `WBEM_FLAG_NO_FLAVORS` (Veya 0x1) belirtilirse, niteleyiciler yayma veya Flavor bilgisi olmadan dahil edilir.

`pstrObjectText`   
dışı `null` Açık giriş işaretçisi. Dönüşte, nesnenin MOF sözdizimi `BSTR` işleme içeren yeni bir ayrılmış.  

## <a name="return-value"></a>Dönüş değeri

Bu işlev tarafından döndürülen aşağıdaki değerler, *Wbemcli. h* üstbilgi dosyasında tanımlanır veya bunları kodunuzda sabitler olarak tanımlayabilirsiniz:

|Sabit  |Değer  |Açıklama  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Genel bir hata oluştu. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Parametre geçerli değil. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | İşlemi gerçekleştirmek için yeterli bellek yok. |
|`WBEM_S_NO_ERROR` | 0 | İşlev çağrısı başarılı oldu.  |
  
## <a name="remarks"></a>Açıklamalar

Bu işlev, [IWbemClassObject:: GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) yöntemine bir çağrı kaydırır.

Döndürülen MOF metni nesneyle ilgili tüm bilgileri içermiyor, ancak özgün nesneyi yeniden oluşturmak için yalnızca MOF derleyicisi için yeterli bilgi yok. Örneğin, hiçbir yayılmış niteleyici veya üst sınıf özelliği dahil değildir.

Aşağıdaki algoritma bir yöntemin parametrelerinin metnini yeniden oluşturmak için kullanılır:

1. Parametreler, tanımlayıcı değerlerinin sırasıyla yeniden sıralandır.
1. `[in]` Ve`[out]` olarak belirtilen parametreler tek bir parametre içinde birleştirilir.
 
`pstrObjectText`işlev çağrıldığında bir `null` öğesine işaretçi olmalıdır; işaretçi serbest bırakılmadığı için yöntem çağrısından önce geçerli olan bir dizeye işaret etmelidir.

## <a name="requirements"></a>Gereksinimler  
**Platform** Bkz. [sistem gereksinimleri](../../get-started/system-requirements.md).  
  
 **Üst bilgi** WMINet_Utils. IDL  
  
 **.NET Framework sürümleri:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [WMI ve performans sayaçları (yönetilmeyen API Başvurusu)](index.md)
