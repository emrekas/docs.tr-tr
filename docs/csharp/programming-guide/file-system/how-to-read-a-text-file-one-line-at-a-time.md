---
title: 'Nasıl yapılır: Bir metin dosyası bir satırı okumak (görsel C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- ReadLine method [C#]
- reading text files, line by line
- text files [C#]
ms.assetid: d62e22c5-a13c-48db-af9b-f10c801b0cb1
ms.openlocfilehash: 831f306a19d926b70170c1a6ebc4ab670f1b9851
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718656"
---
# <a name="how-to-read-a-text-file-one-line-at-a-time-visual-c"></a><span data-ttu-id="f83de-102">Nasıl yapılır: Bir metin dosyası bir satırı okumak (görsel C#)</span><span class="sxs-lookup"><span data-stu-id="f83de-102">How to: Read a Text File One Line at a Time (Visual C#)</span></span>
<span data-ttu-id="f83de-103">Bu örnek, bir dize kullanarak her seferinde bir satır bir metin dosyasının içeriğini okur `ReadLine` yöntemi `StreamReader` sınıfı.</span><span class="sxs-lookup"><span data-stu-id="f83de-103">This example reads the contents of a text file, one line at a time, into a string using the `ReadLine` method of the `StreamReader` class.</span></span> <span data-ttu-id="f83de-104">Her metin satırının dizeye depolanan `line` ve ekranda görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="f83de-104">Each text line is stored into the string `line` and displayed on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f83de-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="f83de-105">Example</span></span>  
  
```csharp
int counter = 0;  
string line;  
  
// Read the file and display it line by line.  
System.IO.StreamReader file =   
    new System.IO.StreamReader(@"c:\test.txt");  
while((line = file.ReadLine()) != null)  
{  
    System.Console.WriteLine(line);  
    counter++;  
}  
  
file.Close();  
System.Console.WriteLine("There were {0} lines.", counter);  
// Suspend the screen.  
System.Console.ReadLine();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f83de-106">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="f83de-106">Compiling the Code</span></span>  
 <span data-ttu-id="f83de-107">Kodu kopyalayın ve yapıştırın `Main` konsol uygulamasının yöntemi.</span><span class="sxs-lookup"><span data-stu-id="f83de-107">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
 <span data-ttu-id="f83de-108">Değiştirin `"c:\test.txt"` gerçek dosya adına sahip.</span><span class="sxs-lookup"><span data-stu-id="f83de-108">Replace `"c:\test.txt"` with the actual file name.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f83de-109">Güçlü Programlama</span><span class="sxs-lookup"><span data-stu-id="f83de-109">Robust Programming</span></span>  
 <span data-ttu-id="f83de-110">Aşağıdaki koşullar özel bir duruma neden olabilir:</span><span class="sxs-lookup"><span data-stu-id="f83de-110">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="f83de-111">Dosya mevcut değil.</span><span class="sxs-lookup"><span data-stu-id="f83de-111">The file may not exist.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="f83de-112">.NET Framework Güvenliği</span><span class="sxs-lookup"><span data-stu-id="f83de-112">.NET Framework Security</span></span>  
 <span data-ttu-id="f83de-113">Dosya adına dayanarak dosyanın içeriği ile ilgili kararlar vermeyin.</span><span class="sxs-lookup"><span data-stu-id="f83de-113">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="f83de-114">Örneğin, dosyayı `myFile.cs` bir C# kaynak dosyası olmayabilir.</span><span class="sxs-lookup"><span data-stu-id="f83de-114">For example, the file `myFile.cs` may not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f83de-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="f83de-115">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="f83de-116">C# Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="f83de-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="f83de-117">Dosya sistemi ve kayıt defteri (C# programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="f83de-117">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)
