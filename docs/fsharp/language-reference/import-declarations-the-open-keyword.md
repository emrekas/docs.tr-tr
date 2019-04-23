---
title: 'İçeri aktarma bildirimleri: Open anahtar sözcüğü'
description: Hakkında bilgi edinin F# bildirimleri ve bir modülde veya öğeleri bir tam adı kullanmadan başvuru ad alanı nasıl belirlediği içeri aktarın.
ms.date: 04/04/2019
ms.openlocfilehash: ad64190c3243c57a185f3b864270fca80590f079
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59055007"
---
# <a name="import-declarations-the-open-keyword"></a>İçeri aktarma bildirimleri: `open` Anahtar sözcüğü

> [!NOTE]
> Bu makaledeki API başvuru bağlantıları için MSDN sürer.  Docs.microsoft.com API başvuru tamamlanmadı.

Bir *bildirim alma* bir modülde veya öğeleri bir tam adı kullanmadan başvuru ad alanı belirtir.

## <a name="syntax"></a>Sözdizimi

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a>Açıklamalar

Tam ad alanında veya modülde yolunu kullanarak kod başvuran her yazma, okunması ve düzenlenmesi zor kod oluşturabilirsiniz. Bunun yerine kullanabileceğiniz `open` anahtar sözcüğü için sık kullanılan modüller ve ad alanları böylece, modül veya isim uzayı üyesi başvurduğunuzda adının kısa formunu yerine tam adını kullanabilirsiniz. Bu anahtar sözcük benzer `using` C# anahtar sözcüğü `using namespace` Visual C++ ' ta ve `Imports` Visual Basic'te.

Modülün veya sağlanan ad alanı, aynı projede veya başvurulan proje ya da derleme olmalıdır. Yüklü değilse, projeye bir başvuru ekleyin, veya kullanın `-reference` komut`-`satırı seçeneğini (veya eşlememiz `-r`). Daha fazla bilgi için [derleyici seçenekleri](compiler-options.md).

İçeri aktarma bildirimi, ad kapsayan ad alanı, modül veya dosya sonuna kadar bildirimi, aşağıdaki kod kullanılabilir hale getirir.

Birden çok içeri aktarma bildirimleri kullandığınızda, ayrı satırlarda görünmeleri gerekir.

Aşağıdaki kod kullanımını gösterir `open` kodu basitleştirmek için anahtar sözcüğü.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

F# Derleyici ktıları bir hata veya uyarı belirsizlikleri aynı adlı birden fazla açık bir modülde veya ad alanı içinde oluştuğunda meydana geldiğinde. Belirsizlikler meydana geldiğinde F# tercihi daha açık bir modülde veya ad alanı sağlar. Örneğin, aşağıdaki kodda, `empty` anlamına gelir `Seq.empty`rağmen `empty` her ikisinde de bulunuyorsa `List` ve `Seq` modüller.

```fsharp
open List
open Seq
printfn "%A" empty
```

Modüllerde veya ad gibi açtığınızda, bu nedenle dikkatli olun `List` veya `Seq` aynı adlara sahip; bunun yerine, nitelikli adlar kullanmayı üyeleri içerir. Kod üzerinde içeri aktarma bildirimleri sırasını bağımlı olduğu tüm durumlarda kaçınmanız gerekir.

## <a name="namespaces-that-are-open-by-default"></a>Varsayılan olarak açık olan ad alanları

Bazı ad alanları, sık sık kullanılır F# kod, örtük olarak açık içeri aktarma bildirimi gerek kalmadan açılmadı. Aşağıdaki tabloda, varsayılan olarak açık olan ad alanlarını gösterir.

|Ad Alanı|Açıklama|
|---------|-----------|
|`Microsoft.FSharp.Core`|Temel içeren F# yerleşik türleri için tanımları gibi yazın `int` ve `float`.|
|`Microsoft.FSharp.Core.Operators`|Temel aritmetik işlemleri gibi içeren `+` ve `*`.|
|`Microsoft.FSharp.Collections`|Değişmez koleksiyon sınıfları içeren `List` ve `Array`.|
|`Microsoft.FSharp.Control`|Geç değerlendirme ve zaman uyumsuz iş akışları gibi denetim yapıları için türler içerir.|
|`Microsoft.FSharp.Text`|Biçimlendirilmiş g/ç için gibi işlevler içeren `printf` işlevi.|

## <a name="autoopen-attribute"></a>AutoOpen özniteliği

Uygulayabileceğiniz `AutoOpen` derlemeye başvurulduğundan, otomatik olarak bir ad alanında veya modülde açmak isteyip istemediğiniz bir bütünleştirilmiş kod özniteliği. Ayrıca uygulayabilirsiniz `AutoOpen` öznitelik üst modülde veya ad alanı açıldığında otomatik olarak bu modülü açmak için bir modül. Daha fazla bilgi için [Core.AutoOpenAttribute sınıfı](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).

## <a name="requirequalifiedaccess-attribute"></a>RequireQualifiedAccess özniteliği

Bazı modüller, kayıtlar veya birleşim türleri belirtebilir `RequireQualifiedAccess` özniteliği. Bu modüller, kayıtlar ve birleşimler öğeleri başvurduğunuzda, içeri aktarma bildirimi içerip bağımsız olarak bir tam adı kullanmanız gerekir. Bu öznitelik stratejik üzerinde kullanırsanız, yaygın olarak tanımlayan türler kullanılan adları, ad çakışmalarını önlemek ve böylece kod daha dayanıklı kitaplıkları değişiklikler yapmak yardımcı olur. Daha fazla bilgi için [Core.RequireQualifiedAccessAttribute sınıfı](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).

## <a name="see-also"></a>Ayrıca bkz.

- [F# Dili Başvurusu](index.md)
- [Ad Alanları](namespaces.md)
- [Modüller](modules.md)
