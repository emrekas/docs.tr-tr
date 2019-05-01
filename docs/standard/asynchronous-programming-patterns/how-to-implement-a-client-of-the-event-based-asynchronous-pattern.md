---
title: 'Nasıl yapılır: Olay Tabanlı Zaman Uyumsuz Desenin İstemcisini Uygulama'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 21a858c1-3c99-4904-86ee-0d17b49804fa
ms.openlocfilehash: 8d2825ff738ffc50ba9a438024db27aff5686a0d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61870350"
---
# <a name="how-to-implement-a-client-of-the-event-based-asynchronous-pattern"></a><span data-ttu-id="28491-102">Nasıl yapılır: Olay Tabanlı Zaman Uyumsuz Desenin İstemcisini Uygulama</span><span class="sxs-lookup"><span data-stu-id="28491-102">How to: Implement a Client of the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="28491-103">Aşağıdaki kod örneği için uyar bir bileşeni kullanmak gösterilmiştir [olay tabanlı zaman uyumsuz desene genel bakış](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span><span class="sxs-lookup"><span data-stu-id="28491-103">The following code example demonstrates how to use a component that adheres to the [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span></span> <span data-ttu-id="28491-104">Bu örnekte bir form kullanır `PrimeNumberCalculator` açıklanan bileşen [nasıl yapılır: Olay tabanlı zaman uyumsuz deseni destekleyen bir bileşeni uygulama](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="28491-104">The form for this example uses the `PrimeNumberCalculator` component described in [How to: Implement a Component That Supports the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).</span></span>  
  
 <span data-ttu-id="28491-105">Bu örnekte bir projeyi çalıştırdığınızda, bir kılavuz "Asal sayı hesaplayıcı" form ve iki düğme görürsünüz: **Yeni görev Başlat** ve **iptal**.</span><span class="sxs-lookup"><span data-stu-id="28491-105">When you run a project that uses this example, you will see a "Prime Number Calculator" form with a grid and two buttons: **Start New Task** and **Cancel**.</span></span> <span data-ttu-id="28491-106">Tıklayabilirsiniz **yeni görev Başlat** düğmesine birkaç kez art arda ve her bir click için rastgele oluşturulmuş test birkaç asal olup olmadığını belirlemek için bir hesaplama zaman uyumsuz bir işlem başlar.</span><span class="sxs-lookup"><span data-stu-id="28491-106">You can click the **Start New Task** button several times in succession, and for each click, an asynchronous operation will begin a computation to determine if a randomly generated test number is prime.</span></span> <span data-ttu-id="28491-107">Form düzenli ilerleme ve artımlı sonuçlarını görüntüler.</span><span class="sxs-lookup"><span data-stu-id="28491-107">The form will periodically display progress and incremental results.</span></span> <span data-ttu-id="28491-108">Her işlemin benzersiz bir görev kimliği atanır</span><span class="sxs-lookup"><span data-stu-id="28491-108">Each operation is assigned a unique task ID.</span></span> <span data-ttu-id="28491-109">Hesaplama sonucu görüntülenen **sonucu** sütun; test sayı prime değilse olarak etiketlenir **bileşik,** ve kendi ilk bölen görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="28491-109">The result of the computation is displayed in the **Result** column; if the test number is not prime, it is labeled as **Composite,** and its first divisor is displayed.</span></span>  
  
 <span data-ttu-id="28491-110">Bekleyen işlemi ile iptal edilebilir **iptal** düğmesi.</span><span class="sxs-lookup"><span data-stu-id="28491-110">Any pending operation can be canceled with the **Cancel** button.</span></span> <span data-ttu-id="28491-111">Birden çok seçim yapılabilir.</span><span class="sxs-lookup"><span data-stu-id="28491-111">Multiple selections can be made.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28491-112">Çoğu sayı üssü olmayacaktır.</span><span class="sxs-lookup"><span data-stu-id="28491-112">Most numbers will not be prime.</span></span> <span data-ttu-id="28491-113">Birden fazla tamamlanmış işlemlerinden sonra asal bulunan değil, yalnızca daha fazla görev başlatın ve bazı asal sayıları sonunda bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="28491-113">If you have not found a prime number after several completed operations, simply start more tasks, and eventually you will find some prime numbers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28491-114">Örnek</span><span class="sxs-lookup"><span data-stu-id="28491-114">Example</span></span>  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="28491-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="28491-115">See also</span></span>

- <xref:System.ComponentModel.AsyncOperation>
- <xref:System.ComponentModel.AsyncOperationManager>
- <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>
