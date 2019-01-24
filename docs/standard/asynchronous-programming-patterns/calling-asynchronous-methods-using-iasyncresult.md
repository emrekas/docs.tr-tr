---
title: 'IAsyncResult Kullanarak Zaman Uyumsuz Yöntemleri Çağırma '
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- ending asynchronous operations
- waiting for asynchronous operations
- asynchronous method calling
- calling asynchronous methods
- asynchronous programming, calling asynchronous methods
- IAsyncResult interface, calling asynchronous methods
- stopping asynchronous operations
ms.assetid: 07fba116-045b-473c-a0b7-acdbeb49861f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01001d68b4bee42453fcb84725507b0cf61184a1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610519"
---
# <a name="calling-asynchronous-methods-using-iasyncresult"></a><span data-ttu-id="9704e-102">IAsyncResult Kullanarak Zaman Uyumsuz Yöntemleri Çağırma </span><span class="sxs-lookup"><span data-stu-id="9704e-102">Calling Asynchronous Methods Using IAsyncResult</span></span>
<span data-ttu-id="9704e-103">Üçüncü taraf sınıf kitaplıkları ve .NET Framework türleri bir uygulama ana uygulama iş parçacığı dışında iş parçacıklarında zaman uyumsuz işlemleri gerçekleştirilirken yürütmeye devam izin yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="9704e-103">Types in the .NET Framework and third-party class libraries can provide methods that allow an application to continue executing while performing asynchronous operations in threads other than the main application thread.</span></span> <span data-ttu-id="9704e-104">Aşağıdaki bölümlerde açıklanmaktadır ve zaman uyumsuz yöntem çağırabilirsiniz farklı yollarını gösteren kod örnekleri sağlamak <xref:System.IAsyncResult> tasarım deseni.</span><span class="sxs-lookup"><span data-stu-id="9704e-104">The following sections describe and provide code examples that demonstrate the different ways you can call asynchronous methods that use the <xref:System.IAsyncResult> design pattern.</span></span>  
  
-   <span data-ttu-id="9704e-105">[Zaman uyumsuz bir işlemi sonlandırarak uygulama yürütmesini engelleme](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).</span><span class="sxs-lookup"><span data-stu-id="9704e-105">[Blocking Application Execution by Ending an Async Operation](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).</span></span>  
  
-   <span data-ttu-id="9704e-106">[Bir AsyncWaitHandle kullanarak uygulamanın yürütülmesini engelleme](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="9704e-106">[Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span></span>  
  
-   <span data-ttu-id="9704e-107">[Zaman uyumsuz bir işlemin durumu için yoklama](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="9704e-107">[Polling for the Status of an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).</span></span>  
  
-   <span data-ttu-id="9704e-108">[Zaman uyumsuz bir işlemi sonlandırmak için bir AsyncCallback temsilcisi kullanma](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="9704e-108">[Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9704e-109">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="9704e-109">See also</span></span>

- [<span data-ttu-id="9704e-110">Olay Tabanlı Zaman Uyumsuz Desen (EAP)</span><span class="sxs-lookup"><span data-stu-id="9704e-110">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- [<span data-ttu-id="9704e-111">Olay Tabanlı Zaman Uyumsuz Desene Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="9704e-111">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
