---
title: Visual Basic yenilikler
ms.date: 10/24/2018
f1_keywords:
- VB.StartPage.WhatsNew
helpviewer_keywords:
- new features, Visual Basic
- what's new [Visual Basic]
- Visual Basic, what's new
ms.assetid: d7e97396-7f42-4873-a81c-4ebcc4b6ca02
ms.openlocfilehash: 20d403e4a6410257068cc3414fcb8dc1e45709e9
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666872"
---
# <a name="whats-new-for-visual-basic"></a>Visual Basic yenilikler

Bu konu, dilin en son sürümlerindeki yeni ve geliştirilmiş özelliklerin ayrıntılı açıklamaları ile her bir Visual Basic sürümü için temel özellik adlarını listeler.

## <a name="current-version"></a>Güncel sürüm

Visual Basic 15,8/Visual Studio 2017 sürüm 15,8 yeni özellikler Için bkz. [Visual Basic 15,8](#visual-basic-158)

## <a name="previous-versions"></a>Önceki sürümler

Visual Basic 15,5/Visual Studio 2017 sürüm 15,5 yeni özellikler Için bkz. [Visual Basic 15,5](#visual-basic-155)

Visual Basic 15,3/Visual Studio 2017 sürüm 15,3 yeni özellikler Için bkz. [Visual Basic 15,3](#visual-basic-153)

Visual Basic 2017/Visual Studio 2017 yeni özellikler Için bkz. [Visual Basic 2017](#visual-basic-2017)

Visual Basic/Visual Studio 2015 yeni özellikler Için bkz. [Visual Basic 14](#visual-basic-14)

.NET Compiler Platform Visual Basic/Visual Studio 2013 teknoloji önizlemeleri ("Roslyn")

Visual Basic/Visual Studio 2012 `Async` ve `await` anahtar sözcükler, yineleyiciler, çağıran bilgi öznitelikleri

Visual Basic, Visual Studio 2010 otomatik uygulanan özellikler, koleksiyon başlatıcıları, örtük satır devamlılığı, dinamik, genel ortak/Contra varyansı, genel ad alanı erişimi

Visual Basic/Visual Studio 2008 dil ile tümleşik sorgu (LINQ), XML değişmez değerleri, yerel tür çıkarımı, nesne başlatıcıları, anonim türler, uzantı `var` yöntemleri, yerel tür çıkarımı `if` , lambda ifadeleri, işleç, kısmi Yöntemler, null yapılabilir değer türleri

Visual Basic/Visual Studio 2005 `My` tür ve yardımcı türleri (uygulama, bilgisayar, dosya sistemi, ağ erişimi)

Visual Basic/Visual Studio .NET 2003 bit kaydırma işleçleri, döngü değişkeni bildirimi

Visual Basic/Visual Studio .NET 2002 Visual Basic .NET ilk sürümü

## <a name="visual-basic-158"></a>Visual Basic 15,8

**En iyileştirilmiş kayan noktalı tamsayı dönüştürme**

Visual Basic önceki sürümlerinde, [çift](../language-reference/data-types/double-data-type.md) ve [tek](../language-reference/data-types/single-data-type.md) değerlerin tamsayılara, görece düşük performansa göre dönüştürülmesi gerekir. Visual Basic 15,8, aşağıdaki yöntemlerden herhangi biri tarafından döndürülen değeri [iç Visual Basic tamsayı dönüştürme işlevlerinden](../language-reference/functions/type-conversion-functions.md) birine geçirdiğinizde (CByte, CShort, CInt,) kayan nokta dönüştürmelerinden oluşan performansı önemli ölçüde artırır. CLng, CSByte, CUShort, CUInt, Külng) ya da aşağıdaki yöntemlerin herhangi biri tarafından döndürülen değer, [kesin seçeneği](../language-reference/statements/option-strict-statement.md) olarak `Off`ayarlandığında tam olarak bir integral türüne dönüştürülebilir:

- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Single)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Single)?displayProperty=nameWithType>
- <xref:System.Math.Ceiling(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Floor(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Round(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Truncate(System.Double)?displayProperty=nameWithType>

Bu iyileştirme kodun çok daha hızlı bir şekilde çalışmasını sağlar ve tamsayı türlerine çok sayıda dönüştürme yapan kod için hızlı bir şekilde daha hızlı çalışır. Aşağıdaki örnek, bu iyileştirmeden etkilenen bazı basit yöntem çağrılarını göstermektedir:

```vb
Dim s As Single = 173.7619
Dim d As Double = s

Dim i1 As Integer = CInt(Fix(s))               ' Result: 173
Dim b1 As Byte = CByte(Int(d))                 ' Result: 173
Dim s1 AS Short = CShort(Math.Truncate(s))     ' Result: 173
Dim i2 As Integer = CInt(Math.Ceiling(d))      ' Result: 174
Dim i3 As Integer = CInt(Math.Round(s))        ' Result: 174

```

Bu, kayan nokta değerlerini yuvarlar değil, bu fazlağa göz atar.

## <a name="visual-basic-155"></a>Visual Basic 15,5

[Girintili olmayan adlandırılmış bağımsız değişkenler](../programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md#mixing-arguments-by-position-and-by-name)

Visual Basic 15,3 ve önceki sürümlerde, bir yöntem bağımsız değişkenleri yalnızca konuma ve ada göre çağırarak, Konumsal bağımsız değişkenlerin adlandırılmış bağımsız değişkenlerden önce gelmesi gerekiyordu. Visual Basic 15,5 ' den başlayarak, son Konumsal bağımsız değişkene kadar olan tüm bağımsız değişkenler doğru konumda olduğu sürece konumsal ve adlandırılmış bağımsız değişkenler herhangi bir sırada görünebilir. Bu özellikle, kodu daha okunabilir hale getirmek için adlandırılmış bağımsız değişkenler kullanıldığında yararlıdır.

Örneğin, aşağıdaki yöntem çağrısının adlandırılmış bir bağımsız değişken arasında iki Konumsal bağımsız değişkeni vardır. Adlandırılmış bağımsız değişken, 19 değerinin bir yaşı temsil ettiğini açık hale getirir.

```vb
StudentInfo.Display("Mary", age:=19, #9/21/1998#)
```

[`Private Protected`üye erişim değiştiricisi](../language-reference/modifiers/private-protected.md)

Bu yeni anahtar sözcük birleşimi, kapsayan sınıf içindeki tüm üyeler tarafından erişilebilen bir üyeyi ve kapsayan sınıftan türetilmiş türleri, ancak yalnızca kapsayan derlemede bulunduklarında tanımlar. Yapılar devralınamadığı `Private Protected` için yalnızca bir sınıfın üyelerine uygulanabilir.

**Baştaki onaltılık/ikili/sekizlik ayırıcı**

Visual Basic 2017 alt çizgi karakteri (`_`) için rakam ayırıcısı olarak destek eklendi. Visual Basic 15,5 ' den başlayarak, alt çizgi karakterini ön ek ve onaltılık, ikili veya sekizlik basamaklar arasında önde gelen bir ayırıcı olarak kullanabilirsiniz. Aşağıdaki örnek, 3.271.948.384 onaltılık bir sayı olarak tanımlamak için önde gelen bir rakam ayırıcısı kullanır:

```vb
Dim number As Integer = &H_C305_F860
```

Alt çizgi karakterini baştaki ayırıcı olarak kullanmak için, Visual Basic projesi (\*. vbproj) dosyanıza aşağıdaki öğeyi eklemeniz gerekir:

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

## <a name="visual-basic-153"></a>Visual Basic 15,3

[**Adlandırılmış demet çıkarımı**](../programming-guide/language-features/data-types/tuples.md#inferred-tuple-element-names)

Kayıt düzeni öğelerinin değerini değişkenlerden atadığınızda, Visual Basic demet öğelerinin adını karşılık gelen değişken adlarından anlar. bir demet öğesini açıkça adlandırmak zorunda değilsiniz. Aşağıdaki örnek, üç adlandırılmış öğe, `state` `stateName`,, ve `capital`içeren bir tanımlama grubu oluşturmak için çıkarımı kullanır.

[!code-vb[Inferred tuple names](../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

**Ek derleyici anahtarları**

Visual Basic komut satırı derleyicisi artık başvuru derlemelerinin çıkışını denetlemek için [ **-refout**](../reference/command-line-compiler/refout-compiler-option.md) ve [ **-refonly**](../reference/command-line-compiler/refonly-compiler-option.md) derleyici seçeneklerini desteklemektedir. **-refout** , başvuru derlemesinin çıkış dizinini tanımlar ve **-refonly** yalnızca bir başvuru derlemesinin derleme tarafından çıkış olduğunu belirtir.

## <a name="visual-basic-2017"></a>Visual Basic 2017

[**Diziler**](../programming-guide/language-features/data-types/tuples.md)

Tanımlama grupları, en yaygın olarak tek bir yöntem çağrısından birden çok değer döndürmek için kullanılan hafif bir veri yapısıdır. Genellikle, bir yöntemden birden çok değer döndürmek için aşağıdakilerden birini yapmanız gerekir:

- Özel bir tür (a `Class` veya a `Structure`) tanımlayın. Bu, ağır bir çözümdür.

- Yönteminden bir değer döndürmenin yanı sıra bir veya daha fazla `ByRef` parametre tanımlayın.

Visual Basic, tanımlama gruplarını hızlıca tanımlamanızı, isteğe bağlı olarak anlam adlarını kendi değerlerine atamanızı ve değerlerini hızlıca almanızı sağlar. Aşağıdaki örnek <xref:System.Int32.TryParse%2A> yöntemine bir çağrı sarmalanmış ve bir tanımlama grubu döndürüyor.

[!code-vb[Tuple](../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

Daha sonra yöntemi çağırabilir ve döndürülen kayıt grubunu aşağıdaki gibi kodla işleyebilirsiniz.

[!code-vb[ReturnTuple](../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

**İkili sabit değerler ve basamak ayırıcıları**

Ya da `&B` `&b`önekini kullanarak bir ikili sabit değeri tanımlayabilirsiniz. Bunlara ek olarak, okunabilirliği artırmak için bir rakam ayırıcısı `_`olarak alt çizgi karakterini de kullanabilirsiniz. Aşağıdaki örnek her iki özelliği de bir `Byte` değer atamak ve ondalık, onaltılı ve ikili sayı olarak göstermek için kullanır.

[!code-vb[Binary](../../../samples/snippets/visualbasic/getting-started/bin-example.vb#1)]

Daha fazla bilgi için [byte](../language-reference/data-types/byte-data-type.md#literal-assignments), [Integer](../language-reference/data-types/integer-data-type.md#literal-assignments), [Long](../language-reference/data-types/long-data-type.md#literal-assignments), [Short](../language-reference/data-types/short-data-type.md#literal-assignments), [SByte](../language-reference/data-types/sbyte-data-type.md#literal-assignments), [UInteger](../language-reference/data-types/uinteger-data-type.md#literal-assignments), [ulong](../language-reference/data-types/ulong-data-type.md#literal-assignments)ve [ushort](../language-reference/data-types/ushort-data-type.md#literal-assignments) veri türlerindeki "değişmez değer atamaları" bölümüne bakın.

[Başvuru dönüş C# değerleri için destek](../programming-guide/language-features/procedures/ref-return-values.md)

7,0 ile C# başlayarak, C# başvuru dönüş değerlerini destekler. Diğer bir deyişle, çağırma yöntemi başvuruya göre döndürülen bir değer aldığında, başvurunun değerini değiştirebilir. Visual Basic, başvuru dönüş değerleri olan Yöntemler yazmanıza izin vermez, ancak başvuru dönüş değerlerini kullanmanıza ve değiştirmenize izin verir.

Örneğin, içinde C# yazılan aşağıdaki `Sentence` sınıf, belirtilen bir alt `FindNext` dizeyle başlayan bir tümcedeki sonraki sözcüğü bulan bir yöntemi içerir. Dize bir başvuru dönüş değeri olarak döndürülür ve yöntemine başvuruya göre geçirilen `Boolean` bir değişken aramanın başarılı olup olmadığını gösterir. Bu, arayanın yalnızca döndürülen değeri okuyamayacağı anlamına gelir; aynı zamanda değiştirebilir ve bu değişiklik `Sentence` sınıfında yansıtılır.

[!code-csharp[Ref-Return](../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

En basit biçimde, aşağıdaki gibi bir kod kullanarak tümcede bulunan kelimeyi değiştirebilirsiniz. Yöntemine bir değer atamayabileceğinizi, ancak yöntemin döndürdüğü ifadeye bunun yerine, başvuru dönüş değeri olduğunu unutmayın.

[!code-vb[Ref-Return](../../../samples/snippets/visualbasic/getting-started/ref-return.vb#1)]

Bu kodla ilgili bir sorun olsa da, bir eşleşme bulunmazsa yöntemin ilk sözcüğü döndürmesinin nedeni budur. Örnek, bir eşleşmenin bulunup bulunmadığını anlamak için `Boolean` bağımsız değişkenin değerini incelemediğinden, eşleşme yoksa ilk sözcüğü değiştirir. Aşağıdaki örnek, eşleşme yoksa ilk sözcüğü kendisiyle değiştirerek bunu düzeltir.

[!code-vb[Ref-Return](../../../samples/snippets/visualbasic/getting-started/ref-return.vb#2)]

Daha iyi bir çözüm, başvuru dönüş değerinin başvuruya göre geçirildiği bir yardımcı yöntem kullanmaktır. Yardımcı yöntemi daha sonra başvuruya göre kendisine geçirilen bağımsız değişkeni değiştirebilir. Aşağıdaki örnek bunu yapar.

[!code-vb[Ref-Return](../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

Daha fazla bilgi için bkz. [Başvuru dönüş değerleri](../programming-guide/language-features/procedures/ref-return-values.md).

## <a name="visual-basic-14"></a>Visual Basic 14

[NameOf](../../csharp/language-reference/operators/nameof.md)

Bir hata iletisinde kullanılmak üzere bir tür veya üyenin Nitelenmemiş dize adını bir dizeyi sabit kodlamadan alabilirsiniz.  Bu, yeniden düzenleme sırasında kodunuzun doğru kalmasını sağlar.  Bu özellik ayrıca Model-View-Controller MVC bağlantıları ve tetikleme özelliği değiştirilen olaylarını aramak için de kullanışlıdır.

[Dize ilişkilendirme](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md)

Dizeler oluşturmak için dize ilişkilendirme ifadeleri kullanabilirsiniz.  Enterpolasyonlu bir dize ifadesi ifade içeren bir şablon dizesi gibi görünür.  Enterpolasyonlu bir dizenin, [bileşik biçimlendirmeye](../../standard/base-types/composite-format.md)göre bağımsız değişkenlere göre anlaşılması daha kolay.

[Null koşullu üye erişimi ve dizin oluşturma](../language-reference/operators/null-conditional-operators.md)

Üye erişimi (`?.`) veya dizin (`?[]`) işlemini gerçekleştirmeden önce çok hafif bir şekilde null için test edebilirsiniz.  Bu işleçler, özellikle veri yapılarına göre azalan şekilde null denetimleri işlemek için daha az kod yazmanıza yardımcı olur.  Sol işlenen veya nesne başvurusu null ise, işlemler null döndürür.

[Çok satırlı dize sabit değerleri](../../visual-basic/programming-guide/language-features/strings/string-basics.md)

Dize sabit değerleri, yeni satır dizileri içerebilir.  Artık eski bir iş için kullanmak zorunda kalmayacak`<xml><![CDATA[...text with newlines...]]></xml>.Value`

**Açıklamalar**

Örtük satır devamlılıkları, başlatıcı ifadeleri içinde ve LINQ ifade terimleri arasında açıklama koyabilirsiniz.

**Daha akıllı tam ad çözümlemesi**

Gibi bilinen kod `Threading.Thread.Sleep(1000)`, "Threading" ad alanını aramak için kullanılan Visual Basic, System. Threading ve System. Windows. Threading arasında belirsizdir ve sonra bir hata bildirin.  Visual Basic artık olası ad alanlarını birlikte kabul eder.  Tamamlanma listesini gösterdiğinizde, Visual Studio Düzenleyicisi tamamlama listesindeki her iki türden üyeleri listeler.

**Yıl-ilk tarih sabit değerleri**

Tarih sabit değerlerini YYYY-AA-GG biçiminde `#2015-03-17 16:10 PM#`olabilir.

**ReadOnly arabirim özellikleri**

Salt okunur Arabirim özelliklerini bir ReadWrite özelliğini kullanarak uygulayabilirsiniz.  Arabirim minimum işlevselliği garanti eder ve bir uygulama sınıfının ayarlanmasının izin vermesini durdurmaz.

[TypeOf \<Expr > IsNot \<türü >](../../visual-basic/language-reference/operators/typeof-operator.md)

Kodunuzun daha okunaklı olması için artık ile `TypeOf` `IsNot`kullanabilirsiniz.

[#Disable Uyarı \<kimliği > ve #Enable Uyarı \<kimliği >](../../visual-basic/language-reference/directives/index.md)

Kaynak dosya içindeki bölgeler için belirli uyarıları devre dışı bırakabilir ve etkinleştirebilirsiniz.

**XML belgesi açıklaması geliştirmeleri**

Belge açıklamalarını yazarken, akıllı Düzenleyici ve parametre adlarını doğrulama, uygun işleme `crefs` (genel türler, işleçler, vb.), renklendirme ve yeniden düzenleme desteği alırsınız.

[Kısmi modül ve arabirim tanımları](../../visual-basic/language-reference/modifiers/partial.md)

Sınıfların ve yapıların yanı sıra, kısmi modüller ve arabirimler bildirebilirsiniz.

[Yöntem gövdeleri içinde #Region yönergeleri](../../visual-basic/language-reference/directives/region-directive.md)

#Region... #End bölge sınırlayıcılarını bir dosyada, işlevlerin içine, hatta işlev gövdelerine yayılan bir yere koyabilirsiniz.

[Geçersiz kılmalar tanımları örtük aşırı yüklemelerdir](../../visual-basic/language-reference/modifiers/overrides.md)

`Overrides` Değiştiricisini bir tanıma eklerseniz, derleyici ortak durumlarda daha az kod yazabileceğiniz şekilde `Overloads` dolaylı olarak ekler.

**Öznitelikler bağımsız değişkenlerinde CObj 'a izin verilir**

Derleyici, kurulumlarını özniteliğinde kullanıldığında CObj (...) öğesinin sabit olmadığı bir hata vermek için kullanılır.

**Farklı arabirimlerde belirsiz Yöntemler bildirme ve kullanma**

Daha önce aşağıdaki kod, çağrı yapmak `IMock` veya çağırmak `GetDetails` için (Bu, ' de C#bildirildiği takdirde) hata veren hatalara sahiptir:

```vb
Interface ICustomer
  Sub GetDetails(x As Integer)
End Interface

Interface ITime
  Sub GetDetails(x As String)
End Interface

Interface IMock : Inherits ICustomer, ITime
  Overloads Sub GetDetails(x As Char)
End Interface

Interface IMock2 : Inherits ICustomer, ITime
End Interface
```

Derleyici, en uygun `GetDetails` çözümü seçmek için normal aşırı yükleme çözümleme kurallarını kullanacaktır ve örnekte gösterilenler gibi Visual Basic arabirim ilişkilerini bildirebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio 2017'deki yenilikler](/visualstudio/ide/whats-new-in-visual-studio)
