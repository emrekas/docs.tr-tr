---
title: Ertelenmiş yürütme örneği (C#)
ms.date: 07/20/2015
ms.assetid: 50f4fbac-81fe-4f26-aedf-506e21419b19
ms.openlocfilehash: 0816594ad016f19af4c97198160b4bafb9b4b8b4
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204127"
---
# <a name="deferred-execution-example-c"></a>Ertelenmiş yürütme örneği (C#)
Bu konu, ertelenmiş yürütmenin ve yavaş değerlendirmenin LINQ to XML sorgularının yürütülmesini nasıl etkilediğini gösterir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, ertelenmiş yürütmeyi kullanan bir genişletme yöntemi kullanılırken yürütme sırasını gösterir. Örnek, üç dizeden oluşan bir dizi bildirir. Daha sonra tarafından `ConvertCollectionToUpperCase`döndürülen koleksiyon üzerinden yinelenir.  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source {0}", str);  
            yield return str.ToUpper();  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        var q = from str in stringArray.ConvertCollectionToUpperCase()  
                select str;  
  
        foreach (string str in q)  
            Console.WriteLine("Main: str {0}", str);  
    }  
}  
```  
  
 Bu örnek aşağıdaki çıktıyı üretir:  
  
```output  
ToUpper: source abc  
Main: str ABC  
ToUpper: source def  
Main: str DEF  
ToUpper: source ghi  
Main: str GHI  
```  
  
 Tarafından `ConvertCollectionToUpperCase`döndürülen koleksiyonda yineleme yapıldığında, her öğe kaynak dize dizisinden alınır ve sonraki öğe kaynak dize dizisinden alınmadan önce büyük harfe dönüştürülür.  
  
 Döndürülen koleksiyondaki her öğe, içindeki `foreach` `Main`döngüde işlenmeden önce, tüm dizeler dizisinin büyük harfe dönüştürülmediğine bakabilirsiniz.  
  
 Bu öğreticideki sonraki konu, zincirleme sorguları birlikte gösterir:  
  
- [Zincirleme sorguları örneği (C#)](./chaining-queries-example.md)  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Öğretici: Sorguları birlikte zincirleme (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
