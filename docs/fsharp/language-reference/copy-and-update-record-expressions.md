---
title: Kopyalama ve güncelleştirme kayıt ifadeleri
description: "'Var olan bir kaydı, güncelleştirmeleri kopyalayan bir kopyalama ve güncelleştirme kayıt expression' alanları belirtilen ve güncelleştirilen bir kaydı döndürür yazmayı öğrenin."
author: ChrSteinert
ms.date: 06/04/2016
ms.openlocfilehash: 5f9b13ebf6c456aff73872b7522d7670c068dd88
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766057"
---
# <a name="copy-and-update-record-expressions"></a>Kopyalama ve güncelleştirme kayıt ifadeleri

A *kopyalama ve güncelleştirme kayıt ifade* varolan bir kaydı kopyalar, belirtilen alanlarını güncelleştirir ve güncelleştirilen kaydı döndüren bir ifadedir.

## <a name="syntax"></a>Sözdizimi

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a>Açıklamalar

Böylece için varolan bir kaydı güncelleştirme olası varsayılan olarak, kayıt sabittir. Bir kaydın tüm alanlarını güncelleştirilen bir kaydı oluşturmak için yeniden belirtilmesi gerekir. Bu görevi kolaylaştırmak amacıyla bir *kopyalama ve güncelleştirme kayıt ifade* kullanılabilir. Bu ifade, varolan bir kaydı alır, ifade belirtilen alanları ve ifade tarafından belirtilen eksik alan kullanarak aynı türde yeni bir tane oluşturur.
Kayıtlardan kopyalayabilir ve büyük olasılıkla bazı alan değerleri değiştirmek varsa, bu yararlı olabilir.

Örneği için yeni oluşturulan bir kaydı alır.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

Yalnızca kullanabilirsiniz, kayıt alanı üzerinde güncelleştirmek için olsaydı *kopyalama ve güncelleştirme kayıt ifade* aşağıdaki gibidir:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a>Ayrıca bkz.

- [Kayıtlar](records.md)
- [F# Dili Başvurusu](index.md)