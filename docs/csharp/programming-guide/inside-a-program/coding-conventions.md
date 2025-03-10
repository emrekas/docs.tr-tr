---
title: C#Kodlama kuralları- C# Programlama Kılavuzu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions, C#
- Visual C#, coding conventions
- C# language, coding conventions
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
ms.openlocfilehash: 27001d1697def083580ecdc742b4b8db924545aa
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589420"
---
# <a name="c-coding-conventions-c-programming-guide"></a>C# Kodlama Kuralları (C# Programlama Kılavuzu)
 Kodlama kuralları aşağıdaki amaçlara hizmet eder:  
  
- Bunlar, koda tutarlı bir görünüm oluşturur, böylece okuyucular düzene göre değil, içeriğe odaklanabilir.  
  
- Bu kullanıcılar, önceki deneyimle dayalı varsayımlar yaparak okuyucuların kodu daha hızlı anlamasına imkan sağlar.  
  
- Kodu kopyalama, değiştirme ve sürdürme işlemlerini kolaylaştırır.  
  
- En iyi C# uygulamaları gösterir.  

 Bu konudaki yönergeler, Microsoft tarafından örnek ve belge geliştirmek için kullanılır.  
  
## <a name="naming-conventions"></a>Adlandırma Kuralları  
  
- [Using yönergeleri](../../language-reference/keywords/using-directive.md)dahil olmayan kısa örneklerde ad alanı nitelikleri kullanın. Bir ad alanının bir projede varsayılan olarak içeri aktarıldığını biliyorsanız, adları bu ad alanından tam olarak nitelemeniz gerekmez. Nitelenmiş adlar, aşağıdaki örnekte gösterildiği gibi, tek bir satırda çok uzunsa bir nokta (.) sonrasında bozulabilir.  
  
     [!code-csharp[csProgGuideCodingConventions#1](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#1)]  
  
- Visual Studio tasarımcı araçları kullanılarak oluşturulan nesnelerin adlarını, diğer yönergelere uyum sağlamak için değiştirmeniz gerekmez.  
  
## <a name="layout-conventions"></a>Düzeni Kuralları  
 İyi düzen, kodunuzun yapısını vurgulamak ve kodun daha kolay okunmasını sağlamak için biçimlendirme kullanır. Microsoft örnekleri ve örnekleri aşağıdaki kurallara uygun şekilde yapılır:  
  
- Varsayılan kod Düzenleyicisi ayarlarını (akıllı girintileme, dört karakterlik girintiler, sekmeler boşluk olarak kaydedilir) kullanın. Daha fazla bilgi için bkz. [Seçenekler, metin düzenleyici C#,, biçimlendirme](/visualstudio/ide/reference/options-text-editor-csharp-formatting).  
  
- Her satırda yalnızca bir ifade yazın.  
  
- Her satırda yalnızca bir bildirim yazın.  
  
- Devamlılık satırları otomatik olarak girintili değilse, bir sekme durağı (dört boşluk) için girinti yapın.  
  
- Yöntem tanımları ve özellik tanımları arasına en az bir boş satır ekleyin.  
  
- Aşağıdaki kodda gösterildiği gibi, bir ifadedeki tümceleri görünür hale getirmek için parantezleri kullanın.  
  
     [!code-csharp[csProgGuideCodingConventions#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#2)]  
  
## <a name="commenting-conventions"></a>Yorum Oluşturma Kuralları  
  
- Yorumu bir kod satırının sonuna değil, ayrı bir satıra yerleştirin.  
  
- Açıklama metnini büyük harfle Başlat.  
  
- Açıklama metnini noktayla bitirin.  
  
- Aşağıdaki örnekte gösterildiği gibi açıklama sınırlayıcısı (//) ve açıklama metni arasına bir boşluk ekleyin.  
  
     [!code-csharp[csProgGuideCodingConventions#3](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#3)]  
  
- Açıklamaların etrafında, biçimli yıldız işaretleri oluşturmayın.  
  
## <a name="language-guidelines"></a>Dil Kuralları  
 Aşağıdaki bölümlerde, C# takımın kod örneklerini ve örnekleri hazırlamak için izlediği uygulamalar açıklanır.  
  
### <a name="string-data-type"></a>Dize Veri Türü  
  
- Aşağıdaki kodda gösterildiği gibi, kısa dizeleri birleştirmek için [dize ilişkilendirmeyi](../../language-reference/tokens/interpolated.md) kullanın.  
  
     [!code-csharp[csProgGuideCodingConventions#6](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#6)]  
  
- Özellikle büyük miktarlarda metinle çalışırken, Döngülerde dizeler eklemek için bir <xref:System.Text.StringBuilder> nesnesi kullanın.  
  
     [!code-csharp[csProgGuideCodingConventions#7](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#7)]  
  
### <a name="implicitly-typed-local-variables"></a>Örtülü Olarak Yazılan Yerel Değişkenler  
  
- Değişkenin türü atamanın sağ tarafından açık olduğunda veya kesin tür önemli olmadığında yerel değişkenler için [örtülü yazma](../classes-and-structs/implicitly-typed-local-variables.md) kullanın.  
  
     [!code-csharp[csProgGuideCodingConventions#8](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#8)]  
  
- Tür atamanın sağ [](../../language-reference/keywords/var.md) tarafından görünmüyorsa, yok kullanmayın.  
  
     [!code-csharp[csProgGuideCodingConventions#9](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#9)]  
  
- Değişkenin türünü belirtmek için değişken adına güvenmeyin. Doğru olmayabilir.  
  
     [!code-csharp[csProgGuideCodingConventions#10](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#10)]  
  
- `var` [Dinamik](../../language-reference/keywords/dynamic.md)yerine kullanılmasını önleyin.  
  
- [For](../../language-reference/keywords/for.md) ve [foreach](../../language-reference/keywords/foreach-in.md) döngüleri içindeki döngü değişkeninin türünü öğrenmek için örtük yazma kullanın.  
  
     Aşağıdaki örnek, bir `for` bildiriminde örtük yazma kullanır.  
  
     [!code-csharp[csProgGuideCodingConventions#7](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#7)]  
  
     Aşağıdaki örnek, bir `foreach` bildiriminde örtük yazma kullanır.  
  
     [!code-csharp[csProgGuideCodingConventions#12](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#12)]  
  
### <a name="unsigned-data-type"></a>İmzasız Veri Türü  
  
- Genel olarak, imzasız `int` türler yerine kullanın. Kullanımı `int` genelinde C#yaygın olarak kullanılır ve kullandığınızda `int`diğer kitaplıklarla etkileşim kurmak daha kolaydır.  
  
### <a name="arrays"></a>Diziler  
  
- Bildirim satırında dizileri başlattığınızda kısa sözdizimini kullanın.  
  
     [!code-csharp[csProgGuideCodingConventions#13](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#13)]  
  
### <a name="delegates"></a>Temsilciler  
  
- Bir temsilci türünün örneklerini oluşturmak için kısa sözdizimini kullanın.  
  
     [!code-csharp[csProgGuideCodingConventions#14](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#14)]  
  
     [!code-csharp[csProgGuideCodingConventions#15](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#15)]  
  
### <a name="try-catch-and-using-statements-in-exception-handling"></a>try-catch ve Özel Durum İşleme bölümünde Deyimleri kullanma  
  
- Çoğu özel durum işleme için [try-catch](../../language-reference/keywords/try-catch.md) ifadesini kullanın.  
  
     [!code-csharp[csProgGuideCodingConventions#16](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#16)]  
  
- C# [Using ifadesini](../../language-reference/keywords/using-statement.md)kullanarak kodunuzu kolaylaştırın. Yalnızca `finally` bloktaki kodun <xref:System.IDisposable.Dispose%2A> yöntemine yönelik bir çağrı olduğu bir [try-finally](../../language-reference/keywords/try-finally.md) deyiminiz varsa, bunun yerine bir `using` ifade kullanın.  
  
     [!code-csharp[csProgGuideCodingConventions#17](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#17)]  
  
### <a name="-and-124124-operators"></a>& & ve &#124; &#124; işleçler  
  
- Özel durumların önüne geçmek ve gereksiz karşılaştırmaları atlayarak performansı artırmak için, [&&](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-and-operator-) aşağıdaki örnekte gösterildiği [ &#124; ](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-or-operator-) gibi karşılaştırmaları [&#124;](../../language-reference/operators/boolean-logical-operators.md#logical-or-operator-) gerçekleştirirken yerine kullanın [&](../../language-reference/operators/boolean-logical-operators.md#logical-and-operator-) .  
  
     [!code-csharp[csProgGuideCodingConventions#18](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#18)]  
  
### <a name="new-operator"></a>Yeni İşleç  
  
- Aşağıdaki bildirimde gösterildiği gibi örtük olarak yazılan nesne örneğinin kısa biçimini kullanın.  
  
     [!code-csharp[csProgGuideCodingConventions#19](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#19)]  
  
     Önceki satır aşağıdaki bildirime eşdeğerdir.  
  
     [!code-csharp[csProgGuideCodingConventions#20](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#20)]  
  
- Nesne oluşturma işlemini basitleştirmek için nesne başlatıcıları kullanın.  
  
     [!code-csharp[csProgGuideCodingConventions#21](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#21)]  
  
### <a name="event-handling"></a>Olay İşleme  
  
- Daha sonra kaldırmanız gerekmeyen bir olay işleyicisi tanımlıyorsanız, bir lambda ifadesi kullanın.  
  
     [!code-csharp[csProgGuideCodingConventions#22](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#22)]  
  
     [!code-csharp[csProgGuideCodingConventions#23](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#23)]  
  
### <a name="static-members"></a>Statik Üyeler  
  
- Sınıf adını kullanarak [statik](../../language-reference/keywords/static.md) üyeleri çağırın: *ClassName. StaticMember*. Bu uygulama, statik erişim Temizleme yaparak kodu daha okunabilir hale getirir.  Türetilmiş bir sınıf adına sahip bir temel sınıfta tanımlanan statik bir üyeyi nitelemeyin.  Kod derlense de, kod okunurluğu yanıltıcı olur ve türetilmiş sınıfa aynı ada sahip bir statik üye eklerseniz kod daha sonra bozulabilir.  
  
### <a name="linq-queries"></a>LINQ Sorguları  
  
- Sorgu değişkenleri için anlamlı adlar kullanın. Aşağıdaki örnek Seattle 'da `seattleCustomers` bulunan müşteriler için kullanır.  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
- Anonim türlerin özellik adlarının, Pascal büyük küçük harf kullanarak doğru şekilde büyük harfli olduğundan emin olmak için diğer adları kullanın.  
  
     [!code-csharp[csProgGuideCodingConventions#26](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#26)]  
  
- Sonuç içindeki Özellik adları belirsiz olduğunda özellikleri yeniden adlandırın. Örneğin, sorgunuz bir müşteri adı ve bir dağıtıcı `Name` kimliği döndürürse, ve `ID` sonuç olarak bırakmak yerine, bir müşterinin adı olduğunu ve `ID` bir dağıtıcının kimliğini açıklığa kavuşturacak `Name` şekilde yeniden adlandırın.  
  
     [!code-csharp[csProgGuideCodingConventions#27](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#27)]  
  
- Sorgu değişkenleri ve Aralık değişkenleri bildiriminde örtük yazma kullanın.  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
- Önceki örneklerde gösterildiği gibi, [from](../../language-reference/keywords/from-clause.md) yan tümcesinin altındaki sorgu yan tümcelerini hizalayın.  
  
- Daha sonra sorgu yan tümcelerinin azaltılmış ve filtrelenmiş veri kümesi üzerinde çalışmasını sağlamak için diğer sorgu yan tümcelerinden önce [WHERE](../../language-reference/keywords/where-clause.md) yan tümceleri kullanın.  
  
     [!code-csharp[csProgGuideCodingConventions#29](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#29)]  
  
- İç koleksiyonlara `from` erişmek için [JOIN](../../language-reference/keywords/join-clause.md) yan tümcesi yerine birden çok yan tümce kullanın. Örneğin, bir `Student` nesne koleksiyonu her biri bir test puanları koleksiyonu içerebilir. Aşağıdaki sorgu yürütüldüğünde, puanı alan öğrencinin son adıyla birlikte 90 ' ten fazla olan her puanı döndürür.  
  
     [!code-csharp[csProgGuideCodingConventions#30](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#30)]  
  
## <a name="security"></a>Güvenlik  
 [Güvenli kodlama yönergeleri](../../../standard/security/secure-coding-guidelines.md)bölümündeki yönergeleri izleyin.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Visual Basic kodlama kuralları](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)
- [Güvenli Kodlama Yönergeleri](../../../standard/security/secure-coding-guidelines.md)
