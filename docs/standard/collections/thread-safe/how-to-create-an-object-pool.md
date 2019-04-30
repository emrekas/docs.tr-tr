---
title: 'Nasıl yapılır: ConcurrentBag Kullanarak Nesne Havuzu Oluşturma'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- object pool, in .NET Framework
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0bc0c6bebbab6e84c165f41300a4cb16c8746a07
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61644429"
---
# <a name="how-to-create-an-object-pool-by-using-a-concurrentbag"></a>Nasıl yapılır: ConcurrentBag Kullanarak Nesne Havuzu Oluşturma
Bu örnek, nesne havuzu uygulamak için eşzamanlı Torbaların kullanmayı gösterir. Nesne havuzları burada bir sınıfın birden çok örneği gerektirir ve sınıfı oluşturma veya yok et maliyetli durumlarda uygulama performansını iyileştirebilir. Bir istemci programını yeni bir nesne istediğinde, nesne havuzu zaten oluşturulduğundan ve havuza geri döndürülen bir sağlamaya ilk çalışır. Yoksa, ancak bundan sonra yeni bir nesne oluşturulur.  
  
 <xref:System.Collections.Concurrent.ConcurrentBag%601> özellikle aynı iş parçacığı hem öğeleri ekleme ve kaldırma sırasında hızlı ekleme ve kaldırma desteklediğinden, nesneleri depolamak için kullanılır. Bu örnek daha fazla geçici olarak oluşturulacak genişletilmesi bir <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, olduğu gibi paket veri yapısı uygulayan <xref:System.Collections.Concurrent.ConcurrentQueue%601> ve <xref:System.Collections.Concurrent.ConcurrentStack%601>.  
  
## <a name="example"></a>Örnek  
 [!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
 [!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- [İş Parçacığı Güvenli Koleksiyonları](../../../../docs/standard/collections/thread-safe/index.md)
