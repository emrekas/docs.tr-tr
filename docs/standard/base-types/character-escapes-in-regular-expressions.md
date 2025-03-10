---
title: .NET normal Ifadelerinde karakter kaçışları
description: .NET normal ifadelerinde özel karakterler ve kaçış karakterleri hakkında bilgi edinin.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- unescaped characters
- replacement patterns
- characters, escapes
- regular expressions, character escapes
- escape characters
- .NET Framework regular expressions, character escapes
- constructs, character escapes
ms.assetid: f49cc9cc-db7d-4058-8b8a-422bc08b29b0
author: rpetrusha
ms.author: ronpet
ms.custom: seodec18
ms.openlocfilehash: 248d434f7aad56d84d952fa27cf49f3d370f4a1c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934826"
---
# <a name="character-escapes-in-regular-expressions"></a>Normal İfadelerdeki Karakter Çıkışları
Normal ifadede ters\\eğik çizgi () aşağıdakilerden birini belirtir:  
  
- Aşağıdaki bölümde gösterildiği gibi, bu karakteri izleyen karakter özel bir karakterdir. Örneğin, `\b` bir normal ifade eşleşmesinin bir sözcük sınırında başlaması gerektiğini belirten bir bağlantıdır, `\t` bir sekmeyi temsil eder ve `\x020` bir alanı temsil eder.  
  
- Aksi halde, kaçışsız bir dil yapısı olarak yorumlanabilecek bir karakter, tam olarak yorumlanmalıdır. Örneğin, bir küme ayracı (`{`) bir nicelik tanımının tanımını başlatır, ancak bir ters eğik çizgiden sonra bir ayraç (`\{`), normal ifade altyapısının küme ayracı ile eşleşmesi gerektiğini gösterir. Benzer şekilde, tek bir ters eğik çizgi, kaçan dil yapısının başlangıcını işaret ediyor, ancak`\\`iki ters eğik çizgi (), normal ifade altyapısının ters eğik çizgiyle eşleşmesi gerektiğini gösterir.  
  
> [!NOTE]
> Karakter kaçışları normal ifade desenlerinde tanınır ancak değiştirme desenlerinde kabul edilmez.  
  
## <a name="character-escapes-in-net"></a>.NET 'teki karakter kaçışları  
 Aşağıdaki tabloda, .NET 'teki normal ifadeler tarafından desteklenen karakter çıkışları listelenmektedir.  
  
