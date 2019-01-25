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
# <a name="how-to-read-text-from-a-file"></a>Nasıl yapılır: Bir dosyadan metin okuma
Aşağıdaki örnek, masaüstü uygulamaları için .NET kullanılarak bir metin dosyasındaki metnin nasıl zaman uyumlu ve zaman uyumsuz olarak okunacağını gösterir. Her iki örnek örneğini oluşturduğunuzda <xref:System.IO.StreamReader> sınıfı, dosyanın göreli veya mutlak yolunu sağlayın. Aşağıdaki örnek, uygulamayla aynı klasörde TestFile.txt adında bir dosya bulunduğunu kabul eder.  
  
 Bu kod örnekleri Windows çalışma zamanı için dosyaları okuma ve yazma için farklı akış türleri sağladığından, Windows Store uygulamaları için geliştirme için geçerli değildir. Nasıl bir Windows Store uygulaması bir dosyaya metin okunacağını gösteren bir örnek için bkz: [hızlı başlangıç: Dosyaları okuma ve yazma](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10)). .NET Framework akışları ile Windows çalışma zamanı akışları arasında dönüştürme yapılacağını gösteren örnekler için bkz [nasıl yapılır: .NET Framework akışları ile Windows çalışma zamanı akışları arasında dönüştürme](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek bir konsol uygulaması bir zaman uyumlu okuma işlemini gösterir. Bu örnekte, bir akış okuyucusunu kullanarak metin dosyası açıldığında, içeriğini bir dizeye kopyalanır ve konsol çıktısı için bir dizedir.  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir Windows Presentation Foundation (WPF) uygulamasında zaman uyumsuz bir okuma işlemini gösterir.  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source6.cs#6)]
 [!code-vb[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source6.vb#6)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.IO.StreamReader>
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>
- [Zaman Uyumsuz Dosya G/Ç](../../../docs/standard/io/asynchronous-file-i-o.md)
- [NIB: Nasıl yapılır: Create a Directory Listing](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69)
- [Hızlı Başlangıç: Dosyaları okuma ve yazma](https://docs.microsoft.com/previous-versions/windows/apps/hh758325%28v=win.10%29)
- [Nasıl yapılır: .NET Framework akışları ve Windows çalışma zamanı akışları arasında dönüştürme](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)
- [Nasıl yapılır: Okuma ve yeni oluşturulan veri dosyasına yazma](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)
- [Nasıl yapılır: Açın ve bir günlük dosyasına Ekle](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)
- [Nasıl yapılır: Bir dosyaya metin yazma](../../../docs/standard/io/how-to-write-text-to-a-file.md)
- [Nasıl yapılır: Dizeden karakterleri okuma](../../../docs/standard/io/how-to-read-characters-from-a-string.md)
- [Nasıl yapılır: Bir dizeye karakter yazma](../../../docs/standard/io/how-to-write-characters-to-a-string.md)
- [Dosya ve Akış G/Ç'si](../../../docs/standard/io/index.md)
