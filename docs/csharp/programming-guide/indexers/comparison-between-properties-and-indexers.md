---
title: Özellikler ve dizin oluşturucular - arasında karşılaştırma C# Programlama Kılavuzu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
ms.openlocfilehash: 41b27905edb8a0e00a6af5a4cce38988161326d0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61680096"
---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a>Özellikler ve Dizin Oluşturucular Arasında Karşılaştırma (C# Programlama Kılavuzu)
Dizin oluşturucular gibi özelliklerdir. Aşağıdaki tabloda gösterilen farklılıklar dışında özellik erişimcileri için tanımlanan tüm kurallar dizin oluşturucu erişimcileri için de geçerlidir.  
  
|Özellik|Dizin Oluşturucu|  
|--------------|-------------|  
|Ortak veri üyeleri değilmiş gibi çağrılacak yöntem sağlar.|Nesne üzerinde dizi gösterimi kullanılarak erişilecek bir nesnenin iç bir koleksiyonun öğeleri sağlar.|  
|Basit bir ad erişilir.|Dizin erişilir.|  
|Statik veya örnek üyesi olabilir.|Bir örnek üyesi olması gerekir.|  
|A [alma](../../../csharp/language-reference/keywords/get.md) özellik erişimcisi sahip parametre yok.|A `get` erişimci bir dizin oluşturucu aynı dizin oluşturucu biçimsel parametre listesine sahip.|  
|A [ayarlamak](../../../csharp/language-reference/keywords/set.md) örtük özellik erişimcisi içeren `value` parametresi.|A `set` bir dizin oluşturucu erişimcisine sahip aynı biçimsel parametre listesi dizin oluşturucu olarak yanı sıra [değer](../../../csharp/language-reference/keywords/value.md) parametresi.|  
|Destekler kısaltılmış sözdizimi ile [Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).|Kısaltılmış sözdizimi desteklemez.|  
  
## <a name="see-also"></a>Ayrıca bkz.

- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)
- [Dizin Oluşturucular](../../../csharp/programming-guide/indexers/index.md)
- [Özellikler](../../../csharp/programming-guide/classes-and-structs/properties.md)
