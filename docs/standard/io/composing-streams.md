---
title: Akışlar Oluşturma
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, base streams
- I/O [.NET Framework], composing streams
- Stream class, composing streams
- base streams
- streams, backing stores
ms.assetid: da761658-a535-4f26-a452-b30df47f73d5
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1f2aa68822dd14b4cb81b48598faa6bdb4c71a13
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544360"
---
# <a name="composing-streams"></a>Akışlar Oluşturma
Bir disk veya bellek gibi bir depolama ortamına bir yedekleme deposudur. Her farklı yedekleme deposu uygulaması kendi akış uygulayan <xref:System.IO.Stream> sınıfı. Her akış türü okur ve Kimden ve Kime, belirtilen yedekleme deposu bayt yazar. Temel akışlar depoları için bağlandığı akışları çağrılır. Temel akışlar yedekleme deposu için akışa bağlanmak için gereken parametrelerine sahip oluşturucular sahiptir. Örneğin, <xref:System.IO.FileStream> dosya işlemleri ve benzeri nasıl paylaşılır belirtir bir yol parametresi belirtin Oluşturucusu vardır.  
  
 Tasarımını <xref:System.IO> sınıflar, Basitleştirilmiş akış oluşturmayı sağlar. Temel akışlar istediğiniz işlevleri sağlayan bir veya daha fazla geçiş akışlara eklenebilir. Tercih edilen türleri okuma ya da kolayca yazılan okuyucuya veya yazara zinciri sonuna eklenebilir.  
  
 Aşağıdaki kod örneği oluşturur bir **FILESTREAM** var olan geçici `MyFile.txt` arabellek sırada `MyFile.txt`. (Unutmayın **FileStreams** varsayılan olarak arabelleğe.) Ardından, bir <xref:System.IO.StreamReader> karakterleri okumak için oluşturulan **FILESTREAM**, için geçirilen **StreamReader** oluşturucu bağımsız değişken olarak. <xref:System.IO.StreamReader.ReadLine%2A> kadar okur <xref:System.IO.StreamReader.Peek%2A> başka karakter bulur.  
  
 [!code-cpp[System.IO.StreamReader#20](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source2.cpp#20)]
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
 Aşağıdaki kod örneği oluşturur bir **FILESTREAM** var olan geçici `MyFile.txt` arabellek sırada `MyFile.txt`. (Unutmayın **FileStreams** varsayılan olarak arabelleğe.) Ardından, bir **BinaryReader** bayt okumak için oluşturulan **FILESTREAM**, için geçirilen **BinaryReader** oluşturucu bağımsız değişken olarak. <xref:System.IO.BinaryReader.ReadByte%2A> kadar okur <xref:System.IO.BinaryReader.PeekChar%2A> hiçbir daha fazla bayt bulur.  
  
 [!code-cpp[System.IO.StreamReader#21](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source3.cpp#21)]
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.IO.StreamReader>
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>
- <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>
- <xref:System.IO.FileStream>
- <xref:System.IO.BinaryReader>
- <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>
- <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>
