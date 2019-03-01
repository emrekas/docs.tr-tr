---
title: Özel durum işleme - C# Programlama Kılavuzu
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- exception handling [C#], about exception handling
- exceptions [C#], handling
ms.assetid: b4e4ecf2-b907-4e58-891f-2563762258e9
ms.openlocfilehash: 87a85511669e676f2943bf5f079b54e96b926490
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56979872"
---
# <a name="exception-handling-c-programming-guide"></a>Özel Durum İşleme (C# Programlama Kılavuzu)
A [deneyin](../../../csharp/language-reference/keywords/try-catch.md) blok, C# programcıları için bir özel durum tarafından etkilenebilecek bölümü kod tarafından kullanılır. İlişkili [catch](../../../csharp/language-reference/keywords/try-catch.md) blokları, oluşturulan özel durumları işlemek için kullanılır. A [son](../../../csharp/language-reference/keywords/try-finally.md) blok olup olmadığı bir özel durum bağımsız olarak çalışan kodu içeren `try` ayrılmış kaynakları serbest bırakmak gibi bloğu `try` blok. A `try` blok gerektiren bir veya daha fazla ilişkili `catch` blokları veya `finally` blok veya her ikisini de.  
  
 Aşağıdaki örneklerde gösterildiği bir `try-catch` deyimi, bir `try-finally` ifadesi ve bir `try-catch-finally` deyimi.  
  
 [!code-csharp[csProgGuideExceptions#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#6)]  
  
 [!code-csharp[csProgGuideExceptions#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#7)]  
  
 [!code-csharp[csProgGuideExceptions#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#8)]  
  
 A `try` olmadan engelleyecek bir `catch` veya `finally` blok bir derleyici hatasına neden olur.  
  
## <a name="catch-blocks"></a>Catch blokları  
 A `catch` blok yakalamak için özel durumun türünü belirtebilirsiniz. Tür belirtimi adlı bir *özel durum filtresi*. Özel durum türü nesnesinden türetilmesi <xref:System.Exception>. Genel olarak, belirtmeyin <xref:System.Exception> özel durum filtre olarak ya da oluşturulmuş olabilecek tüm özel durumların nasıl işleneceğini bilmiyorsanız `try` blok veya dahil ettiyseniz bir [throw](../../../csharp/language-reference/keywords/throw.md) deyimi, sonunda`catch`blok.  
  
 Birden çok `catch` farklı bir özel durum filtreleri bloklarla zincirleme yapılabilir birlikte. `catch` Blokları üstten alta kodunuzu, ancak yalnızca bir değerlendirilir `catch` blok, oluşturulan her özel durum için yürütülür. İlk `catch` türünü tam ya da temel sınıfta oluşturulan özel durumun belirten bloğu yürütülür. Hayır ise `catch` blok eşleşen bir özel durum filtresi belirtir bir `catch` bir filtre yok blok seçili deyiminde varsa. Konumlandırmak önemlidir `catch` en (diğer bir deyişle, en çok türetilen) özel durum blokları türleri önce.  
  
 Aşağıdaki koşullar doğru olduğunda özel durumları yakalamalısınız:  
  
-   Bir iyi, özel durum oluşturulur ve yeni bir dosya adı, catch geçilmesidir girmesinin istendiği gibi belirli bir kurtarma uygulayabilirsiniz neden anlama sahip bir <xref:System.IO.FileNotFoundException> nesne.  
  
-   Oluşturun ve yeni, daha belirli bir özel durum.  
  
     [!code-csharp[csProgGuideExceptions#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#9)]  
  
-   Kısmen için ek işleme iletmeden önce özel bir durumu işlemek istersiniz. Aşağıdaki örnekte, bir `catch` bloğu özel durumu yeniden atamadan önce bir hata günlüğü için bir giriş eklemek için kullanılır.  
  
     [!code-csharp[csProgGuideExceptions#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#10)]  
  
## <a name="finally-blocks"></a>Finally blokları  
 A `finally` blok içinde gerçekleştirilen eylemler temizlemek sağlayan bir `try` blok. Varsa, `finally` bloğun son, sonra `try` bloğu ve eşleşen `catch` blok. A `finally` bloğu her zaman çalışır, bağımsız olarak, bir özel durum olup olmadığını veya `catch` özel durum türüyle eşleşen bloğu bulundu.  
  
 `finally` Blok, dosya akışları, veritabanı bağlantıları gibi kaynakları serbest bırakmak için kullanılabilir ve grafik işleme nesneleri sonlandırmak için çalışma zamanı çöp toplayıcı için beklemenize gerek kalmadan. Bkz: [using deyimi](../../../csharp/language-reference/keywords/using-statement.md) daha fazla bilgi için.  
  
 Aşağıdaki örnekte, `finally` açılmış bir dosyayı kapatmak için kullanılan blok `try` blok. Dosya kapatılmadan hemen önce dosya tanıtıcısı durumu denetlenir dikkat edin. Varsa `try` blok dosyayı açamaz, dosya tanıtıcısı hala değerine sahip `null` ve `finally` blok kapatmak deneyin değil. Alternatif olarak, dosya başarıyla açılıp açılmadığını `try` bloğu `finally` blok açık dosyayı kapatır.  
  
 [!code-csharp[csProgGuideExceptions#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#11)]  
  
## <a name="c-language-specification"></a>C# Dil Belirtimi  

Daha fazla bilgi için [özel durumları](~/_csharplang/spec/exceptions.md) ve [try deyimi](~/_csharplang/spec/statements.md#the-try-statement) içinde [ C# dil belirtimi](../../language-reference/language-specification/index.md). Dil belirtimi, C# sözdizimi ve kullanımı için kesin bir kaynaktır.
  
## <a name="see-also"></a>Ayrıca bkz.

- [C# başvurusu](../../../csharp/language-reference/index.md)
- [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)
- [Özel Durumlar ve Özel Durum İşleme](../../../csharp/programming-guide/exceptions/index.md)
- [try-catch](../../../csharp/language-reference/keywords/try-catch.md)
- [try-finally](../../../csharp/language-reference/keywords/try-finally.md)
- [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)
- [using Deyimi](../../../csharp/language-reference/keywords/using-statement.md)
