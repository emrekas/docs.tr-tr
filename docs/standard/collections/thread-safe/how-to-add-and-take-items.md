---
title: "Nasıl yapılır: Öğeleri Tek Tek Ekleme ve Bir BlockingCollection'dan ve Alma"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, blocking dictionary
ms.assetid: 38f2f3d8-15e5-4bf4-9c83-2b5b6f22bad1
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0e24c6b5aa02e8bc7ca4bcbf2c69bffd06216962
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054295"
---
# <a name="how-to-add-and-take-items-individually-from-a-blockingcollection"></a>Nasıl yapılır: Öğeleri Tek Tek Ekleme ve Bir BlockingCollection'dan ve Alma
Bu örnek nasıl öğelerinden ekleyip gösterir bir <xref:System.Collections.Concurrent.BlockingCollection%601> bir engelleyici ve engelleyici olmayan bir şekilde. Daha fazla bilgi için <xref:System.Collections.Concurrent.BlockingCollection%601>, bkz: [BlockingCollection genel bakışı](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).  
  
 Bir numaralandırma örneği bir <xref:System.Collections.Concurrent.BlockingCollection%601> boş ve daha fazla öğe eklenecek kadar bkz [nasıl yapılır: Bir Blockingcollection'daki öğeleri kaldırmak için ForEach kullanma](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md).
  
## <a name="example"></a>Örnek  
 Bu ilk örnekte, böylece işlemleri geçici olarak koleksiyon geçerli olduğunda engeller ve eklemek için öğeleri (çekerken) boş veya (eklerken) maksimum kapasite veya belirtilen zaman aşımı süresi dolduysa gösterilmektedir. Oluşturucuda belirtilen en yüksek kapasiteli Blockingcollection'a oluşturulduğunda kapasite üst sınırı engelleme yalnızca etkin olduğunu unutmayın.  
  
 [!code-csharp[CDS_BlockingCollection#01](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example01.cs#01)]
 [!code-vb[CDS_BlockingCollection#01](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/simpleblocking.vb#01)]  
  
## <a name="example"></a>Örnek  
 Bu ikinci örnek ekleyin ve böylece işlemleri değil engeller öğeleri almak nasıl gösterir. Hiçbir öğe varsa, sınırlanmış bir koleksiyon üzerinde en yüksek kapasite sınırına veya zaman aşımı süresi dolduysa, ardından <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> veya <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> işlem false döndürür. Böylece, iş parçacığı bir süre için bazı diğer faydalı iş yapmak ve sonra yeniden yeni bir öğe almak veya daha önce eklenemedi aynı öğeyi eklemeyi denediğinizde deneyin. Programı iptal erişirken uygulamak nasıl de gösterir. bir <xref:System.Collections.Concurrent.BlockingCollection%601>.  
  
 [!code-csharp[CDS_BlockingCollection#02](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example02.cs#02)]
 [!code-vb[CDS_BlockingCollection#02](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/nonblockingbc.vb#02)]  
  
## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [BlockingCollection’a Genel Bakış](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md)
