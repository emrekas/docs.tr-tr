---
title: 'Nasıl yapılır: Ardışık Düzende Engelleme Koleksiyonu Dizilerini Kullanma'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, blocking collections in pipeline
ms.assetid: a39c7ec3-3ad7-4f4d-8fe4-b3e9dbabe2ed
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a4667d78fdf91a3e62c22d88c7cbe9effaae57d5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61923376"
---
# <a name="how-to-use-arrays-of-blocking-collections-in-a-pipeline"></a><span data-ttu-id="80573-102">Nasıl yapılır: Ardışık Düzende Engelleme Koleksiyonu Dizilerini Kullanma</span><span class="sxs-lookup"><span data-stu-id="80573-102">How to: Use Arrays of Blocking Collections in a Pipeline</span></span>
<span data-ttu-id="80573-103">Aşağıdaki örnek, dizileri kullanma işlemi gösterilmektedir <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> statik yöntemleriyle gibi nesneleri <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> ve <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A> bileşenleri arasında hızlı ve esnek bir veri aktarımı uygulamak için.</span><span class="sxs-lookup"><span data-stu-id="80573-103">The following example shows how to use arrays of <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> objects with static methods such as <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> and <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A> to implement fast and flexible data transfer between components.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80573-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="80573-104">Example</span></span>  
 <span data-ttu-id="80573-105">Aşağıdaki örnek, her nesne, dönüştürme ve çıkış koleksiyonuna geçirerek giriş koleksiyonu, verileri eşzamanlı olarak sürüyor bir temel bir ardışık düzen uygulaması gösterir.</span><span class="sxs-lookup"><span data-stu-id="80573-105">The following example demonstrates a basic pipeline implementation in which each object is concurrently taking data from the input collection, transforming it, and passing it to the output collection.</span></span>  
  
 [!code-csharp[CDS_BlockingCollection#07](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example07.cs#07)]
 [!code-vb[CDS_BlockingCollection#07](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/bcpipeline.vb#07)]  
  
## <a name="see-also"></a><span data-ttu-id="80573-106">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="80573-106">See also</span></span>

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [<span data-ttu-id="80573-107">İş Parçacığı Güvenli Koleksiyonları</span><span class="sxs-lookup"><span data-stu-id="80573-107">Thread-Safe Collections</span></span>](../../../../docs/standard/collections/thread-safe/index.md)
