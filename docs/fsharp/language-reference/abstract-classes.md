---
title: Soyut sınıflar
description: Hakkında bilgi edinin F# bırakın bazı veya tüm üyeleri uygulanmayanları sınıflar, soyut ve nesne türleri farklı bir dizi ortak işlevselliği temsil eder.
ms.date: 05/16/2016
ms.openlocfilehash: fecd3b2d550c6b8f59fa614f5d00c5f730a4896a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772781"
---
# <a name="abstract-classes"></a>Soyut sınıflar

*Soyut sınıflar* uygulanmayanları, bazı veya tüm üyeleri bırakın ve böylece uygulamaları türetilmiş sınıflar tarafından sağlanması sınıflardır.

## <a name="syntax"></a>Sözdizimi

```fsharp
// Abstract class syntax.
[<AbstractClass>]
type [ accessibility-modifier ] abstract-class-name =
[ inherit base-class-or-interface-name ]
[ abstract-member-declarations-and-member-definitions ]

// Abstract member syntax.
abstract member member-name : type-signature
```

## <a name="remarks"></a>Açıklamalar

Nesne yönelimli programlama, soyut bir sınıf bir hiyerarşinin temel sınıf olarak kullanılan ve nesne türleri farklı bir dizi ortak işlevselliği temsil eder. Adı "Özet" da anlaşılacağı gibi soyut sınıflar genellikle doğrudan somut varlıkları sorun etki alanında oturum karşılık gelmez. Ancak, bunlar ne birçok farklı somut ortak varlıkların temsil.

Soyut sınıflar olmalıdır `AbstractClass` özniteliği. Bunlar uygulanan ve üyeleri gerçeklenmemiş. Kullanımı *soyut* uygulandığında bir sınıf diğer .NET dilleri; aynı olan ancak kullanımı *soyut* yöntemleri (ve Özellikler) uygulandığında bir biraz farklıdır F# Diğer .NET dillerinde, kullanımdan. İçinde F#, bir yöntem ile işaretlenmiş `abstract` anahtar sözcüğü, bu gösterir bir üyesi olarak bilinen bir girdiye sahip bir *sanal dağıtım yuvası*, bu tür için sanal işlevleri iç tablosuna. Diğer bir deyişle, yöntem sanal rağmen `virtual` anahtar sözcüğü kullanılan değil F# dili. Anahtar sözcüğü `abstract` olup yöntemin bağımsız olarak sanal yöntemleri kullanılır. Bir sanal dağıtım yuvası bildirimi, bu dağıtım yuvası için bir yöntem tanımını ayrıdır. Bu nedenle, F# eşdeğerdir bir sanal yöntem bildiriminde ve başka bir .NET dil tanımında bir soyut yöntem bildiriminde hem ile ya da ayrı bir tanımı bir birleşimini `default` anahtar sözcüğü veya `override` anahtar sözcüğü. Daha fazla bilgi ve örnekler için bkz. [yöntemleri](members/methods.md).

Bir sınıf bildirimi yapıldı ancak tanımlanmadı soyut yöntemler varsa soyut olarak kabul edilir. Bu nedenle, soyut metotlar içeren sınıflar mutlaka soyut sınıflar değildir. Bir sınıf, soyut yöntemler tanımsız sürece kullanmayın **AbstractClass** özniteliği.

Önceki sözdiziminde, *erişilebilirlik değiştiricisi* olabilir `public`, `private` veya `internal`. Daha fazla bilgi için [erişim denetimi](access-control.md).

Diğer bir tür olduğu gibi soyut sınıflar, bir temel sınıf ve bir veya daha fazla temel arabirimleri olabilir. Birlikte ayrı bir satırda her bir temel sınıf veya arabirim görünür `inherit` anahtar sözcüğü.

Soyut bir sınıf türü tanımı tam olarak tanımlanan üyeler içerebilir, ancak soyut üyeler içerebilir. Soyut sözdizimi, önceki sözdiziminde ayrı olarak gösterilir. Bu sözdizimi *tür imzası* üyesi içeren bir liste sırası ve dönüş türleri, parametre türleri ile ayrılır `->` belirteçleri ve/veya `*` belirteçler uygun şekilde curried için ve tupled Parametreler. Soyut üye türü imzalarını sözdizimi imza dosyalarında kullanılan ve IntelliSense Visual Studio Kod Düzenleyicisi'nde gösterilen ile aynı olur.

Aşağıdaki kod, iki soyut olmayan türetilmiş sınıflar, kare ve daire olan şekil, soyut bir sınıf göstermektedir. Örneğin, soyut sınıflar, yöntemler ve Özellikler kullanmayı gösterir. Örnekte, somut varlıkları daire ve köşeli ortak öğeleri şekil soyut sınıfını temsil eder. Ortak özelliklerini (iki boyutlu bir koordinat sistemi) tüm şekiller out şekli sınıfına soyutlanır: kılavuz, bir döndürme açısını ve alanında ve çevre özelliklerini konumu. Bu, hangi bireysel şekiller değiştirilemez davranışı konumu dışında geçersiz kılınabilir.

Döndürme yöntemi, kendi Simetri nedeniyle döndürme sabit olan daire sınıfı olduğu gibi geçersiz kılınabilir. Bu nedenle daire sınıfında döndürme yöntemi hiçbir şey yapmaz bir yöntemle değiştirilir.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2901.fs)]

**Çıkış:**

```
Perimeter of square with side length 10.000000 is 40.000000
Circumference of circle with radius 5.000000 is 31.415927
Area of Square: 100.000000
Area of Circle: 78.539816
```

## <a name="see-also"></a>Ayrıca bkz.

- [Sınıflar](classes.md)
- [Üyeler](members/index.md)
- [Yöntemler](members/methods.md)
- [Özellikler](members/Properties.md)