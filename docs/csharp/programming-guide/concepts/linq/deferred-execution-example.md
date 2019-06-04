---
title: Ertelenmiş yürütme örneği (C#)
ms.date: 07/20/2015
ms.assetid: 50f4fbac-81fe-4f26-aedf-506e21419b19
ms.openlocfilehash: c9ac87cf2b2af4114e5a20c211b4a6b3f7fced6b
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486100"
---
# <a name="deferred-execution-example-c"></a><span data-ttu-id="e309c-102">Ertelenmiş yürütme örneği (C#)</span><span class="sxs-lookup"><span data-stu-id="e309c-102">Deferred Execution Example (C#)</span></span>
<span data-ttu-id="e309c-103">Bu konu nasıl ertelenmiş yürütme gösterir ve geç değerlendirme, LINQ to XML sorgularında yürütme etkiler.</span><span class="sxs-lookup"><span data-stu-id="e309c-103">This topic shows how deferred execution and lazy evaluation affect the execution of your LINQ to XML queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e309c-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="e309c-104">Example</span></span>  
 <span data-ttu-id="e309c-105">Aşağıdaki örnek, ertelenmiş yürütme kullanan bir genişletme yöntemi kullanırken, yürütme sırasını gösterir.</span><span class="sxs-lookup"><span data-stu-id="e309c-105">The following example shows the order of execution when using an extension method that uses deferred execution.</span></span> <span data-ttu-id="e309c-106">Örneğin, üç dize dizisi bildirir.</span><span class="sxs-lookup"><span data-stu-id="e309c-106">The example declares an array of three strings.</span></span> <span data-ttu-id="e309c-107">Bunun ardından tarafından döndürülen bir koleksiyonda gezinir `ConvertCollectionToUpperCase`.</span><span class="sxs-lookup"><span data-stu-id="e309c-107">It then iterates through the collection returned by `ConvertCollectionToUpperCase`.</span></span>  
  
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
  
 <span data-ttu-id="e309c-108">Bu örnek aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="e309c-108">This example produces the following output:</span></span>  
  
```  
ToUpper: source abc  
Main: str ABC  
ToUpper: source def  
Main: str DEF  
ToUpper: source ghi  
Main: str GHI  
```  
  
 <span data-ttu-id="e309c-109">Tarafından döndürülen koleksiyon üzerinden yineleme sırasında dikkat `ConvertCollectionToUpperCase`, her öğe kaynak string dizisinden alınır ve sonraki önce büyük harfe dönüştürülmüş öğesi, kaynak string dizisinden alınır.</span><span class="sxs-lookup"><span data-stu-id="e309c-109">Notice that when iterating through the collection returned by `ConvertCollectionToUpperCase`, each item is retrieved from the source string array and converted to uppercase before the next item is retrieved from the source string array.</span></span>  
  
 <span data-ttu-id="e309c-110">Döndürülen koleksiyondaki her öğe içinde işlenmeden önce tüm dizi dizeleri büyük harfe dönüştürülmesi değil gördüğünüz `foreach` içinde döngü `Main`.</span><span class="sxs-lookup"><span data-stu-id="e309c-110">You can see that the entire array of strings is not converted to uppercase before each item in the returned collection is processed in the `foreach` loop in `Main`.</span></span>  
  
 <span data-ttu-id="e309c-111">Bu öğreticide bir sonraki konu birbirine zincirleme sorgular gösterilmektedir:</span><span class="sxs-lookup"><span data-stu-id="e309c-111">The next topic in this tutorial illustrates chaining queries together:</span></span>  
  
- [<span data-ttu-id="e309c-112">Zincirleme örneği sorgular (C#)</span><span class="sxs-lookup"><span data-stu-id="e309c-112">Chaining Queries Example (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/chaining-queries-example.md)  
  
## <a name="see-also"></a><span data-ttu-id="e309c-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="e309c-113">See also</span></span>

- [<span data-ttu-id="e309c-114">Öğretici: Sorguları birbirine zincirleme (C#)</span><span class="sxs-lookup"><span data-stu-id="e309c-114">Tutorial: Chaining Queries Together (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
