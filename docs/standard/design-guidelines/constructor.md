---
title: Oluşturucu Tasarımı
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- parameterless constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
author: KrzysztofCwalina
ms.openlocfilehash: a43ec815275e58f4bc6462fb4f5cb4733267de31
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972112"
---
# <a name="constructor-design"></a>Oluşturucu Tasarımı

İki tür Oluşturucu vardır: tür oluşturucular ve örnek oluşturucular.

Tür oluşturucuları statiktir ve tür kullanılmadan önce CLR tarafından çalıştırılır. Örnek oluşturucular, bir tür örneği oluşturulduğunda çalışır.

Tür oluşturucular hiçbir parametre alamaz. Örnek oluşturucular olabilir. Parametre kullanmayan örnek oluşturucular genellikle parametresiz oluşturucular olarak adlandırılır.

Oluşturucular, bir türün örneklerini oluşturmanın en doğal yoludur. Çoğu geliştirici, örnek oluşturma (örneğin, Factory yöntemleri) için alternatif yolları düşünmeleri için bir oluşturucuyu arar ve kullanmayı dener.

**✓ CONSIDER** sağlayan basit, ideal olarak varsayılan, Oluşturucular.

Basit bir oluşturucunun çok az sayıda parametresi vardır ve tüm parametreler temel elemanlar veya Numaralandırmalar. Bu tür basit oluşturucular Framework kullanılabilirliğini artırır.

**✓ CONSIDER** statik Üreteç yöntemi yerine bir oluşturucu istenen işlemin semantiği doğrudan yapımı yeni bir örneğini eşleşmiyorsa ya da Oluşturucusu tasarım yönergeleri izleyerek doğal olmayan hissi kullanarak.

**✓ DO** ana özelliklerini ayarlamak için kısayol olarak Oluşturucusu parametrelerini kullanın.

Boş oluşturucuyu, ardından bazı özellik kümelerini ve birden çok bağımsız değişkenle bir oluşturucuyu kullanarak, semantik bir farklılık olmamalıdır.

**✓ DO** Oluşturucu parametreleri yalnızca özelliğini ayarlamak için kullanılan Oluşturucu parametreleri ve bir özellik için aynı adı kullanın.

Bu parametre ve özellikler arasındaki tek fark büyük küçük harf olmalıdır.

**✓ DO** Oluşturucusu en az iş.

Oluşturucular, Oluşturucu parametrelerini yakalamaya göre çok daha fazla çalışmamalıdır. Diğer bir işleme maliyeti, gerekli olana kadar Gecikmeli olmalıdır.

**✓ DO** uygunsa örnek Oluşturucular, özel durumlar oluşturma.

**✓** , Bu tür bir Oluşturucu gerekliyse, sınıflarda Ortak parametresiz oluşturucuyu açık bir şekilde bildirir.

Bir tür üzerinde açıkça herhangi bir Oluşturucu bildirmezseniz, birçok dil (gibi C#) otomatik olarak ortak parametresiz bir Oluşturucu ekler. (Soyut sınıflar korumalı bir Oluşturucu alır.)

Bir sınıfa parametreli Oluşturucu eklemek derleyicinin parametresiz oluşturucuyu eklemesini önler. Bu genellikle yanlışlıkla önemli değişikliklere neden olur.

**X** yapılar üzerinde parametresiz oluşturucular AÇıKÇA tanımlamayı önleyin.

Bu, parametresiz Oluşturucu tanımlanmamışsa, dizideki her yuvada çalıştırılması gerekmediğinden, dizi oluşturmayı daha hızlı hale getirir. Birçok derleyicilerin C#, bu nedenle yapıların parametresiz oluşturuculara sahip olduğuna izin vermez.

**X AVOID** kurucusu içinde bir nesne üzerinde sanal üyeler çağırma.

En türetilmiş türün Oluşturucusu henüz tam olarak çalıştırılmasa bile, sanal bir üyenin çağrılması en fazla türetilmiş geçersiz kılmanın çağrılmasına neden olur.

## <a name="type-constructor-guidelines"></a>Tür Oluşturucu yönergeleri

**✓ DO** statik oluşturucular özel yap.

Sınıf oluşturucusu olarak da adlandırılan statik bir Oluşturucu, bir türü başlatmak için kullanılır. CLR, türün ilk örneği oluşturulmadan veya bu türdeki herhangi bir statik üye çağrılmadan önce statik oluşturucuyu çağırır. Statik Oluşturucu çağrıldığında kullanıcının denetimi yoktur. Statik bir Oluşturucu özel değilse, CLR dışındaki kodla çağrılabilir. Oluşturucuda gerçekleştirilen işlemlere bağlı olarak, bu beklenmeyen davranışlara neden olabilir. C# Derleyici statik oluşturucuları özel olmaya zorlar.

**X DO NOT** statik oluşturucular özel durumlar oluşturma.

Bir tür oluşturucusundan bir özel durum oluşturulursa, tür geçerli uygulama etki alanında kullanılamaz.

**✓ CONSIDER** çalışma zamanı açıkça tanımlanmış bir statik oluşturucusu yok türleri performansını optimize etmek mümkün olduğundan statik oluşturucular açıkça kullanmak yerine statik alanları satır içi başlatılıyor.

*Kısımları © 2005, 2009 Microsoft Corporation. Tüm hakları saklıdır.*

*, Framework tasarım yönergelerinden [Pearson Eğitim, Inc. izni ile yeniden yazdırılıyor: Microsoft Windows geliştirme serisi 'nin bir parçası olarak, bezysztof](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Cwalina ve atacan abkms, Ekim 22, 2008 ile Addison-Wesley Professional ile yeniden kullanılabilir .NET kitaplıkları için kurallar, ıoms ve desenler.*

## <a name="see-also"></a>Ayrıca bkz.

- [Üye Tasarımı Yönergeleri](../../../docs/standard/design-guidelines/member.md)
- [Çerçeve Tasarım Yönergeleri](../../../docs/standard/design-guidelines/index.md)
