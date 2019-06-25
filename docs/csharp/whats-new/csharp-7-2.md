---
title: C# 7.2 yenilikleri
description: C# 7.2 yenilikleri genel bakış.
ms.date: 08/16/2017
ms.openlocfilehash: 79402c9b569cb6848aaf240d83ba71338d525b35
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2019
ms.locfileid: "67347421"
---
# <a name="whats-new-in-c-72"></a>C# 7.2 yenilikleri

C# 7.2 birçok yararlı özellik ekleyen başka bir noktası sürümdür.
Bu sürüm için bir tema, gereksiz kopyalarını veya ayırmaları önleyerek değer türleri ile daha verimli bir şekilde çalışıyor.

Geri kalan özellikleri, küçük, iyi sahip özellikleridir.

C# 7.2 kullanan [dil sürüm seçimi](../language-reference/configure-language-version.md) derleyici dil sürüm seçmek için yapılandırma öğesi.

Bu sürümdeki yeni diz özellikleri şunlardır:

* [Güvenli verimli kod yazmak için teknikleri](#safe-efficient-code-enhancements)
  - Başvuru semantiği kullanarak değer türleri ile çalışmayı etkinleştirmek söz dizimi geliştirmeleri birleşimi.
* [Girintili olmayan adlandırılmış bağımsız değişkenler](#non-trailing-named-arguments)
  - Adlandırılmış bağımsız değişkenler konumsal bağımsız değişken tarafından izlenebilir.
* [Sayısal sabit değerlerde önde gelen altçizgilere](#leading-underscores-in-numeric-literals)
  - Artık sayısal değişmez değerler yazdırılan herhangi bir rakam önce önde gelen altçizgilere sahip olabilir.
* [`private protected` Erişim değiştiricisi](#private-protected-access-modifier)
  - `private protected` Erişim değiştiricisi, aynı derlemedeki türetilmiş sınıflar için erişim sağlar.
* [Koşullu `ref` ifadeleri](#conditional-ref-expressions)
  - Koşullu ifadenin sonucu (`?:`) artık bir başvuru olabilir.

Bu makalenin geri kalanında her özelliğine genel bakış sağlar. Her bir özellik için ardındaki mantık öğreneceksiniz. Söz dizimi öğreneceksiniz. Bu özellikleri kullanarak ortamınıza keşfedebilirsiniz `dotnet try` genel aracı:

1. Yükleme [dotnet deneyin](https://github.com/dotnet/try/blob/master/README.md#setup) genel aracı.
1. Kopya [dotnet/try-samples](https://github.com/dotnet/try-samples) depo.
1. Geçerli dizin kümesine *csharp7* alt *deneyin-samples* depo.
1. `dotnet try`'i çalıştırın.

## <a name="safe-efficient-code-enhancements"></a>Güvenli verimli kod geliştirmeleri

Tanıtılan 7.2 dil özellikleri, değer türleri ile başvuru semantiği kullanırken çalışmanıza olanak tanır. Kopyalama değer türleri başvuru türleri kullanmayla ilişkili bellek ayırmaları ödemeden en aza indirerek, performansı artırmak için tasarlanmıştır. Özellikler şunlardır:

- `in` Değiştirici bağımsız değişken başvuruyla geçirildi ancak tarafından çağrılan yöntem değiştirilmemiş belirtmek için parametreleri. Ekleme `in` değiştiricisi bir bağımsız değişken için bir [kaynağı uyumlu değişiklik](version-update-considerations.md#source-compatible-changes).
- `ref readonly` Değiştirici yöntemi döndüğünde, bir yöntem değerine başvuru ile döndürülen ancak bu nesne için yazma izin vermez belirtmek için. Ekleme `ref readonly` değiştiricisi bir [kaynağı uyumlu değişiklik](version-update-considerations.md#source-compatible-changes), dönüş için bir değer atanır. Ekleme `readonly` değiştirici mevcut bir `ref` dönüş deyimi bir [uyumsuz değişiklik](version-update-considerations.md#incompatible-changes). Bildirimi güncelleştirmek çağıranlar gerektirir `ref` eklemek için yerel değişkenleri `readonly` değiştiricisi.
- `readonly struct` Yapı sabittir ve olarak geçirilmelidir belirtmek için bildirimi bir `in` üye yöntemlerinin parametre. Ekleme `readonly` değiştiricisi var olan bir yapı bildirim için bir [ikili uyumlu değişiklik](version-update-considerations.md#binary-compatible-changes).
- `ref struct` Bildirimi, bir yapı türü yönetilen bellek doğrudan erişir ve her zaman yığını ayrılmalıdır. Ekleme `ref` değiştirici mevcut bir `struct` bildirimi bir [uyumsuz değişiklik](version-update-considerations.md#incompatible-changes). A `ref struct` bunu ayrıldığı yığında diğer konumlarda kullanılan veya bir sınıf üyesi olamaz.

Tüm bunlar hakkında daha fazla değişiklikler okuyabilirsiniz [güvenli verimli kod yazma](../write-safe-efficient-code.md).

## <a name="non-trailing-named-arguments"></a>Girintili olmayan adlandırılmış bağımsız değişkenler

Yöntem çağrıları artık bu adlandırılmış bağımsız değişkenler doğru konumda olduğunda, önünde konumsal bağımsız değişkenler adlandırılmış bağımsız değişkenler kullanabilirsiniz. Daha fazla bilgi için [adlandırılmış ve isteğe bağlı bağımsız değişkenler](../programming-guide/classes-and-structs/named-and-optional-arguments.md).

## <a name="leading-underscores-in-numeric-literals"></a>Sayısal sabit değerlerde önde gelen altçizgilere

Rakam ayırıcıları C# 7.0 desteği uygulamasına izin vermedi `_` değişmez değerin ilk karakteri olarak. Onaltılık ve ikili sayısal değişmez değerler artık ile başlayan bir `_`.

Örneğin:

```csharp
int binaryValue = 0b_0101_0101;
```

## <a name="private-protected-access-modifier"></a>_Özel korumalı_ erişim değiştiricisi

Yeni bir bileşik erişim değiştiricisi: `private protected` üye sınıfı veya aynı derlemede bildirilmiş türetilmiş sınıfları içeren tarafından erişilebilecek gösterir. Sırada `protected internal` türetilmiş sınıflar veya aynı derlemede bulunan sınıflar tarafından erişime `private protected` türetilen türlerin aynı derlemede bildirilmiş erişimi sınırlar.

Daha fazla bilgi için [erişim değiştiricilerine](../language-reference/keywords/access-modifiers.md) dil başvurusu.

## <a name="conditional-ref-expressions"></a>Koşullu `ref` ifadeleri

Son olarak, koşullu ifade bir değer sonuç yerine bir başvuru sonuç üretebilir. Örneğin, bir iki dizinin içindeki ilk öğeye bir başvuru almak için aşağıdaki yazmalısınız:

```csharp
ref var r = ref (arr != null ? ref arr[0] : ref otherArr[0]);
```

Değişken `r` ilk değeri ya da bir başvurudur `arr` veya `otherArr`.

Daha fazla bilgi için [koşullu işleç (?:) ](../language-reference/operators/conditional-operator.md) dil başvurusu.
