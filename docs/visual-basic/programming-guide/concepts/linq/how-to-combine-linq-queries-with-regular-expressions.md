---
title: 'Nasıl yapılır: (Visual Basic) Normal ifadelerle LINQ sorgularını birleştirme'
ms.date: 07/20/2015
ms.assetid: 3da1bd10-b0d8-4d5b-a637-966891c13592
ms.openlocfilehash: 35d82b562211a9dd7fa035fe878bcdee769b8a85
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54652481"
---
# <a name="how-to-combine-linq-queries-with-regular-expressions-visual-basic"></a><span data-ttu-id="7fcbe-102">Nasıl yapılır: (Visual Basic) Normal ifadelerle LINQ sorgularını birleştirme</span><span class="sxs-lookup"><span data-stu-id="7fcbe-102">How to: Combine LINQ Queries with Regular Expressions (Visual Basic)</span></span>
<span data-ttu-id="7fcbe-103">Bu örnek nasıl kullanılacağını gösterir <xref:System.Text.RegularExpressions.Regex> daha karmaşık metin dizelerini eşleştirme için normal bir ifade oluşturmak için sınıf.</span><span class="sxs-lookup"><span data-stu-id="7fcbe-103">This example shows how to use the <xref:System.Text.RegularExpressions.Regex> class to create a regular expression for more complex matching in text strings.</span></span> <span data-ttu-id="7fcbe-104">LINQ Sorgu tam olarak normal ifade ile arama ve sonuçlar şekil için istediğiniz dosyaları filtre kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="7fcbe-104">The LINQ query makes it easy to filter on exactly the files that you want to search with the regular expression, and to shape the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fcbe-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="7fcbe-105">Example</span></span>  
  
```vb  
Class LinqRegExVB  
  
    Shared Sub Main()  
  
        ' Root folder to query, along with all subfolders.  
        ' Modify this path as necessary so that it accesses your Visual Studio folder.  
        Dim startFolder As String = "C:\Program Files (x86)\Microsoft Visual Studio 14.0\"
        ' One of the following paths may be more appropriate on your computer.  
        'Dim startFolder As String = "C:\Program Files (x86)\Microsoft Visual Studio\2017\"
  
        ' Take a snapshot of the file system.  
        Dim fileList As IEnumerable(Of System.IO.FileInfo) = GetFiles(startFolder)  
  
        ' Create a regular expression to find all things "Visual".  
        Dim searchTerm As System.Text.RegularExpressions.Regex =   
            New System.Text.RegularExpressions.Regex("Visual (Basic|C#|C\+\+|Studio)")  
  
        ' Search the contents of each .htm file.  
        ' Remove the where clause to find even more matches!  
        ' This query produces a list of files where a match  
        ' was found, and a list of the matches in that file.  
        ' Note: Explicit typing of "Match" in select clause.  
        ' This is required because MatchCollection is not a   
        ' generic IEnumerable collection.  
        Dim queryMatchingFiles = From afile In fileList  
                                Where afile.Extension = ".htm"  
                                Let fileText = System.IO.File.ReadAllText(afile.FullName)  
                                Let matches = searchTerm.Matches(fileText)  
                                Where (matches.Count > 0)  
                                Select Name = afile.FullName,  
                                       Matches = From match As System.Text.RegularExpressions.Match In matches  
                                                 Select match.Value  
  
        ' Execute the query.  
        Console.WriteLine("The term " & searchTerm.ToString() & " was found in:")  
  
        For Each fileMatches In queryMatchingFiles  
            ' Trim the path a bit, then write   
            ' the file name in which a match was found.  
            Dim s = fileMatches.Name.Substring(startFolder.Length - 1)  
            Console.WriteLine(s)  
  
            ' For this file, write out all the matching strings  
            For Each match In fileMatches.Matches  
                Console.WriteLine("  " + match)  
            Next  
        Next  
  
        ' Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit")  
        Console.ReadKey()  
    End Sub  
  
    ' Function to retrieve a list of files. Note that this is a copy  
    ' of the file information.  
    Shared Function GetFiles(ByVal root As String) As IEnumerable(Of System.IO.FileInfo)  
        Return From file In My.Computer.FileSystem.GetFiles(  
                   root, FileIO.SearchOption.SearchAllSubDirectories, "*.*")   
               Select New System.IO.FileInfo(file)  
    End Function  
  
End Class  
```  
  
 <span data-ttu-id="7fcbe-106">Ayrıca Sorgulayabileceğiniz Not <xref:System.Text.RegularExpressions.MatchCollection> tarafından döndürülen nesne gibi bir `RegEx` arama.</span><span class="sxs-lookup"><span data-stu-id="7fcbe-106">Note that you can also query the <xref:System.Text.RegularExpressions.MatchCollection> object that is returned by a `RegEx` search.</span></span> <span data-ttu-id="7fcbe-107">Bu örnekte, sonuçları yalnızca her bir eşleşme değeri oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="7fcbe-107">In this example only the value of each match is produced in the results.</span></span> <span data-ttu-id="7fcbe-108">Ancak, aynı zamanda filtreleme, sıralama ve gruplandırma bu koleksiyon üzerinde her türlü gerçekleştirmek için LINQ kullanılacak mümkündür.</span><span class="sxs-lookup"><span data-stu-id="7fcbe-108">However, it is also possible to use LINQ to perform all kinds of filtering, sorting, and grouping on that collection.</span></span> <span data-ttu-id="7fcbe-109">Çünkü <xref:System.Text.RegularExpressions.MatchCollection> genel olmayan <xref:System.Collections.IEnumerable> koleksiyonuna sahip sorgudaki Aralık değişkeninin türünü açıkça durumuna.</span><span class="sxs-lookup"><span data-stu-id="7fcbe-109">Because <xref:System.Text.RegularExpressions.MatchCollection> is a non-generic <xref:System.Collections.IEnumerable> collection, you have to explicitly state the type of the range variable in the query.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7fcbe-110">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="7fcbe-110">Compiling the Code</span></span>  
 <span data-ttu-id="7fcbe-111">.NET Framework sürüm 3.5 veya daha yüksek bir System.Core.dll başvurusu ile hedefleyen bir proje oluşturun ve bir `Imports` System.Linq ad alanı bildirimi.</span><span class="sxs-lookup"><span data-stu-id="7fcbe-111">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fcbe-112">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="7fcbe-112">See also</span></span>
- [<span data-ttu-id="7fcbe-113">LINQ ve dizeler (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7fcbe-113">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
- [<span data-ttu-id="7fcbe-114">LINQ ve dosya dizinleri (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7fcbe-114">LINQ and File Directories (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
