---
title: 'Nasıl yapılır: Belirtilen öznitelik veya ada sahip dosyaları sorgulama (C#)'
ms.date: 07/20/2015
ms.assetid: 560e3879-b0b3-4549-ad02-0a53aff2f83c
ms.openlocfilehash: e600899251fe08884088275307f4311f3b9787cd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61702028"
---
# <a name="how-to-query-for-files-with-a-specified-attribute-or-name-c"></a><span data-ttu-id="92dba-102">Nasıl yapılır: Belirtilen öznitelik veya ada sahip dosyaları sorgulama (C#)</span><span class="sxs-lookup"><span data-stu-id="92dba-102">How to: Query for Files with a Specified Attribute or Name (C#)</span></span>
<span data-ttu-id="92dba-103">Bu örnek nasıl (örneğin, ".txt") belirtilen dosya adı uzantısına sahip tüm dosyaları bulmak belirtilen dizin ağacında gösterir.</span><span class="sxs-lookup"><span data-stu-id="92dba-103">This example shows how to find all files that have a specified file name extension (for example ".txt") in a specified directory tree.</span></span> <span data-ttu-id="92dba-104">Ayrıca oluşturma saatini temel alan ağacında ya da yeni veya eski dosyayı iade işlemini de gösterir.</span><span class="sxs-lookup"><span data-stu-id="92dba-104">It also shows how to return either the newest or oldest file in the tree based on the creation time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92dba-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="92dba-105">Example</span></span>  
  
```csharp  
class FindFileByExtension  
{  
    // This query will produce the full path for all .txt files  
    // under the specified folder including subfolders.  
    // It orders the list according to the file name.  
    static void Main()  
    {  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\";  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        //Create the query  
        IEnumerable<System.IO.FileInfo> fileQuery =  
            from file in fileList  
            where file.Extension == ".txt"  
            orderby file.Name  
            select file;  
  
        //Execute the query. This might write out a lot of files!  
        foreach (System.IO.FileInfo fi in fileQuery)  
        {  
            Console.WriteLine(fi.FullName);  
        }  
  
        // Create and execute a new query by using the previous   
        // query as a starting point. fileQuery is not   
        // executed again until the call to Last()  
        var newestFile =  
            (from file in fileQuery  
             orderby file.CreationTime  
             select new { file.FullName, file.CreationTime })  
            .Last();  
  
        Console.WriteLine("\r\nThe newest .txt file is {0}. Creation time: {1}",  
            newestFile.FullName, newestFile.CreationTime);  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="92dba-106">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="92dba-106">Compiling the Code</span></span>  
 <span data-ttu-id="92dba-107">.NET Framework sürüm 3.5 veya üzeri bir System.Core.dll başvurusu ile hedefleyen bir proje oluşturun ve `using` System.Linq ve System.IO ad alanları için yönergeleri.</span><span class="sxs-lookup"><span data-stu-id="92dba-107">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to   System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92dba-108">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="92dba-108">See also</span></span>

- [<span data-ttu-id="92dba-109">LINQ to Objects'in (C#)</span><span class="sxs-lookup"><span data-stu-id="92dba-109">LINQ to Objects (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)
- [<span data-ttu-id="92dba-110">LINQ ve dosya dizinleri (C#)</span><span class="sxs-lookup"><span data-stu-id="92dba-110">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)
