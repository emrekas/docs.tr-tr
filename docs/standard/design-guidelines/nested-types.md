---
title: İç içe Geçmiş Türler
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- types, nested
- public nested types
- type design guidelines, nested types
- nested types
- members [.NET Framework], type
- class library design guidelines [.NET Framework], nested types
ms.assetid: 12feb7f0-b793-4d96-b090-42d6473bab8c
author: KrzysztofCwalina
ms.openlocfilehash: 22c14d05105154ff642cb8a44eda8e7c5d0575e4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756877"
---
# <a name="nested-types"></a>İç içe Geçmiş Türler
İç içe türü kapsayan tür adlı başka bir tür kapsamında tanımlanan bir türdür. İç içe türü, kapsayan türdeki tüm üyelerine erişebilir. Örneğin, kapsayan türdeki ve protected olarak kapsayan türdeki tüm üst öğelerinden içinde tanımlanan alanların tanımlı özel alanlara erişimi vardır.  
  
 Genel olarak, iç içe geçmiş türler kullanılmamalıdır. Bunun birkaç nedeni vardır. Bazı geliştiriciler kavramı ile tamamen tanıdık olmayan. Örneğin, bu geliştiricilerin iç içe geçmiş türlerinin değişkenleri bildirme söz dizimi ile ilgili sorunlar olabilir. İç içe geçmiş türler kapsayan türlerini de çok sıkı şekilde bağlı ve bu nedenle genel amaçlı türleri için uygun değildir.  
  
 İç içe geçmiş türler uygulama ayrıntılarını kapsayan türleri modellemek için uygundur. Son kullanıcı, iç içe türün değişkenler bildirmek nadiren olmalıdır ve neredeyse hiç açıkça iç içe geçmiş türler oluşturmak sahip olmalıdır. Örneğin, bir koleksiyonun Numaralandırıcı, koleksiyon iç içe geçmiş bir tür olabilir. Numaralandırıcılar genellikle kapsayan türü tarafından örneği oluşturulur ve birçok dilde foreach deyimi desteklediğinden, numaralandırıcı değişkenleri nadiren son kullanıcı tarafından bildirilmesi gerekir.  
  
 **✓ DO** üye erişilebilirlik semantiği istenen şekilde iç içe geçmiş tür ve dış türü arasındaki ilişkiyi olduğunda iç içe geçmiş türler kullanın.  
  
 **X DO NOT** kullanım ortak iç içe geçmiş türler, mantıksal bir gruplandırma olarak oluşturun; ad alanları için bunu kullanın.  
  
 **X AVOID** herkese açık şekilde iç içe geçmiş türler açık. Tek özel durumu, iç içe türün değişkenleri yalnızca sınıflara veya diğer gelişmiş özelleştirme senaryoları gibi nadir senaryolarda bildirilmelidir gerektiğinde olur.  
  
 **X DO NOT** türü içeren türde dışında başvurulacak olasılığı olan iç içe geçmiş türler kullanın.  
  
 Örneğin, bir sınıfta tanımlanan yönteme geçirilen bir sabit listesi sınıfı iç içe geçmiş tür olarak tanımlanmamalıdır.  
  
 **X DO NOT** istemci kodu tarafından örneğinin oluşturulması gerekirse iç içe geçmiş türler kullanın.  Bir tür genel bir oluşturucusu varsa, bu yuvalanmış olmayabilir.  
  
 Bir tür oluşturulabilir, kilitlersiniz türüne sahip bir yerde kendi framework belirtmek için (oluşturun, birlikte çalışmak ve dış türün kullanmadan yok) ve bu nedenle iç içe yerleştirilmiş. İç türleri değil yaygın olarak yeniden kullanılabilir dışında herhangi bir ilişkisi olmayan dış türün dış türe vermemektedir.  
  
 **X DO NOT** iç içe geçmiş tür bir arabirim üye olarak tanımlayın. Birçok dilde bu tür bir yapı desteklemez.  
  
 *Kısımları © 2005, 2009 Microsoft Corporation. Tüm hakları saklıdır.*  
  
 *İzni Pearson eğitim, Inc. tarafından yeniden yazdırılmaları [çerçeve tasarım yönergeleri: Kuralları, deyimlerini ve yeniden kullanılabilir .NET kitaplıkları, sürüm 2 için desenler](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina ve Brad Abrams, 22 Eki 2008 Addison Wesley Professional ile Microsoft Windows geliştirme serisi bir parçası olarak yayımlandı.*  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Tür Tasarımı Yönergeleri](../../../docs/standard/design-guidelines/type.md)
- [Çerçeve Tasarım Yönergeleri](../../../docs/standard/design-guidelines/index.md)
