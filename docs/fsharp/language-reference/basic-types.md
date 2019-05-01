---
title: Temel türler
description: Kullanılan temel temel türler Bul F# dili.
ms.date: 07/09/2018
ms.openlocfilehash: 74a276792e2566b8f18b87f4bdcfb923b713b9c5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61959126"
---
# <a name="basic-types"></a>Temel türler

Bu konu içinde tanımlanan temel türleri listeler F# dili. Bu en temel türler F#, neredeyse tüm temel oluşturan F# program. Bunlar, bir üst .NET ilkel türler.

|Tür|.NET türü|Açıklama|
|----|---------|-----------|
|`bool`|<xref:System.Boolean>|Olası değerler `true` ve `false`.|
|`byte`|<xref:System.Byte>|0 ile 255 değerler.|
|`sbyte`|<xref:System.SByte>|-128 ile 127 değerleri.|
|`int16`|<xref:System.Int16>|-32768 ile 32767 değerleri.|
|`uint16`|<xref:System.UInt16>|0 ile 65535 değerler.|
|`int`|<xref:System.Int32>|-2.147.483.648 ile 2.147.483.647 değerleri.|
|`uint32`|<xref:System.UInt32>|4.294.967.295'e kadar değerleri 0.|
|`int64`|<xref:System.Int64>|9.223.372.036.854.775.807-9,223,372,036,854,775,808 değeri.|
|`uint64`|<xref:System.UInt64>|18,446,744,073,709,551,615 0 değeri.|
|`nativeint`|<xref:System.IntPtr>|İmzalı bir tamsayı olarak yerel bir işaretçi.|
|`unativeint`|<xref:System.UIntPtr>|İşaretsiz bir tamsayı olarak yerel işaretçi.|
|`char`|<xref:System.Char>|Unicode karakter değeri.|
|`string`|<xref:System.String>|Unicode metin.|
|`decimal`|<xref:System.Decimal>|Bir kayan nokta veri türü, en az 28 basamaktan oluşur.|
|`unit`|Uygulanamaz|Gerçek bir değer olmaması gösterir. Belirtilen tek biçimsel değeri türüne sahip `()`. Birimi değeri `()`, genellikle burada bir değer gerekiyordu ancak gerçek değer kullanılabilir veya anlamlı bir yer tutucu olarak kullanılır.|
|`void`|<xref:System.Void>|Hiçbir tür veya değer gösterir.|
|`float32`, `single`|<xref:System.Single>|Bir 32-bit kayan nokta türü.|
|`float`, `double`|<xref:System.Double>|Bir 64-bit kayan nokta türü.|

> [!NOTE]
> Kullanarak 64-bit tamsayı türü için çok büyük bir tamsayı ile hesaplamalar gerçekleştirebilirsiniz [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) türü. `bigint` bir temel tür olarak kabul edilmez; Bunun için bir kısaltma olduğundan `System.Numerics.BigInteger`.

## <a name="see-also"></a>Ayrıca bkz.

- [F# Dili Başvurusu](index.md)