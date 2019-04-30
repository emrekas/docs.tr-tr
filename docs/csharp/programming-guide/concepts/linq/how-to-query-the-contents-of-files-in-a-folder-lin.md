---
title: 'Nasıl yapılır: Bir klasör (LINQ) metin dosyalarında içeriğini sorgulama (C#)'
ms.date: 07/20/2015
ms.assetid: f5b4dce7-1a34-4eb4-9bf1-60d5bdda264c
ms.openlocfilehash: 66e2a2d6ee2b8dd3be3e66f7277947b6d6f749a4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667801"
---
# <a name="how-to-query-the-contents-of-text-files-in-a-folder-linq-c"></a><span data-ttu-id="1eb65-102">Nasıl yapılır: Bir klasör (LINQ) metin dosyalarında içeriğini sorgulama (C#)</span><span class="sxs-lookup"><span data-stu-id="1eb65-102">How to: Query the Contents of Text Files in a Folder (LINQ) (C#)</span></span>
<span data-ttu-id="1eb65-103">Bu örnek, belirtilen dizin ağacındaki tüm dosyalar üzerinde sorgulama, her dosyasını açın ve içeriğini inceleyin gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="1eb65-103">This example shows how to query over all the files in a specified directory tree, open each file, and inspect its contents.</span></span> <span data-ttu-id="1eb65-104">Bu tür bir teknik dizinler oluşturmak veya bir dizin ağacında içeriği dizinlerini tersine çevirecek şekilde kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="1eb65-104">This type of technique could be used to create indexes or reverse indexes of the contents of a directory tree.</span></span> <span data-ttu-id="1eb65-105">Bu örnekte basit dize arama gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="1eb65-105">A simple string search is performed in this example.</span></span> <span data-ttu-id="1eb65-106">Ancak, daha karmaşık tür deseniyle eşleşen normal bir ifade ile gerçekleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="1eb65-106">However, more complex types of pattern matching can be performed with a regular expression.</span></span> <span data-ttu-id="1eb65-107">Daha fazla bilgi için [nasıl yapılır: Normal ifadelerle LINQ sorgularını birleştirme (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="1eb65-107">For more information, see [How to: Combine LINQ Queries with Regular Expressions (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1eb65-108">Örnek</span><span class="sxs-lookup"><span data-stu-id="1eb65-108">Example</span></span>  
  
```csharp  
class QueryContents  
{  
    public static void Main()  
    {  
        // Modify this path as necessary.  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\";  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        string searchTerm = @"Visual Studio";  
  
        // Search the contents of each file.  
        // A regular expression created with the RegEx class  
        // could be used instead of the Contains method.  
        // queryMatchingFiles is an IEnumerable<string>.  
        var queryMatchingFiles =  
            from file in fileList  
            where file.Extension == ".htm"  
            let fileText = GetFileText(file.FullName)  
            where fileText.Contains(searchTerm)  
            select file.FullName;  
  
        // Execute the query.  
        Console.WriteLine("The term \"{0}\" was found in:", searchTerm);  
        foreach (string filename in queryMatchingFiles)  
        {  
            Console.WriteLine(filename);  
        }  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    // Read the contents of the file.  
    static string GetFileText(string name)  
    {  
        string fileContents = String.Empty;  
  
        // If the file has been deleted since we took   
        // the snapshot, ignore it and return the empty string.  
        if (System.IO.File.Exists(name))  
        {  
            fileContents = System.IO.File.ReadAllText(name);  
        }  
        return fileContents;  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1eb65-109">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="1eb65-109">Compiling the Code</span></span>  
 <span data-ttu-id="1eb65-110">.NET Framework sürüm 3.5 veya üzeri bir System.Core.dll başvurusu ile hedefleyen bir proje oluşturun ve `using` System.Linq ve System.IO ad alanları için yönergeleri.</span><span class="sxs-lookup"><span data-stu-id="1eb65-110">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eb65-111">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="1eb65-111">See also</span></span>

- [<span data-ttu-id="1eb65-112">LINQ ve dosya dizinleri (C#)</span><span class="sxs-lookup"><span data-stu-id="1eb65-112">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)
- [<span data-ttu-id="1eb65-113">LINQ to Objects'in (C#)</span><span class="sxs-lookup"><span data-stu-id="1eb65-113">LINQ to Objects (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)
