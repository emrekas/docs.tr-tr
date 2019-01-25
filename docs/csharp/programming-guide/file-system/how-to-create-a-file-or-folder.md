---
title: 'Nasıl yapılır: Bir dosya veya klasör - oluşturma C# Programlama Kılavuzu'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- folders [C#]
- creating files [C#]
- files [C#]
- creating folders [C#]
ms.assetid: 4582ee2d-d72d-4687-bcb9-08d336c62c25
ms.openlocfilehash: 8f0b375a2e2ed7304c43a27309dbdde5a2f5a476
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54731887"
---
# <a name="how-to-create-a-file-or-folder-c-programming-guide"></a><span data-ttu-id="8f8f1-102">Nasıl yapılır: Bir dosya veya klasör oluşturma (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="8f8f1-102">How to: Create a File or Folder (C# Programming Guide)</span></span>
<span data-ttu-id="8f8f1-103">Programlı olarak bilgisayarınızda bir klasör oluşturun, bir alt klasör oluşturun alt klasöründe bir dosya oluşturun ve dosyaya veri yazmak.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-103">You can programmatically create a folder on your computer, create a subfolder, create a file in the subfolder, and write data to the file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f8f1-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="8f8f1-104">Example</span></span>  
 [!code-csharp[csFilesandFolders#10](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-create-a-file-or-folder_1.cs)]  
  
 <span data-ttu-id="8f8f1-105">Klasör zaten varsa, <xref:System.IO.Directory.CreateDirectory%2A> hiçbir şey ve hiçbir özel durum atılmaz.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-105">If the folder already exists, <xref:System.IO.Directory.CreateDirectory%2A> does nothing, and no exception is thrown.</span></span> <span data-ttu-id="8f8f1-106">Ancak, <xref:System.IO.File.Create%2A?displayProperty=nameWithType> mevcut bir dosyayı yeni bir dosya ile değiştirir.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-106">However, <xref:System.IO.File.Create%2A?displayProperty=nameWithType> replaces an existing file with a new file.</span></span> <span data-ttu-id="8f8f1-107">Örnekte bir `if` - `else` varolan bir dosyanın değiştirilmesini önlemek için deyimi.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-107">The example uses an `if`-`else` statement to prevent an existing file from being replaced.</span></span>  
  
 <span data-ttu-id="8f8f1-108">Örnekte aşağıdaki değişiklikleri yaparak, belirli bir ada sahip bir dosya zaten var olup üzerinde göre farklı sonuçlar belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-108">By making the following changes in the example, you can specify different outcomes based on whether a file with a certain name already exists.</span></span> <span data-ttu-id="8f8f1-109">Böyle bir dosya yoksa, kod bir tane oluşturur.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-109">If such a file doesn't exist, the code creates one.</span></span> <span data-ttu-id="8f8f1-110">Böyle bir dosya varsa, kod verileri bu dosyaya ekler.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-110">If such a file exists, the code appends data to that file.</span></span>  
  
-   <span data-ttu-id="8f8f1-111">Rastgele olmayan dosya adı belirtin.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-111">Specify a non-random file name.</span></span>  
  
    ```csharp  
    // Comment out the following line.  
    //string fileName = System.IO.Path.GetRandomFileName();  
  
    // Replace that line with the following assignment.  
    string fileName = "MyNewFile.txt";  
    ```  
  
-   <span data-ttu-id="8f8f1-112">Değiştirin `if` - `else` deyimiyle `using` aşağıdaki kodda deyimi.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-112">Replace the `if`-`else` statement with the `using` statement in the following code.</span></span>  
  
    ```csharp  
    using (System.IO.FileStream fs = new System.IO.FileStream(pathString, FileMode.Append))   
    {  
        for (byte i = 0; i < 100; i++)  
        {  
            fs.WriteByte(i);  
        }  
    }  
    ```  
  
 <span data-ttu-id="8f8f1-113">Örneği birkaç kere çalıştırın verileri doğrulamak için dosyayı her seferinde eklenir.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-113">Run the example several times to verify that data is added to the file each time.</span></span>  
  
 <span data-ttu-id="8f8f1-114">Daha fazla bilgi için `FileMode` , bkz, deneyebileceğiniz değerleri <xref:System.IO.FileMode>.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-114">For more `FileMode` values that you can try, see <xref:System.IO.FileMode>.</span></span>  
  
 <span data-ttu-id="8f8f1-115">Aşağıdaki koşullar özel bir duruma neden olabilir:</span><span class="sxs-lookup"><span data-stu-id="8f8f1-115">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="8f8f1-116">Klasör adı yanlış biçimlendirilmiş.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-116">The folder name is malformed.</span></span> <span data-ttu-id="8f8f1-117">Örneğin, geçersiz karakterler içeriyor veya yalnızca boşluk (<xref:System.ArgumentException> sınıfı).</span><span class="sxs-lookup"><span data-stu-id="8f8f1-117">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException> class).</span></span> <span data-ttu-id="8f8f1-118">Kullanım <xref:System.IO.Path> geçerli yol adları oluşturmak için sınıf.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-118">Use the <xref:System.IO.Path> class to create valid path names.</span></span>  
  
-   <span data-ttu-id="8f8f1-119">Oluşturulacak klasörün üst klasörü salt okunurdur (<xref:System.IO.IOException> sınıfı).</span><span class="sxs-lookup"><span data-stu-id="8f8f1-119">The parent folder of the folder to be created is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="8f8f1-120">Klasör adı `null` (<xref:System.ArgumentNullException> sınıfı).</span><span class="sxs-lookup"><span data-stu-id="8f8f1-120">The folder name is `null` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="8f8f1-121">Klasör adı çok uzun (<xref:System.IO.PathTooLongException> sınıfı).</span><span class="sxs-lookup"><span data-stu-id="8f8f1-121">The folder name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="8f8f1-122">Yalnızca bir iki nokta üst üste, klasör adı olan ":" (<xref:System.IO.PathTooLongException> sınıfı).</span><span class="sxs-lookup"><span data-stu-id="8f8f1-122">The folder name is only a colon, ":" (<xref:System.IO.PathTooLongException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="8f8f1-123">.NET Framework Güvenliği</span><span class="sxs-lookup"><span data-stu-id="8f8f1-123">.NET Framework Security</span></span>  
 <span data-ttu-id="8f8f1-124">Örneği <xref:System.Security.SecurityException> sınıfı kısmi güven durumlarda oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-124">An instance of the <xref:System.Security.SecurityException> class may be thrown in partial-trust situations.</span></span>  
  
 <span data-ttu-id="8f8f1-125">Klasör oluşturma izniniz yoksa, örnek bir örneğini atar <xref:System.UnauthorizedAccessException> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-125">If you don’t have permission to create the folder, the example throws an instance of the <xref:System.UnauthorizedAccessException> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f8f1-126">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="8f8f1-126">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="8f8f1-127">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="8f8f1-127">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="8f8f1-128">Dosya sistemi ve kayıt defteri (C# programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="8f8f1-128">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)
