---
title: EndEnumeration işlevi (yönetilmeyen API Başvurusu)
description: EndEnumeration işlevi, bir numaralandırma sonlandırır.
ms.date: 11/06/2017
api_name:
- EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndEnumeration
helpviewer_keywords:
- EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65904da9efea90d31960d71ae0da8c81dffeccf1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000473"
---
# <a name="endenumeration-function"></a>EndEnumeration işlevi

Bir çağrı ile başlatılan bir numaralandırma sırasını sonlandırıyor [BeginEnumeration işlevi](beginenumeration.md).

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sözdizimi

```cpp
HRESULT EndEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr
);
```

## <a name="parameters"></a>Parametreler

`vFunc`\
[in] Bu parametre kullanılmaz.

`ptr`\
[in] Bir işaretçi bir [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) örneği.

## <a name="return-value"></a>Dönüş değeri

Bu işlev tarafından döndürülen aşağıdaki değerleri tanımlanan *WbemCli.h* üst bilgi dosyası veya tanımlayabilirsiniz bunları sabitleri kodunuzda:

|Sabit  |Değer  |Açıklama  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Genel bir hata oluştu. |
|`WBEM_S_NO_ERROR` | 0 | İşlev çağrısı başarılı oldu.  |

## <a name="remarks"></a>Açıklamalar

Bu işlev bir çağrı sarılır [IWbemClassObject::EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) yöntemi.

Bir çağrı `EndEnumeration` işlevi gerekli değildir, ancak numaralandırma ile ilişkili kaynakları serbest nedeniyle önerilir. Ancak, kaynakları otomatik olarak sonraki numaralandırma başlattığınızda veya nesne serbest serbest bırakılır.

## <a name="requirements"></a>Gereksinimler

**Platformlar:** Bkz: [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).

**Üst bilgi:** WMINet_Utils.idl

**.NET framework sürümleri:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Ayrıca bkz.

- [WMI ve performans sayaçları (yönetilmeyen API Başvurusu)](index.md)