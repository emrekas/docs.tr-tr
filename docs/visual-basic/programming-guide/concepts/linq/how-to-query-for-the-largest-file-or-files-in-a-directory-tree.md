---
title: 'Nasıl yapılır: En büyük dosya veya dizin ağacında (LINQ) (Visual Basic) dosyalar için sorgu'
ms.date: 07/20/2015
ms.assetid: 8c1c9f0c-95dd-4222-9be2-9ec026a13e81
ms.openlocfilehash: 7ba330b18020b7c3b823b70d0541cdda199aa898
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58820733"
---
# <a name="how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq-visual-basic"></a><span data-ttu-id="7a547-102">Nasıl yapılır: En büyük dosya veya dizin ağacında (LINQ) (Visual Basic) dosyalar için sorgu</span><span class="sxs-lookup"><span data-stu-id="7a547-102">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="7a547-103">Bu örnek dosyanın bayt cinsinden boyutu ile ilgili beş sorguları gösterir:</span><span class="sxs-lookup"><span data-stu-id="7a547-103">This example shows five queries related to file size in bytes:</span></span>  
  
-   <span data-ttu-id="7a547-104">Bayt cinsinden en büyük dosya boyutu almak nasıl.</span><span class="sxs-lookup"><span data-stu-id="7a547-104">How to retrieve the size in bytes of the largest file.</span></span>  
  
-   <span data-ttu-id="7a547-105">En küçük dosyanın bayt cinsinden boyutunu almak nasıl.</span><span class="sxs-lookup"><span data-stu-id="7a547-105">How to retrieve the size in bytes of the smallest file.</span></span>  
  
-   <span data-ttu-id="7a547-106">Nasıl alınacağını <xref:System.IO.FileInfo> belirtilen kök klasörünün altında bir veya daha fazla klasörlerden nesne en büyük veya küçük dosyası.</span><span class="sxs-lookup"><span data-stu-id="7a547-106">How to retrieve the <xref:System.IO.FileInfo> object largest or smallest file from one or more folders under a specified root folder.</span></span>  
  
-   <span data-ttu-id="7a547-107">10 en büyük dosyaları gibi bir dizi almak nasıl.</span><span class="sxs-lookup"><span data-stu-id="7a547-107">How to retrieve a sequence such as the 10 largest files.</span></span>  
  
-   <span data-ttu-id="7a547-108">Nasıl yapılır sırası dosyaları, dosya boyutu bayt cinsinden göre gruplara belirtilen bir boyuttan daha az olan dosyalar yoksayılıyor.</span><span class="sxs-lookup"><span data-stu-id="7a547-108">How to order files into groups based on their file size in bytes, ignoring files that are less than a specified size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a547-109">Örnek</span><span class="sxs-lookup"><span data-stu-id="7a547-109">Example</span></span>  
 <span data-ttu-id="7a547-110">Aşağıdaki örnek, sorgulama ve bunların dosya boyutunu bayt cinsinden bağlı olarak, Grup dosyaları göster beş ayrı sorguları içerir.</span><span class="sxs-lookup"><span data-stu-id="7a547-110">The following example contains five separate queries that show how to query and group files, depending on their file size in bytes.</span></span> <span data-ttu-id="7a547-111">Bu örnekler diğer bazı özellikte sorgu temel kolayca değiştirebilirsiniz <xref:System.IO.FileInfo> nesne.</span><span class="sxs-lookup"><span data-stu-id="7a547-111">You can easily modify these examples to base the query on some other property of the <xref:System.IO.FileInfo> object.</span></span>  
  
