---
title: Option Strict ekstresi (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Strict
- vb.OptionStrict
helpviewer_keywords:
- Strict keyword [Visual Basic]
- Option Strict statement [Visual Basic]
- conversions [Visual Basic], implicit
- late binding [Visual Basic]
- implicit conversions [Visual Basic]
ms.assetid: 5883e0c1-a920-4274-8e46-b0ff047eaee5
ms.openlocfilehash: a8466cb0672ccf26717d012bdebb7363f31ebb08
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912264"
---
# <a name="option-strict-statement"></a>Option Strict Deyimi
Örtük veri türü dönüşümlerini yalnızca genişletme dönüştürmelerine kısıtlar, geç bağlamaya izin vermez ve bir `Object` tür ile sonuçlanan örtülü yazmaya izin vermez.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Option Strict { On | Off }  
```  
  
## <a name="parts"></a>Bölümler  
  
|Terim|Tanım|  
|---|---|  
|`On`|İsteğe bağlı. Denetlemeye `Option Strict` izin vermez.|  
|`Off`|İsteğe bağlı. Denetlemeyi `Option Strict` devre dışı bırakır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir `Option Strict On` dosyada `Option Strict` olduğunda veya göründüğünde, aşağıdaki koşullar derleme zamanı hatasına neden olur:  
  
- Örtük daraltma dönüşümleri  
  
- Geç bağlama  
  
- Bir `Object` tür ile sonuçlanan örtük yazma  
  
> [!NOTE]
> [Derleme sayfasında, proje Tasarımcısı 'nda (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)ayarlayabileceğiniz uyarı yapılandırmalarında, derleme zamanı hatasına neden olan üç koşula karşılık gelen üç ayar vardır. Bu ayarların nasıl kullanılacağı hakkında daha fazla bilgi için, bu konunun ilerleyen kısımlarında [IDE 'de uyarı yapılandırması ayarlamak için](../../../visual-basic/language-reference/statements/option-strict-statement.md#conditions) bölümüne bakın.  
  
 `Option Strict Off` İfade, ilişkili IDE ayarları bu hataları veya uyarıları açmak için belirtse bile, her üç koşulun hata ve uyarı denetimini devre dışı bırakır. `Option Strict On` İfade, ilişkili IDE ayarları bu hataları veya uyarıları kapatmak için belirtse bile, her üç koşulun hata ve uyarı denetimini etkinleştirir.  
  
 Kullanıldıysa, `Option Strict` deyimi bir dosyadaki diğer kod deyimlerinin önüne gelmelidir.  
  
 `Option Strict` Olarak`On`ayarladığınızda, Visual Basic tüm programlama öğeleri için veri türlerinin belirtildiğini denetler. Veri türleri açıkça belirtilebilir veya yerel tür çıkarımı kullanılarak belirtilebilir. Aşağıdaki nedenlerden dolayı tüm programlama öğelerinizin veri türlerini belirtme önerilir:  
  
- Değişkenleriniz ve parametreleriniz için IntelliSense desteği sunar. Bu, kod yazarken özelliklerini ve diğer üyelerini görmenizi sağlar.  
  
- Derleyicinin tür denetlemesi gerçekleştirmesini sağlar. Tür denetimi, tür dönüştürme hataları nedeniyle çalışma zamanında başarısız olan deyimler bulmanıza yardımcı olur. Ayrıca, bu yöntemleri desteklemeyen nesnelerdeki yöntemlere yapılan çağrıları tanımlar.  
  
- Kod yürütülmesini hızlandırır. Bunun bir nedeni, bir programlama öğesi için bir veri türü belirtplanlamıyorsanız Visual Basic derleyicisinin bu `Object` türü atamasını sağlamaz. Derlenmiş kodun ve diğer veri türleri arasında `Object` geri ve ileri dönüştürülmesi gerekebilir ve bu da performansı azaltır.  
  
## <a name="implicit-narrowing-conversion-errors"></a>Örtük daraltma dönüştürme hataları  
 Örtük daraltma dönüştürme hataları, daraltma dönüştürmesi olan bir örtük veri türü dönüştürmesi olduğunda oluşur.  
  
 Visual Basic, birçok veri türünü diğer veri türlerine dönüştürebilir. Bir veri türünün değeri, daha az duyarlık veya daha küçük bir kapasiteye sahip bir veri türüne dönüştürüldüğünde veri kaybı oluşabilir. Bu tür bir daraltma dönüştürmesi başarısız olursa, bir çalışma zamanı hatası oluşur. `Option Strict`Bu daraltma dönüştürmelerinde derleme zamanı bildirimini sağlar, böylece bunları önleyebilirsiniz. Daha fazla bilgi için bkz. [örtük ve açık dönüştürmeler](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) ve [genişletme ve daraltma dönüştürmeleri](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 Hatalara neden olabilecek dönüştürmeler, ifadelerde oluşan örtük dönüşümler içerir. Daha fazla bilgi için aşağıdaki konulara bakın:  
  
- [+ İşleci](../../../visual-basic/language-reference/operators/addition-operator.md)  
  
- [+= İşleci](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
  
- [\ İşleci (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
  
- [/= İşleci (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
  
- [Char Veri Türü](../../../visual-basic/language-reference/data-types/char-data-type.md)  
  
 [& işlecini](../../../visual-basic/language-reference/operators/concatenation-operator.md)kullanarak dizeleri birleştirme sırasında, dizelerin tüm dönüştürmeleri genişletme olarak kabul edilir. Bu nedenle, açık olsa bile `Option Strict` bu dönüştürmeler örtük bir daraltma dönüştürme hatası oluşturmaz.  
  
 Karşılık gelen parametresinden farklı bir veri türüne sahip bir bağımsız değişkeni olan bir yöntemi çağırdığınızda, bir daraltma dönüştürmesi açık olursa `Option Strict` derleme zamanı hatasına neden olur. Bir genişletme dönüşümü veya açık bir dönüştürme kullanarak derleme zamanı hatasından kaçınabilirsiniz.  
  
 Örtük daraltma dönüştürme hataları, bir `For Each…Next` koleksiyondaki öğelerden döngü denetim değişkenine dönüşümler için derleme zamanında bastırılır. Açık olsa bile `Option Strict` bu durum oluşur. Daha fazla bilgi için, her biri Için içindeki "dönüştürmeleri daraltma" bölümüne bakın [... Sonraki Ifade](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
## <a name="late-binding-errors"></a>Geç bağlama hataları  
 Bir nesne, tür `Object`olarak belirtilen bir özelliğin veya yöntemin bir özelliğine atandığında geç bağlanır. Daha fazla bilgi için bkz. [erken ve geç bağlama](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md).  
  
## <a name="implicit-object-type-errors"></a>Örtük nesne türü hataları  
 Örtük nesne türü hataları, tanımlı bir değişken için uygun bir tür çıkarsanmadığında oluşur, bu nedenle bir türü `Object` algılanır. Bu öncelikle, bir `Dim` `As` yan tümce kullanmadan bir değişkeni bildirmek için bir deyimi kullandığınızda oluşur ve `Option Infer` kapalı olur. Daha fazla bilgi için bkz. [Option Infer deyimleri](../../../visual-basic/language-reference/statements/option-infer-statement.md) ve [Visual Basic Language belirtimi](../../../visual-basic/reference/language-specification/index.md).  
  
 Yöntem parametreleri `As` için, yan tümcesi kapalıysa `Option Strict` isteğe bağlıdır. Ancak, herhangi bir parametre bir `As` yan tümce kullanıyorsa, tümünün onu kullanması gerekir. `Option Strict` Açık ise`As` , yan tümce her parametre tanımı için gereklidir.  
  
 Bir `As` yan tümce kullanmadan bir değişken bildirir ve öğesini olarak `Nothing`ayarlarsanız, `Object`değişkenin türü vardır. Bu durumda açık ve `Option Strict` `Option Infer` açık olduğunda derleme zamanı hatası oluşmaz. Buna bir örnektir `Dim something = Nothing`.  
  
### <a name="default-data-types-and-values"></a>Varsayılan veri türleri ve değerleri  
 Aşağıdaki tabloda, bir [Dim ifadesinde](../../../visual-basic/language-reference/statements/dim-statement.md)veri türünü ve başlatıcıyı belirtmenin çeşitli birleşimlerinin sonuçları açıklanmaktadır.  
  
|Veri türü belirtildi mi?|Başlatıcı belirtildi mi?|Örnek|Sonuç|  
|---|---|---|---|  
|Hayır|Hayır|`Dim qty`|Kapalıysa (varsayılan), değişkeni olarak `Nothing`ayarlanır. `Option Strict`<br /><br /> `Option Strict` Açık ise, bir derleme zamanı hatası oluşur.|  
|Hayır|Evet|`Dim qty = 5`|`Option Infer` Açık ise (varsayılan), değişkeni başlatıcının veri türünü alır. Bkz. [Yerel tür çıkarımı](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Kapalıysa ve `Option Strict` kapalıysa, değişken veri türünü `Object`alır. `Option Infer`<br /><br /> `Option Infer` Kapalıysa ve`Option Strict` açık ise, bir derleme zamanı hatası oluşur.|  
|Evet|Hayır|`Dim qty As Integer`|Değişken, veri türü için varsayılan değer olarak başlatılır. Daha fazla bilgi için bkz. [Dim deyimleri](../../../visual-basic/language-reference/statements/dim-statement.md).|  
|Evet|Evet|`Dim qty  As Integer = 5`|Başlatıcının veri türü belirtilen veri türüne dönüştürülebilir değilse, bir derleme zamanı hatası oluşur.|  
  
## <a name="when-an-option-strict-statement-is-not-present"></a>Option Strict bir Ifade yoksa  
 Kaynak kodu bir `Option Strict` ifade içermiyorsa, derleme sayfasındaki **katı ayar seçeneğini** , [Proje Tasarımcısı (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) kullanılır. **Derleme sayfasında** , hata oluşturan koşullar üzerinde ek denetim sağlayan ayarlar bulunur.  
  
 Komut satırı derleyicisini kullanıyorsanız, bir ayarı `Option Strict`belirtmek için [/OptionStrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) derleyici seçeneğini kullanabilirsiniz.  
  
### <a name="to-set-option-strict-in-the-ide"></a>IDE 'de Option Strict ayarlamak için  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
1. **Çözüm Gezgini**bir proje seçin. **Proje** menüsünde **Özellikler**' e tıklayın.  
  
2. **Derle** sekmesinde, **katı kutu seçeneğini** belirleyin.  
  
### <a name="conditions"></a>IDE 'de uyarı yapılandırması ayarlamak için  
 Derleme sayfasını, bir `Option Strict` ifade yerine [Proje Tasarımcısı (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) kullandığınızda, hata oluşturan koşullar üzerinde ek denetime sahip olursunuz. **Derleme sayfasının** `Option Strict` **Uyarı yapılandırması** bölümü, açık olduğunda derleme zamanı hatasına neden olan üç koşula karşılık gelen ayarlara sahiptir. Aşağıdaki ayarlar şunlardır:  
  
- **Örtük dönüştürme**  
  
- **Geç bağlama; çağrı çalışma zamanında başarısız olabilir**  
  
- **Örtük tür; nesne varsayıldı**  
  
 **Option Strict** **on on**olarak ayarlandığında, bu uyarı yapılandırma ayarlarının üçü de **hata**olarak ayarlanır. **Option Strict** ' i **off**olarak ayarlarsanız, üç ayar **hiçbiri None**olarak ayarlanır.  
  
 Her uyarı yapılandırma ayarını **hiçbiri**, **Uyarı**veya **hata**olarak tek tek değiştirebilirsiniz. Üç uyarı yapılandırma ayarı **hata**olarak ayarlanırsa, `On` `Option strict` kutusunda görünür. Üçü de **hiçbiri**olarak ayarlandıysa, `Off` bu kutuda görüntülenir. Bu ayarların diğer birleşimleri için **(özel)** görüntülenir.  
  
### <a name="to-set-the-option-strict-default-setting-for-new-projects"></a>Yeni projeler için katı varsayılan ayar seçeneğini ayarlamak için  
 Bir proje oluşturduğunuzda, **Derle** sekmesindeki **katı** ayarı **Seçenekler** iletişim kutusunda **katı** ayarına ayarlanır.  
  
 Bu iletişim `Option Strict` kutusunda ayarlamak için, **Araçlar** menüsünde **Seçenekler**' e tıklayın. **Seçenekler** iletişim kutusunda, **Projeler ve çözümler**' i genişletin ve ardından **vb Varsayılanları**' na tıklayın. Vb`Off`varsayılan olarak ilk varsayılan ayar.  
  
### <a name="to-set-option-strict-on-the-command-line"></a>Komut satırında Strict seçeneğini ayarlamak için  
 **Vbc** komutuna [/OptionStrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) derleyici seçeneğini ekleyin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örneklerde, dönüştürmeleri daraltma örtük tür dönüştürmelerinden kaynaklanan derleme zamanı hataları gösterilmektedir. Bu hata kategorisi, **derleme sayfasındaki** **örtük dönüştürme** koşuluna karşılık gelir.  
  
 [!code-vb[VbVbalrStatements#161](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#161)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, geç bağlamanın neden olduğu bir derleme zamanı hatası gösterir. Bu hata kategorisi, geç bağlamaya karşılık gelir; çağrı **derleme sayfasındaki** **çalışma zamanında başarısız olabilir** .  
  
 [!code-vb[VbVbalrStatements#162](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#162)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örneklerde, örtülü bir türle `Object`belirtilen değişkenlerin neden olduğu hatalar gösterilmektedir. Bu hata kategorisi, **derleme sayfasındaki** **örtük tür; nesne varsayıldı** koşulunu karşılık gelir.  
  
 [!code-vb[VbVbalrStatements#163](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#163)]  
  
 [!code-vb[VbVbalrStatements#164](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class13.vb#164)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Genişletme ve Daraltma Dönüştürmeleri](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Örtük ve Açık Dönüştürmeler](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Derleme Sayfası, Proje Tasarımcısı (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [Option Explicit Deyimi](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Tür Dönüştürme İşlevleri](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Nasıl yapılır: Bir nesnenin üyelerine erişin](../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)
- [XML'de Katıştırılmış İfadeler](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [Gevşek Temsilci Dönüştürme](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Office Çözümlerinde Geç Bağlama](/visualstudio/vsto/late-binding-in-office-solutions)
- [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [Visual Basic Varsayılanları, Projeler, Seçenekler İletişim Kutusu](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
