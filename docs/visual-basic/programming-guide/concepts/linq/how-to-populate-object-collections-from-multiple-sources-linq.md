---
title: 'Nasıl yapılır: (LINQ) (Visual Basic) birden fazla kaynaktan nesne koleksiyonları doldurma'
ms.date: 06/22/2018
ms.assetid: 63062a22-e6a9-42c0-b357-c7c965f58f33
ms.openlocfilehash: 0228d152539abe3bf0db5a8e5bf4581eaf957b31
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638827"
---
# <a name="how-to-populate-object-collections-from-multiple-sources-linq-visual-basic"></a><span data-ttu-id="2de25-102">Nasıl yapılır: (LINQ) (Visual Basic) birden fazla kaynaktan nesne koleksiyonları doldurma</span><span class="sxs-lookup"><span data-stu-id="2de25-102">How to: Populate Object Collections from Multiple Sources (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="2de25-103">Bu örnek, yeni türleri dizisine farklı kaynaklardan verileri birleştirme gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="2de25-103">This example shows how to merge data from different sources into a sequence of new types.</span></span>

> [!NOTE]
> <span data-ttu-id="2de25-104">Bellek içi verileri veya veri, dosya sisteminde hala bir veritabanındaki verilerle katılın çalışmayın.</span><span class="sxs-lookup"><span data-stu-id="2de25-104">Don't try to join in-memory data or data in the file system with data that is still in a database.</span></span> <span data-ttu-id="2de25-105">Böyle etki alanları arası birleştirmeler farklı şekilde, birleştirme işlemleri veritabanı sorguları ve diğer kaynağı türleri için tanımlanabilir nedeniyle tanımlanmamış sonuçlara yol açabilir.</span><span class="sxs-lookup"><span data-stu-id="2de25-105">Such cross-domain joins can yield undefined results because of different ways in which join operations might be defined for database queries and other types of sources.</span></span> <span data-ttu-id="2de25-106">Buna ek olarak, veritabanındaki veri miktarı yeterince büyük olduğunda bu tür bir işlem bellek yetersiz özel durum neden olabilecek bir riski yoktur.</span><span class="sxs-lookup"><span data-stu-id="2de25-106">Additionally, there is a risk that such an operation could cause an out-of-memory exception if the amount of data in the database is large enough.</span></span> <span data-ttu-id="2de25-107">Bellek içi veriler bir veritabanından veri katılmak için ilk çağrı `ToList` veya `ToArray` veritabanında sorgu ve ardından birleştirme döndürülen koleksiyon üzerinde gerçekleştirin.</span><span class="sxs-lookup"><span data-stu-id="2de25-107">To join data from a database to in-memory data, first call `ToList` or `ToArray` on the database query, and then perform the join on the returned collection.</span></span>

## <a name="to-create-the-data-file"></a><span data-ttu-id="2de25-108">Veri dosyası oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="2de25-108">To create the data file</span></span>

