---
title: 'Nasıl yapılır: (LINQ) bir dizedeki karakterleri sorgulama (C#)'
ms.date: 07/20/2015
ms.assetid: 727a1be7-dbec-4ab8-b414-bc2d56feb6ff
ms.openlocfilehash: 0c577fc2dc2ae07574580f819a6fb51336107dfb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54665636"
---
# <a name="how-to-query-for-characters-in-a-string-linq-c"></a>Nasıl yapılır: (LINQ) bir dizedeki karakterleri sorgulama (C#)
Çünkü <xref:System.String> sınıfın uyguladığı genel <xref:System.Collections.Generic.IEnumerable%601> arabirimi, bir karakter dizisi herhangi bir dize sorgulanabilir. Ancak, bu yaygın bir LINQ kullanımı değildir. İşlem eşleştirme karmaşık deseni için kullanmak <xref:System.Text.RegularExpressions.Regex> sınıfı.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir dize içerdiği sayısal basamak sayısını belirlemek için sorgular. "İlk kez yürütüldükten sonra sorguyu yeniden," unutmayın. Herhangi bir gerçek sonuç sorgunun kendisi depolamaz mümkün olmasıdır.  
  
```csharp  
class QueryAString  
{  
    static void Main()  
    {  
        string aString = "ABCDE99F-J74-12-89A";  
  
        // Select only those characters that are numbers  
        IEnumerable<char> stringQuery =  
          from ch in aString  
          where Char.IsDigit(ch)  
          select ch;  
  
        // Execute the query  
        foreach (char c in stringQuery)  
            Console.Write(c + " ");  
  
        // Call the Count method on the existing query.  
        int count = stringQuery.Count();  
        Console.WriteLine("Count = {0}", count);  
  
        // Select all characters before the first '-'  
        IEnumerable<char> stringQuery2 = aString.TakeWhile(c => c != '-');  
  
        // Execute the second query  
        foreach (char c in stringQuery2)  
            Console.Write(c);  
  
        Console.WriteLine(System.Environment.NewLine + "Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
  Output: 9 9 7 4 1 2 8 9  
  Count = 8  
  ABCDE99F  
*/  
```  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 .NET Framework sürüm 3.5 veya üzeri bir System.Core.dll başvurusu ile hedefleyen bir proje oluşturun ve `using` System.Linq ve System.IO ad alanları için yönergeleri.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [LINQ ve dizeler (C#)](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)
- [Nasıl yapılır: Normal ifadelerle LINQ sorgularını birleştirme (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md)
