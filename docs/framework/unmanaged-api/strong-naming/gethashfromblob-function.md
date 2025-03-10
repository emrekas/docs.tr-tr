---
title: GetHashFromBlob İşlevi
ms.date: 03/30/2017
api_name:
- GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromBlob
helpviewer_keywords:
- GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 59b4df08157ce14a58393e54b671e8f41b8998ed
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799236"
---
# <a name="gethashfromblob-function"></a>GetHashFromBlob İşlevi

Belirtilen karma algoritmasını kullanarak, belirtilen bellek adresindeki derlemenin karmasını alır.

Bu işlev kullanım dışı bırakıldı. Bunun yerine [ICLRStrongName:: GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md) yöntemini kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetHashFromBlob (
    [in]  BYTE    *pbBlob,
    [in]  DWORD   cchBlob,
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE    *pbHash,
    [in]  DWORD   cchHash,
    [out] DWORD   *pchHash
);
```

## <a name="parameters"></a>Parametreler

`pbBlob`\
'ndaki Karma hale getirilen bellek bloğunun adresine yönelik bir işaretçi.

`cchBlob`\
'ndaki Bellek bloğunun bayt cinsinden uzunluğu.

`piHashAlg`\
[in, out] Karma algoritmayı belirten bir sabit. Varsayılan algoritma için sıfır kullanın.

`pbHash`\
dışı Döndürülen karma arabelleği.

`cchHash`\
'ndaki İstenen en büyük boyut `pbHash`.

`pchHash`\
dışı Döndürülen `pbHash`bayt cinsinden boyutu.

## <a name="requirements"></a>Gereksinimler

**Platform** Bkz. [sistem gereksinimleri](../../get-started/system-requirements.md).

**Üst bilgi** StrongName. h

**Kitaplığı** MsCorEE. dll dosyasına bir kaynak olarak dahildir

**.NET Framework sürümleri:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Ayrıca bkz.

- [GetHashFromBlob Yöntemi](../hosting/iclrstrongname-gethashfromblob-method.md)
- [ICLRStrongName Arabirimi](../hosting/iclrstrongname-interface.md)
