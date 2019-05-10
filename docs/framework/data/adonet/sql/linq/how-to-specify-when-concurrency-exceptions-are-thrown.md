---
title: 'Nasıl yapılır: Eşzamanlılık Özel Durumları Oluştuğunda Belirtme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 344ae068-ff63-4a2e-8b00-af22e143675f
ms.openlocfilehash: 0be17e7ceb6a5e5230d2619be350266d0282078c
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/29/2019
ms.locfileid: "64910804"
---
# <a name="how-to-specify-when-concurrency-exceptions-are-thrown"></a><span data-ttu-id="b85df-102">Nasıl yapılır: Eşzamanlılık Özel Durumları Oluştuğunda Belirtme</span><span class="sxs-lookup"><span data-stu-id="b85df-102">How to: Specify When Concurrency Exceptions are Thrown</span></span>
<span data-ttu-id="b85df-103">İçinde [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], <xref:System.Data.Linq.ChangeConflictException> iyimser eşzamanlılık çakışmaları nedeniyle nesne güncelleştirme sırasında özel durum oluştu.</span><span class="sxs-lookup"><span data-stu-id="b85df-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when objects do not update because of optimistic concurrency conflicts.</span></span> <span data-ttu-id="b85df-104">Daha fazla bilgi için [iyimser eşzamanlılık: Genel Bakış](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b85df-104">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
 <span data-ttu-id="b85df-105">Yaptığınız değişiklikleri veritabanına göndermeden önce eşzamanlılık özel durumları oluşturulduğu durumlar belirtebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="b85df-105">Before you submit your changes to the database, you can specify when concurrency exceptions should be thrown:</span></span>  
  
- <span data-ttu-id="b85df-106">Özel durum ilk arıza (<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>).</span><span class="sxs-lookup"><span data-stu-id="b85df-106">Throw the exception at the first failure (<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>).</span></span>  
  
- <span data-ttu-id="b85df-107">Tüm güncelleştirme çalıştığında son, biriken tüm hataları ve özel durum birikmiş hataları rapor (<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>).</span><span class="sxs-lookup"><span data-stu-id="b85df-107">Finish all update tries, accumulate all failures, and report the accumulated failures in the exception (<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>).</span></span>  
  
 <span data-ttu-id="b85df-108">Oluşturulduğunda, <xref:System.Data.Linq.ChangeConflictException> özel erişim sağlar bir <xref:System.Data.Linq.ChangeConflictCollection> koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="b85df-108">When thrown, the <xref:System.Data.Linq.ChangeConflictException> exception provides access to a <xref:System.Data.Linq.ChangeConflictCollection> collection.</span></span> <span data-ttu-id="b85df-109">Bu koleksiyon (eşlenmiş bir tek bir başarısız güncelleştirme deneyin), her bir çakışma dahil olmak üzere ayrıntılarını sağlar <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A> koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="b85df-109">This collection provides details for each conflict (mapped to a single failed update try), including access to the <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A> collection.</span></span> <span data-ttu-id="b85df-110">Eşzamanlılık denetimi başarısız olan güncelleştirmeyi tek bir üye için her üye çakışma eşler.</span><span class="sxs-lookup"><span data-stu-id="b85df-110">Each member conflict maps to a single member in the update that failed the concurrency check.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b85df-111">Örnek</span><span class="sxs-lookup"><span data-stu-id="b85df-111">Example</span></span>  
 <span data-ttu-id="b85df-112">Aşağıdaki kod, her iki değer örnekleri gösterir.</span><span class="sxs-lookup"><span data-stu-id="b85df-112">The following code shows examples of both values.</span></span>  
  
 [!code-csharp[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b85df-113">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="b85df-113">See also</span></span>

- [<span data-ttu-id="b85df-114">Nasıl yapılır: Değişiklik çakışmalarını yönetme</span><span class="sxs-lookup"><span data-stu-id="b85df-114">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [<span data-ttu-id="b85df-115">Veri Değişiklikleri Yapma ve Gönderme</span><span class="sxs-lookup"><span data-stu-id="b85df-115">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
