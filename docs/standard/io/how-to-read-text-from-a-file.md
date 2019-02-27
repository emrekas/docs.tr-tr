---
title: 'Nasıl yapılır: Bir dosyadan metin okuma'
ms.date: 01/03/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- streams, reading text from files
- reading text files
- reading data, text files
- data streams, reading text from files
- I/O [.NET Framework], reading text from files
ms.assetid: ed180baa-dfc6-4c69-a725-46e87edafb27
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7330c209ce6514459d3ab1dd58dc1c80b1978a56
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/26/2019
ms.locfileid: "56834959"
---
# <a name="how-to-read-text-from-a-file"></a><span data-ttu-id="6f402-102">Nasıl yapılır: Bir dosyadan metin okuma</span><span class="sxs-lookup"><span data-stu-id="6f402-102">How to: Read text from a file</span></span>
<span data-ttu-id="6f402-103">Aşağıdaki örnek, masaüstü uygulamaları için .NET kullanılarak bir metin dosyasındaki metnin nasıl zaman uyumlu ve zaman uyumsuz olarak okunacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="6f402-103">The following examples show how to read text synchronously and asynchronously from a text file using .NET for desktop apps.</span></span> <span data-ttu-id="6f402-104">Her iki örnek örneğini oluşturduğunuzda <xref:System.IO.StreamReader> sınıfı, dosyanın göreli veya mutlak yolunu sağlayın.</span><span class="sxs-lookup"><span data-stu-id="6f402-104">In both examples, when you create the instance of the <xref:System.IO.StreamReader> class, you provide the relative or absolute path to the file.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6f402-105">Windows çalışma zamanı için dosyaları okuma ve yazma için farklı akış türleri sağladığından Bu kod örnekleri için evrensel Windows (UWP) uygulamaları, geliştirme için geçerli değildir.</span><span class="sxs-lookup"><span data-stu-id="6f402-105">These code examples do not apply to developing for Universal Windows (UWP) apps, because the Windows Runtime provides different stream types for reading and writing to files.</span></span> <span data-ttu-id="6f402-106">Bir UWP uygulamasında bir dosyadan metin okuma gösteren bir örnek için bkz: [hızlı başlangıç: Dosyaları okuma ve yazma](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10)).</span><span class="sxs-lookup"><span data-stu-id="6f402-106">For an example that shows how to read text from a file in a UWP app, see [Quickstart: Reading and writing files](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10)).</span></span> <span data-ttu-id="6f402-107">.NET Framework akışları ile Windows çalışma zamanı akışları arasında dönüştürme yapılacağını gösteren örnekler için bkz [nasıl yapılır: .NET Framework akışları ve Windows çalışma zamanı akışları arasında dönüştürme](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span><span class="sxs-lookup"><span data-stu-id="6f402-107">For examples that show how to convert between .NET Framework streams and Windows Runtime streams, see [How to: Convert between .NET Framework streams and Windows Runtime streams](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span></span>  
  
## <a name="example-synchronous-read-in-a-console-app"></a><span data-ttu-id="6f402-108">Örnek: Bir konsol uygulamasında zaman uyumlu okuma</span><span class="sxs-lookup"><span data-stu-id="6f402-108">Example: Synchronous read in a console app</span></span>  
<span data-ttu-id="6f402-109">Aşağıdaki örnek bir konsol uygulaması bir zaman uyumlu okuma işlemini gösterir.</span><span class="sxs-lookup"><span data-stu-id="6f402-109">The following example shows a synchronous read operation within a console app.</span></span> <span data-ttu-id="6f402-110">Bu örnek, bir akış okuyucusunu kullanarak metin dosyasını açar, içeriğini bir dizeye kopyalar ve konsola dizesi çıkarır.</span><span class="sxs-lookup"><span data-stu-id="6f402-110">This example opens the text file using a stream reader, copies the contents to a string, and outputs the string to the console.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6f402-111">Örnek adlı bir dosya olduğunu varsayar *TestFile.txt* uygulama ile aynı klasörde zaten mevcut.</span><span class="sxs-lookup"><span data-stu-id="6f402-111">The example assumes that a file named *TestFile.txt* already exists in the same folder as the app.</span></span>  

 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example-asynchronous-read-in-a-wpf-app"></a><span data-ttu-id="6f402-112">Örnek: Bir WPF uygulamasında zaman uyumsuz okuma</span><span class="sxs-lookup"><span data-stu-id="6f402-112">Example: Asynchronous read in a WPF app</span></span> 
 <span data-ttu-id="6f402-113">Aşağıdaki örnek, bir Windows Presentation Foundation (WPF) uygulamasında zaman uyumsuz bir okuma işlemini gösterir.</span><span class="sxs-lookup"><span data-stu-id="6f402-113">The following example shows an asynchronous read operation in a Windows Presentation Foundation (WPF) app.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6f402-114">Örnek adlı bir dosya olduğunu varsayar *TestFile.txt* uygulama ile aynı klasörde zaten mevcut.</span><span class="sxs-lookup"><span data-stu-id="6f402-114">The example assumes that a file named *TestFile.txt* already exists in the same folder as the app.</span></span>  

 [!code-csharp[TextFiles](../../../samples/snippets/csharp/VS_Snippets_Wpf/TextFiles/MainWindow.xaml.cs)]
 [!code-vb[TextFiles](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextFiles/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6f402-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="6f402-115">See also</span></span>

- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="6f402-116">Zaman uyumsuz dosya g/ç</span><span class="sxs-lookup"><span data-stu-id="6f402-116">Asynchronous file I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
- <span data-ttu-id="6f402-117">[Nasıl yapılır: Create a directory listing](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="6f402-117">[How to: Create a directory listing](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))</span></span>  
- [<span data-ttu-id="6f402-118">Hızlı Başlangıç: Dosyaları okuma ve yazma</span><span class="sxs-lookup"><span data-stu-id="6f402-118">Quickstart: Reading and writing files</span></span>](https://docs.microsoft.com/previous-versions/windows/apps/hh758325%28v=win.10%29)  
- [<span data-ttu-id="6f402-119">Nasıl yapılır: .NET Framework akışları ve Windows çalışma zamanı akışları arasında dönüştürme</span><span class="sxs-lookup"><span data-stu-id="6f402-119">How to: Convert between .NET Framework streams and Windows Runtime streams</span></span>](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
- [<span data-ttu-id="6f402-120">Nasıl yapılır: Okuma ve yeni oluşturulan veri dosyasına yazma</span><span class="sxs-lookup"><span data-stu-id="6f402-120">How to: Read and write to a newly created data file</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="6f402-121">Nasıl yapılır: Açın ve bir günlük dosyasına Ekle</span><span class="sxs-lookup"><span data-stu-id="6f402-121">How to: Open and append to a log file</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="6f402-122">Nasıl yapılır: Bir dosyaya metin yazma</span><span class="sxs-lookup"><span data-stu-id="6f402-122">How to: Write text to a file</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="6f402-123">Nasıl yapılır: Dizeden karakterleri okuma</span><span class="sxs-lookup"><span data-stu-id="6f402-123">How to: Read characters from a string</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
- [<span data-ttu-id="6f402-124">Nasıl yapılır: Bir dizeye karakter yazma</span><span class="sxs-lookup"><span data-stu-id="6f402-124">How to: Write characters to a string</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="6f402-125">Dosya ve akış g/ç</span><span class="sxs-lookup"><span data-stu-id="6f402-125">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