```vb  
Module QueryBySize  
    Sub Main()  
  
        ' Change the drive\path if necessary  
        Dim root As String = "C:\Program Files\Microsoft Visual Studio 9.0"  
  
        'Take a snapshot of the folder contents  
        Dim dir As New System.IO.DirectoryInfo(root)  
        Dim fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories)  
  
        ' Return the size of the largest file  
        Dim maxSize = Aggregate aFile In fileList Into Max(GetFileLength(aFile))  
  
        'Dim maxSize = fileLengths.Max  
        Console.WriteLine("The length of the largest file under {0} is {1}", _  
                          root, maxSize)  
  
        ' Return the FileInfo object of the largest file  
        ' by sorting and selecting from the beginning of the list  
        Dim filesByLengDesc = From file In fileList _  
                              Let filelength = GetFileLength(file) _  
                              Where filelength > 0 _  
                              Order By filelength Descending _  
                              Select file  
  
        Dim longestFile = filesByLengDesc.First  
  
        Console.WriteLine("The largest file under {0} is {1} with a length of {2} bytes", _  
                          root, longestFile.FullName, longestFile.Length)  
  
        Dim smallestFile = filesByLengDesc.Last  
  
        Console.WriteLine("The smallest file under {0} is {1} with a length of {2} bytes", _  
                                root, smallestFile.FullName, smallestFile.Length)  
  
        ' Return the FileInfos for the 10 largest files  
        ' Based on a previous query, but nothing is executed  
        ' until the For Each statement below.  
        Dim tenLargest = From file In filesByLengDesc Take 10  
  
        Console.WriteLine("The 10 largest files under {0} are:", root)  
  
        For Each fi As System.IO.FileInfo In tenLargest  
            Console.WriteLine("{0}: {1} bytes", fi.FullName, fi.Length)  
        Next  
  
        ' Group files according to their size,  
        ' leaving out the ones under 200K  
        Dim sizeGroups = From file As System.IO.FileInfo In fileList _  
                         Where file.Length > 0 _  
                         Let groupLength = file.Length / 100000 _  
                         Group file By groupLength Into fileGroup = Group _  
                         Where groupLength >= 2 _  
                         Order By groupLength Descending  
  
        For Each group In sizeGroups  
            Console.WriteLine(group.groupLength + "00000")  
  
            For Each item As System.IO.FileInfo In group.fileGroup  
                Console.WriteLine("   {0}: {1}", item.Name, item.Length)  
            Next  
        Next  
  
        ' Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
  
    End Sub  
  
    ' This method is used to catch the possible exception  
    ' that can be raised when accessing the FileInfo.Length property.  
    ' In this particular case, it is safe to ignore the exception.  
    Function GetFileLength(ByVal fi As System.IO.FileInfo) As Long  
        Dim retval As Long  
        Try  
            retval = fi.Length  
        Catch ex As FileNotFoundException  
            ' If a file is no longer present,  
            ' just return zero bytes.   
            retval = 0  
        End Try  
  
        Return retval  
    End Function  
End Module  
```  
  
 <span data-ttu-id="7a547-112">Bir veya daha fazla tamamlamak döndürülecek <xref:System.IO.FileInfo> nesneler, sorguyu ilk denetleyeceğini her bir veri kaynağı ve sonra bunları kendi uzunluğu özelliğinin değeri sıralayın.</span><span class="sxs-lookup"><span data-stu-id="7a547-112">To return one or more complete <xref:System.IO.FileInfo> objects, the query first must examine each one in the data source, and then sort them by the value of their Length property.</span></span> <span data-ttu-id="7a547-113">Ardından tek bir ya da ile en fazla uzunluk dizisi döndürebilir.</span><span class="sxs-lookup"><span data-stu-id="7a547-113">Then it can return the single one or the sequence with the greatest lengths.</span></span> <span data-ttu-id="7a547-114">Kullanım <xref:System.Linq.Enumerable.First%2A> listedeki ilk öğe döndürmek için.</span><span class="sxs-lookup"><span data-stu-id="7a547-114">Use <xref:System.Linq.Enumerable.First%2A> to return the first element in a list.</span></span> <span data-ttu-id="7a547-115">Kullanım <xref:System.Linq.Enumerable.Take%2A> ilk n öğe sayısını döndürmek için.</span><span class="sxs-lookup"><span data-stu-id="7a547-115">Use <xref:System.Linq.Enumerable.Take%2A> to return the first n number of elements.</span></span> <span data-ttu-id="7a547-116">Listenin başında en küçük öğeleri yerleştirmek için azalan sıralama düzeni belirtin.</span><span class="sxs-lookup"><span data-stu-id="7a547-116">Specify a descending sort order to put the smallest elements at the start of the list.</span></span>  
  
 <span data-ttu-id="7a547-117">Burada bir dosya silindi başka bir iş parçacığında bu yana zaman dönemi içindeki durumda gerçekleştirilecektir olası özel kullanmak bayt cinsinden boyutunu almak için ayrı bir yöntem için sorguyu çağırır <xref:System.IO.FileInfo> nesne oluşturulduğu çağrısında`GetFiles`.</span><span class="sxs-lookup"><span data-stu-id="7a547-117">The query calls out to a separate method to obtain the file size in bytes in order to consume the possible exception that will be raised in the case where a file was deleted on another thread in the time period since the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="7a547-118">Bile aracılığıyla <xref:System.IO.FileInfo> nesnesi zaten oluşturuldu, özel durum ortaya çıkabilir çünkü bir <xref:System.IO.FileInfo> nesne yenilemek çalışır, <xref:System.IO.FileInfo.Length%2A> erişilen özelliği ilk kez en geçerli boyutunu bayt cinsinden kullanarak özellik.</span><span class="sxs-lookup"><span data-stu-id="7a547-118">Even through the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property by using the most current size in bytes the first time the property is accessed.</span></span> <span data-ttu-id="7a547-119">Bu işlem bir try-catch bloğunda sorgu dışında koyarak, biz yan etkilere neden olabilecek sorguları işlemlerinde önleme kural izleyin.</span><span class="sxs-lookup"><span data-stu-id="7a547-119">By putting this operation in a try-catch block outside the query, we follow the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="7a547-120">Genel olarak, çok dikkatli özel durumlar, tüketildiğinde uygulama bilinmeyen bir durumda kaldı değil emin olmak için özenli olunması gerekir.</span><span class="sxs-lookup"><span data-stu-id="7a547-120">In general, great care must be taken when consuming exceptions, to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7a547-121">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="7a547-121">Compiling the Code</span></span>  
 <span data-ttu-id="7a547-122">.NET Framework sürüm 3.5 veya daha yüksek bir System.Core.dll başvurusu ile hedefleyen bir proje oluşturun ve bir `Imports` System.Linq ad alanı bildirimi.</span><span class="sxs-lookup"><span data-stu-id="7a547-122">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a547-123">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="7a547-123">See also</span></span>

- [<span data-ttu-id="7a547-124">LINQ to Objects'in (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a547-124">LINQ to Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
- [<span data-ttu-id="7a547-125">LINQ ve dosya dizinleri (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a547-125">LINQ and File Directories (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