|Karakter veya sıra|Açıklama|  
|---------------------------|-----------------|  
|Aşağıdakiler hariç tüm karakterler:<br /><br /> biçimindeki telefon numarasıdır. $ ^ { [ ( &#124; ) * + ? \ |**Karakter veya dizi** sütununda listelenenler dışındaki karakterlerin normal ifadelerde özel bir anlamı yoktur; Bunlar kendileriyle eşleşir.<br /><br /> **Karakter veya dizi** sütununa dahil edilen karakterler özel normal ifade dili öğeleridir. Bunları düzenli bir ifadede eşleştirmek için, bu, kaçış veya [pozitif bir karakter grubuna](../../../docs/standard/base-types/character-classes-in-regular-expressions.md)dahil edilmeleri gerekir. Örneğin, normal ifade `\$\d+` veya `[$]\d+` "$1200" ile eşleşir.|  
|`\a`|Bir Bell (alarm) karakteriyle `\u0007`eşleşir.|  
|`\b`|Bir `[` *character_group* `\u0008`karakter sınıfında, geri al, ile eşleşir.`]`  (Bkz. [karakter sınıfları](../../../docs/standard/base-types/character-classes-in-regular-expressions.md).) Bir karakter sınıfı dışında, `\b` bir sözcük sınırı ile eşleşen bir bağlantıdır. (Bkz [](../../../docs/standard/base-types/anchors-in-regular-expressions.md). Tutturucuların.)|  
|`\t`|Bir sekmeden eşleşir, `\u0009`.|  
|`\r`|Bir satır dönüşüyle eşleşir `\u000D`,. Yeni satır karakteri ile eşdeğer olmadığına unutmayın. `\n` `\r`|  
|`\v`|Dikey bir sekme `\u000B`ile eşleşir.|  
|`\f`|Bir form akışı `\u000C`ile eşleşir.|  
|`\n`|Yeni bir satırla eşleşir, `\u000A`.|  
|`\e`|Bir kaçış ile eşleşir `\u001B`,.|  
|`\`*nnn*&#124; Bir ASCII karakteriyle eşleşir, burada *nnn* sekizli karakter kodunu temsil eden iki veya üç sayıdan oluşur. Örneğin, `\040` bir boşluk karakterini temsil eder. Bu yapı yalnızca bir basamak varsa (örneğin, `\2`) veya bir yakalama grubu sayısına karşılık geliyorsa, bir geri başvuru olarak yorumlanır. (Bkz. [Backreference yapıları](../../../docs/standard/base-types/backreference-constructs-in-regular-expressions.md).)|  
|`\x`*nn*|*Nn* 'in iki basamaklı bir onaltılık karakter kodu olduğu ASCII karakteriyle eşleşir.|  
|`\c` *X*|Bir ASCII denetim karakteriyle eşleşir, burada X, denetim karakterinin harfidir. Örneğin, CTRL `\cC` -C ' dir.|  
|`\u`*nnnn*|Değeri *nnnn* onaltılık olan bir UTF-16 kod birimiyle eşleşir. **Not:**  Unicode belirtmek için kullanılan Perl 5 karakter kaçış, .NET tarafından desteklenmez. Perl 5 karakter `\x{`kaçış biçimi *####* `…}`, *####* burada`…` bir dizi onaltılık basamak olur. Bunun yerine `\u` *nnnn*kullanın.|  
|`\`&#124; Bunun ardından, kaçış karakteri olarak tanınmayan bir karakter gelmesi durumunda, bu karakterle eşleşir. Örneğin, `\*` bir yıldız işareti (*) ile eşleşir ve ile `\x2A`aynıdır.|  
  
## <a name="an-example"></a>Bir Örnek  
 Aşağıdaki örnek, bir normal ifadede karakter kaçışları kullanımını gösterir. Dünyanın en büyük şehirlerinin adlarını ve 2009 içindeki popülasyonlarını içeren bir dizeyi ayrıştırır. Her şehir adı, bir sekme (`\t`) veya dikey çubuk (&#124; veya `\u007c`) tarafından popülasyondan ayrılır. Bireysel şehirler ve bunların popülasyonu bir satır başı ve satır besleme ile birbirinden ayrılır.  
  
 [!code-csharp[RegularExpressions.Language.Escapes#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.escapes/cs/escape1.cs#1)]
 [!code-vb[RegularExpressions.Language.Escapes#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.escapes/vb/escape1.vb#1)]  
  
 Normal ifade `\G(.+)[\t|\u007c](.+)\r?\n` aşağıdaki tabloda gösterildiği gibi yorumlanır.  
  
|Desen|Açıklama|  
|-------------|-----------------|  
|`\G`|En son eşleşmenin sona erdiği eşleşmeyi Başlat.|  
|`(.+)`|Karakterleri bir veya daha fazla kez eşleştirin. Bu ilk yakalama grubudur.|  
|`[\t\u007c]`|Bir sekmeden (`\t`) veya dikey çubukla (&#124;) eşleştirin.|  
|`(.+)`|Karakterleri bir veya daha fazla kez eşleştirin. Bu ikinci yakalama grubudur.|  
|`\r?\n`|Bir satır başı ve ardından yeni bir satır gelen sıfır veya bir oluşumunu eşleştirin.|  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Normal İfade Dili - Hızlı Başvuru](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
