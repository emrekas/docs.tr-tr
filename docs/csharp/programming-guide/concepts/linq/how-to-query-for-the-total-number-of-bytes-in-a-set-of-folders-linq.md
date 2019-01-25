---
title: 'Nasıl yapılır: Sorgu (LINQ) klasör kümesi bayt toplam sayısı (C#)'
ms.date: 07/20/2015
ms.assetid: a01bd1d4-133c-4ca2-aa4e-e93e81d6076c
ms.openlocfilehash: 52f428bcf427065b80e91c4d299c5d8fd9f32972
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607559"
---
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-c"></a>Nasıl yapılır: Sorgu (LINQ) klasör kümesi bayt toplam sayısı (C#)
Bu örnek belirtilen bir klasördeki tüm dosyaları ve tüm alt klasörleri tarafından kullanılan bayt toplam sayısını almak nasıl gösterir.  
  
## <a name="example"></a>Örnek  
 <xref:System.Linq.Enumerable.Sum%2A> Yöntemi, seçilen tüm öğelerin değerini ekler `select` yan tümcesi. Belirtilen dizin ağacındaki en büyük veya en küçük dosya çağırarak almak için bu sorguyu kolayca değiştirebilirsiniz <xref:System.Linq.Enumerable.Min%2A> veya <xref:System.Linq.Enumerable.Max%2A> yöntemi yerine <xref:System.Linq.Enumerable.Sum%2A>.  
  
```csharp  
class QuerySize  
{  
    public static void Main()  
    {  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\VC#";  
  
        // Take a snapshot of the file system.  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<string> fileList = System.IO.Directory.GetFiles(startFolder, "*.*", System.IO.SearchOption.AllDirectories);  
  
        var fileQuery = from file in fileList  
                        select GetFileLength(file);  
  
        // Cache the results to avoid multiple trips to the file system.  
        long[] fileLengths = fileQuery.ToArray();  
  
        // Return the size of the largest file  
        long largestFile = fileLengths.Max();  
  
        // Return the total number of bytes in all the files under the specified folder.  
        long totalBytes = fileLengths.Sum();  
  
        Console.WriteLine("There are {0} bytes in {1} files under {2}",  
            totalBytes, fileList.Count(), startFolder);  
        Console.WriteLine("The largest files is {0} bytes.", largestFile);  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit.");  
        Console.ReadKey();  
    }  
  
    // This method is used to swallow the possible exception  
    // that can be raised when accessing the System.IO.FileInfo.Length property.  
    static long GetFileLength(string filename)  
    {  
        long retval;  
        try  
        {  
            System.IO.FileInfo fi = new System.IO.FileInfo(filename);  
            retval = fi.Length;  
        }  
        catch (System.IO.FileNotFoundException)  
        {  
            // If a file is no longer present,  
            // just add zero bytes to the total.  
            retval = 0;  
        }  
        return retval;  
    }  
}  
```  
  
 Yalnızca belirtilen dizin ağacı bayt sayısını varsa, daha verimli bir şekilde bir veri kaynağı olarak liste koleksiyonu oluşturma işleminin ek yüke neden olur bir LINQ Sorgu oluşturmadan bunu yapabilirsiniz. Sorguyu daha karmaşık hale geldiğinde veya aynı veri kaynağında birden çok sorguları çalıştırmak sahip olduğunda LINQ yaklaşım kullanışlılığını artırır.  
  
 Sorgu dosya uzunluğu elde etmek için ayrı bir yöntemi için çağırır. Dosya başka bir iş parçacığında sonra silinmişse, oluşturulur ve olası özel kullanmak için bunu yapar <xref:System.IO.FileInfo> nesne oluşturulduğu çağrısında `GetFiles`. Olsa bile <xref:System.IO.FileInfo> nesnesi zaten oluşturuldu, özel durum ortaya çıkabilir çünkü bir <xref:System.IO.FileInfo> nesne yenilemek çalışır, <xref:System.IO.FileInfo.Length%2A> özelliği ile erişilen özelliği ilk kez en güncel uzunluğu. Bir try-catch bloğunda sorgu dışında bu işlemi koyarak kod yan etkilere neden olabilecek sorguları işlemlerinde önleme kuralı izler. Genel olarak, bir uygulama bilinmeyen bir durumda kaldı değil emin olmak için özel durumlar tükettiğinizde çok dikkatli olunmalıdır.  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 .NET Framework sürüm 3.5 veya üzeri bir System.Core.dll başvurusu ile hedefleyen bir proje oluşturun ve `using` System.Linq ve System.IO ad alanları için yönergeleri.  
  
## <a name="see-also"></a>Ayrıca bkz.

- [LINQ to Objects'in (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)
- [LINQ ve dosya dizinleri (C#)](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)
