---
title: Zincirleme örneği sorgular (C#)
ms.date: 07/20/2015
ms.assetid: abbca162-d95e-43af-b92c-e46e6aa2540e
ms.openlocfilehash: 8564a2ece7dc09bd3330dc9bdad31689408089cf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598548"
---
# <a name="chaining-queries-example-c"></a>Zincirleme örneği sorgular (C#)
Bu örnek önceki örneğe dayanmaktadır ve her ikisi de ertelenmiş yürütme ve geç değerlendirme kullanın, zincir birlikte iki sorgular ne olacağını gösterir.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, başka bir genişletme yöntemi sunulmuştur, `AppendString`, kaynak koleksiyondaki her dize üzerine belirtilen bir dize ekler ve ardından yeni bir dize verir.  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source >{0}<", str);  
            yield return str.ToUpper();  
        }  
    }  
  
    public static IEnumerable<string>  
      AppendString(this IEnumerable<string> source, string stringToAppend)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("AppendString: source >{0}<", str);  
            yield return str + stringToAppend;  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        IEnumerable<string> q1 =  
            from s in stringArray.ConvertCollectionToUpperCase()  
            select s;  
  
        IEnumerable<string> q2 =  
            from s in q1.AppendString("!!!")  
            select s;  
  
        foreach (string str in q2)  
        {  
            Console.WriteLine("Main: str >{0}<", str);  
            Console.WriteLine();  
        }  
    }  
}  
```  
  
 Bu örnek aşağıdaki çıktıyı üretir:  
  
```  
ToUpper: source >abc<  
AppendString: source >ABC<  
Main: str >ABC!!!<  
  
ToUpper: source >def<  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
ToUpper: source >ghi<  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
 Bu örnekte, her bir genişletme yöntemi bir kaynak koleksiyondaki her öğe için aynı anda çalıştığını görebilirsiniz.  
  
 Ne bu örnekten açık olmalıdır, biz koleksiyonları yield sorguları birbirine zincirlenmiş olsa bile, Ara koleksiyon gerçekleştirilmiş olur. Bunun yerine, her öğe yavaş bir yöntemden diğerine geçirilir. Büyük harf ve son olarak üçüncü bir ünlem işareti sahip olduğu her bir dizenin bir dize dizisi oluşturmak için önce bir dize dizisi alın ve ardından ikinci bir dize dizisi oluşturan bir yaklaşım daha çok daha küçük bellek Ayak izi bu sonuçlarında dönüştürüldü eklenmiş bir işaret eder.  
  
 Bu öğreticide bir sonraki konu Ara gerçekleştirme gösterilmektedir:  
  
- [Ara gerçekleştirme (C#)](../../../../csharp/programming-guide/concepts/linq/intermediate-materialization.md)  
  
## <a name="see-also"></a>Ayrıca bkz.

- [Öğretici: Sorguları birbirine zincirleme (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)
