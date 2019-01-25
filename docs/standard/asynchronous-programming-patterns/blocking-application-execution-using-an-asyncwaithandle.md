---
title: Bir AsyncWaitHandle Kullanarak Uygulamanın Yürütülmesini Engelleme
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- blocks, asynchronous operations
- ending asynchronous operations
- asynchronous programming, ending operations
- asynchronous programming, blocking applications
- stopping asynchronous operations
- blocking application execution
ms.assetid: 3e32daf2-8161-4e8f-addd-9fd9ff101b03
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d667135b815dc5d47ba5f7de8d237796a6fd6e10
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54729531"
---
# <a name="blocking-application-execution-using-an-asyncwaithandle"></a><span data-ttu-id="160f4-102">Bir AsyncWaitHandle Kullanarak Uygulamanın Yürütülmesini Engelleme</span><span class="sxs-lookup"><span data-stu-id="160f4-102">Blocking Application Execution Using an AsyncWaitHandle</span></span>
<span data-ttu-id="160f4-103">İşlem tamamlanana kadar zaman uyumsuz bir işlemin sonuçları için beklerken, diğer iş yapmak için devam edemiyor uygulamaları engellemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="160f4-103">Applications that cannot continue to do other work while waiting for the results of an asynchronous operation must block until the operation completes.</span></span> <span data-ttu-id="160f4-104">Uygulamanızın ana iş parçacığı bir zaman uyumsuz bir işlemin tamamlanması beklenirken engellemek için aşağıdaki seçeneklerden birini kullanın:</span><span class="sxs-lookup"><span data-stu-id="160f4-104">Use one of the following options to block your application's main thread while waiting for an asynchronous operation to complete:</span></span>  
  
-   <span data-ttu-id="160f4-105">Kullanım <xref:System.IAsyncResult.AsyncWaitHandle%2A> özelliği <xref:System.IAsyncResult> zaman uyumsuz işlem tarafından döndürülen **başlamak**_OperationName_ yöntemi.</span><span class="sxs-lookup"><span data-stu-id="160f4-105">Use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin**_OperationName_ method.</span></span> <span data-ttu-id="160f4-106">Bu yaklaşım, bu konuda gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="160f4-106">This approach is demonstrated in this topic.</span></span>  
  
-   <span data-ttu-id="160f4-107">Zaman uyumsuz işlemin çağrı **son**_OperationName_ yöntemi.</span><span class="sxs-lookup"><span data-stu-id="160f4-107">Call the asynchronous operation's **End**_OperationName_ method.</span></span> <span data-ttu-id="160f4-108">Bu yaklaşım gösteren bir örnek için bkz: [zaman uyumsuz bir işlemi sonlandırarak uygulama yürütmesini engelleme](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).</span><span class="sxs-lookup"><span data-stu-id="160f4-108">For an example that demonstrates this approach, see [Blocking Application Execution by Ending an Async Operation](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).</span></span>  
  
 <span data-ttu-id="160f4-109">Bir veya daha fazla kullanan uygulamaları <xref:System.Threading.WaitHandle> bir zaman uyumsuz işlem tamamlanana kadar engelleyin nesnelere genellikle çağıracaktır **başlamak**_OperationName_ yöntemi yapılabilir herhangi bir çalışma gerçekleştirme işlem, ardından zaman uyumsuz işlemleri bloğu sonuçlarını olmadan tamamlar.</span><span class="sxs-lookup"><span data-stu-id="160f4-109">Applications that use one or more <xref:System.Threading.WaitHandle> objects to block until an asynchronous operation is complete will typically call the **Begin**_OperationName_ method, perform any work that can be done without the results of the operation, and then block until the asynchronous operation(s) completes.</span></span> <span data-ttu-id="160f4-110">Bir uygulamanın tek bir işlem birini çağırarak engelleyebilirsiniz <xref:System.Threading.WaitHandle.WaitOne%2A> yöntemlerini kullanarak <xref:System.IAsyncResult.AsyncWaitHandle%2A>.</span><span class="sxs-lookup"><span data-stu-id="160f4-110">An application can block on a single operation by calling one of the <xref:System.Threading.WaitHandle.WaitOne%2A> methods using the <xref:System.IAsyncResult.AsyncWaitHandle%2A>.</span></span> <span data-ttu-id="160f4-111">Zaman uyumsuz işlemleri tamamlamak için bir dizi için beklenirken engellemek için ilişkili depolama <xref:System.IAsyncResult.AsyncWaitHandle%2A> bir dizi ve, çağrı nesneleri <xref:System.Threading.WaitHandle.WaitAll%2A> yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="160f4-111">To block while waiting for a set of asynchronous operations to complete, store the associated <xref:System.IAsyncResult.AsyncWaitHandle%2A> objects in an array and call one of the <xref:System.Threading.WaitHandle.WaitAll%2A> methods.</span></span> <span data-ttu-id="160f4-112">Zaman uyumsuz işlemleri tamamlamak için bir dizi herhangi biri için beklenirken engellemek için ilişkili depolama <xref:System.IAsyncResult.AsyncWaitHandle%2A> bir dizi ve, çağrı nesneleri <xref:System.Threading.WaitHandle.WaitAny%2A> yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="160f4-112">To block while waiting for any one of a set of asynchronous operations to complete, store the associated <xref:System.IAsyncResult.AsyncWaitHandle%2A> objects in an array and call one of the <xref:System.Threading.WaitHandle.WaitAny%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="160f4-113">Örnek</span><span class="sxs-lookup"><span data-stu-id="160f4-113">Example</span></span>  
 <span data-ttu-id="160f4-114">Aşağıdaki kod örneğinde, kullanıcı tarafından belirtilen bir bilgisayar için etki alanı adı sistemi bilgileri almak için DNS sınıfında zaman uyumsuz metotlar kullanma gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="160f4-114">The following code example demonstrates using asynchronous methods in the DNS class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="160f4-115">Örnek kullanarak engelleme gösterir <xref:System.Threading.WaitHandle> zaman uyumsuz işlemle ilişkili.</span><span class="sxs-lookup"><span data-stu-id="160f4-115">The example demonstrates blocking using the <xref:System.Threading.WaitHandle> associated with the asynchronous operation.</span></span> <span data-ttu-id="160f4-116">Unutmayın `null` (`Nothing` Visual Basic'te) geçirilen <xref:System.Net.Dns.BeginGetHostByName%2A> `requestCallback` ve `stateObject` parametreleri olduğundan, bunlar bu yaklaşım kullanırken gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="160f4-116">Note that `null` (`Nothing` in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` and `stateObject` parameters because these are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlockWait.cs#2)]
 [!code-vb[AsyncDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlockWait.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="160f4-117">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="160f4-117">See also</span></span>

- [<span data-ttu-id="160f4-118">Olay Tabanlı Zaman Uyumsuz Desen (EAP)</span><span class="sxs-lookup"><span data-stu-id="160f4-118">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- [<span data-ttu-id="160f4-119">Olay Tabanlı Zaman Uyumsuz Desene Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="160f4-119">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