- <span data-ttu-id="2de25-109">Bölümünde anlatıldığı gibi names.csv ve scores.csv dosyaları proje klasörünüze kopyalayın [nasıl yapılır: Dosyalardan içerik (LINQ) (Visual Basic) katılın](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md).</span><span class="sxs-lookup"><span data-stu-id="2de25-109">Copy the names.csv and scores.csv files into your project folder, as described in [How to: Join Content from Dissimilar Files (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md).</span></span>

## <a name="example"></a><span data-ttu-id="2de25-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="2de25-110">Example</span></span>

<span data-ttu-id="2de25-111">Aşağıdaki örnek, adlandırılmış tür işlemi gösterilir `Student` birleştirilen verilerin elektronik tablo verilerini .csv biçiminde benzetimini dizeleri iki bellek içi koleksiyonlardan depolamak için.</span><span class="sxs-lookup"><span data-stu-id="2de25-111">The following example shows how to use a named type `Student` to store merged data from two in-memory collections of strings that simulate spreadsheet data in .csv format.</span></span> <span data-ttu-id="2de25-112">Dizenin ilk koleksiyon kimlikleri ve Öğrenci adlarını ve ikinci koleksiyon Öğrenci Kimliği (ilk sütunda) ve dört sınavı puanları temsil eder.</span><span class="sxs-lookup"><span data-stu-id="2de25-112">The first collection of strings represents the student names and IDs, and the second collection represents the student ID (in the first column) and four exam scores.</span></span> <span data-ttu-id="2de25-113">Kimlik, yabancı anahtar olarak kullanılır.</span><span class="sxs-lookup"><span data-stu-id="2de25-113">The ID is used as the foreign key.</span></span>

```vb
Imports System.Collections.Generic
Imports System.Linq

Class Student
    Public FirstName As String
    Public LastName As String
    Public ID As Integer
    Public ExamScores As List(Of Integer)
End Class

Class PopulateCollection

    Shared Sub Main()

        ' Merge content from spreadsheets into a list of Student objects.

        ' These data files are defined in How to: Join Content from
        ' Dissimilar Files (LINQ).

        ' Each line of names.csv consists of a last name, a first name, and an
        ' ID number, separated by commas. For example, Omelchenko,Svetlana,111
        Dim names As String() = System.IO.File.ReadAllLines("../../../names.csv")

        ' Each line of scores.csv consists of an ID number and four test
        ' scores, separated by commas. For example, 111, 97, 92, 81, 60
        Dim scores As String() = System.IO.File.ReadAllLines("../../../scores.csv")

        ' The following query merges the content of two dissimilar spreadsheets
        ' based on common ID values.
        ' Multiple From clauses are used instead of a Join clause
        ' in order to store the results of scoreLine.Split.
        ' Note the dynamic creation of a list of integers for the
        ' ExamScores member. The first item is skipped in the split string
        ' because it is the student ID, not an exam score.
        Dim queryNamesScores = From nameLine In names
                          Let splitName = nameLine.Split(New Char() {","})
                          From scoreLine In scores
                          Let splitScoreLine = scoreLine.Split(New Char() {","})
                          Where Convert.ToInt32(splitName(2)) = Convert.ToInt32(splitScoreLine(0))
                          Select New Student() With {
                               .FirstName = splitName(0), .LastName = splitName(1), .ID = splitName(2),
                               .ExamScores = (From scoreAsText In splitScoreLine Skip 1
                                             Select Convert.ToInt32(scoreAsText)).ToList()}

        ' Optional. Store the query results for faster access in future
        ' queries. This could be useful with very large data files.
        Dim students As List(Of Student) = queryNamesScores.ToList()

        ' Display each student's name and exam score average.
        For Each s In students
            Console.WriteLine("The average score of " & s.FirstName & " " &
                              s.LastName & " is " & s.ExamScores.Average())
        Next

        ' Keep console window open in debug mode.
        Console.WriteLine("Press any key to exit.")
        Console.ReadKey()
    End Sub
End Class

' Output:
' The average score of Omelchenko Svetlana is 82.5
' The average score of O'Donnell Claire is 72.25
' The average score of Mortensen Sven is 84.5
' The average score of Garcia Cesar is 88.25
' The average score of Garcia Debra is 67
' The average score of Fakhouri Fadi is 92.25
' The average score of Feng Hanying is 88
' The average score of Garcia Hugo is 85.75
' The average score of Tucker Lance is 81.75
' The average score of Adams Terry is 85.25
' The average score of Zabokritski Eugene is 83
' The average score of Tucker Michael is 92
```

<span data-ttu-id="2de25-114">İçinde [Select tümcesi](../../../../visual-basic/language-reference/queries/select-clause.md) yan tümcesi, bir nesne Başlatıcı her yeni örneği oluşturmak için kullanılan `Student` iki kaynaklardan gelen verileri kullanarak nesne.</span><span class="sxs-lookup"><span data-stu-id="2de25-114">In the [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md) clause, an object initializer is used to instantiate each new `Student` object by using the data from the two sources.</span></span>

<span data-ttu-id="2de25-115">Bir sorgunun sonuçlarını depolamak yoksa, anonim türleri adlandırılmış türler daha kullanışlı olabilir.</span><span class="sxs-lookup"><span data-stu-id="2de25-115">If you don't have to store the results of a query, anonymous types can be more convenient than named types.</span></span> <span data-ttu-id="2de25-116">Sorgu sonuçları sorgunun yürütüldüğü yöntemi dışında geçirirseniz, adlandırılmış türler gereklidir.</span><span class="sxs-lookup"><span data-stu-id="2de25-116">Named types are required if you pass the query results outside the method in which the query is executed.</span></span> <span data-ttu-id="2de25-117">Aşağıdaki örnek önceki örnekle aynı görevi gerçekleştirir, ancak anonim türler yerine adlandırılmış türlerini kullanır:</span><span class="sxs-lookup"><span data-stu-id="2de25-117">The following example performs the same task as the previous example, but uses anonymous types instead of named types:</span></span>

```vb
' Merge the data by using an anonymous type.
' Note the dynamic creation of a list of integers for the
' ExamScores member. We skip 1 because the first string
' in the array is the student ID, not an exam score.
Dim queryNamesScores2 =
    From nameLine In names
    Let splitName = nameLine.Split(New Char() {","})
    From scoreLine In scores
    Let splitScoreLine = scoreLine.Split(New Char() {","})
    Where Convert.ToInt32(splitName(2)) = Convert.ToInt32(splitScoreLine(0))
    Select New With
           {.Last = splitName(0),
            .First = splitName(1),
            .ExamScores = (From scoreAsText In splitScoreLine Skip 1
                           Select Convert.ToInt32(scoreAsText)).ToList()}

' Display each student's name and exam score average.
For Each s In queryNamesScores2
    Console.WriteLine("The average score of " & s.First & " " &
                      s.Last & " is " & s.ExamScores.Average())
Next
```

## <a name="compiling-the-code"></a><span data-ttu-id="2de25-118">Kod derleme</span><span class="sxs-lookup"><span data-stu-id="2de25-118">Compiling the code</span></span>

<span data-ttu-id="2de25-119">Oluşturun ve aşağıdaki seçeneklerden birini hedefleyen bir proje derleme:</span><span class="sxs-lookup"><span data-stu-id="2de25-119">Create and compile a project that targets one of the following options:</span></span>

- <span data-ttu-id="2de25-120">.NET framework sürüm 3.5 System.Core.dll öğesine başvuru ile.</span><span class="sxs-lookup"><span data-stu-id="2de25-120">.NET Framework version 3.5 with a reference to System.Core.dll.</span></span>
- <span data-ttu-id="2de25-121">.NET framework sürüm 4.0 veya üzeri.</span><span class="sxs-lookup"><span data-stu-id="2de25-121">.NET Framework version 4.0 or higher.</span></span>
- <span data-ttu-id="2de25-122">.NET core sürüm 1.0 veya üzeri.</span><span class="sxs-lookup"><span data-stu-id="2de25-122">.NET Core version 1.0 or higher.</span></span>

## <a name="see-also"></a><span data-ttu-id="2de25-123">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="2de25-123">See also</span></span>

- [<span data-ttu-id="2de25-124">LINQ ve dizeler (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2de25-124">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
