---
title: Özellikleri kullanma- C# Programlama Kılavuzu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- set accessor [C#]
- get accessor [C#]
- properties [C#], about properties
ms.assetid: f7f67b05-0983-4cdb-96af-1855d24c967c
ms.openlocfilehash: fdaa4b511b18495d2a35f72ee017a01aab0b4ee8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922048"
---
# <a name="using-properties-c-programming-guide"></a>Özellikleri Kullanma (C# Programlama Kılavuzu)
Özellikler her iki alanın ve yöntemin yönlerini birleştirir. Bir nesnenin kullanıcısına, bir özellik bir alan gibi görünür, özelliğe erişim de aynı sözdizimini gerektirir. Bir sınıfın uygulayıcısı için bir özellik bir veya iki kod blobunun yanı sıra bir [Get](../../language-reference/keywords/get.md) erişimcisini ve/veya [set](../../language-reference/keywords/set.md) erişimcisini temsil eder. `get` Erişimci için kod bloğu, özellik okuma sırasında yürütülür. `set` erişimci için kod bloğu, özelliğe yeni bir değer atandığında yürütülür. `set` Erişimcisi olmayan bir özellik salt okunurdur. `get` Erişimcisi olmayan bir özellik salt yazılır olarak değerlendirilir. Her iki erişimciyi sahip bir özellik okuma-yazma ' dır.  
  
 Alanların aksine, özellikler değişken olarak sınıflandırılmaz. Bu nedenle, bir özelliği [ref](../../language-reference/keywords/ref.md) veya [Out](../../language-reference/keywords/out-parameter-modifier.md) parametresi olarak geçiremezsiniz.  
  
 Özelliklerin birçok kullanımı vardır: bir değişikliğe izin vermeden önce verileri doğrulayabilir; verilerin aslında bir veritabanı gibi başka bir kaynaktan alındığı bir sınıf üzerinde saydam bir şekilde veri sunabilir; bir olayı oluşturma veya diğer alanların değerini değiştirme gibi veriler değiştirildiğinde bir eylem gerçekleştirebilir.  
  
 Özellikler, alanın erişim düzeyini, sonra özelliğin türünü ve sonra özelliğin adını ve ardından bir `get`-erişimci ve/ `set` veya erişimci bildiren bir kod bloğunu belirterek sınıf bloğunda bildirilir. Örneğin:  
  
 [!code-csharp[csProgGuideProperties#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#7)]  
  
 Bu örnekte, `Month` erişimcinin `Month` değerin 1 ile 12 arasında ayarlandığından emin `set` olması için bir özellik olarak bildirilmiştir. Özelliği `Month` , gerçek değeri izlemek için bir özel alan kullanır. Özelliğin verilerinin gerçek konumu genellikle özelliğin "yedekleme deposu" olarak adlandırılır. Özelliklerin özel alanları bir yedekleme deposu olarak kullanması yaygındır. Bu alan, yalnızca özelliği çağırarak değiştirilebilmesi için özel olarak işaretlenir. Ortak ve özel erişim kısıtlamaları hakkında daha fazla bilgi için bkz. [erişim değiştiricileri](./access-modifiers.md).  
  
 Otomatik uygulanan özellikler basit özellik bildirimleri için Basitleştirilmiş söz dizimi sağlar. Daha fazla bilgi için bkz. [Otomatik uygulanan özellikler](./auto-implemented-properties.md).  
  
## <a name="the-get-accessor"></a>Get erişimcisi  
 `get` Erişimcinin gövdesi bir yönteme benzer. Özellik türünün bir değerini döndürmesi gerekir. `get` Erişimcinin yürütülmesi alanın değerini okumayla eşdeğerdir. Örneğin, `get` erişimcisinden özel değişkeni döndürmekte ve iyileştirmeler etkinleştirildiğinde, `get` erişimci metoduna yapılan çağrı derleyici tarafından satır içine alınır ve bu nedenle Yöntem çağrısı yoktur. Ancak, derleyici derleme `get` zamanında hangi yöntemin çalışma zamanında çağrıldığı hakkında bilgi içermediği için bir sanal erişimci yöntemi satır içine alınamaz. Aşağıda özel bir alanın `get` `name`değerini döndüren bir erişimci verilmiştir:  
  
 [!code-csharp[csProgGuideProperties#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#8)]  
  
 Özelliğe başvurduğunuzda, bir atamanın `get` hedefi dışında, özelliğin değerini okumak için erişimci çağrılır. Örneğin:  
  
 [!code-csharp[csProgGuideProperties#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#9)]  
  
 Erişimci bir return veya [throw](../../language-reference/keywords/throw.md) ifadesinde bitmelidir ve denetim erişimci gövdesini kapatamıyor olmalıdır. [](../../language-reference/keywords/return.md) `get`  
  
 `get` Erişimciyi kullanarak nesnenin durumunu değiştirmek için hatalı bir programlama stilidir. Örneğin, aşağıdaki erişimci `number` alana her erişildiğinde nesnenin durumunu değiştirmenin yan etkisini üretir.  
  
 [!code-csharp[csProgGuideProperties#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#10)]  
  
 Erişimci `get` , alan değerini döndürmek veya hesaplamak ve döndürmek için kullanılabilir. Örneğin:  
  
 [!code-csharp[csProgGuideProperties#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#11)]  
  
 Önceki kod segmentinde, `Name` özelliğe bir değer atamadıysanız, değerini döndürür.  
  
## <a name="the-set-accessor"></a>Set erişimcisi  
 Erişimci `set` , dönüş türü [void](../../language-reference/keywords/void.md)olan bir yönteme benzer. Türü özelliğin türü olan adlı `value`örtük bir parametre kullanır. Aşağıdaki örnekte, `set` `Name` özelliğine bir erişimci eklenmiştir:  
  
 [!code-csharp[csProgGuideProperties#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#12)]  
  
 Özelliğe bir değer atadığınızda, `set` erişimci yeni değer sağlayan bir bağımsız değişken kullanılarak çağrılır. Örneğin:  
  
 [!code-csharp[csProgGuideProperties#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#13)]  
  
 `value` Bir`set` erişimcinin yerel değişken bildirimi için örtük parametre adını kullanmak hatadır.  
  
## <a name="remarks"></a>Açıklamalar  
 `public`Özellikler ,`internal`,, veya`private protected`olarakişaretlenebilir. `private` `protected` `protected internal` Bu erişim değiştiricileri, sınıfın kullanıcılarının özelliğe nasıl erişekullanabileceğinizi tanımlar. Aynı özelliğe `set` yönelik veerişimcilerifarklıerişimdeğiştiricilerinesahipolabilir.`get` Örneğin `get` `set` `private` `protected`, türü dışından salt okuma erişimine izin vermek olabilir ve ya da olabilir. `public` Daha fazla bilgi için bkz. [erişim değiştiricileri](./access-modifiers.md).  
  
 Özelliği `static` anahtar sözcüğü kullanılarak statik bir özellik olarak bildirilemez. Bu özellik, sınıfın bir örneği mevcut olmasa bile, özelliği herhangi bir zamanda çağıranlar için kullanılabilir hale getirir. Daha fazla bilgi için bkz. [statik sınıflar ve statik sınıf üyeleri](./static-classes-and-static-class-members.md).  
  
 Bir özellik [sanal](../../language-reference/keywords/virtual.md) anahtar sözcüğü kullanılarak sanal bir özellik olarak işaretlenebilir. Bu, türetilmiş sınıfların [geçersiz kılma](../../language-reference/keywords/override.md) anahtar sözcüğünü kullanarak özellik davranışını geçersiz kılmasını sağlar. Bu seçenekler hakkında daha fazla bilgi için bkz. [Devralma](./inheritance.md).  
  
 Sanal bir özelliği geçersiz kılan bir özellik de [mühürlenebilir](../../language-reference/keywords/sealed.md), bu da türetilmiş sınıflar için artık sanal değildir. Son olarak, bir özellik [soyut](../../language-reference/keywords/abstract.md)olarak bildirilemez. Bu, sınıfta bir uygulama olmadığı ve türetilen sınıfların kendi uygulamasını yazması gerektiği anlamına gelir. Bu seçenekler hakkında daha fazla bilgi için bkz. [soyut ve korumalı sınıflar ve sınıf üyeleri](./abstract-and-sealed-classes-and-class-members.md).  
  
> [!NOTE]
> [Statik](../../language-reference/keywords/static.md) bir özelliğin erişimcisi üzerinde [sanal](../../language-reference/keywords/virtual.md), [Özet](../../language-reference/keywords/abstract.md)veya [geçersiz kılma](../../language-reference/keywords/override.md) değiştiricisi kullanmak hatadır.  
  
## <a name="example"></a>Örnek  
 Bu örnek örnek, statik ve salt okunurdur özelliklerini gösterir. Klavye üzerinden çalışanın adını kabul eder, 1 artırır `NumberOfEmployees` ve çalışan adını ve numarasını görüntüler.  
  
 [!code-csharp[csProgGuideProperties#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#2)]  
  
## <a name="example"></a>Örnek  
 Bu örnek, türetilmiş bir sınıfta aynı ada sahip başka bir özellik tarafından gizlenen bir temel sınıftaki bir özelliğe nasıl erişebileceğinizi gösterir.  
  
 [!code-csharp[csProgGuideProperties#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#3)]  
  
 Aşağıda, önceki örnekteki önemli noktaları verilmiştir:  
  
- Türetilmiş sınıftaki `Name` özelliği, temel sınıftaki özelliği `Name` gizler. Böyle bir durumda, `new` değiştirici türetilmiş sınıftaki özelliğin bildiriminde kullanılır:  
  
     [!code-csharp[csProgGuideProperties#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#4)]  
  
- Atama `(Employee)` , temel sınıftaki gizli özelliğe erişmek için kullanılır:  
  
     [!code-csharp[csProgGuideProperties#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#5)]  
  
     Üyeleri gizleme hakkında daha fazla bilgi için bkz. [Yeni değiştirici](../../language-reference/keywords/new-modifier.md).  
  
## <a name="example"></a>Örnek  
 Bu örnekte `Cube` , iki sınıf, ve `Square`soyut bir sınıfı `Shape`uygular ve soyut `Area` özelliğini geçersiz kılar. Özelliklerde geçersiz kılma değiştiricisinin kullanımını göz önünde [kılarsınız](../../language-reference/keywords/override.md) . Program, yüzü bir giriş olarak kabul eder ve kare ve küpün alanını hesaplar. Ayrıca, alanı bir girdi olarak kabul eder ve kare ve küp için ilgili tarafı hesaplar.  
  
 [!code-csharp[csProgGuideProperties#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#6)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [C# Programlama Kılavuzu](../index.md)
- [Özellikler](./properties.md)
- [Arabirim Özellikleri](./interface-properties.md)
- [Otomatik Uygulanan Özellikler](./auto-implemented-properties.md)
