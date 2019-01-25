---
title: 'Nasıl yapılır: -Bir metin dosyasına yazma C# Programlama Kılavuzu'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
ms.openlocfilehash: ce0321d91835fbdf6c37f4b7736f0de900e9f838
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666806"
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a><span data-ttu-id="7da54-102">Nasıl yapılır: Bir metin dosyasına yazma (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="7da54-102">How to: Write to a Text File (C# Programming Guide)</span></span>
<span data-ttu-id="7da54-103">Bu örnekler bir metin dosyasına yazmanın çeşitli yollarını göstermektedir.</span><span class="sxs-lookup"><span data-stu-id="7da54-103">These examples show various ways to write text to a file.</span></span> <span data-ttu-id="7da54-104">İlk iki örnek statik yöntemler kullanın <xref:System.IO.File?displayProperty=nameWithType> her öğe herhangi yazmak için sınıf `IEnumerable<string>` ve bir metin dosyasına bir dize.</span><span class="sxs-lookup"><span data-stu-id="7da54-104">The first two examples use static convenience methods on the <xref:System.IO.File?displayProperty=nameWithType> class to write each element of any `IEnumerable<string>` and a string to a text file.</span></span> <span data-ttu-id="7da54-105">Örnek 3, dosyaya yazmak gibi her satır ayrı ayrı işlemeniz gerektiğinde bir dosyaya metin ekleme gösterir.</span><span class="sxs-lookup"><span data-stu-id="7da54-105">Example 3 shows how to add text to a file when you have to process each line individually as you write to the file.</span></span> <span data-ttu-id="7da54-106">Örnek 1-3 dosyasındaki tüm varolan içeriğin üzerine, ancak örnek 4 varolan bir dosyaya nasıl metin ekleneceği gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="7da54-106">Examples 1-3 overwrite all existing content in the file, but example 4 shows you how to append text to an existing file.</span></span>  
  
 <span data-ttu-id="7da54-107">Bu örneklerin tümü dosyalara dize değişmez değerleri yazmaktadır.</span><span class="sxs-lookup"><span data-stu-id="7da54-107">These examples all write string literals to files.</span></span> <span data-ttu-id="7da54-108">Bir dosyaya yazılacak Metin biçimlendirmek istediğiniz kullanırsanız <xref:System.String.Format%2A> yöntemi veya C# [dize ilişkilendirme](../../../csharp/language-reference/tokens/interpolated.md) özelliği.</span><span class="sxs-lookup"><span data-stu-id="7da54-108">If you want to format text written to a file, use the <xref:System.String.Format%2A> method or C# [string interpolation](../../../csharp/language-reference/tokens/interpolated.md) feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7da54-109">Örnek</span><span class="sxs-lookup"><span data-stu-id="7da54-109">Example</span></span>  
 [!code-csharp[csFilesandFolders#3](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-write-to-a-text-file_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="7da54-110">Güçlü Programlama</span><span class="sxs-lookup"><span data-stu-id="7da54-110">Robust Programming</span></span>  
 <span data-ttu-id="7da54-111">Aşağıdaki koşullar özel bir duruma neden olabilir:</span><span class="sxs-lookup"><span data-stu-id="7da54-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="7da54-112">Dosya mevcut ve salt okunur.</span><span class="sxs-lookup"><span data-stu-id="7da54-112">The file exists and is read-only.</span></span>  
  
-   <span data-ttu-id="7da54-113">Yol adı çok uzun olabilir.</span><span class="sxs-lookup"><span data-stu-id="7da54-113">The path name may be too long.</span></span>  
  
-   <span data-ttu-id="7da54-114">Disk dolu olabilir.</span><span class="sxs-lookup"><span data-stu-id="7da54-114">The disk may be full.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7da54-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="7da54-115">See also</span></span>

- [<span data-ttu-id="7da54-116">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="7da54-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="7da54-117">Dosya sistemi ve kayıt defteri (C# programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="7da54-117">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)
- [<span data-ttu-id="7da54-118">Örnek: Bir koleksiyonu uygulama depolamaya kaydetme</span><span class="sxs-lookup"><span data-stu-id="7da54-118">Sample: Save a collection to Application Storage</span></span>](https://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
