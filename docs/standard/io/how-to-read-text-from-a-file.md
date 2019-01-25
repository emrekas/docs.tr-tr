---
title: 'Nasıl yapılır: Bir dosyadan metin okuma'
ms.date: 06/19/2018
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
ms.openlocfilehash: f667b0a757a676788b693691504512dfc227a7e9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646678"
---
# <a name="how-to-read-text-from-a-file"></a><span data-ttu-id="77f0c-102">Nasıl yapılır: Bir dosyadan metin okuma</span><span class="sxs-lookup"><span data-stu-id="77f0c-102">How to: Read Text from a File</span></span>
<span data-ttu-id="77f0c-103">Aşağıdaki örnek, masaüstü uygulamaları için .NET kullanılarak bir metin dosyasındaki metnin nasıl zaman uyumlu ve zaman uyumsuz olarak okunacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="77f0c-103">The following examples show how to read text synchronously and asynchronously from a text file using .NET for desktop apps.</span></span> <span data-ttu-id="77f0c-104">Her iki örnek örneğini oluşturduğunuzda <xref:System.IO.StreamReader> sınıfı, dosyanın göreli veya mutlak yolunu sağlayın.</span><span class="sxs-lookup"><span data-stu-id="77f0c-104">In both examples, when you create the instance of the <xref:System.IO.StreamReader> class, you provide the relative or absolute path to the file.</span></span> <span data-ttu-id="77f0c-105">Aşağıdaki örnek, uygulamayla aynı klasörde TestFile.txt adında bir dosya bulunduğunu kabul eder.</span><span class="sxs-lookup"><span data-stu-id="77f0c-105">The following examples assume that the file named TestFile.txt is in the same folder as the application.</span></span>  
  
 <span data-ttu-id="77f0c-106">Bu kod örnekleri Windows çalışma zamanı için dosyaları okuma ve yazma için farklı akış türleri sağladığından, Windows Store uygulamaları için geliştirme için geçerli değildir.</span><span class="sxs-lookup"><span data-stu-id="77f0c-106">These code examples do not apply to developing for Windows Store Apps because the Windows Runtime provides different stream types for reading and writing to files.</span></span> <span data-ttu-id="77f0c-107">Nasıl bir Windows Store uygulaması bir dosyaya metin okunacağını gösteren bir örnek için bkz: [hızlı başlangıç: Dosyaları okuma ve yazma](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10)).</span><span class="sxs-lookup"><span data-stu-id="77f0c-107">For an example that shows how to read text from a file in a Windows Store app, see [Quickstart: Reading and writing files](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10)).</span></span> <span data-ttu-id="77f0c-108">.NET Framework akışları ile Windows çalışma zamanı akışları arasında dönüştürme yapılacağını gösteren örnekler için bkz [nasıl yapılır: .NET Framework akışları ile Windows çalışma zamanı akışları arasında dönüştürme](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span><span class="sxs-lookup"><span data-stu-id="77f0c-108">For examples that show how to convert between .NET Framework streams and Windows runtime streams, see [How to: Convert Between .NET Framework Streams and Windows Runtime Streams](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="77f0c-109">Örnek</span><span class="sxs-lookup"><span data-stu-id="77f0c-109">Example</span></span>  
 <span data-ttu-id="77f0c-110">Aşağıdaki örnek bir konsol uygulaması bir zaman uyumlu okuma işlemini gösterir.</span><span class="sxs-lookup"><span data-stu-id="77f0c-110">The following example shows a synchronous read operation within a console application.</span></span> <span data-ttu-id="77f0c-111">Bu örnekte, bir akış okuyucusunu kullanarak metin dosyası açıldığında, içeriğini bir dizeye kopyalanır ve konsol çıktısı için bir dizedir.</span><span class="sxs-lookup"><span data-stu-id="77f0c-111">In this example, the text file is opened using a stream reader, the contents are copied to a string, and the string is output to the console.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="77f0c-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="77f0c-112">Example</span></span>  
 <span data-ttu-id="77f0c-113">Aşağıdaki örnek, bir Windows Presentation Foundation (WPF) uygulamasında zaman uyumsuz bir okuma işlemini gösterir.</span><span class="sxs-lookup"><span data-stu-id="77f0c-113">The following example shows an asynchronous read operation in a Windows Presentation Foundation (WPF) application.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source6.cs#6)]
 [!code-vb[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source6.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="77f0c-114">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="77f0c-114">See also</span></span>

- <xref:System.IO.StreamReader>
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>
- [<span data-ttu-id="77f0c-115">Zaman Uyumsuz Dosya G/Ç</span><span class="sxs-lookup"><span data-stu-id="77f0c-115">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)
- [<span data-ttu-id="77f0c-116">NIB: Nasıl yapılır: Create a Directory Listing</span><span class="sxs-lookup"><span data-stu-id="77f0c-116">NIB: How to: Create a Directory Listing</span></span>](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69)
- [<span data-ttu-id="77f0c-117">Hızlı Başlangıç: Dosyaları okuma ve yazma</span><span class="sxs-lookup"><span data-stu-id="77f0c-117">Quickstart: Reading and writing files</span></span>](https://docs.microsoft.com/previous-versions/windows/apps/hh758325%28v=win.10%29)
- [<span data-ttu-id="77f0c-118">Nasıl yapılır: .NET Framework akışları ve Windows çalışma zamanı akışları arasında dönüştürme</span><span class="sxs-lookup"><span data-stu-id="77f0c-118">How to: Convert Between .NET Framework Streams and Windows Runtime Streams</span></span>](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)
- [<span data-ttu-id="77f0c-119">Nasıl yapılır: Okuma ve yeni oluşturulan veri dosyasına yazma</span><span class="sxs-lookup"><span data-stu-id="77f0c-119">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)
- [<span data-ttu-id="77f0c-120">Nasıl yapılır: Açın ve bir günlük dosyasına Ekle</span><span class="sxs-lookup"><span data-stu-id="77f0c-120">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)
- [<span data-ttu-id="77f0c-121">Nasıl yapılır: Bir dosyaya metin yazma</span><span class="sxs-lookup"><span data-stu-id="77f0c-121">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)
- [<span data-ttu-id="77f0c-122">Nasıl yapılır: Dizeden karakterleri okuma</span><span class="sxs-lookup"><span data-stu-id="77f0c-122">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)
- [<span data-ttu-id="77f0c-123">Nasıl yapılır: Bir dizeye karakter yazma</span><span class="sxs-lookup"><span data-stu-id="77f0c-123">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)
- [<span data-ttu-id="77f0c-124">Dosya ve Akış G/Ç'si</span><span class="sxs-lookup"><span data-stu-id="77f0c-124">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
