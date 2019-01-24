---
title: .NET Framework türlerini dizelere dönüştürme
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: dc2e2b65-f623-4dc3-938b-d2a054d6832c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 98ebc9248b0585295adf12e04dece0fef654c2e8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54583135"
---
# <a name="converting-net-framework-types-to-strings"></a>.NET Framework türlerini dizelere dönüştürme
.NET Framework türü bir dizeye dönüştürmek istiyorsanız kullanmanız **ToString** yöntemi. **ToString** yöntemi geçirilen tür dize gösterimini döndürür. Aşağıdaki tablo XML Şeması (XSD) belirtimlerine eşleyen biçiminde bir dize döndürecek .NET Framework türleri listeler.  
  
|.NET Framework türü|Döndürülen dize türü|  
|-------------------------|--------------------------|  
|Boole değeri|"true", "false"|  
|Single.PositiveInfinity|"INF"|  
|Single.NegativeInfinity|"-INF"|  
|Double.PositiveInfinity|"INF"|  
|Double.NegativeInfinity|"-INF"|  
|DateTime|Biçimi yyyy-aa-ddTHH:mm:sszzzzzz ve onun alt kümeleri.|  
|Zaman aralığı|Biçimidir PnYnMnTnHnMnS, örneğin, `P2Y10M15DT10H30M20S` 2 yıl, 10 ay, 15 gün, 10hours süre olan 30 dakika ve 20 saniye.|  
  
## <a name="see-also"></a>Ayrıca bkz.

- [XML Veri Türlerini Dönüştürme](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)
- [.NET Framework Veri Türleri için Dizeleri Dönüştürme](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)
