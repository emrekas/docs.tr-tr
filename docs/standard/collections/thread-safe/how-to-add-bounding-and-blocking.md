---
title: 'Nasıl yapılır: Koleksiyona Sınırlama ve Engelleme İşlevi Ekleme'
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- thread-safe collections, custom blocking collections
ms.assetid: 4c2492de-3876-4873-b5a1-000bb404d770
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3f52d1067a8aa907c8f1cf8b550eec82d1133b3f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052124"
---
# <a name="how-to-add-bounding-and-blocking-functionality-to-a-collection"></a><span data-ttu-id="9f023-102">Nasıl yapılır: Koleksiyona Sınırlama ve Engelleme İşlevi Ekleme</span><span class="sxs-lookup"><span data-stu-id="9f023-102">How to: Add Bounding and Blocking Functionality to a Collection</span></span>
<span data-ttu-id="9f023-103">Bu örnekte, sınırlama ve engelleme işlevi bir özel koleksiyon sınıfına uygulayarak ekleme işlemi açıklanır <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=nameWithType> arabirim sınıfı ve ardından dahili depolama mekanizması olarak bir sınıf örneği kullanarak bir <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9f023-103">This example shows how to add bounding and blocking functionality to a custom collection class by implementing the <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=nameWithType> interface in the class, and then using a class instance as the internal storage mechanism for a <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9f023-104">Sınırlama ve engelleme hakkında daha fazla bilgi için bkz. [BlockingCollection genel bakışı](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9f023-104">For more information about bounding and blocking, see [BlockingCollection Overview](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f023-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="9f023-105">Example</span></span>  
 <span data-ttu-id="9f023-106">Özel koleksiyon sınıfı bir dizi olarak öncelik düzeyleri gösterilir bir temel öncelik sırasıdır <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="9f023-106">The custom collection class is a basic priority queue in which the priority levels are represented as an array of <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType> objects.</span></span> <span data-ttu-id="9f023-107">Ek bir sıralama yok, her bir kuyruk içinde gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="9f023-107">No additional ordering is performed within each queue.</span></span>  
  
 <span data-ttu-id="9f023-108">İstemci kod içinde üç görevler oluşturulduklarında başlatılır.</span><span class="sxs-lookup"><span data-stu-id="9f023-108">In the client code, three tasks are started.</span></span> <span data-ttu-id="9f023-109">İlk görev yürütme sırasında herhangi bir noktada iptal etkinleştirmek klavye vuruşları için yalnızca yoklar.</span><span class="sxs-lookup"><span data-stu-id="9f023-109">The first task just polls for keyboard strokes to enable cancellation at any point during execution.</span></span> <span data-ttu-id="9f023-110">İkinci görev üretici parçacığıdır; Bu engelleme koleksiyona yeni öğeler ekler ve her bir öğe rastgele bir değere göre bir öncelik verir.</span><span class="sxs-lookup"><span data-stu-id="9f023-110">The second task is the producer thread; it adds new items to the blocking collection and gives each item a priority based on a random value.</span></span> <span data-ttu-id="9f023-111">Üçüncü görev öğeleri kullanıma sunuldukça koleksiyondan kaldırır.</span><span class="sxs-lookup"><span data-stu-id="9f023-111">The third task removes items from the collection as they become available.</span></span>  
  
 <span data-ttu-id="9f023-112">İş parçacıklarından diğerinden daha hızlı çalışır hale getirerek, uygulamanın davranışı ayarlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9f023-112">You can adjust the behavior of the application by making one of the threads run faster than the other.</span></span> <span data-ttu-id="9f023-113">Üretici daha hızlı çalışır, engelleyici koleksiyon öğeleri, zaten oluşturucuda belirtilen öğe sayısını içeriyorsa eklenmelerini önler olarak sınırlayıcı işlevselliğini fark edeceksiniz.</span><span class="sxs-lookup"><span data-stu-id="9f023-113">If the producer runs faster, you will notice the bounding functionality as the blocking collection prevents items from being added if it already contains the number of items that is specified in the constructor.</span></span> <span data-ttu-id="9f023-114">Tüketici daha hızlı çalışır, yeni bir öğe eklenmesi tüketici engelleme işlevleri bekler fark edeceksiniz.</span><span class="sxs-lookup"><span data-stu-id="9f023-114">If the consumer runs faster, you will notice the blocking functionality as the consumer waits for a new item to be added.</span></span>  
  
 [!code-csharp[CDS_BlockingCollection#06](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/prodcon.cs#06)]  
  
 <span data-ttu-id="9f023-115">Varsayılan olarak, depolama alanı için bir <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> olduğu <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9f023-115">By default, the storage for a <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> is <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f023-116">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="9f023-116">See also</span></span>

- [<span data-ttu-id="9f023-117">İş Parçacığı Güvenli Koleksiyonları</span><span class="sxs-lookup"><span data-stu-id="9f023-117">Thread-Safe Collections</span></span>](../../../../docs/standard/collections/thread-safe/index.md)
